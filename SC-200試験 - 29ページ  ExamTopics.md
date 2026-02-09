## トピック5 - 質問セット5

質問1 トピック5

Microsoft 365 サブスクリプションがあり、以下のリソースが含まれています。  
  
• Microsoft 365 E5 ライセンスが割り当てられたユーザー 100 人  
• Microsoft Entra テナントに参加している Windows 11 デバイス 100 台  
  
ユーザーは Web 上の Outlook を使用して Microsoft Exchange Online メールボックスにアクセスします。  
  
ユーザーアカウントが侵害された場合に、Web 上の Outlook セッション トークンを取り消せるようにする必要があります。どのような設定が必要ですか？

- A. Microsoft Entraのセキュリティデフォルト
- B. Microsoft Entra 認証済み ID
- C. Microsoft Entraの条件付きアクセスポリシー
- D. Microsoft Entra ID 保護

正解は **C. Microsoft Entraの条件付きアクセスポリシー** です。

## 解説

ユーザーアカウントが侵害された際に Web 版 Outlook（Exchange Online）のセッショントークンを迅速に取り消すためには、**継続的アクセス評価 (CAE: Continuous Access Evaluation)** の仕組みを利用します。

- **なぜ「C」なのか:** 継続的アクセス評価 (CAE) は、Microsoft Entra の**条件付きアクセスポリシー**の一部として制御されます。CAE を構成することで、パスワードの変更、アカウントの無効化、あるいは「ユーザーリスク」の増大といったクリティカルなイベントが発生した際に、通常の有効期限（1時間など）を待たずに**ほぼリアルタイム（数分以内）でセッショントークンを失効**させることができます。
    
- **他の選択肢が不適切な理由:**
    
    - **A. セキュリティデフォルト:** 組織全体の基本的な保護（MFA 強制など）を有効にしますが、セッションの取り消しに関する詳細な構成はできません。
        
    - **B. 認証済み ID:** 分散型アイデンティティ（資格情報の提示など）のための仕組みであり、セッション管理とは無関係です。
        
    - **D. Microsoft Entra ID 保護:** 侵害の「検知（リスク判定）」を行いますが、その検知結果に基づいて「セッションをどう制御するか」という具体的な**構成（ポリシー）**は、条件付きアクセスポリシーで行うのが一般的です。

質問2 トピック5

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。  
  
以下のリスクを軽減するには、Defender for Cloud を構成する必要があります。  
  
• アプリケーション ソースコード内の脆弱性  
• 宣言型テンプレート内のエクスプロイトツールキット  
• 悪意のある IP アドレスからの操作  
• 公開されたシークレット  
  
使用すべき 2 つの Defender for Cloud サービスはどれですか？ 正解はそれぞれソリューションの一部を示しています。  
  
注: 正解は 1 点です。

- A. Microsoft Defender for Resource Manager
- B. Microsoft Defender for DNS
- C. Microsoft Defender for App Service
- D. Microsoft Defender for Servers
- E. DevOps 向け Microsoft Defender

**正解:** AE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**解説:**
Defender for Cloudのサービス選択。

1. **Vulnerabilities in application source code** & **Exploit toolkits in declarative templates** & **Exposed secrets**: これらはすべて開発段階（CI/CD、コードリポジトリ）のリスクです。**「Microsoft Defender for DevOps」** がこれらをスキャン・検出します（GitHub Advanced SecurityやAzure DevOps連携）。
2. **Operations from malicious IP addresses**: サーバーやリソースに対するネットワーク攻撃や不審な通信の検出です。**「Microsoft Defender for Servers」**（またはApp Service, Key Vaultなど）が脅威検出を行いますが、最も一般的な「悪意あるIPからの操作」はサーバーワークロードに対するものです。あるいは、DNSレベルでの保護を提供する **「Microsoft Defender for DNS」** もありますが、ソースコード脆弱性とセットで問われている場合、サーバー保護がペアになることが多いです。
※正解のAEは **A (Defender for Resource Manager)** と **E (Defender for DevOps)** です。
   - **Defender for DevOps**: ソースコード、テンプレート、シークレット用。
   - **Defender for Resource Manager**: Azureリソースに対する管理操作（ARM API）への攻撃を検知します。「宣言型テンプレート（ARM/Bicep）」の展開自体や、不審なリソース変更操作などを監視対象としますが、テンプレート内のエクスプロイトなどはDevOpsの領域です。しかし、正解がAを含んでいる場合、「悪意あるIPからの操作」が管理操作（コントロールプレーン）に対するものを指している可能性があります。

質問3 トピック5

Microsoft Defender for DevOps を使用する Azure DevOps 組織があるとします。この組織には、Repo1 という Azure DevOps リポジトリと、Pipeline1 という Azure Pipelines パイプラインが含まれています。Pipeline1 は、Repo1 に保存されているコードのビルドとデプロイに使用されます。Pipeline1 の実行時に、Microsoft Defender for Cloud が Repo1 内のコードに対してシークレットスキャンを実行できるようにする必要があります。  
  
組織に何をインストールし、Pipeline1 の YAML ファイルに何を追加すればよいでしょうか。回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image244.png)

## 回答

- **Install:** `The Microsoft Security DevOps extension`
    
- **Add:** `Steps`
    
---
## 解説

Microsoft Defender for DevOps を Azure Pipelines と統合し、ビルド時にシークレットスキャン（機密情報の混入チェック）を実行するには、以下の手順が必要です。

### 1. 拡張機能のインストール

**Microsoft Security DevOps 拡張機能**は、Defender for Cloud の機能をパイプラインに統合するための公式ツールです。これをインストールすることで、静的アプリケーション セキュリティ テスト (SAST) やシークレットスキャン（Gitleaks など）を一つのタスクで実行可能になります。

### 2. YAML ファイルへの追加

Azure Pipelines の YAML 構成において、具体的なアクション（タスク）は **`steps`** セクションに追加します。

- **例:** パイプライン内で `MicrosoftSecurityDevOps@1` タスクを `steps:` の配下に記述することで、実行時にスキャンがトリガーされます。
    
---
### 技術的な補足

シークレットスキャンの結果は、Azure DevOps の「Pipelines」のスキャン結果タブだけでなく、**Microsoft Defender for Cloud ポータル**の「DevOps セキュリティ」ダッシュボードにも集約されます。これにより、複数のリポジトリや組織を横断してセキュリティ状態を一元管理できるようになります。

質問4 トピック5

Azure DevOps組織があり、Repo1というAzure Reposリポジトリが含まれており、Microsoft Defender for DevOpsにオンボードされています。Infrastructure  
  
as Code (IaC)ファイルを作成し、Repo1に保存します。IaCファイルは、BicepファイルとHelm Chartsとしてフォーマットされています。IaC  
  
ファイル内の構成ミスを特定するには、Defender for DevOpsを構成する必要があります。  
  
それぞれのファイルの種類には、どのスキャンツールを使用すべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image246.png)

**正解:** ![](https://img.examtopics.com/sc-200/image247.png)

**解説:**
Defender for DevOps（MSDO）で使用されるIaCスキャンツールです。

1. **Bicep files**: **「Template Analyzer」**。MicrosoftのTemplate Analyzerは、ARMテンプレートおよびBicepファイルのセキュリティ構成ミスをスキャンするために使用されます。
2. **Helm Charts**: **「Terrascan」**。Terrascanは、Terraform, Helm, K8s, DockerfileなどのIaCスキャンをサポートしています。Checkovも有名ですが、MicrosoftのMSDO統合ではTerrascanが採用されています（または両方サポートされていますが、選択肢にある方を選びます）。

質問5 トピック5

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft 365 Defender for Endpoint を使用しています。Microsoft 365 Defender ポータルを使用して、Windows サーバーへのリモートシェル接続を開始できることを確認する必要があります。  
  
何を構成すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image248.png)

Microsoft Defender for Endpoint を使用して、Windows サーバーに対してリモートシェル（ライブレスポンス）を開始するための正しい設定は以下の通りです。

## 回答

- **Advanced feature (高度な機能):** `Live Response for Servers`
    
- **For the device group (デバイスグループの設定):** `The Automation level`
    
---
## 解説

1. 高度な機能 (Advanced feature)

Windows サーバーに対してリモートでのコマンド実行やファイル操作（ライブレスポンス）を許可するには、まずグローバル設定でこの機能を有効にする必要があります。

- **Live Response for Servers:** これをオンにすることで、サーバー OS（Windows Server など）を搭載したデバイスに対してライブレスポンスセッションを開始できるようになります。
    
- **なぜ他が不適切か:** `Device discovery` は未管理デバイスの検出用であり、`EDR in block mode` はアンチウイルスソフトが検知しきれなかった脅威をブロックするための機能で、どちらもリモートシェル接続とは関係ありません。
    
2. デバイスグループの設定 (For the device group)

高度な機能を有効にした後、対象となるサーバーが含まれる**デバイスグループ**側でも、管理アクションが許可されるように構成する必要があります。

- **The Automation level (自動化レベル):** デバイスグループの設定では、自動調査および修復のレベル（Full、Semi、None）を定義します。ライブレスポンス（特にスクリプトの実行など）は、この管理レベル設定や権限スコープと密接に関連しているため、デバイスグループのプロパティにおいてこれを適切に構成する必要があります。
    
- **なぜ他が不適切か:** `A device tag` や `A device value` は、デバイスをグループに振り分けるための「条件」であり、機能を有効化または制御するための「設定項目」ではありません。

質問6 トピック5

オンプレミスデバイスが500台あります。Microsoft Defender 365を利用するMicrosoft 365 E5サブスクリプションを保有しています。Microsoft Defender 365にデバイスを100台オンボードします。管理されていないオンプレミスデバイスを特定する必要があります。オンボードされた特定のデバイスのみが検出を実行するようにソリューションを設定する必要があります。  
  
まず何をすべきでしょうか？

- A. デバイス グループを作成します。
- B. 除外を作成します。
- C. 検出モードを基本に設定します。
- D. タグを作成します。

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  
まず、オンボードされた特定のデバイスにタグを付ける必要があります。次に、「設定」→「デバイスの検出」でモードを「標準」に設定し、「これらのタグを持つデバイスのみ」を選択します。タグがないと、標準検出を実行するデバイスを絞り込むことができません。

質問7 トピック5

Microsoft 365 E5 サブスクリプションがあり、Device1 というデバイスが含まれています。Device1 は Microsoft Defender for Endpoint に登録されています。Device1  
  
から、証拠として File1.exe というファイルを含むインシデントが報告されました。  
  
「調査パッケージの収集」アクションを開始し、ZIP ファイルをダウンロードします。File1.exe  
  
が最初に実行された時刻と最後に実行された時刻を特定する必要があります。  
  
調査パッケージで確認すべき点は何でしょうか？

- A. プロセス
- B. 自動実行
- C. セキュリティイベントログ
- D. スケジュールされたタスク
- E. プリフェッチファイル

**正解：** E [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
調査パッケージ（Investigation package）に含まれるデータから実行可能ファイルの実行時刻を特定するための情報源です。
**「Prefetch files (プリフェッチファイル)」**: Windowsのプリフェッチファイル（.pf）は、アプリケーションの起動頻度や起動速度を最適化するためのものですが、副次的に「そのアプリケーションが最後に実行された日時」や「実行回数」などの情報が含まれています。調査パッケージにはプリフェッチファイルのダンプが含まれており、これを解析することで、File1.exeの初回/最終実行時刻を特定できます。

質問8 トピック5

Microsoft Defender for Cloud が有効になっている Azure サブスクリプションをお持ちです。Windows  
  
Server 2022 を実行し、Amazon Web Services (AWS) でホストされている Server1 という仮想マシンがあります。Defender  
  
for Cloud を使用して Server1 のログを収集し、脆弱性を解決する必要があります。Server1  
  
に最初にインストールすべきものは何ですか？

- A. Microsoft 監視エージェント
- B. Azure Monitorエージェント
- C. Azure Connected Machine エージェント
- D. Azure Pipelinesエージェント

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
AWS上のWindows Server (Server1) をAzure (Defender for Cloud) で保護・ログ収集するための最初の手順です。
**「Azure Connected Machine agent」**: これをインストールすることで、非Azureサーバー（オンプレミスやAWS）をAzure Arc対応サーバーとして登録できます。Azure Arcに登録されると、Azure VM拡張機能（Azure Monitor Agentなど）をインストールできるようになり、Defender for Cloudによる保護やログ収集が可能になります。
※MMA (Microsoft Monitoring Agent) は廃止予定であり、現在はAzure Monitor Agent (AMA) が標準ですが、AMAを非AzureサーバーにインストールするにはAzure Arc (Connected Machine Agent) が前提条件として推奨されます。

質問9 トピック5

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをご利用です。Microsoft Graph API を攻撃ベクトルとして利用することが知られている攻撃者を調査しています。攻撃者は以下の表に示す戦術を実行します。  
  
![](https://img.examtopics.com/sc-200/image270.png)  
  
組織内で悪意のあるアクティビティを検索する必要があります。MicrosoftGraphActivityLogs  テーブルを使用して分析できる戦術はどれでしょうか？

- A. Tactic2のみ
- B. 戦術1と戦術2のみ
- C. 戦術2と戦術3のみ
- D. 戦術1、戦術2、戦術3

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
MicrosoftGraphActivityLogsテーブルで検出可能な戦術（Tactic）についてです。
このテーブルには、Microsoft Graph APIへのすべてのリクエストログが含まれます。

- **Tactic 1 (Reconnaissance: 偵察)**: `User.Read.All` などのAPIを使用してディレクトリ情報を収集する行為はログに記録されます。
- **Tactic 2 (Discovery: 探索)**: `Mail.Read` などでメール内容を探索する行為もAPIコールとして記録されます。
- **Tactic 3 (Collection: 収集)**: データをダウンロードする行為もAPIコールです。
したがって、攻撃者がGraph APIを使用している限り、すべての戦術のアクティビティがログに含まれるため、分析可能です。

質問10 トピック5

次の Advanced Security Information Model (ASIM) パーサーを含む Microsoft Sentinel ワークスペースがあります。  
  
• \_Im\_ProcessCreate  
• imProcessCreate  
  
vimProcessCreate という新しいソース固有のパーサーを作成します。  
  
次の要件を満たすようにパーサーを変更する必要があります。  
  
• すべての ProcessCreate パーサーを呼び出します。  
• フィールドをプロセス スキーマに標準化します。  
  
各要件を満たすには、どのパーサーを変更する必要がありますか。 回答するには、適切なパーサーを正しい要件にドラッグします。  
  
各パーサーは、1 回または複数回使用することも、まったく使用しないこともできます。 コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image271.png)
### 正解

画像の質問に対する回答：

|要件|使用するパーサー|
|---|---|
|**すべての ProcessCreate パーサーを呼び出します**|**`_Im_ProcessCreate`**|
|**フィールドをプロセス スキーマに標準化します**|**`vimProcessCreate`**|

### 根拠

公式ドキュメントより：

1. **`_Im_ProcessCreate`について**:
    - 統合パーサーは「複数のソース固有パーサーを呼び出し、すべてのデータソースを統合する」役割を持つ
    - 引用: "The **unifying** parser in turn calls **source-specific** parsers to perform the actual parsing and normalization"
2. **`vimProcessCreate`について**:
    - 新しく作成されたソース固有パーサー
    - ソース固有パーサーの役割は「実際の解析と正規化を実行する」
    - 生データをASIMスキーマの標準フィールドにマッピングする
3. **`imProcessCreate`について**:
    - これはワークスペースデプロイ版の統合パーサー
    - 開発/テスト環境で使用されるが、この問題では選択肢として提示されていない


質問11 トピック5
  
Windows Server を実行するオンプレミス サーバーがあります。SW1  という Microsoft Sentinel ワークスペースがあります。SW1 は、Azure Monitor エージェント データ コネクタを使用してサーバーから Windows セキュリティ ログ エントリを収集するように構成されています。  
  
収集するイベントの範囲をイベント 4624 と 4625 のみに制限する予定です。  
  
コネクタに適用されたフィルターの構文を検証するには、PowerShell スクリプトを使用する必要があります。  

スクリプトをどのように完成させる必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image273.png)

### 正解

powershell

```powershell
$events = '*[System[(EventID=4624 or EventID=4625)]]'
Get-WinEvent -LogName 'Security' $events -FilterXPath
```

### 各空欄の正しい選択肢

1. **最初の空欄（$eventsの値）**:
    - `'*[System[(EventID=4624 or EventID=4625)]]'`
2. **第二の空欄（Get-WinEventのパラメータ）**:
    - `-FilterXPath`

### 根拠（公式ドキュメントより）

#### 1. XPath構文について

公式ドキュメント "[Collect Windows events from virtual machine with Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/vm/data-collection-windows-events)" より：

> **XPath entries are written in the form `LogName!XPathQuery`**
> 
> 例: `Security!*[System[EventID=1035]]`

ただし、**PowerShellの`Get-WinEvent`コマンドレットでは、LogNameは`-LogName`パラメータで別途指定**するため、XPath部分のみを指定します。

#### 2. 複数のイベントIDをフィルターする構文

同ドキュメントのサンプルより：

|説明|XPath|
|---|---|
|System events with Event ID = 4648のみ|`System!*[System[EventID=4648]]`|
|Success and failure Security events **except** for Event ID 4624|`Security!*[System[(band(Keywords,13510798882111488)) and (EventID != 4624)]]`|

また、"[Use the data ingestion benefit](https://learn.microsoft.com/en-us/azure/defender-for-cloud/data-ingestion-benefit)" より、**複数のイベントIDを含める場合の正しい構文**:

xpath

```xpath
*[System[(EventID=4624 or EventID=4625 or EventID=4688)]]
```

#### 3. Get-WinEventコマンドレットの使い方

公式ドキュメント "[Connect Microsoft Sentinel to other Microsoft services with a Windows agent-based data connector](https://learn.microsoft.com/en-us/azure/sentinel/connect-services-windows-based)" より：

> To test the validity of an XPath query, use the PowerShell cmdlet **Get-WinEvent** with the _**-FilterXPath**_ parameter. For example:
> 
> powershell
> 
> ```powershell
> $XPath = '*[System[EventID=1035]]'
> Get-WinEvent -LogName 'Application' -FilterXPath $XPath
> ```

### 正しいスクリプト構文

powershell

```powershell
$events = '*[System[(EventID=4624 or EventID=4625)]]'
Get-WinEvent -LogName 'Security' -FilterXPath $events
```

**重要なポイント**:

- XPath式はSystem要素内で複数のEventIDを`or`で結合
- `Get-WinEvent`では`-FilterXPath`パラメータを使用
- `-LogName 'Security'`でSecurityログを指定
- Azure Monitor AgentのDCRで使用する際は、`Security!`プレフィックスが必要になりますが、PowerShellでローカルテストする際は不要です

この構文により、イベント4624（成功したログオン）と4625（失敗したログオン）のみが返されます。

質問12 トピック5

Microsoft 365 サブスクリプションをご利用で、Microsoft Defender for Endpoint プラン 2 をご利用で、500 台の Windows デバイスを保有しています。Microsoft Defender XDR のカスタム デセプション ルールを作成する予定です。  
  
このルールが特定の 10 台のデバイスにのみ適用されるようにする必要があります。  
  
まず何をすべきでしょうか？

- A. ルールにカスタムルアーを追加します。
- B. 各デバイスの IP アドレスをルールのデコイ アカウントとホストのリストに追加します。
- C. デバイスをグループに追加します。
- D. デバイスにタグを割り当てます。

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
Defender XDRのデセプション（Deception）ルールを特定のデバイス（10台）のみに適用する方法です。
**「Assign a tag to the devices (デバイスにタグを割り当てる)」**:
デセプションルールのスコープ設定では、**「デバイス タグ (Device Tags)」** を使用して対象をフィルタリングすることができます。デバイスグループも使えますが、特定の少数のデバイスを対象にする場合、タグ付けが柔軟で一般的です。選択肢にデバイスグループがある場合でも、タグが正解となるケースが多いです（詳細な粒度制御のため）。

質問13 トピック5

Microsoft Defender for Cloud を使用する Sub1 という Azure サブスクリプションがあります。Sub1 に PCI DSS 4.0 イニシアチブを割り当て、Defender for Cloud の規制コンプライアンス ダッシュボードにそのイニシアチブを表示する必要があります。  
  
環境設定のセキュリティ ポリシーで、業界標準や規制標準を追加するオプションが利用できないことがわかりました。  
  
まず何をすべきでしょうか？

- A. Log Analytics の継続的なエクスポート設定を構成します。
- B. サブスクリプションに対して Cloud Security Posture Management (CSPM) プランを有効にします。
- C. Azure Event Hubs の連続エクスポート設定を構成します。
- D. Microsoft Cloud Security Benchmark (MCSB) の割り当てを無効にします。

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
規制コンプライアンスダッシュボードでPCI DSS 4.0などの基準を追加するための前提条件です。
**「Enable the Cloud Security Posture Management (CSPM) plan」**: Defender CSPMプラン（有料）を有効にすることで、デフォルトのMicrosoft Cloud Security Benchmark (MCSB) 以外の規制基準（PCI DSS, ISO 27001など）を追加・管理できるようになります。無料版（Foundational CSPM）ではカスタム基準や追加基準の利用が制限されています。

質問14 トピック5

SW1というMicrosoft Sentinelワークスペースがあります。SW1 で有効になっている異常ルールを特定する必要があります。Microsoft Sentinelで確認すべき項目は何ですか？

- A. コンテンツハブ
- B. エンティティの行動
- C. 分析
- D. 設定

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
Sentinelで有効になっている「異常（Anomaly）ルール」を確認する場所です。
**「Analytics (分析)」**: 異常ルール（Anomaly rules）は、分析ルールのタブ（Active rulesまたはRule templates）の中に一覧表示されます。ここで有効/無効の状態を確認したり、編集したりできます。「Entity behavior」はUEBAのダッシュボード、「Content hub」はソリューションのインストール場所です。

質問15 トピック5

WS1 という Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。  
  
新しい攻撃ベクトルを検出するハンティングクエリを作成します。この攻撃ベクトルは、MITRE ATT&CK データベースに登録されている戦術にマッピングされます。  
  
新しい攻撃ベクトルが検出されたときに、WS1 でインシデントが作成されることを確認する必要があります。  
  
どのような設定が必要ですか？

- A. 狩猟ライブストリームセッション
- B. クエリブックマーク
- C. スケジュールされたクエリルール
- D. 融合ルール

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/29/#)  

**解説:**
新しい攻撃ベクトル（Hunting queryで見つかるものなど）に基づいて、将来的に自動でインシデントを作成するようにするための設定です。
**「Scheduled query rule (スケジュールされたクエリルール)」**: ハンティングクエリを定期的に実行し、条件に合致した場合にアラート（およびインシデント）を作成するには、そのクエリを「分析ルール（Analytics rule）」、具体的には「スケジュールされたクエリルール」に変換または作成する必要があります。

質問16 トピック5

Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
社内のセキュリティチームが、ネットワーク上のコマンドアンドコントロール (C2) エージェントのトラフィックを検出しています。エージェントは 50 時間に 1 回通信します。  
  
侵害されたデバイスを特定し、通信パターンを確立する Microsoft Defender XDR カスタム検出ルールを作成する必要があります。このソリューションは、以下の要件を満たす必要があります。  
  
• 過去 14 日間に通信したすべてのデバイスを特定する。  
• デバイスの特定にかかる時間を最小限に抑える。  
  
このルールの検出頻度はどのくらいに設定すればよいでしょうか。

- A. 12時間ごと
- B. 24時間ごと
- C. 3時間ごと
- D. 1時間ごと
### 問題の分析

**要件**:

- C2エージェントは **50時間に1回** 通信
- 過去 **14日間** に通信したすべてのデバイスを特定
- デバイス特定にかかる時間を **最小限** に抑える

### ルール頻度とルックバック期間の関係

公式ドキュメント "[Create custom detection rules](https://learn.microsoft.com/en-us/defender-xdr/custom-detection-rules)" より:

|頻度|ルックバック期間|
|---|---|
|**24時間ごと**|過去 **30日間**|
|**12時間ごと**|過去 **48時間**|
|**3時間ごと**|過去 **12時間**|
|**1時間ごと**|過去 **4時間**|

> "The rule then runs again at fixed intervals, applying a lookback period based on the frequency you choose"

### 重要な考察

1. **C2通信パターン**: 50時間に1回 = 約2.08日に1回
2. **要件**: 過去14日間のデータをカバー必要
3. **各頻度の問題点**:
    - **1時間ごと** → ルックバック4時間（50時間の通信を検出不可）
    - **3時間ごと** → ルックバック12時間（50時間の通信を検出不可）
    - **12時間ごと** → ルックバック48時間（50時間未満なので検出不可）
    - **24時間ごと** → ルックバック30日間（**14日間の要件を満たす唯一の選択肢**）

### 正解: **B. 24時間ごと**

### 根拠

1. **ルックバック期間の要件**:
    - 50時間ごとの通信を検出するには、少なくとも50時間以上のルックバック期間が必要
    - 過去14日間をカバーする必要がある
    - **24時間ごと** の頻度のみが **30日間** のルックバック期間を提供
2. **検出時間の最小化**:
    - より頻繁な実行（1時間、3時間、12時間）は、ルックバック期間が短すぎて50時間ごとの通信を見逃す
    - 24時間ごとの実行で、最大24時間以内に新しい通信を検出可能

質問17 トピック5

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをお持ちです。  
  
以下のステートメントを含むクエリがあります。  
  
![](https://img.examtopics.com/sc-200/image315.png)  
  
このクエリを使用するカスタム検出ルールを構成する必要があります。このソリューションでは、クエリに一致するイベントに関する通知を受け取るまでの時間を最小限に抑える必要があります。  
  
このルールの通知頻度はどのくらいに設定すればよいでしょうか？

- A. 1時間ごと
- B. 継続的（NRT）
- C. 12時間ごと
- D. 3時間ごと

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/30/#)  

**解説:**
Microsoft Defender XDR（旧M365 Defender）のカスタム検出ルール（Advanced Huntingクエリに基づく検出）の頻度設定です。
**「Every hour (1時間ごと)」**: カスタム検出ルールの実行頻度（Frequency）の選択肢として、以前は「1時間ごと」「3時間ごと」「12時間ごと」「24時間ごと」がありました。「Continuous (NRT)」はSentinelのAnalytics Ruleにはありますが、Defender XDRのカスタム検出にはNRT（Near Real-Time）という選択肢は通常存在しません（最短で1時間）。
※質問文に「minimize the time until you receive a notification」とあるため、選択可能な最短頻度である**1時間ごと（Every hour）**が正解です。
（注: SentinelのNRTルールとは混同しやすいですが、XDR portalでの設定の話です）

