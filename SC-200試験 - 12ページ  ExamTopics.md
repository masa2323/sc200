質問#45 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。Amazon  Web Services (AWS) アカウントには、EC2-1 という名前の Amazon Elastic Compute Cloud (EC2) インスタンスが含まれています。EC2-1 を Defender for Cloud にオンボードする必要があります。EC2-1 には何をインストールすればよいですか？

- A. Log Analyticsエージェント
- B. Azure Connected Machine エージェント
- C. 統合された Microsoft Defender for Endpoint ソリューション パッケージ
- D. Microsoft 監視エージェント

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
AWS EC2インスタンスをDefender for Cloudにオンボードするために必要なエージェントです。
**「Azure Connected Machineエージェント (Azure Connected Machine agent)」**: AWS上のEC2インスタンスをAzure Arc対応サーバーとして接続することで、Defender for Cloud（Defender for Servers）の保護対象とすることができます。EC2インスタンスにインストールする最初のエージェントはこれです。なお、Azure Monitorエージェント (AMA) は、Arc接続後に拡張機能としてデプロイされます。

質問#46 トピック2

Microsoft Defender for Cloud を使用し、RG1 というリソース グループを含む Azure サブスクリプションがあります。RG1 には、Windows Server 2019 を実行する 20 台の仮想マシンが含まれています。RG1 内の仮想マシンに対して、ジャストインタイム (JIT) アクセスを構成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 最大要求時間を 2 時間に制限する。  
• プロトコル アクセスをリモート デスクトップ プロトコル (RDP) のみに制限する。  
• 管理作業を最小限に抑える。  
  
では、どのようなソリューションを使用すべきでしょうか。

- A. Azure AD 特権 ID 管理 (PIM)
- B. Azureポリシー
- C. アズール・バスティオン
- D. アズールフロントドア

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
管理作業を最小限に抑えつつ、RDPアクセスのJIT (Just-In-Time) 制御を2時間制限で構成する場合の選択肢です。
**「Azure Policy」**: JIT VMアクセスを大規模に適用し、構成を強制するための推奨される方法です。Azure Policyを使用することで、すべてのVM（または特定のリソースグループ内のVM）に対してJITを有効にするポリシー定義を割り当てることができます。個別に設定する手間を省き、管理を効率化できます。
※JITの時間はデフォルト3時間ですが、設定で変更可能です。要件の「2時間」もポリシーパラメータやDefender for Cloudの設定で対応できます。

質問#47 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションを所有しています。GCP1 という Google Cloud Platform (GCP) 組織を作成します。  
  
ネイティブ クラウド コネクタを使用して、GCP1 を Defender for Cloud にオンボードする必要があります。このソリューションでは、今後作成されるすべての GCP プロジェクトが自動的にオンボードされるようにする必要があります。  
  
このソリューションには何を含めるべきですか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image170.png)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image171.png)

**解説:**
GCP組織をDefender for Cloudにオンボードし、新しいプロジェクトも自動的に対象にするための設定です。

1. **Azure Arcの自動プロビジョニング**: Azure Arcエージェントを自動的にインストールする設定を有効にします。これにより、GCP上のVMが自動的にAzure Arcに接続され、管理対象となります。
2. **Microsoft Defender for Containersの自動プロビジョニング**: コンテナ保護（GKEなど）も要件に含まれる場合（設問には明示されていませんが、完全な保護には通常含まれます）、これも有効にします。しかし、より重要なのは**「監査ログ (Audit logs)」**の設定です。GCPコネクタの設定で、「GCP監査ログをDefener for Cloudに送信する」構成を行うことで、組織レベルでの監視が可能になります。
※画像選択肢の詳細は不明ですが、Defender for CloudのGCPコネクタ設定における「自動プロビジョニング（Auto provisioning）」設定画面での適切なオプションを選択する問題です。

質問#48 トピック2

VM1 という仮想マシンを含む Azure サブスクリプションがあり、Microsoft Defender for Cloud を使用しています。Microsoft Defender for Cloud では、Azure Monitor エージェントを使用するように自動プロビジョニングが設定されています。VM1 での PowerShell の不審な使用に関する誤検知アラートを抑制するカスタムアラート抑制ルールを作成する必要があります。  
  
まず何をすべきでしょうか？

- A. Microsoft Defender for Cloud から、アラートを Log Analytics ワークスペースにエクスポートします。
- B. Microsoft Defender for Cloud からワークフロー自動化を追加します。
- C. VM1 で PowerShell アラートをトリガーします。
- D. VM1 で、Get-MPThreatCatalog コマンドレットを実行します。

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
誤検知（False Positive）のアラートに対する抑制ルールを作成する前に必要なステップです。
**「VM1でPowerShellアラートをトリガーします」**: アラート抑制ルールを作成するには、まず対象となるアラートがDefender for Cloud上に存在している必要があります。既存のアラートを選択して「同様のアラートを抑制する」アクションを実行するのが標準的な手順です。そのため、まだアラートが発生していない場合は、まずアラートをトリガーさせる必要があります。

質問#52 トピック2

次の表に示すリソースがあります。Microsoft  Defender for Cloud を使用する Azure サブスクリプションがあります。  
  
![](https://img.examtopics.com/sc-200/image194.png)  
  
各リソースで Microsoft Defender for Servers を有効にする必要があります。Azure Arc エージェントのインストールが必要なリソースはどれですか？

- A. サーバー3のみ
- B. Server1とServer4のみ
- C. Server1、Server2、Server4のみ
- D. サーバー1、サーバー2、サーバー3、およびサーバー4

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
Microsoft Defender for Serversを有効にするためにAzure Arcエージェントのインストールが必要なリソースを特定します。

- **Server1 (AWS EC2)**: Azure外のVMなので、**必要**。
- **Server2 (Azure VM)**: Azureネイティブのリソースなので、Arcエージェントは**不要**（VMエージェントを使用）。
- **Server3 (Azure VM with SQL)**: Azureネイティブなので、Arcエージェントは**不要**。
- **Server4 (Physical Server)**: オンプレミスの物理サーバーなので、**必要**。
したがって、Arcエージェントが必要なのは **Server1 と Server4** です。
（※正解選択肢が C (Server1, Server2, Server4) となっていますが、Server2はAzure VMであれば不要なはずです。ただし、Server2が「Azure VM」と明記されているにも関わらずCが正解とされる場合、設問の前提（OS要件や管理形態）に特殊な条件があるか、あるいはServer2が管理されていない（エージェントが壊れている等）とみなされている可能性があります。標準的な知識では **Server1とServer4** ですが、選択肢の構成上Cが選ばれているようです。ここでは解説として「Azure外のリソースにはArcが必要、Azure VMには不要」という原則を押さえておいてください。）

質問#53 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。Account1 という GitHub アカウントがあり、10 個のリポジトリが含まれています。Defender for Cloud が Account1 のリポジトリにアクセスできることを確認する必要があります。Microsoft Defender for Cloud ポータルでまず何をすべきでしょうか？

- A. 統合を有効にします。
- B. プランを有効にします。
- C. 環境を追加します。
- D. セキュリティポリシーを有効にします。

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
GitHubリポジトリをDefender for Cloudに統合する最初のステップです。
**「環境を追加します (Add environment)」**: Defender for Cloudの「環境設定 (Environment settings)」ブレードから、「環境を追加 (Add environment)」を選択し、「GitHub」を選んで接続ウィザードを開始します。これにより、GitHub組織またはアカウントとの接続（コネクタ）を作成します。

質問#54 トピック2

Microsoft Defender for Cloud を使用する Sub1 という Azure サブスクリプションがあります。AzDO1 という Azure DevOps 組織があります。Sub1 と AzDO1 を統合する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• Defender for Cloud を使用して、パイプラインで公開されているシークレットを検出する。  
• 管理作業を最小限に抑える。  
  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正解は 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image195.png)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image196.png)

**解説:**
1. Defender for Cloud での設定: Add an environment

Azure DevOps などの外部リポジトリを Defender for Cloud と連携させるには、**「環境設定（Environment settings）」**から新しい環境（コネクタ）を追加する必要があります。

- **Add an environment:** このウィザードを通じて、特定の Azure DevOps 組織（AzDO1）への接続を確立します。これにより、Defender for Cloud がリポジトリのメタデータをスキャンし、セキュリティの推奨事項を表示できるようになります。
    
- 「Enable a plan」はサブスクリプション全体で DevOps セキュリティを有効にする操作ですが、特定の組織 `AzDO1` との**統合**を直接行う操作は「Add an environment」です。
    

2. AzDO1 での設定: Install an extension

パイプライン内で公開されているシークレット（パスワードや API キーなど）を検出するには、パイプラインのビルドプロセス中にスキャンを実行する必要があります。

- **Install an extension:** **Microsoft Security DevOps** 拡張機能を Azure DevOps にインストールします。この拡張機能には、シークレットスキャン（CredScan など）を含む複数のセキュリティ静的解析ツールが含まれており、パイプラインのタスクとして簡単に追加できます。
    
- **最小限の管理作業:** 自前でスクリプトを組んだり外部ツールを構成したりするよりも、公式の拡張機能を利用して Defender for Cloud のダッシュボードに結果を集約させるのが最も効率的です。
    
---
この統合により、パイプラインでシークレットが混入した際に Defender for Cloud の **DevOps Security** 画面でアラートを確認できるようになります。
