質問#25 トピック2

Azure サブスクリプションをお持ちです。  
以下の要件を満たすには、権限を委任する必要があります。
✑ Azure Defender を有効化および無効化する。
✑ リソースにセキュリティ推奨事項を適用する。  
ソリューションでは、最小権限の原則を適用する必要があります。  
各要件には、どの Azure Security Center ロールを使用する必要がありますか？回答するには、適切なロールを正しい要件にドラッグしてください。各ロールは、1 回使用することも、複数回使用することも、まったく使用しないこともできます。コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
注: 正しい選択ごとに 1 ポイントが付与されます。  
選択して配置:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0008200001.jpg)  

**正解:** ![](https://img.examtopics.com/sc-200/image416.png)

**解説:**
この問題のポイントは、**「最小権限の原則（Principle of Least Privilege）」**と、Microsoft Defender for Cloud（旧 Azure Defender）における各ロールの権限範囲を正しく理解することにあります。

1. Azure Defender の有効化・無効化

Azure Defender（現在の Microsoft Defender for Cloud の各プラン）の有効化や無効化といったセキュリティ設定の変更には、サブスクリプション レベルでの書き込み権限が必要です。

- **Security Admin（セキュリティ管理者）**：セキュリティ ポリシーの編集、推奨事項の表示、アラートの破棄、そしてセキュリティ設定（Defender のプランの切り替え）の変更が可能です。
    
- Subscription Contributor や Subscription Owner でも可能ですが、これらはセキュリティ以外のリソース管理権限も持ってしまうため、セキュリティ設定に特化した **Security Admin** が最小権限となります。
    

2. リソースにセキュリティ推奨事項を適用する

「推奨事項を適用する（Remediate）」という操作は、実際に対象リソースの設定を変更（例：ディスクの暗号化を有効にする、ネットワーク セキュリティ グループの設定を変更するなど）することを意味します。

- **Security Admin**：推奨事項を表示・管理することはできますが、**リソースそのものの構成を変更する権限（書き込み権限）は持っていません。**
    
- **Resource Group Owner**：対象のリソースが含まれるリソース グループに対してフル アクセス権限を持っているため、リソースの構成変更を伴う「推奨事項の適用」を実行できます。
    
- Subscription Owner / Contributor でも可能ですが、範囲がサブスクリプション全体に及ぶため、特定のリソース グループに限定した **Resource Group Owner** の方が最小権限の原則に合致しています。

質問#26 トピック2

Azure Defender を使用する Azure サブスクリプションを所有しています。Azure Security Center のワークフロー自動化を使用して、Azure Defender の脅威アラートに対応する予定です。  
脅威の修復を自動的に実行する Azure ポリシーを作成する必要があります。  
ソリューションには何を含めるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正しい選択ごとに 1 ポイントが加算されます。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0008300001.jpg)  

**解説:**
このソリューションは、「特定の条件下で自動的に修復（オートメーションの構成）をデプロイする」という Azure Policy の仕組みと、「アラートを検知してアクションを実行する」ワークフロー自動化の仕組みを組み合わせています。

1. Set available effects to: DeployIfNotExists

Azure Policy において、リソースが準拠していない場合に「リソースをデプロイして修復する」ために使用されるエフェクトは **DeployIfNotExists (DINE)** です。

- **Append**: リソース作成時に特定のフィールドを追加しますが、既存の構成の欠落を補ってデプロイ（修復）することはできません。
    
- **EnforceRegoPolicy**: 主に Azure Kubernetes Service (AKS) のアドミッション コントロールで使用されるもので、今回のケースには適しません。
    
2. To perform remediation use: Azure Logic Apps (Alert trigger)

Microsoft Defender for Cloud のワークフロー自動化（Workflow Automation）は、基本的に **Azure Logic Apps** をエンジンとして使用します。

- **トリガーの種類**: 脅威アラートに対応する場合、Logic App のトリガーは **「When an Azure Security Center Alert is created or triggered（アラートが作成またはトリガーされたとき）」** である必要があります。
    
- **Automation Runbook**: Webhook を介して Runbook を呼び出すことも技術的には可能ですが、Defender for Cloud の「ワークフロー自動化」機能がネイティブに統合し、推奨しているのは Logic Apps です。
    
### まとめ
1. **Azure Policy (DeployIfNotExists)** を使用して、サブスクリプション内に「ワークフロー自動化（アラート時に Logic App を動かす設定）」が確実に存在するように強制します。
    
2. そのポリシーによってデプロイされる **Logic App** が、アラート発生時に実際の修復処理（脅威の遮断など）を実行します。

質問#27 トピック2

オンプレミスのデータセンターに、App1 というカスタム Web アプリが含まれています。App1 は Active Directory ドメイン サービス (AD DS) 認証を使用しており、Microsoft Entra アプリケーション プロキシを使用してアクセスできます。Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションがあります。  
  
ユーザーが機密性の高いドキュメントをダウンロードしたというアラートを受け取りました。  
  
アラートに関連するリスクに対処するために、ユーザーが App1 を使用して「Highly Confidential」の機密ラベルが適用されたドキュメントのダウンロードを開始する際には、多要素認証 (MFA) を必須にする必要があります。  
  
どうすればよいでしょうか。回答するには、回答領域から適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image311.png)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image312.png)

**解説:**
オンプレミスアプリ（App Proxy経由）での機密ファイルダウンロード時にMFAを強制し、ダウンロードを制御するソリューションです。

1. **Conditional Access policy**: ユーザーがアプリにアクセスする条件（アプリ、ユーザー、場所など）に基づいてアクセスを制御します。ここで、**「Microsoft Defender for Cloud Appsの条件付きアクセスアプリ制御を使用する (Use Conditional Access App Control)」** を選択し、セッションをMDCA（Defender for Cloud Apps）にプロキシします。
2. **Session policy (in Defender for Cloud Apps)**: プロキシされたセッション内で、ユーザーのアクション（ダウンロード）を監視・制御します。**「Microsoft Defender for Cloud Appsのセッションポリシー」** を作成し、ファイルに「Highly Confidential」ラベルが付いている場合にダウンロードをブロックする（またはダウンロード時にMFAを要求する）設定を行います。

質問#28 トピック2

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Amazon Web Services (AWS) に Linux 仮想マシンがあります。Azure Defender をデプロイし、自動プロビジョニングを有効にしています。
Azure Defender を使用して仮想マシンを監視する必要があります。  
解決策: Azure Arc を有効にし、仮想マシンを Azure Arc にオンボードします。  
これは目標を達成していますか?  

- A. はい
- B. いいえ

**Correct Answer:** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)  

**解説:**
AWS上のLinux VMをAzure Defender (Defender for Cloud) で監視するための適切な手順です。
**「Azure Arcを有効にし、仮想マシンをAzure Arcにオンボードする」**: これが正解です。非Azureサーバー（AWS, GCP, オンプレミス）をDefender for Cloudで保護・監視するための推奨される方法は、まずAzure Arc対応サーバーとして接続することです。これにより、Azure上のリソースとして扱われ、Defenderエージェント（Log AnalyticsエージェントやMDEなど）の自動プロビジョニングやポリシー管理が可能になります。

質問#29 トピック2

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Amazon Web Services (AWS) に Linux 仮想マシンがあります。Azure Defender をデプロイし、自動プロビジョニングを有効にしています。
Azure Defender を使用して仮想マシンを監視する必要があります。  
解決策: 仮想マシンに Log Analytics エージェントを手動でインストールします。  
これは目標を達成していますか?  

- A. はい
- B. いいえ

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)  

**解説:**
**「仮想マシンにLog Analyticsエージェントを手動でインストールする」**: これは目標を完全には達成しません（または推奨される最善策ではありません）。
単にログを収集するだけであれば可能ですが、Azure Defenderの統合的な監視機能（自動プロビジョニング、脆弱性管理、推奨事項の完全なサポートなど）をAWS上のVMで利用するには、**Azure Arc** を介して接続するのが現在の標準的な設計です。したがって、Q28のアプローチ（Arc有効化）が正解であり、手動インストールのみでは「いいえ」となります。

質問#30 トピック2

オンプレミスのLinuxサーバーが5台あります。Microsoft Defender for Cloudを使用するAzureサブスクリプションを所有しています。Linux サーバーを保護するには、Defender for Cloudを使用する必要があります。  
まずサーバーに何をインストールすればよいでしょうか？  

- A. 依存エージェント
- B. Log Analyticsエージェント
- C. Azure Connected Machine エージェント
- D. ゲスト構成拡張機能

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)  

**解説:**
オンプレミスのLinuxサーバーをDefender for Cloudで保護するために最初にインストールすべきものは、**「Azure Connected Machineエージェント (Azure Connected Machine agent)」** です。
このエージェントをインストールすることで、サーバーはAzure Arcにオンボードされ、AzureリソースIDを持ちます。その後、Defender for CloudからLog Analyticsエージェントや他の拡張機能をデプロイして保護を有効化できます。

質問#31 トピック2

Azureサブスクリプションをお持ちです。このサブスクリプションには、Microsoft Defender for Cloudにオンボードされている仮想マシンが10台含まれています。Defender for Cloudが仮想マシン上でデジタル通貨マイニング行為を検出した場合、メール通知を受信するようにする必要があります。ソリューションはテストメールを生成する必要があります。
3 つのアクションのうち、どのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序で並べ替えてください。  
選択して配置：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0008700001.jpg)  

- **From Logic App Designer, create a logic app.**
    - ドキュメントによると、まずAzure Logic Appsでロジックアプリを作成する必要があります
    - Workflow automationの設定画面で「visit the Logic Apps page」を選択してLogic Appの作成プロセスを開始します
- **From Workflow automation in Defender for Cloud, add a workflow automation.**
    - Logic Appを作成した後、Defender for Cloudの「Workflow automation」セクションで新しい自動化ルールを追加します
    - ここでトリガー条件（デジタル通貨マイニング検出など）を設定し、作成したLogic Appを選択します
    - ドキュメントには「Select your logic app, and then save the automation」と記載されています
- **From Security alerts in Defender for Cloud, create a sample alert.**
    - ドキュメントの「Generate sample security alerts」セクションによると、設定をテストするためにサンプルアラートを作成できます
    - Security alertsページのツールバーから「Sample alerts」を選択し、サブスクリプションとDefenderプランを選択して「Create sample alerts」をクリックします
    - これにより、メール通知などの設定が正しく機能するかを検証できます（テストメールが生成されます）

![](https://www.examtopics.com/assets/media/exam-media/04261/0008800001.png)  

![](https://www.examtopics.com/assets/media/exam-media/04261/0008900001.png)  

質問#32 トピック2
  
Microsoft Defender for Cloud が有効になっている Microsoft サブスクリプションをお持ちです。  
  
次の表に示す Azure ロジック アプリを構成します。  
  
![](https://img.examtopics.com/sc-200/image128.png)  
  
「不審なプロセスが実行されました」というアラートがトリガーされたときに実行される自動アクションを構成する必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。
3 つのアクションのうち、順番に実行する必要があるのはどれですか？ 回答するには、アクションの一覧から適切なアクションを回答領域に移動し、正しい順序で並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image129.png)

**解説:**
「この問題の鍵は、既存のアラート詳細画面から直接ワークフロー自動化を作成することで、設定の手間（アラート名の指定など）を省く点にあります。

1. ロジックアプリの選択

まず、表に示された 2 つのロジックアプリのうち、今回のアラート（Alert）に対応できるのは **LogicApp2** です。

- **LogicApp1**: トリガーが「推奨事項（Recommendation）」のため、アラートには反応しません。
- **LogicApp2**: トリガーが「アラート（Alert）」のため、今回の要件に適しています。
    
2. 手順の詳細

- **Filter by alert title**: Microsoft Defender for Cloud の「セキュリティ アラート」画面で、対象となる「不審なプロセスが実行されました（Suspicious process executed）」を検索して特定します。
    
- **Select Take action**: アラートの詳細を開き、「アクションの実行（Take action）」タブを選択します。ここには、その特定のアラートに対する推奨される対応策や自動化オプションが集約されています。
    
- **Configure the Trigger automated response settings**: 「アクションの実行」タブ内にある「自動応答のトリガー（Trigger automated response）」セクションで、**LogicApp2** を選択してワークフロー自動化を作成します。これにより、今後同じタイトルのアラートが発生した際に、自動的にロジックアプリが実行されるようになります。
    

この手順で構成を行うと、アラート名などのフィルター条件が自動的に入力されるため、ゼロからワークフロー自動化を作成するよりも管理作業を最小限に抑えることができます。

質問#33 トピック2

Microsoft Defender for Cloud が有効になっている Azure サブスクリプションをお持ちです。Windows Server 2022 を実行し、Amazon Web Services (AWS) でホストされている Server1 という仮想マシンがあります。Defender for Cloud を使用して Server1 のログを収集し、脆弱性を解決する必要があります。Server1 に最初にインストールすべきものは何ですか？

- A. Microsoft 監視エージェント
- B. Azure Monitorエージェント
- C. Azure Arcエージェント
- D. Azure Pipelinesエージェント

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)  

**解説:**
AWS上のWindows Server 2022からログを収集し、脆弱性を解決するための最初のステップです。
**「Azure Arcエージェント (Azure Arc agent)」** (正しくはAzure Connected Machine agentですが、選択肢ではこれに相当) を最初にインストールします。これにより、AWS上のサーバーがAzureの管理下に置かれ（Arc対応サーバー）、その後のログ収集エージェント（AMA/MMA）の配布や脆弱性スキャン機能の適用が可能になります。

質問#34 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションがあり、storage1 というストレージ アカウントが含まれています。storage1 内の BLOB に対して、異常に多くの削除操作が発生したというアラートを受け取りました。  
  
どの BLOB が削除されたのかを特定する必要があります。  
  
確認すべき点は何でしょうか。

- A. ストレージ1のアクティビティログ
- B. Azure Storage Analytics ログ
- C. アラートの詳細
- D. アラートの関連エンティティ

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/10/#)  

**解説:**
Blobが削除されたことを特定し、誰がいつ削除したかなどの詳細を確認するにはログが必要です。
**「Azure Storage Analytics logs」** (またはAzure MonitorのStorage logs) を確認する必要があります。アクティビティログ (A) には、ストレージアカウントの作成やキーの変更などの管理操作（コントロールプレーン）のみが記録され、Blobの読み書き・削除といったデータプレーンの操作は記録されません。
アラートの詳細 (C) や関連エンティティ (D) も手がかりにはなりますが、具体的な操作ログ（どのBlobが削除されたか）を直接確認する一次情報源はストレージログです。
