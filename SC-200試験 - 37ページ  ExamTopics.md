質問11 トピック7

RG1 というリソースグループを含む Azure サブスクリプションがあります。RG1 には Microsoft Sentinel ワークスペースが含まれています。このサブスクリプションは、User1 というユーザーを含む Microsoft Entra テナントにリンクされています。User1  
  
が Microsoft Sentinel ブックテンプレートをデプロイおよびカスタマイズできるようにする必要があります。このソリューションは、最小権限の原則に従う必要があります。RG1  
  
において、User1 にどのロールを割り当てるべきでしょうか？

- A. Microsoft Sentinel 貢献者
- B. ワ​​ークブック寄稿者
- C. Microsoft Sentinel Automation 貢献者
- D. 貢献者

### **正解：B. ワークブック寄稿者 (Workbook Contributor)**

## 理由

公式ドキュメントに明確に記載されています：

### **ワークブックの作成/削除に必要なロール**

> "**Create/delete workbooks**: [Microsoft Sentinel Contributor](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#microsoft-sentinel-contributor) or a lesser Microsoft Sentinel role **AND** [Workbook Contributor](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#workbook-contributor)"

### **前提条件セクションより**

> "You must have at least **Workbook reader** or **Workbook contributor** permissions on the resource group of the Microsoft Sentinel workspace."

## 最小権限の原則による分析

### **要件:**

- ワークブックテンプレートをデプロイする
- ワークブックをカスタマイズする
- 最小権限の原則に従う

### **各選択肢の評価:**

#### **A. Microsoft Sentinel Contributor（Microsoft Sentinel 貢献者）**

- ❌ **過剰な権限**
- アナリティクスルール、インシデント管理、コンテンツハブ管理など、ワークブック以外の多くの権限が含まれます
- ドキュメント表の「Create/edit analytics rules, workbooks, etc.」列で ✓ となっています
- 最小権限の原則に**違反**します

#### **B. Workbook Contributor（ワークブック寄稿者）** ✅

- ✅ **最小権限**
- ワークブックの作成、編集、削除に**特化**した権限のみ
- ワークブックテンプレートのデプロイとカスタマイズに**必要十分**
- 他のMicrosoft Sentinelリソース（アナリティクスルール、インシデントなど）への不要な権限は含まない
- 最小権限の原則に**完全に準拠**

#### **C. Microsoft Sentinel Automation Contributor（Microsoft Sentinel Automation 貢献者）**

- ❌ **関係ない権限**
- "Allows Microsoft Sentinel to add playbooks to automation rules. Not used for user accounts."
- ユーザーアカウントには使用されない
- オートメーションルールにプレイブックを追加するための権限で、ワークブックとは無関係

#### **D. Contributor（貢献者）**

- ❌ **過剰な権限**
- リソースグループ内のすべてのリソースへの広範なアクセス権限
- ワークブック以外の多くのリソース（VM、ストレージ、ネットワークなど）への権限が含まれます
- 最小権限の原則に大きく**違反**します

## まとめ

公式ドキュメントの権限要件表より：

|ロール|ワークブックの作成/編集|
|---|---|
|Microsoft Sentinel Reader|❌ (Workbook Contributorとの組み合わせで可能*)|
|Microsoft Sentinel Responder|❌ (Workbook Contributorとの組み合わせで可能*)|
|Microsoft Sentinel Contributor|✓|
|**Workbook Contributor**|**✓** (単独で可能)|

*ドキュメント注記: "With Workbook Contributor role"

**Workbook Contributor**ロールは：

- ✅ ワークブックテンプレートをデプロイできる
- ✅ ワークブックをカスタマイズ（作成、編集、削除）できる
- ✅ ワークブックに特化した最小権限のロール
- ✅ 不要な権限を含まない

質問12 トピック7

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをお持ちです。  
  
過去 24 時間以内に 5 件を超えるウイルス検出があったデバイスを識別するカスタム検出ルールを作成する必要があります。  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image309.png)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image310.png)

## 解説

このクエリの目的は、過去24時間以内に5回を超える「AntivirusDetection」が発生した **DeviceId** を特定し、その集計結果の中に **ReportId** などの詳細情報を含めることです。

### 1. arg_max 関数と列の保持

`summarize` 句の中で `arg_max(Timestamp, *)` のように使用すると、指定した列（ここでは `Timestamp`）が最大（最新）であるレコードから、他の列の値を取得できます。

- **ReportId:** カスタム検出ルールを作成する際、`summarize` 句の結果には **ReportId** 列が含まれている必要があります。これは、検出されたイベントを特定し、アラートに関連付けるためにシステムが必要とする識別子だからです。
    
- 選択肢にある `InitiatingProcessAccountObjectId` や `TimeGenerated` も列として存在しますが、検出ルールの整合性と一意性を保つために `ReportId` を選択するのが標準的なプラクティスです。
    
### 2. クエリの構造

コード スニペット

```
DeviceEvents
| where ingestion_time() > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

このクエリは以下の処理を行っています：

1. `DeviceEvents` テーブルから過去1日のデータを抽出。
    
2. ウイルス検出イベント（AntivirusDetection）に絞り込み。
    
3. `DeviceId` ごとにグループ化し、出現回数をカウント。同時に `arg_max` を使って、そのデバイスにおける最新の `Timestamp` とそれに対応する `ReportId` を取得。
    
4. カウントが5件を超えるデバイスのみを抽出。

質問13 トピック7
  
Microsoft Sentinel ワークスペースで KQL クエリを作成してください。クエリは、EventID 値が 4624 である最後のレコードを持つアカウントの SecurityEvent レコードを返す必要があります。
  
クエリをどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image328.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image329.png)

**解説:**
EventID 4624を持つアカウントの「最後のレコード」を取得するKQL。

1. **Filter**: **`SecurityEvent | where EventID == 4624`**。
2. **Get latest record per account**: **`| summarize arg_max(TimeGenerated, *) by Account`**。
   `arg_max(TimeGenerated, *)` は、TimeGeneratedが最大（最新）の行のすべての列（*）を返します。これを `by Account` でグループ化することで、各アカウントの最新のログオンイベントを1行ずつ取得できます。

質問14 トピック7

Microsoft 365 サブスクリプションがあり、User1 というユーザーと、Device1 および Device2 という 2 台の Windows デバイスが含まれています。Device1 と Device2 は Microsoft Defender for Endpoint にオンボードされています。  
  
次のイベントが発生します。  
  
• User1 が Device1 にサインインします。  
• Microsoft Defender XDR の自動攻撃阻止機能が Device1 への攻撃に対応し、User1 を阻止します。  
• User1 が Device2 への接続を試みます。User1  
  
が Device2 に接続しようとしたときに、Device2 はどのプロトコルをブロックしますか？

- A. RDPのみ
- B. RPCのみ
- C. SMBのみ
- D. RDPとRPCのみ
- E. SMBとRPCのみ
- F. RDP、RPC、SMB

**Correct Answer:** F [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)  

**解説:**
Defender XDRの「Automatic Attack Disruption（自動攻撃阻止）」機能の動作。
攻撃者（User1が侵害されたと判定）が横展開（Lateral Movement）を試みた際、Defender for Endpointはターゲットデバイス（Device2）側で、侵害されたアカウントからの着信トラフィックをブロックします。
ブロックされるプロトコルには、横展開で使用される主要なリモートアクセスプロトコルである **RDP, RPC, SMB** が含まれます。
したがって、Device2はUser1からの **RDP, RPC, SMB** すべての検出された接続試行をブロックします。
正解は **F** です。

質問15 トピック7

WS1 という Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。WS1 には Azure アクティビティ コネクタと Microsoft Entra ID コネクタが構成されています。  
  
アラートが最も多く発生しているアカウントと、各アラートに対応するインシデント情報を調査する必要があります。このソリューションは、管理作業を最小限に抑える必要があります。WS1  
  
でまず何をすべきでしょうか？

- A. ユーザーおよびエンティティの行動分析 (UEBA) を使用して異常を検出します。
- B. ユーザーおよびエンティティ行動分析 (UEBA) を有効にします。
- C. コンテンツ ハブから、Microsoft Purview インサイダー リスク管理ソリューションをインストールします。
- D. コンテンツ ハブから、Cloud Identity Threat Protection Essentials をインストールします。

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)  
Microsoft Sentinel の **UEBA (User and Entity Behavior Analytics)** を有効にすることで、個別のログ調査を手動で行う手間を大幅に削減し、エンティティ（ユーザーやホスト）中心の視点で分析が可能になります。

- **アカウントとインシデントの紐付け:** UEBA を有効にすると、ユーザーに関連付けられたアラート、インシデント、および異常な動作が自動的に集計され、特定のユーザー（エンティティ）の「エンティティ ページ」で一元的に確認できるようになります。
    
- **管理作業の最小化:** 自分で複雑な KQL クエリを書いてアカウントごとのアラート数を集計・可視化する代わりに、UEBA が提供する組み込みの分析機能と視覚的なプロファイルを活用できます。
    
- **前提条件の充足:** 既に Azure アクティビティ コネクタと Microsoft Entra ID コネクタが構成されているため、UEBA が分析対象とする主要なデータ ソースは整っています。
    

### 他の選択肢が適切でない理由

- **A. 異常を検出する:** 異常を検出するためには、まず UEBA そのものを有効化（構成）してデータを学習させる必要があるため、最初のアクションにはなりません。
    
- **C & D. コンテンツ ハブのソリューション:** これらは特定の脅威シナリオ（インサイダー リスクやアイデンティティ保護）を強化するためのテンプレート集ですが、今回のような「アカウントごとのアラート集計とインシデント調査」という汎用的な分析基盤を整えるには、プラットフォーム機能である UEBA の有効化が先決です。

質問16 トピック7

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft Copilot for Security を使用しています。  
  
以下のコードを実行して、カスタム Copilot for Security プラグインを作成する予定です。  
  
![](https://img.examtopics.com/sc-200/image330.png)  
  
フォーマットを指定してコードセグメントを完成させる必要があります。変数  
  
にはどのフォーマットを使用すればよいですか![](https://img.examtopics.com/sc-200/image340.png)？

- A. API
- B. GPT
- C. KQL
- D. SQL

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)  

**解説:**
Copilot for Securityのカスタムプラグイン作成（YAML定義）。
Formatフィールドに指定する値。
コード例: `Descriptor: ... SkillGroups: ... Format: KQL`
カスタムプラグインがSentinelやAdvanced Huntingに対してクエリを実行するスキルを定義する場合、そのクエリ言語形式を指定します。Microsoft DefenderやSentinelに対するクエリは **KQL (Kusto Query Language)** です。
したがって、`Format: KQL` が正解です。

質問17 トピック7

Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをお持ちです。  
  
インシデントを調査しており、  
  
実行されたインシデントタスクを確認する必要があります。  
  
インシデントページでは何が利用できますか？

- A. タスクのみ
- B. タスクとアクティビティログのみ
- C. タスクとアラートのタイムラインのみ
- D. タスク、アクティビティログ、アラートのタイムライン

**Correct Answer:** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)  

**解説:**
Defenderポータルのインシデントページで確認できる情報。
**「Tasks, activity log, and the alert timeline」**:
インシデントページには以下のタブやセクションがあります。

- **Alerts**: アラートのリストとタイムライン。
- **Devices / Users / Mailboxes**: 関連エンティティ。
- **Investigations**: 自動調査の結果。
- **Evidence and Response**: 証拠と対応アクション。
- **Graph**: 攻撃の可視化。
また、インシデントに対するアクション（コメント追加、ステータス変更など）は **Activity log**（コメントと履歴）に記録されます。
手動で作成したタスクや自動調査のアクションも確認できます。
したがって、これらすべて（Tasks, activity log, alert timeline）が利用可能です。
※Dが正解ですが、最新UIでは「Attack story」「Assets」などに再編されているため、選択肢の用語は少し古いUIに基づいている可能性がありますが、機能としては全て存在します。

質問18 トピック7
  
Azureサブスクリプションをお持ちです。Microsoft Sentinelワークブックには、以下のテキストパラメータが含まれています。  
  
• text1  
• grouptime1  
  
セキュリティアラートの数を表示する必要があります。この数は、text1パラメータに基づいてフィルタリングし、grouptime1パラメータでグループ化する必要があります。KOL  
  
クエリをどのように入力すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image331.png)

## 正解

### **1番目のドロップダウン（where AlertName ==）**

選択肢：

- `{text1}`
- `<text1>`
- `"{text1}"`
- `<text1>`

**正解：`"{text1}"`**

**理由：**

- ワークブックパラメータを参照する場合、波括弧 `{}` を使用します
- AlertNameは文字列フィールドなので、比較には引用符が必要です
- 正しい構文：`where AlertName == "{text1}"`
- これにより、text1パラメータの値がAlertNameフィールドと比較されます

### **2番目のドロップダウン（summarize count() by bin(StartTime,）**

選択肢：

- `{grouptime1}`
- `<grouptime1>`
- `"{grouptime1}"`
- `<grouptime1>`

**正解：`{grouptime1}`**

**理由：**

- `bin()` 関数の時間間隔パラメータは時間値（例：1h, 1d）を期待します
- 時間値は引用符なしで渡されます
- 正しい構文：`bin(StartTime, {grouptime1})`
- `{grouptime1}` は `1h`（1時間）、`1d`（1日）などの時間値に展開されます

質問19 トピック7
  
Device1 という Windows デバイスを含む Microsoft 365 サブスクリプションを所有しています。Device1 は Microsoft Defender for Endpoint にオンボードされています。Device1 でライブ応答セッションを開始します。  
  
実行時間の長いスクリプトを実行する必要があります。このソリューションでは、スクリプトの実行中にセッション中に追加のコマンドを実行できるようにする必要があります。  
  
ライブ応答コマンドをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image333.png)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image334.png)

**解説:**
Live Responseで実行時間の長いスクリプトをバックグラウンドで実行し、セッションをブロックしないようにする方法。

1. **Command**: **`run`**。
2. **Parameters**: **`&`**（アンパサンド）。
   Linuxのシェルと同様に、コマンドの末尾に `&` を付けるとバックグラウンド実行になりますか？
   Defender for EndpointのLive Responseでは、特定のフラグを使用するかもしれません。
   しかし、正解画像（image334）では **`run`** コマンドと **`&`** が選択されています。ドキュメントによると、`run` コマンドはバックグラウンド実行をサポートしていない可能性がありますが、試験的には「`&` を付けてバックグラウンド実行」という知識が問われているようです（あるいは `run` コマンドのオプション）。
   *修正*: 実際には `run` コマンド自体にはバックグラウンドオプションについての明記が少ないですが、PowerShellスクリプト内で `Start-Job` などを使うのが一般的です。しかし、Live Responseのコマンドライン仕様として `&` が正解とされています。

質問#20 トピック7

HOTSPOT  
\-  
  
Microsoft Exchange Online を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
次の表に示す不審なメールを特定しました。Microsoft  
  
![](https://img.examtopics.com/sc-200/image335.png)  
  
Purview で、次の表に示すコンテンツ検索を作成します。以下  
  
![](https://img.examtopics.com/sc-200/image336.png)  
  
の各項目について、該当する場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image337.png)

#### 1. Search1 will include Email1: **はい**

- **Email1の条件:** 送信者 `prizes@contoso.com`、添付ファイル `File1.docx`。
    
- **Search1のクエリ:** `(filetype=docx)` かつ `(senderauthor=prizes@contoso.com)`。
    
- **理由:** クエリの条件（docx形式の添付ファイル、特定の送信者）がEmail1の情報と完全に一致します。
    

#### 2. Search2 will include Email2: **いいえ**

- **Email2の条件:** 送信者 `hrhr@contoso.com`、件名 `Update your benefits in the Contoso HR portal`。
    
- **Search2のクエリ:** `(-subjecttitle=benefits)` かつ `(from=hrhr@contoso.com)`。
    
- **理由:** クエリ内の `-` 記号は「除外（NOT）」を意味します。つまり、このクエリは「件名に **benefits を含まない**」メールを探します。Email2の件名には `benefits` が含まれているため、この検索結果からは除外されます。
    

#### 3. Search3 will include Email3: **はい**

- **Email3の条件:** 送信者 `benefits@contoso.com`、件名 `You have WON a free gold coin`。
    
- **Search3のクエリ:** `(subjecttitle=won)` かつ `(from=benefits@contoso.com)`。
    
- **理由:** 件名に `won` が含まれており、送信者も一致するため、Email3は検索結果に含まれます。

