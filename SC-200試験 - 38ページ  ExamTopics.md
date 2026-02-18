質問#21 トピック7

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft Copilot for Security をご利用です。Copilot for Security ワークスペースでは、以下のプラグインを使用しています。  
  
• Microsoft Entra  
• Microsoft Defender XDR  
  
Microsoft Defender ポータルから、Copilot for Security を使用して、報告されたインシデントを調査します。  
  
調査に Microsoft Entra ID Protection の情報を含めるプロンプトブックを実行する必要があります。  
  
まず何をすべきでしょうか？

- A. Microsoft Defender ポータルからインシデント レポートを作成します。
- B. Copilot for Security スタンドアロン エクスペリエンスで調査を開きます。
- C. Microsoft Sentinel で調査を開きます。
- D. Microsoft Defender ポータルから、高度な検索クエリを作成します。

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)  

**解説:**
Copilot for SecurityでEntra ID Protectionの情報を含むPromptbookを実行する方法。
DefenderポータルのCopilot統合（Embedded experience）では、利用可能な機能やプラグインがコンテキストに限定される場合があります（Defenderプラグインが主）。
**「Open the investigation in the Copilot for Security standalone experience」**。
Entra ID Protectionプラグインを含む包括的な調査や、カスタムPromptbookの実行は、スタンドアロンポータル（security.microsoft.com/copilot ではなく copilot.security.microsoft.com）で行うのが最も確実です。特に「Entra ID Protection情報を含めるPromptbook」がカスタムのものである場合、スタンドアロンエクスペリエンスの方が柔軟性があります。
Defenderポータル内でもCopilotは使えますが、クロスプロダクト（Entra ID Protectionなど）の広範なデータを含むPromptbookを実行するには、スタンドアロンエクスペリエンスに切り替える（Open in standalone）のが標準的なフローです。

質問#22 トピック7

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft Copilot for Security を使用しています。Copilot for Security セッションを開始し、それぞれに応答を求める 5 つのプロンプトを入力します。  
  
プロンプトは使用しますが、応答は含めないプロンプトブックを作成する必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。  
  
どうすればよいでしょうか？

- A. 各プロンプトを選択し、\[プロンプトブックの作成\] を選択します。
- B. 新しいプロンプトブックを作成し、各プロンプトを含めます。
- C. 次の入力を持つ新しいプロンプトを入力します: セッションプロンプトからプロンプトブックを作成します。
- D. セッションを共有し、\[プロンプトブックの作成\] を選択します。

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)  
### 正解の理由：A. 各プロンプトを選択し、[プロンプトブックの作成] を選択します。

この方法は、現在実行中のセッションから特定のプロンプトを再利用可能なテンプレートとして保存するための**最も直接的で管理負荷の低い**手順です。

- **操作の簡便性:** セッション内の特定のプロンプトのチェックボックスを選択し、そのままプロンプトブックとして保存できます。
- **要件の充足:** 問題文にある「応答（AIの回答）を含めない」という要件についても、この機能は「プロンプト（命令文）の連なり」を保存するものなので、自動的に満たされます。
    

---
### 他の選択肢が最適ではない理由

- **B. 新しいプロンプトブックを作成し、各プロンプトを含めます:** ゼロから新しいプロンプトブックを作成し、手動で 5 つのプロンプトをコピー＆ペーストして構成する方法です。実行は可能ですが、既存のセッションから直接作成できる「A」と比較して管理・作業の手間（コピーの手間など）が増えるため、問題文の「管理作業を最小限に抑える」という要件に反します。
- **C. 「セッションプロンプトからプロンプトブックを作成します」と入力する:** Copilot 自体への自然言語による命令でプロンプトブックを作成する機能は、現時点では標準の管理フローとして提供されていません。プロンプトブックの作成は UI 上の操作で行います。
- **D. セッションを共有し、[プロンプトブックの作成] を選択します:** セッションを「共有」することは、他のユーザーにリンクを送ることやレポート化を目的としています。共有手順の中にプロンプトブック作成が統合されているわけではなく、手順として遠回りになります。
    
---
### 💡 試験・実務でのポイント

Copilot for Security のプロンプトブックには **「カスタムプロンプトブック」** と **「標準プロンプトブック（Microsoft提供）」** があります。実務において、社内のインシデント対応手順を標準化する（例：特定のアラートに対して常に同じ 5 つの調査クエリを投げる）際には、この「既存セッションからの作成」が非常に重宝されます。


質問#23 トピック7

オンプレミスの Windows 11 Pro デバイスが 1,000 台あり、Microsoft Defender for Endpoint にオンボードされています。Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションを所有しています。  
  
攻撃者がデバイス上で以下の操作を実行したことが判明しました。  
  
• レジストリベースのウイルス対策除外のファイルシステム パスを変更した  
• 悪意のあるファイルをファイルシステム パスにダウンロードした  
  
デバイスでライブ応答セッションを開始しました。  
  
レジストリの変更を元に戻す必要があります。  
  
どのコマンドを実行すればよいでしょうか？

- A. 修復する
- B. レジストリ
- C. スキャン
- D. 分析する

## シナリオの分析
**状況**:

- 攻撃者がレジストリベースのウイルス対策除外のファイルシステムパスを変更
- ライブ応答セッション開始済み
- **レジストリの変更を元に戻す必要がある**

## 重要な誤解の解消
質問は「レジストリの変更を元に戻す」と述べていますが、これには**2つの異なる意味**があります:
### 1. **以前に`remediate`で削除したレジストリを復元する場合**
→ `undo`コマンドを使用

### 2. **攻撃者が変更したレジストリを削除/修復する場合**
→ `remediate`コマンドを使用

## 正解の判定
このシナリオでは:
- 攻撃者がウイルス対策除外設定を変更した
- まだライブ応答での修復アクションは実行されていない
- **悪意のあるレジストリ変更を削除する必要がある**

したがって、**A. 修復する（remediate）** が正解です。

## 各選択肢の評価

### **A. 修復する（remediate）** ✅ **正解**

**機能**:

```console
# Remediate registry entry
remediate registry HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Exclusions\Paths\C:\malicious\path
```

**`remediate`コマンドのレジストリアクション**:
- レジストリエントリを**削除**する
- 攻撃者が追加/変更した悪意のあるレジストリ設定を除去

**適用場面**:
- 攻撃者が作成した除外設定を削除
- マルウェアが設定した永続化メカニズムを除去

### **B. レジストリ（registry）**

**機能**:

```console
# Show registry values
registry HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Exclusions
```

**問題点**:
- これは**基本コマンド**で、レジストリ値を**表示**するだけ
- 変更や修復はできない
- 調査用のコマンド

### **C. スキャン（scan）**
**機能**:

- クイックウイルススキャンを実行

**問題点**:
- レジストリ変更を元に戻すことはできない
- マルウェア検出用

### **D. 分析する（analyze）**
**機能**:
- エンティティを分析して判定を出す

**問題点**:
- Windowsでのみ利用可能
- 分析のみで修復はしない

## `remediate`と`undo`の関係

```console
# Step 1: 悪意のあるレジストリを削除（remediate）
remediate registry HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Exclusions\Paths\C:\malware

# Step 2: もし誤って削除した場合は復元（undo）
undo registry HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Exclusions\Paths\C:\malware
```

## 正解
**A. 修復する（remediate）**
**理由**:

1. 攻撃者が作成/変更した悪意のあるレジストリエントリを削除できる
2. `remediate`はレジストリエントリを削除する修復アクションを実行
3. シナリオは「元に戻す」ではなく「悪意のある変更を除去する」という意味
4. `undo`は`remediate`で削除したものを復元するコマンドであり、このシナリオでは不適切

質問#24 トピック7

オンプレミス ネットワークには、contoso.com と fabrikam.com という 2 つの Active Directory ドメイン サービス (AD DS) ドメインが含まれています。Contoso.com には Group1 というグループが含まれています。Fabrikam.com には Group2 というグループが含まれています。WS1 という Microsoft Sentinel ワークスペースがあり、そこには Rule1 というスケジュールされたクエリルールが含まれています。Rule1 は、異常な AD DS セキュリティ イベントに応答してアラートを生成します。各アラートはインシデントを作成します。  
  
次の要件を満たすインシデント トリアージ ソリューションを実装する必要があります。  
  
• contoso.com からのセキュリティ インシデントは Group1 に割り当てる必要があります。  
• fabrikam.com からのセキュリティ インシデントは Group2 に割り当てる必要があります。  
• 管理作業を最小限に抑える必要があります。  
  
このソリューションには何を含める必要がありますか。

- A. インシデントの作成によってトリガーされるプレイブック
- B. アラートの作成によってトリガーされるプレイブック
- C. ルール1に割り当てられた1つの自動化ルール
- D. ルール1に割り当てられた2つの自動化ルール

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/38/#)  

**解説:**
ドメイン（contoso.com vs fabrikam.com）に基づいてインシデントの所有者グループを割り当てるトリアージソリューション。
管理作業を最小限にする。
**「Two automation rules assigned to Rule1」**。
オートメーションルール（Automation rules）は、インシデント作成時に条件に基づいてアクション（所有者の割り当て、タグ付けなど）を自動実行します。

1. **Automation Rule A**:
   - Condition: `Domain` contain `contoso.com` (またはEntity条件)
   - Action: Assign to `Group1`
2. **Automation Rule B**:
   - Condition: `Domain` contain `fabrikam.com`
   - Action: Assign to `Group2`
これらをスケジュールされたルール（Rule1）に関連付けます。Automation ruleはインシデントトリガーで動作し、Playbook（Logic Apps）よりも軽量でコストがかからず、設定も簡単（Sentinel内だけで完結）です。管理作業・コストの観点でPlaybookよりAutomation ruleが推奨されます。
※「1つのルールで分岐」も可能かもしれませんが（If-else的な）、Automation rulesは条件ごとに作成するのが基本です。したがって「2つのオートメーションルール」を作成し、それぞれに条件を設定するのが正解です。

質問#25 トピック7

Microsoft 365 サブスクリプションをお持ちです。  
  
以下の KQL クエリがあります。  
  
![](https://img.examtopics.com/sc-200/image339.png)  
  
このクエリを使用して Microsoft Defender XDR カスタム検出ルールを作成できることを確認する必要があります。  
  
クエリに何を追加すればよいでしょうか？

- A. | 集計 (タイムスタンプ、レポート ID) = arg\_max (タイムスタンプ、レポート ID)、デバイス ID による count()
- B. | 集計 (ReportId) = make\_set(ReportId)、デバイスIDによるcount()
- C. | 集計 (Timestamp, DeviceName)=arg\_min(Timestamp, DeviceName)、DeviceId による count()
- D. | 集計 (タイムスタンプ) = 範囲 (タイムスタンプ)、デバイス ID による count()

正解は **A. | summarize (Timestamp, ReportId) = arg_max(Timestamp, ReportId) by DeviceId** です。 ※選択肢 A の日本語訳が少し不自然ですが、技術的には `arg_max` を使用して必要な列を抽出する構成を指しています。

---
### 正解の理由

Microsoft Defender XDR でカスタム検出ルールを作成する場合、クエリ結果には以下の列が含まれていることが**必須要件**となります。

- **Timestamp:** イベントが発生した時刻を特定するため。
- **DeviceId:** どのアクション（隔離や分離など）をどのデバイスに対して実行するかを定義するため。
- **ReportId:** インシデントの証拠として特定のイベントを一意に識別するため。
    

`arg_max(Timestamp, ReportId) by DeviceId` を使用することで、各デバイスにおける最新のイベント時刻とレポート ID を抽出しつつ、カスタム検出ルールの要件を満たす形式にデータをまとめることができます。

---
### 他の選択肢が適さない理由

- **B, C, D:** これらはいずれも `count()` や `make_set`、`range` などを使用してデータを集計・変形していますが、カスタム検出ルールに必要な「一意の ReportId とそれに関連付けられた Timestamp」を正しく、かつ最新の状態で維持して抽出する形式としては不適切です。特に `arg_min` (C) は最も古いイベントを返してしまうため、最新の脅威を検知するルールには向きません。
    
### 💡 試験対策のポイント

カスタム検出ルールの問題では、**「DeviceId と ReportId が結果に含まれているか」**が最大のチェックポイントです。これらがないと、システムは「見つけた脅威に対して、具体的にどのデバイスの、どのイベントを処理すればいいのか」がわからず、ルールとして保存できません。

質問#26 トピック7
  
Microsoft Defender for Office 365 を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
検出はされたものの、配信後にメールボックスから正常に削除されなかった、潜在的に悪意のあるメールに関するイベントを一覧表示するハンティングクエリを作成する必要があります。このソリューションでは、イベントがメール受信者のサインインイベントと相関関係にあることを確認する必要があります。  
  
クエリはどのように完成させるべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正しい選択肢は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image355.png)


**正解:** ![](https://img.examtopics.com/sc-200/image356.png)

### 回答内容

1. **最初のドロップダウン (ActionType):** **"ZAP"**
2. **2 番目のドロップダウン (join 条件):** **AccountUpn**
    
---
### 技術解説

#### 1. ActionType に "ZAP" を選択する理由

Microsoft Defender for Office 365 において、配信済みのメールボックスから遡及的に悪意のあるメールを検知・処理する仕組みを **ZAP (Zero-hour Auto Purge)** と呼びます。

- **要件の確認:** 「配信後にメールボックスから検出された」という条件に合致するのは ZAP のイベントです。
- **ActionResult == "Error":** クエリ内で `ActionResult == "Error"` と指定されているため、「検出はしたが、正常に削除（移動）できなかった」イベントを絞り込んでいます。
    
#### 2. join 条件に AccountUpn を選択する理由

`EmailPostDeliveryEvents` テーブルと `IdentityLogonEvents` テーブルを結合して、メールの受信者とサインインイベントを紐付ける必要があります。

- **$left.RecipientEmailAddress:** 左側のテーブル（メールイベント）にある受信者のメールアドレス列です。
- **$right.AccountUpn:** 右側のテーブル（サインインイベント）において、メールアドレス形式の ID を保持している列は `AccountUpn` です。これらを紐付けることで、特定のメールを受信したユーザーのサインイン挙動を追跡できます。

質問#27 トピック7
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションを所有しています。Device1 というデバイス上で、File1.exe というファイルによって開始された悪意のあるプロセスを発見しました。File1.exe がいつ作成されたかを特定する KQL クエリを作成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• FileName、InitiatingProcessFileName、および InitiatingProcessCommandLine 列を返す。  
• 返されるデータの量を最小限に抑える。  
  
クエリはどのように完成させるべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image401.png)

**正解:** ![](https://img.examtopics.com/sc-200/image402.png)

**解説:**
#### 1. `DeviceFileEvents` を選択する理由

「`File1.exe` がいつ**作成**されたか」を特定するには、ファイルの作成、修正、削除などのファイルシステム操作を記録しているテーブルを使用する必要があります。

- **`DeviceFileEvents`:** ファイルの作成 (`FileCreated`) などのイベントを専門に扱うテーブルであるため、今回の要件に最適です。
- 他のテーブル（`DeviceProcessEvents` など）はプロセスの実行を記録しますが、ファイルがディスク上に作成された瞬間を特定するには `DeviceFileEvents` が適しています。
    
#### 2. `| project-keep` を選択する理由

問題文の要件である「特定の列のみを返す」かつ「データの量を最小限に抑える」を満たすためのフィルタリング演算子を選択します。

- **`| project-keep`:** 指定した列（`FileName`, `InitiatingProcessFileName`, `InitiatingProcessCommandLine`）**だけを保持**し、それ以外のすべての列を破棄します。これにより、出力データのサイズを最小化できます。
- `| extend` は列を追加し、`| project-away` は特定の列を除外しますが、必要な列だけを効率よく抽出するには `project-keep`（または一般的な `project`）が最適です。

質問#28 トピック7

Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。Microsoft Entra ID 監査ログ用のワークブックを作成してカスタマイズする必要があります。  
  
どの 3 つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答領域に移動し、正しい順序に並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image403.png)

### 回答：実行すべき 3 つのアクションとその順序

1. **From Content hub, install the Microsoft Entra ID solution.**
2. **From Workbooks, select Microsoft Entra ID Audit logs and then select View Template.**
3. **From Workbooks, select Microsoft Entra ID Audit logs and then select Save.**
    
---
### 解説：なぜこの順序になるのか

- **ステップ 1 (Content hub):** 現在の Microsoft Sentinel では、ワークブックのテンプレートやデータコネクタなどのアセットは「コンテンツハブ (Content hub)」から **ソリューションとしてインストール** する必要があります。これにより、ワークブックのテンプレートがギャラリーに表示されるようになります。
- **ステップ 2 (View Template):** ギャラリー（Workbooks）に表示されたテンプレートを選択し、まずは「**テンプレートを表示 (View Template)**」をクリックして内容を確認します。テンプレートの状態ではまだ編集やカスタマイズはできません。
- **ステップ 3 (Save):** テンプレート画面で「**保存 (Save)**」をクリックすることで、自分のワークスペース内にそのワークブックのインスタンス（コピー）が作成されます。保存して初めて、クエリの書き換えや視覚化の変更といった「カスタマイズ」が可能になります。
    
### 💡 実務でのポイント

「データコネクタの構成 (Configure a Data connector)」も重要ですが、この問題はあくまで **「ワークブックを作成・カスタマイズする手順」** に焦点を当てています。試験対策としては、以下の流れをセットで覚えておくと確実です。

質問#29 トピック7
  
Sub1 という Azure サブスクリプションがあり、そこには WS1 という Microsoft Sentinel ワークスペースが含まれています。WS1 に、以下の要件を満たすハンティング クエリを作成する必要があります。  
  
• 7 日間に各 Microsoft Entra セキュリティ プリンシパルによって毎日実行された変更の数を返す  
• Sub1 内のリソースへの成功した変更をすべて特定する  
• 不足しているデータ ポイントを 0 に置き換える  
  
KQL クエリをどのように完成させるべきですか？ 回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択肢は 1 つにつき 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image405.png)

**正解:** ![](https://img.examtopics.com/sc-200/image406.png)

**解説:**
#### 1. `AzureActivity` を選択する理由

要件の「Sub1 内のリソースへの成功した変更」を特定するには、Azure リソースレベルの操作ログを保持しているテーブルが必要です。

- **`AzureActivity`:** Azure Resource Manager (ARM) を介して行われた「リソースの作成、更新、削除（書き込み操作）」を記録します。クエリ内の `OperationNameValue endswith "write"` や `ActivityStatusValue` といった列名は、このテーブルに固有のものです。
- `AuditLogs` は Microsoft Entra ID（ユーザーやグループの変更）を扱い、`AzureDiagnostics` は特定リソース内部の診断ログを扱うため、今回の要件には適しません。
    
#### 2. `| make-series` を選択する理由

要件の「7日間にわたり毎日（時系列）」かつ「不足しているデータポイントを 0 に置き換える」を同時に満たすのは、この演算子のみです。

- **欠損値の補完:** `make-series` 演算子には `default=0` というパラメータを指定でき、データが存在しない日（バケット）に対しても 0 を補完して連続した時系列データを作成できます。
- **時系列の生成:** `in range(ago(7d), now(), 1d)` という構文と組み合わせて、指定期間の統計値を配列として生成します。
- `summarize` では、データが存在しない日付は結果行そのものが生成されないため、別途 0 を埋める複雑な処理が必要になります。

質問#30 トピック7

次のKQLクエリを含むMicrosoft Sentinelワークブックがあります。  
  
![](https://img.examtopics.com/sc-200/image407.png)  
  
返された値に基づいてerrCount列の色を変更するビジュアルを作成する必要があります。  
  
ビジュアルはどのように設定すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image408.png)

**正解:** ![](https://img.examtopics.com/sc-200/image409.png)

**解説:**
#### 1. Visualization (可視化の種類)

- **Grid** を選択します。
- 提示された KQL クエリは、`ErrorCode` や `Category` ごとに `errCount` を集計しており、複数の列を持つ表形式のデータを生成します。
- このような多列データを表示し、さらに特定の列に対して個別の書式設定（色の変更など）を行うには、**Grid（グリッド）** 形式が最適です。
    
#### 2. Column renderer (列のレンダラー)

- **Heatmap** を選択します。
- 「返された値に基づいて `errCount` 列の色を変更する」という要件において、**Heatmap（ヒートマップ）** は値の大きさに応じて色の濃淡やグラデーションを自動的に適用するため、データの傾向を視覚化するのに非常に効果的です。
- **Thresholds（しきい値）** も色を変更できますが、こちらは「10以上なら赤」といった具体的な論理条件を定義する場合に使用します。
- **Big number** は単一の大きな数値を表示するためのものであり、表（Grid）の中の一つの列の書式設定としては **Heatmap** がこのシナリオに合致しています。
    
---
### 💡 実務でのポイント

Sentinel ワークブックの「列の設定 (Column Settings)」では、列ごとに異なるレンダラーを適用できます。例えば、`errCount` に **Heatmap** を適用して重要度を可視化し、別の列に **Thresholds** を適用して「成功/失敗」をアイコンで表示するといった使い分けが一般的です。
