質問#28 トピック5

Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
デバイス上でウイルス対策ソフトウェアによる検出が 5 件以上検出された場合にアラートを生成する、Rule1 というカスタム検出ルールがあります。Rule1 のルックバック期間は 12 時間です。  
  
ルックバック期間を 48 時間に変更する必要があります。Rule1 のどこを変更すればよいでしょうか？

- A. 範囲
- B. KQLクエリの要約演算子
- C. 頻度
- D. KQLクエリのwhere演算子

## 回答: **C. 頻度**

### 理由:

Microsoft Defender XDRのカスタム検出ルールでは、**頻度（Frequency）の設定によってルックバック期間が自動的に決定されます**。

ドキュメントから確認できる頻度とルックバック期間の関係:

|頻度|ルックバック期間|
|---|---|
|**Every 24 hours**|30日間|
|**Every 12 hours**|**48時間**|
|**Every 3 hours**|12時間|
|**Every hour**|4時間|
|**Continuous (NRT)**|リアルタイム|

### 問題の状況:

- **現在**: ルックバック期間が12時間
    - これは「Every 3 hours」の頻度設定に対応
- **変更後**: ルックバック期間を48時間に変更したい
    - **「Every 12 hours」の頻度に変更する必要がある**

### 他の選択肢が正解でない理由:

- **A. 範囲（Scope）**: デバイスグループの適用範囲を設定するもので、ルックバック期間とは無関係
- **B. KQLクエリの要約演算子**: `summarize`演算子はデータの集計に使用するが、ルックバック期間を制御しない
- **D. KQLクエリのwhere演算子**: `where`演算子はフィルタリングに使用するが、ドキュメントでは「Avoid filtering custom detections by using the Timestamp column」と明記されており、頻度に基づいて自動的にプリフィルタリングされる

質問#29 トピック5

Microsoft 365 サブスクリプションを所有しています。サブスクリプションには、Microsoft Defender for Endpoint にオンボードされている 500 台の Windows 11 デバイスが含まれています。Microsoft Defender XDR で次の操作を実行する必要があります。  
  
• 会社の財務部門で、偽のキャッシュされた資格情報をランダムなエンドポイントに入力します。  
• 攻撃者が偽のキャッシュされた資格情報を使用しようとした場合に、Microsoft Defender XDR でインシデントが作成されるようにする。  
  
ソリューションでは、偽のキャッシュされた資格情報が財務部門のエンドポイントにのみ植え付けられるようにする必要があります。  
  
順番に実行する必要がある 3 つのアクションはどれですか。回答するには、アクション リストから適切なアクションを回答領域に移動し、正しい順序に並べ替えます。  
  
注: 回答の選択肢の順序は複数あっても正しい場合があります。正しい順序を選択した場合でも、ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image446.png)

## 回答領域 (Answer Area)

|**順序**|**アクション**|
|---|---|
|**1**|**From Advanced features of the Endpoints settings, set Deception to On.**|
|**2**|**From the Endpoints settings, create a device group.**|
|**3**|**From the Endpoints settings, create a basic lure.**|

---
## 解説とロジック

このソリューションを実現するためには、機能の有効化、対象の限定、および実際のデプロイという3つのステップが必要です。

### 1. 機能の有効化 (Set Deception to On)

まず、Microsoft Defender XDR でデセプション（欺瞞）機能自体を有効にする必要があります。これは「設定」＞「エンドポイント」＞「高度な機能」の中で行います。

### 2. 対象の限定 (Create a device group)

「財務部門のエンドポイントにのみ植え付ける」という要件を満たすためには、財務部門のデバイスをグループ化する必要があります。

- **デバイスグループ** を作成し、財務部門の Windows 11 デバイスをそのスコープに含めます。これにより、ルアーの適用範囲を特定の部門だけに限定できます。

### 3. ルアーの作成とデプロイ (Create a basic lure)

最後に、実際に偽のキャッシュされた資格情報を配布する設定を行います。

- **Basic lure（基本的なルアー）** を作成する際、上記で作成したデバイスグループをターゲットに指定します。
- このルアー設定の中で、攻撃者が使用した際にアラートを発生させるための偽の資格情報（ハニートークン）が自動的または手動で構成され、対象デバイスにランダムに配布されます。

## トピック6 - 質問セット6

質問1 トピック6

Microsoft Exchange Online を使用する Microsoft 365 E5 サブスクリプションをお持ちです。  
  
フィッシング詐欺メールを識別する必要があります。  
  
どの 3 つのコマンドレットを順番に実行すればよいでしょうか？ 回答するには、コマンドレットのリストから適切なコマンドレットを回答エリアに移動し、正しい順序に並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image250.png)

**解説:**
Exchange Online PowerShellを使用して、ユーザーが報告したフィッシングメールを調査・抽出する手順です。

1. **Connect-ExchangeOnline**: Exchange Onlineに接続します。
2. **New-ComplianceSearch**: コンプライアンス検索（コンテンツ検索）を作成し、条件（ユーザーからの報告や件名など）に一致するメッセージを検索します。`New-ComplianceSearch -Name "PhishingSearch" -ContentMatchQuery "..."`
3. **Start-ComplianceSearch**: 作成したコンプライアンス検索ジョブを開始します。
※`Start-ComplianceSearchAction -Preview` などで結果を確認することもありますが、まずは検索の定義と開始が必須です。

質問2 トピック6

WS1 という Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。WS1 内のインシデントに、実行する必要があるアクションのリストが含まれていることを確認する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• インシデントの種類ごとにカスタマイズされたアクションのリストを作成できること。  
• 管理作業を最小限に抑えること。  
  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが加算されます。  
  
![](https://img.examtopics.com/sc-200/image252.png)

## 回答エリア (Answer Area)

- **Document the actions by configuring:** **Tasks**
- **Build the list of actions by selecting:** **Automated response**
    
---
## 解説とロジック

### 1. Document the actions by configuring: Tasks

Microsoft Sentinel の **「インシデント タスク (Incident Tasks)」** は、アナリストが調査中に実行すべき手順をリスト化して表示するための専用機能です。

- **Comments** や **Tags** は情報の付加には役立ちますが、手順の進捗管理や「アクションのリスト」としての構造化には向いていません。
- **Tasks** を使用することで、個々のアクションが完了したかどうかをチェックボックス形式で追跡できるようになります。
    
### 2. Build the list of actions by selecting: Automated response

インシデントの種類に応じて自動的にタスクを追加するには、**「自動応答 (Automated response)」**（オートメーション ルール）を構成します。

- **オートメーション ルール** のアクションとして **「Add task (タスクの追加)」** を選択できます。
- 特定の分析ルール（インシデントの種類）をトリガー条件に設定することで、インシデントが生成された瞬間に、あらかじめ定義したカスタムアクションリストを自動的にインシデントへ紐付けることが可能です。
- これにより、手動で毎回リストを作成する手間が省け、管理作業を最小限に抑えることができます。

質問3 トピック6

Microsoft Sentinel を使用する Azure サブスクリプションを所有しています。  
  
インシデントへの対応と、Microsoft Sentinel によって検出されたセキュリティ脅威の修復に必要な管理作業を最小限に抑える必要があります。  
  
どの 2 つの機能を使用すべきでしょうか？ 正解はそれぞれ解決策の一部を示しています。  
  
注: 正解は 1 点です。

- A. Microsoft Sentinel ワークブック
- B. Azure Automation ランブック
- C. Microsoft Sentinel 自動化ルール
- D. Microsoft Sentinel プレイブック
- E. Azure Functions アプリ

**正解** [：](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)CD🗳️  

**解説:**
Sentinelでインシデント対応と脅威修復の管理作業を最小化する機能です。

- **C. Microsoft Sentinel automation rules (自動化ルール)**: インシデントのトリアージ、割り当て、終了、プレイブックの実行などを自動化し、手作業を減らします。
- **D. Microsoft Sentinel playbooks (プレイブック)**: Logic Appsベースのワークフローで、ファイアウォールのブロック、ユーザー無効化、チケット起票などの複雑な修復アクションを自動化します。
この2つの組み合わせがSentinelのSOAR（Security Orchestration, Automation, and Response）機能の中核です。

質問4 トピック6

AzureサブスクリプションにUser1というユーザーとWS1というMicrosoft Sentinelワークスペースが含まれています。WS1はMicrosoft Defender for Cloudを使用しています。  
  
次の表に示すMicrosoftセキュリティ分析ルールがあります。
  
![](https://img.examtopics.com/sc-200/image275.png)  
  
User1 がRule1、Rule2、Rule3、Rule4に一致するアクションを実行した場合、WS1にはいくつのインシデントが作成されますか？

- A. 1
- B. 2
- C. 3
- D. 4 ​

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/31/#)  

**解説:**
複数の分析ルール（Rule1-4）によって生成されるアラートのグループ化（インシデント統合）設定です。

- Rule1: Low severity, Enabled, Grouping=Disabled -> 1アラートで1インシデント作成（単独）
- Rule2: Medium severity, Enabled, Grouping=Enabled (Group alerts into a single incident if matching entities) -> エンティティ一致でまとまるが、他ルールとの連携設定（Fusionなど）がない限り、Rule2同士でまとまる。
- Rule3, Rule4...
表の詳細（Grouping設定）を見ると、
- Rule 1: Grouping **Disabled**
- Rule 2: Grouping **Disabled**
- Rule 3: Grouping **Disabled**
- Rule 4: Grouping **Disabled**
すべてのルールでグルーピング（Alert grouping）が無効になっています。
したがって、これらのルールがそれぞれトリガーされた場合、各アラートごとに個別のインシデントが作成されます。
User1がRule1, Rule2, Rule3, Rule4に一致するアクションを実行した場合、それぞれのアラートが発生し、それぞれが独立したインシデントになります。
合計 **4つ** のインシデントが作成されます。
※FusionなどのAI相関ルールが働けば別ですが、表の設定（分析ルール設定）だけを見る限り、グルーピング無効なので別々になります。

質問5 トピック6

オンプレミスネットワークがあります。Microsoft Defender for Identity を使用する Microsoft 365 E5 サブスクリプションを所有しています。Microsoft Defender ポータルから、User1 というユーザーの Device1 というデバイスで発生したインシデントを調査します。このインシデントには、次の Defender for Identity アラートが含まれています。  

個人情報盗難の疑い (Pass-the-Ticket) (外部 ID 2018)  
  
ユーザーとデバイスに影響を与えることなく、インシデントを封じ込める必要があります。このソリューションは、管理作業を最小限に抑える必要があります。  
  
どうすればよいでしょうか？

- A. User1 のみを無効にします。
- B. デバイス1のみを隔離します。
- C. 以前デバイス 1 にサインインしたすべてのアカウントのパスワードをリセットします。
- D. User1 を無効にし、Device1 を隔離します。
- E. User1 を無効にし、Device1 を隔離し、以前に Device1 にサインインしたすべてのアカウントのパスワードをリセットします。
### 回答: **C以前デバイス 1 にサインインしたすべてのアカウントのパスワードをリセットします。**

### 理由:

**Pass-the-Ticket攻撃の特性:**
- 攻撃者がKerberos チケットを盗み、別のコンピューターで再利用する横展開攻撃
- 盗まれたチケットは、そのチケットの有効期限が切れるまで使用可能
- **パスワードをリセットすると、攻撃者が新しいKerberosチケットを作成できなくなる**

質問6 トピック6
  
Workspace1 という Log Analytics ワークスペースを含む Azure サブスクリプションがあります。Azure  アクティビティ ログと Microsoft Entra ID ログを Workspace1 に転送するように構成します。  
  
リスクの高いユーザーによってクエリまたは変更された Azure リソースを特定する必要があります。KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが加算されます。  
  
![](https://img.examtopics.com/sc-200/image276.png)

**正解:** ![](https://img.examtopics.com/sc-200/image441.png)

**解説:**
このクエリの目的は、Microsoft Entra ID（旧Azure AD）でリスクがあると判定されたユーザー（`AADRiskyUsers`）が行った、Microsoft Graph API経由のリソース操作を可視化することです。

### 1. テーブルの選択 (MicrosoftGraphActivityLogs)

- **理由:** クエリの後半にある `RequestId`、`RequestMethod`、`ResponseStatusCode` といった列は、**MicrosoftGraphActivityLogs** テーブルに固有のものです。
- **AzureActivity** はAzureリソース（VMやネットワーク等）の管理操作を記録しますが、APIリクエストのメソッドやステータスコードをこの形式で持つのはGraphログです。
- **UserRiskEvents** はリスクそのものの詳細を記録するテーブルであり、リソースへのアクセスログは含みません。
    
### 2. リソースパスの抽出 ((parse_url(RequestUri).Path))

- **理由:** `RequestUri` 列には、`https://graph.microsoft.com/v1.0/users/...` のような完全なURLが含まれています。
- **関数の役割:** `parse_url()` 関数を使用することで、URLからパス部分（例: `/v1.0/users`）のみを抽出できます。その後の `replace_string` や `replace_regex` オペレーターは、このパスからバージョン情報やスラッシュの重複を取り除き、クリーンな **resourcePath** を作成するために使用されています。

質問7 トピック6

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションがあり、Device1 という Windows デバイスが搭載されています。  
  
ライブ応答セッションを使用して、Device1 で Prod という不審なプロセスを調査します。  
  
次の操作を実行する必要があります。  
  
• Prod を停止します。  
• Prod を送信して詳細を確認します。  
  
各操作に対してどのライブ応答コマンドを実行する必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image278.png)

**解説:**
ライブ応答セッションでは、特定のコマンドを使用してデバイス上で直接操作を行うことができます。

### 1. Stop Proc1 (プロセスの停止)

- **コマンド:** **remediate**
    
- **理由:** `remediate` コマンドは、ファイル、レジストリ、または **プロセス** に対して修復アクションを実行するために使用されます。プロセスを停止（Kill）したい場合は、`remediate process <ProcessId>` のように入力します。
    
### 2. Send Proc1 for further review (詳細確認のための送信)

- **コマンド:** **analyze**
    
- **理由:** `analyze` コマンドは、指定したファイル（今回の場合は不審なプロセスの実行ファイルなど）を Microsoft のマルウェア分析センターに送信し、詳細なスキャンや判定を依頼するために使用されます。
    
- **補足:** `getfile` はファイルをローカルにダウンロードして自分で確認するためのコマンドですが、「詳細を確認するために送信する（さらにレビューに回す）」という文脈では、プラットフォーム側の分析機能を呼び出す `analyze` が正解となります。
![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 31 ページを表示しています。

質問8 トピック6
  
Microsoft Defender for Endpoint を使用する Microsoft 365 E5 サブスクリプションがあり、Device1 という Windows デバイスが搭載されています。Device1 で検出された不審な実行ファイルを調査する必要があります。調査には以下の要件を満たす必要があります。  
  
• ファイルのイメージファイルパスを特定する。  
• Device1 でファイルが最初に検出された日時を特定する。  
  
検出イベントのタイムラインから確認すべき点は何ですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image280.png)

**解説:**
### 1. イメージ ファイル パスの特定 (Entities)

デバイス タイムライン上のイベントを選択すると、詳細ペインが開きます。

- **Entities（エンティティ）:** このタブには、そのイベントに関与した「ファイル」「プロセス」「ユーザー」などの詳細な属性がリストされます。ファイルの **イメージ ファイル パス（実行場所）** は、このエンティティ情報のメタデータとして明記されています。
    
### 2. 最初に検出された時刻の特定 (Event entities graph)

- **Event entities graph（イベント エンティティ グラフ）:** このタブは、関連するイベントを時系列の相関図として視覚化します。
    
- ファイルが作成され、実行され、その後のアクティビティにつながる一連のフローを表示するため、攻撃のチェーンの中で **「いつ、どのアクションが最初のトリガー（最初の検出）となったのか」** を時系列で追跡して特定するのに最適です。
