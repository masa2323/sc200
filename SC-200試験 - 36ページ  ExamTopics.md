質問#49トピック6

以下のテーブルを含むMicrosoft Sentinelワークスペースがあります。  
  
![](https://img.examtopics.com/sc-200/image488.png)  
  
検索を使用してログデータを調査する必要があります。  
  
どのテーブルを検索できますか？

- A. 表3のみ
- B. 表1と表3のみ
- C. 表3と表4のみ
- D. 表1、表3、表4のみ
- E. 表1、表2、表3、表4

### **正解：E. 表1、表2、表3、表4**

## 理由

公式ドキュメントの「Table plans」セクションに明確に記載されています：

### **検索ジョブ（Search jobs）のサポート**

テーブルプランの比較表によると：

| Features        | Analytics | Basic | Auxiliary |
| --------------- | --------- | ----- | --------- |
| **Search jobs** | ✅         | ✅     | ✅         |

> "**Search jobs**: ✅ (supported for all three table plans)"

### **各テーブルの分析**

1. **Table1**: Basic + Interactive retention → ✅ 検索可能
2. **Table2**: Basic + Archive period → ✅ 検索可能
3. **Table3**: Analytics + Interactive retention → ✅ 検索可能
4. **Table4**: Analytics + Archive period → ✅ 検索可能

質問1 トピック7

User1というユーザーとWS1というMicrosoft Sentinelワークスペースを含むAzureサブスクリプションがあります。WS1  にAdvanced Security Information Model (ASIM)認証パーサーをデプロイします。  
  
これらのパーサーを使用して、User1が過去24時間に生成した認証イベントをクエリする必要があります。ソリューションは、クエリのパフォーマンスを最大限に高める必要があります。  
  
クエリをどのように完了すればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image254.png)


**正解:** ![](https://img.examtopics.com/sc-200/image255.png)

### 回答

- **1つ目のドロップダウン:** **ASimAuthentication (**
    
- **2つ目のドロップダウン:** **targetusername_has**
    
---
### 解説

このクエリを完成させるロジックは、「どの関数を呼ぶか」と「どの引数を使ってフィルタリングするか」の2点に集約されます。

#### 1. パーサーの選択 (ASimAuthentication)

ASIMにおいて、特定のスキーマ（この場合は認証：Authentication）全体を対象にクエリを投げるには、**統合パーサー（Unifying Parser）**を使用します。

- **ASimAuthentication:** 認証イベント全体を統合してクエリするための関数です。
    
- **imAuthentication:** 特定のソースに特化した実装パーサーを指すことが多く、広範な調査には適しません。
    
- **identityInfo:** これはユーザープロファイル情報を格納するテーブルであり、認証イベントそのものを調査するものではありません。
    
#### 2. パフォーマンスの最適化 (targetusername_has)

ASIMパーサーの大きな特徴は、関数呼び出し時に**引数によるフィルタリング（Filtering Parameters）**が可能な点です。

- **targetusername_has:** この引数に関数内で値を渡すと、データが統合される前の段階（各ソースのテーブルをスキャンする際）でフィルタリングが行われるため、クエリのパフォーマンスが劇的に向上します。
    
- **contains / has:** これらはKQLの演算子として関数呼び出しの「後」に `where` 句などで使われることが一般的ですが、ASIMの関数引数として直接指定することで、より早い段階でデータを絞り込めます。

質問2 トピック7

AzureサブスクリプションにUser1というユーザーとWS1というMicrosoft Sentinelワークスペースが含まれています。User1  がWS1に対してユーザーおよびエンティティ行動分析（UEBA）を有効にできるようにする必要があります。このソリューションは、最小権限の原則に従う必要があります。User1 にはどのロールを割り当てるべきですか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正しい選択は1点です。  
  
![](https://img.examtopics.com/sc-200/image256.png)

**正解:** ![](https://img.examtopics.com/sc-200/image257.png)

**解説:**
SentinelでUEBA（User and Entity Behavior Analytics）を有効にするために必要な最小権限。

1. **Global Administrator**: **「Global Administrator」**（またはSecurity Administrator）。UEBAの有効化（オンボーディング）には、テナントレベルのディレクトリ読み取り権限や設定変更が必要なため、**Global Administrator** または **Security Administrator** が必要です。Sentinel固有のロールだけでは不十分な場合があります（特に初回有効化時）。
   *修正*: Microsoftドキュメントによると、UEBAを有効にするには、Sentinelワークスペースが含まれるリソースグループの **「Microsoft Sentinel Contributor」** ロールに加えて、テナントの **「Global Administrator」** または **「Security Administrator」** ロールが必要です。
   質問は「どのロールを割り当てるべきか」で、選択肢の中にSentinel ContributorとGlobal Adminがあれば両方ですが、通常UEBA有効化のネックになるのは **Global Administrator / Security Administrator** です。
   *詳細*: UEBA有効化には「ディレクトリ閲覧」以上の権限（データ同期の設定など）が必要です。

質問3 トピック7
  
SW1 という Microsoft Sentinel ワークスペースがあります。SW1 では、ユーザーおよびエンティティ行動分析 (UEBA) を有効にします。KQL を使用して、次のタスクを実行する必要があります。  
  
• 各エンティティタイプのフィールドを持つエンティティデータを表示します。  
• ルールのパフォーマンスを分析して、ルールの品質を評価します。  
  
各タスクで KQL のどのテーブルを使用する必要がありますか？回答するには、適切なテーブルを正しいタスクにドラッグしてください。各テーブルは 1 回、複数回、またはまったく使用しない場合があります。コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image284.png)

**正解:** ![](https://img.examtopics.com/sc-200/image285.png)

### 解説

UEBA が有効なワークスペースでは、特定の分析データが専用のテーブルに格納されます。

#### 1. エンティティデータの表示 (View entity data)

**BehaviorAnalytics** テーブルを使用します。 このテーブルには、UEBA によって生成されたユーザーやホストなどのエンティティに関する情報が格納されています。各エンティティのタイプ（User, Host, IP 等）や、関連するメタデータ、ユーザーの行動傾向などの詳細フィールドが含まれており、エンティティ中心の調査を行う際の主要なソースとなります。

#### 2. ルール品質の評価 (Assess rule quality)

**Anomalies** テーブルを使用します。 Microsoft Sentinel の機械学習によって検出された「異常（Anomalies）」がこのテーブルに記録されます。これらの異常は「アラート」の前段階である場合が多く、どのような異常が検知されているかを分析することで、既存の分析ルールが適切に機能しているか、あるいはノイズが多いかといったルールの品質評価に役立てることができます。

---
### その他のテーブルについて

- **AuditLogs:** Entra ID の変更履歴などを管理するログ。
    
- **AzureDiagnostics:** Azure リソースの診断ログ。
    
- **CommonSecurityLog:** CEF 形式のセキュリティデバイスログ。

質問4 トピック7

オンプレミスネットワークには、Active Directory Domain Services (AD DS) フォレストが含まれています。Microsoft Defender for Identity を使用する Microsoft Entra テナントがあります。AD DS フォレストはテナントと同期しています。AD DS ドメインコントローラーへの LDAP シンプルバインドを識別するハンティングクエリを作成する必要があります。  
  
どのテーブルをクエリすればよいでしょうか？

- A. AADサービスプリンシパルリスクイベント
- B. AADDomainServicesAccountLogon
- C. サインインログ
- D. アイデンティティログオンイベント

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)  

**解説:**
Defender for Identityで「LDAP Simple Bind（平文認証）」を検出するためのハンティングクエリ対象テーブル。
Defender for Identity（旧AATP）のログは **`IdentityLogonEvents`** や `IdentityQueryEvents`, `IdentityDirectoryEvents` などに統合されています。
LDAPのクリアテキストパスワード使用（Simple Bind）は、ログオン試行の一種またはディレクトリサービスへのアクセスイベントとして記録されます。
正解は **`IdentityLogonEvents`** (D) です。
LogonTypeやProtocolとして「LDAP」が含まれ、FailureReasonやAdditionalFieldsで「Clear text」が含まれるものを探します。
A, Bは存在しないかAAD関連。C（SignInLogs）はEntra ID（Azure AD）のログであり、オンプレミスADのLDAPバインドは記録されません。

質問5 トピック7

Microsoft 365 サブスクリプションをお持ちです。  
  
グループの変更または削除要求を送信したすべてのセキュリティプリンシパルを特定する必要があります。KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image286.png)

**正解:** ![](https://img.examtopics.com/sc-200/image287.png)

**解説:**
### 1. RequestUri の選択

`MicrosoftGraphActivityLogs` において、操作対象のリソース（この場合は `/groups`）を特定するための情報は **RequestUri** フィールドに格納されています。

- **RequestUri:** APIリクエストのパスが含まれます（例: `https://graph.microsoft.com/v1.0/groups/...`）。ここに `/group` が含まれているものを探すことで、グループ関連の操作に絞り込めます。
    
- **Scopes / Type:** これらは権限の範囲やリソースの種類を示しますが、URLパスを直接フィルタリングする方が直接的で確実です。
    
### 2. RequestMethod != "GET" の選択

「変更または削除」という要件を満たすには、単なる「参照（読み取り）」操作を除外する必要があります。

- **"GET":** HTTPの GET メソッドはデータの取得（読み取り）に使用されます。これを `!=`（等しくない）で除外することで、作成（POST）、更新（PATCH/PUT）、削除（DELETE）といった**書き込み操作のみ**を抽出できます。

質問6 トピック7

Microsoft 365 サブスクリプションで Microsoft Defender for Endpoint プラン 2 が利用されており、Device1 という macOS デバイスが含まれています。Device1 で発生した Defender for Endpoint エージェントのアラートを調査する必要があります。このソリューションは、以下の要件を満たす必要があります。  
  
• Device1 上のアクティブなネットワーク接続をすべて特定する。  
• Device1 で実行中のプロセスをすべて特定する。  
• Device1 のログイン履歴を取得する。  
• 管理作業を最小限に抑える。

Microsoft Defender ポータルから最初に行うべきことは何でしょうか？

- A. \[デバイス\] から、\[デバイス 1 の調査パッケージの収集\] をクリックします。
- B. エンドポイントの高度な機能から、Live Response の署名されていないスクリプトの実行を有効にします。
- C. デバイスから、デバイス 1 でライブ応答セッションを開始します。
- D. エンドポイントの高度な機能から、認証済みテレメトリを無効にします。

### **正解：A. [デバイス] から、[デバイス 1 の調査パッケージの収集] をクリックします。**

## 理由

公式ドキュメントの「Investigation package contents for Mac and Linux devices」セクションに、macOSデバイスの調査パッケージに含まれる内容が明確に記載されています：

### **macOSの調査パッケージに含まれる内容**

|Object|macOS|
|---|---|
|**Network connections**|✅ Active connections  <br>✅ Active listening connections  <br>✅ ARP table  <br>✅ Firewall rules  <br>✅ Interface configuration  <br>✅ Proxy settings  <br>✅ VPN settings|
|**Processes**|✅ A list of all running processes|
|**Users and groups**|✅ **Sign-in history**  <br>✅ Sudoers|

### **要件の確認**

調査パッケージの収集により、以下のすべての要件が満たされます：

1. ✅ **Device1上のアクティブなネットワーク接続をすべて特定する**
    - "Active connections" が含まれています
2. ✅ **Device1で実行中のプロセスをすべて特定する**
    - "A list of all running processes" が含まれています
3. ✅ **Device1のログイン履歴を取得する**
    - "Sign-in history" が含まれています
4. ✅ **管理作業を最小限に抑える**
    - 調査パッケージの収集は**1回のアクション**で完了します
    - すべての情報がZIPファイルとしてまとめてダウンロードされます

### **他の選択肢が不適切な理由**

#### **B. エンドポイントの高度な機能から、Live Response の署名されていないスクリプトの実行を有効にします。**

- これは設定の変更であり、実際の調査アクションではありません
- 署名されていないスクリプトを実行する必要性がありません
- この設定を有効にしても、要件の情報は取得できません

#### **C. デバイスから、デバイス 1 でライブ応答セッションを開始します。**

- ライブ応答セッションでも情報は取得できますが、管理作業が増えます
- 複数のコマンド（`processes`、ログイン履歴の取得など）を手動で実行する必要があります
- **重要な問題**：ライブ応答の基本コマンドである`connections`は、**macOSではサポートされていません** ドキュメントには明確に記載されています：
    
    |Command|Windows|macOS|Linux|
    |---|---|---|---|
    |`connections`|Y|**N**|N|
    
    つまり、ライブ応答セッションではmacOSのネットワーク接続情報を取得できません

#### **D. エンドポイントの高度な機能から、認証済みテレメトリを無効にします。**

- これは全く関係のない設定です
- 調査には何も役立ちません

### **まとめ**

**調査パッケージの収集**は：

- 1回のクリックで完了（管理作業最小）
- すべての要件を満たす情報を含む
- macOSデバイスで完全にサポートされている
- ネットワーク接続、プロセス、ログイン履歴のすべてが含まれる

質問7 トピック7
  
Microsoft Sentinel ワークスペースがあります。Microsoft SharePoint Online および OneDrive サイトからのデータを視覚化する予定です。  
  
このビジュアル用の KQL クエリを作成する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• すべてのワークロードを単一の操作として選択する。  
• Operations と Users という 2 つのパラメーターを含める。  
• 結果から、サイト URL の空値を除外する。  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image288.png)
## 正解

### **1番目のドロップダウン（OfficeActivity テーブルのフィルタ）**

選択肢：

- `| where Operation in ((Operations))`
- `| where Operation in ((Operations))`
- `| where ("{Operations}"=="AH" or {Operations})`
- `| where "{Operations:label}" = = "AH" or Operation in ((Operations))`

**正解：`| where Operation in ((Operations))`**

**理由：**

- `((Operations))`はダッシュボードパラメータの構文です
- これにより、Operationsパラメータで選択された値でフィルタリングされます
- 「OperationsとUsersという2つのパラメーターを含める」という要件を満たします

### **2番目のドロップダウン（固定フィルタ - 灰色表示）**

```
| where OfficeWorkload in ('OneDrive', 'SharePoint')
```

これは固定されており、変更できません。SharePointとOneDriveのワークロードを選択します。

### **3番目のドロップダウン（Site_Url のフィルタ）**

選択肢：

- `| project Site_Url`
- `| where Operation != ""`
- `| where SiteUrl != ""`
- `| where SiteUrl =~ ""`

**正解：`| where SiteUrl != ""`**

**理由：**

- `!= ""`は空文字列でないことを確認します
- 「結果から、サイトURLの空値を除外する」という要件を満たします
- 画像では`SiteUrl`（アンダースコアなし）の選択肢が表示されているようです

質問8 トピック7

カスタムブックを含むMicrosoft Sentinelワークスペースがあります。  
  
セキュリティイベントの概要をクエリする必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• 過去1週間に取り込まれたセキュリティイベントの数を特定する。  
• 日別のイベント数をグラフに表示する。  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image305.png)

#### 1. bin 関数の使用

`summarize count() by ...` の中で、連続的な時間データを「1日単位」などのまとまりに区切るには **`bin()`** 関数を使用します。

- **bin:** 指定したサイズ（この場合は `7d` のコンテキストに基づき、日次などの単位）で値を丸めます。
    
- **coalesce / extract / max_of:** これらはデータの抽出や欠損値の補完、最大値の取得に使われる関数であり、時間軸でのグルーピングには使用しません。
    
#### 2. 時間軸の指定 (TimeGenerated)

グラフの横軸（時間軸）として使用する標準的なフィールドは **`TimeGenerated`** です。

- **TimeGenerated:** イベントが生成された日時を保持しており、これに対して `bin` を適用することで、「2026-02-01」「2026-02-02」といった日ごとの集計が可能になります。
    
- **Account / EventID / ProcessId:** これらはイベントの属性を識別するためのフィールドであり、時間経過による推移を表示するための軸としては不適切です。

質問9 トピック7
  
Microsoft Sentinel ワークスペースに、Workbook1 というカスタム ワークブックが含まれています。Workbook1 に、ログオン イベント ID が 4624 および 4634 のアカウントのログオン回数を表示するビジュアルを作成する必要があります。  
  
クエリをどのように完成させるべきでしょうか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image307.png)

## 正解

### **1番目のドロップダウン（結合演算子）**

選択肢：

- `join`
- `project`
- `summarize`
- `union`

**正解：`join`**

**理由：**

- 2つの異なるSecurityEventクエリ（EventID 4624とEventID 4634）の結果を結合する必要があります
- `join`演算子は、共通のキー（この場合はAccount）に基づいて2つのテーブルの行を結合します
- これにより、各アカウントのログオン数とログオフ数を同じ行に表示できます

### **2番目のドロップダウン（結合の種類）**

選択肢：

- `full`
- `inner`
- `left`
- `right`

**正解：`full`**

**理由：**

- **Full outer join**を使用すると、両方のテーブルのすべてのアカウントが結果に含まれます
- ログオンだけがあってログオフがないアカウント、またはその逆のケースも表示されます
- これにより、すべてのアカウントのログオンとログオフのアクティビティを完全に把握できます

**他の選択肢が不適切な理由：**

- `inner`：両方のイベント（4624と4634）が存在するアカウントのみを表示（データが欠ける可能性がある）
- `left`：EventID 4624のアカウントのみを保持
- `right`：EventID 4634のアカウントのみを保持

質問10 トピック7

Microsoft Defender for Endpoint を使用しているオンプレミスの Windows 11 デバイスが 500 台あります。  
ネットワーク デバイスの検出を有効にします。  
  
検出されたネットワーク デバイスを識別し、各ネットワーク デバイスを検出したオンボード デバイスの ID を返すハンティング クエリを作成する必要があります。  
  
どの組み込み関数を使用すればよいでしょうか。

- A. SeenBy()
- B. デバイスからIP()
- C. 次()
- D. current\_cluster\_endpoint()

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/36/#)  
## 理由

公式ドキュメントの「Device discovery overview」セクションに、SeenBy()関数の使用目的と方法が明確に記載されています。

### **SeenBy()関数の説明**

> "By invoking the **SeenBy** function, in your advanced hunting query, you can get detail on **which onboarded device a discovered device was seen by**. This information can help determine the network location of each discovered device and subsequently, help to identify it in the network."

### **使用例（公式ドキュメントより）**

kql

```kql
DeviceInfo
| where OnboardingStatus != "Onboarded"
| summarize arg_max(Timestamp, *) by DeviceId 
| where isempty(MergedToDeviceId) 
| limit 100
| invoke SeenBy()
| project DeviceId, DeviceName, DeviceType, SeenBy
```

### **SeenBy()関数の機能**

1. **検出されたネットワークデバイスを識別**
    - オンボードされていないデバイス（ネットワークデバイス含む）を特定します
2. **各デバイスを検出したオンボードデバイスのIDを返す**
    - `SeenBy`カラムに、そのデバイスを検出したオンボードされているDefender for EndpointデバイスのIDが表示されます
3. **ネットワークロケーションの特定に役立つ**
    - どのオンボードデバイスが検出したかを知ることで、ネットワーク上の位置を特定できます

### **他の選択肢が不適切な理由**

#### **B. デバイスからIP() (DeviceFromIP)**

- これは実在しないか、標準的なKQL組み込み関数ではありません
- IPアドレスからデバイスを検索する機能ですが、ネットワークデバイス検出の文脈では使用されません

#### **C. 次() (Next)**

- これはKQLの標準関数ですが、ネットワークデバイス検出には関係ありません
- 時系列データで次の値を取得するために使用されます

#### **D. current_cluster_endpoint()**

- これはKustoクラスタの情報を取得する関数です
- ネットワークデバイス検出やデバイスの関係性の特定には使用されません

### **まとめ**

**SeenBy()** は、Microsoft Defender for Endpointのネットワークデバイス検出機能において、検出されたデバイスとそれを検出したオンボードデバイスの関係を明らかにするための専用の組み込み関数です。

この関数を使用することで：

- ✅ 検出されたネットワークデバイスを識別できる
- ✅ 各ネットワークデバイスを検出したオンボードデバイスのIDを取得できる
- ✅ ネットワークトポロジーとデバイスの位置を理解できる

