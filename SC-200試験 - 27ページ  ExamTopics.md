質問#26 トピック4

次の表に示すユーザーを含むMicrosoft 365 E5サブスクリプションをご利用の場合、Microsoft Entra Internet Accessを構成します。Microsoft Entra Internet Accessを管理できるのはどのユーザーですか？
  
![](https://img.examtopics.com/sc-200/image364.png)  
  
- A. ユーザー1のみ
- B. ユーザー2のみ
- C. ユーザー3のみ
- D. ユーザー1とユーザー2のみ
- E. ユーザー1、ユーザー2、ユーザー3

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)  

**解説:**
Microsoft Entra Internet Access（Global Secure Accessの一部）を管理するために必要な権限です。
**「Global Secure Access Administrator (グローバル セキュア アクセス管理者)」**: このロールは、Entra Internet AccessおよびEntra Private Accessの構成を管理できます。
ユーザー1は「Global Secure Access Administrator」を持っているので管理可能です。
ユーザー2は「Security Administrator」を持っています。セキュリティ管理者は通常、セキュリティ関連の設定（Global Secure Access含む）に対する広範なアクセス権を持っています。
ユーザー3は「Application Administrator」であり、アプリ登録などはできますが、ネットワークセキュリティサービスであるInternet Accessの全体管理権限ではありません。
したがって、ユーザー1とユーザー2が管理可能です。

質問#27 トピック4
  
Sub1 という Azure サブスクリプションがあり、RG1 というリソース グループが含まれています。RG1 には、Azure ロールベース アクセス制御 (Azure RBAC) を使用する KV1 と KV2 という 2 つの Azure キー コンテナーが含まれています。  
  
このサブスクリプションには、次の表に示すユーザーが含まれています。
  
![](https://img.examtopics.com/sc-200/image365.png)  
  
KV1 には Secret1 というシークレットが含まれています。KV2 には Secret2 というシークレットが含まれています。  
  
各シークレットの値を読み取ることができるのはどのユーザーですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image366.png)

**正解:** ![](https://img.examtopics.com/sc-200/image367.png)

**解説:**
- ユーザー1：サブ1のKey Vault管理者 スコープ：サブ1（サブスクリプション）にはRG1が含まれており、RG1にはKV1とKV2が含まれています。権限：Key Vault管理者として、ユーザー1はKV1とKV2の両方にフルアクセスでき、シークレットの読み取り権限も含まれます。アクセス：KV1：シークレット1を読み取ることができます。KV2：シークレット2を読み取ることができます。
- ユーザー2：RG1のKey Vault閲覧者 スコープ：RG1（リソースグループ）にはKV1とKV2の両方が含まれています。権限：Key Vault閲覧者として、ユーザー2はKV1とKV2のプロパティを表示できますが、シークレット値にアクセスするためのデータプレーン権限がありません。アクセス：KV1：シークレット1を読み取ることができません。KV2：シークレット2を読み取ることができません。
- ユーザー3：KV1のKey Vaultシークレットユーザー スコープ：KV1（特定のキーコンテナー）。権限: Key Vault シークレット ユーザーである User3 は、KV1 内のシークレットを読み取ることができますが、スコープが KV1 に制限されているため、KV2 に対する権限はありません。アクセス: KV1: Secret1 を読み取ることができます。KV2: Secret2 を読み取ることはできません (KV2 のスコープでは権限がありません)。

質問#28 トピック4
  
Microsoft Sentinel ワークスペースがあります。  
  
以下の要件を満たすプレイブックを作成する必要があります。  
  
• 自動化ルールを使用して、エンティティに対してアクションをトリガーする。  
• 「エンティティ - ホストの取得」アクションを呼び出す。  
  
どの種類のプレイブックを使用し、どのパラメーターを指定する必要がありますか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image368.png)

### **回答エリアの選択**

- **Playbook types（プレイブックの種類）:** * **Only a playbook that uses an incident trigger and a playbook that uses an alert trigger only**
    - （インシデントトリガーを使用するプレイブック、およびアラートトリガーのみを使用するプレイブックのみ）
    
- **Parameters（パラメーター）:** * **Alert and FullIncidentProperties only**
    - （AlertおよびFullIncidentPropertiesのみ）
        
---
#### **解説**

1. プレイブックの種類について

Microsoft Sentinelの**自動化ルール（Automation rules）**は、以下の条件が発生したときにプレイブックを実行できます。

- インシデントの作成時
- インシデントの更新時
- アラートの作成時
    
そのため、自動化ルールに関連付けられるプレイブックは、**「Microsoft Sentinel インシデントトリガー」**または**「Microsoft Sentinel アラートトリガー」**を使用している必要があります。 「エンティティトリガー」を使用するプレイブックは、エンティティページなどからの**手動実行**を目的としたものであり、自動化ルールから直接トリガーすることはできません。

2. パラメーターについて

プレイブック内で「エンティティ - ホストの取得（Get - Entities (Host)）」などのアクションを呼び出すには、トリガーとなったイベントからエンティティ情報を抽出する必要があります。

- インシデントトリガーの場合、**FullIncidentProperties**（インシデントの全プロパティ）にエンティティ情報が含まれます。
- アラートトリガーの場合、**Alert**（アラート）オブジェクトにエンティティ情報が含まれます。
    
したがって、自動化ルールを介してこれらの情報を処理するためには、これらのパラメーターが指定されている必要があります。

質問#29 トピック4
  
contoso.com という Microsoft Entra テナントにリンクされた Sub1 という Azure サブスクリプションがあります。Contoso.com には User1 というユーザーがいます。Sub1 には Microsoft Sentinel ワークスペースがあります。Microsoft Copilot for Security のキャパシティをプロビジョニングします。User1 が Copilot for Security を使用して以下のタスクを実行できるようにする必要があります。  
  
• データ共有およびフィードバックのオプションを更新する。  
• Microsoft Sentinel のインシデントを調査する。  
  
ソリューションは、最小権限の原則に従う必要があります。  
  
各タスクにおいて、User1 にどのロールを割り当てる必要がありますか？ 回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image370.png)

**正解:** ![](https://img.examtopics.com/sc-200/image371.png)

**解説:**
1. データ共有およびフィードバックのオプションの更新**

Microsoft Copilot for Security の設定（データ共有プロンプト、フィードバック、テナント設定など）を管理するには、**管理者権限**が必要です。

- **Security Administrator（セキュリティ管理者）** または **Global Administrator（グローバル管理者）** は、デフォルトで Copilot for Security の「所有者」権限を持ち、これらの設定を構成できます。
- 「最小権限の原則」に従う場合、全権限を持つグローバル管理者ではなく、**Security Administrator** を選択するのが適切です。
- Security Operator（セキュリティ オペレーター）は、ツールの利用は可能ですが、テナント全体の共有設定などを変更する権限は持ちません。
    
2. Microsoft Sentinel インシデントの調査**

Copilot for Security を通じて Microsoft Sentinel のデータにアクセスし、インシデントの調査を行うには、Sentinel ワークスペース側で適切な権限が必要です。

- **Microsoft Sentinel Responder（Microsoft Sentinel 応答者）**：インシデントの表示、割り当て、ステータスの変更、および調査を行うことができます。「調査（Investigate）」という要件を満たすための最小権限のロールです。
- **Microsoft Sentinel Reader（Microsoft Sentinel 閲覧者）**：データの表示は可能ですが、インシデントの調査（アクションの実行）には不十分です。
- **Cloud App Security Administrator**：Microsoft Defender for Cloud Apps に特化したロールであり、Sentinel 全体のインシデント調査には適していません。

質問#30 トピック4

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。Azure Resource Manager (ARM) テンプレートを使用して、Microsoft Defender for Cloud が特定のアラートを受信したときにロジック アプリをトリガーするワークフロー自動化を作成する必要があります。  
  
テンプレートはどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image372.png)

### **回答エリアの選択**

- **logicAppResourceId:** **Microsoft.Logic**
    
---
#### **解説**

Azure Resource Manager (ARM) テンプレートにおいて、リソースの完全な ID を生成する `resourceId` 関数を使用する場合、**「リソース プロバイダー/リソース タイプ」** の形式で指定する必要があります。

- **Microsoft.Logic:** Azure Logic Apps のリソース プロバイダーです。Logic App 本体は `Microsoft.Logic/workflows` というタイプで定義されます。
    
- **Microsoft.Security:** これはワークフロー自動化リソース自体（`Microsoft.Security/automations`）を定義する際に使用するプロバイダーであり、呼び出し先の Logic App を指すものではありません。
    
- **Microsoft.Automation:** Azure Automation（Runbookなど）に使用されるプロバイダーです。
    
- **Microsoft.AlertsManagement:** Azure Monitor のアラート管理に関連するプロバイダーです。
    
したがって、テンプレートの該当箇所を `[resourceId('Microsoft.Logic/workflows', parameters('logicAppName'))]` と完成させることで、正しい Logic App のリソース ID が参照されるようになります。

質問#31 トピック4

Microsoft 365 E5 サブスクリプションをお持ちです。Windows デバイスで PowerShell を使用して Microsoft Purview 監査ログを検索する必要があります。  
  
まず何をすればよいでしょうか？

- A. Microsoft Graph PowerShell モジュールをインストールします。
- B. PowerShell リモート処理を有効にします。
- C. Microsoft Exchange Online PowerShell モジュールをインストールします。
- D. TrustedHosts リストを変更します。

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)  

**解説:**
PowerShellを使用してMicrosoft Purview（旧コンプライアンス）監査ログを検索するための前提条件です。
**「Install the Microsoft Exchange Online PowerShell module」**: 監査ログ検索コマンドレット `Search-UnifiedAuditLog` は、**Exchange Online PowerShell** モジュールに含まれています。これを使用するために、モジュールのインストールとExchange Onlineへの接続が必要です。

質問#32 トピック4
  
Microsoft 365 サブスクリプションをお持ちです。サブスクリプションには、Microsoft Defender for Endpoint にオンボードされている Windows 11 デバイスが 500 台含まれています。  
  
次の要件を満たすように Defender for Endpoint を構成する必要があります。  
  
• セキュリティ運用アナリストがクライアントコンピューターで PowerShell スクリプトを実行できるようにする。  
• クライアントコンピューター上の脅威の自動修復を実行する。

Microsoft Defender XDR ポータルで構成する必要があるエンドポイント設定はどれですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image444.png)

#### **回答エリアの選択**

- **To ensure that the analysts can run PowerShell script（アナリストが PowerShell スクリプトを実行できるようにする）:**
    - **Live Response in Advanced features**（高度な機能のライブ応答）
        
- **To perform the automatic remediation of threats（脅威の自動修復を実行する）:**
    - **Device groups**（デバイス グループ）
        
---
#### **解説**

1. PowerShell スクリプトの実行（Live Response）**

セキュリティ運用アナリストがリモートからデバイスに対して PowerShell スクリプトを実行したり、調査コマンドを走らせたりするには、**ライブ応答（Live Response）**機能を有効にする必要があります。

- **設定箇所:** [設定] > [エンドポイント] > [高度な機能] 内にある「Live Response」および「Live Response unsigned script execution（未署名のスクリプト実行）」をオンにします。
- これにより、アナリストは「ライブ応答セッション」を開始し、ライブラリにアップロードしたスクリプトを実行できるようになります。
    
2. 脅威の自動修復（Automatic Remediation）**

Defender for Endpoint では、デバイスごとにどの程度の自動化を許可するか（完全な自動修復、承認が必要な修復、修復なしなど）を**デバイスグループ**単位で設定します。

- **設定箇所:** [設定] > [エンドポイント] > [デバイス グループ] を作成または編集し、**「自動化レベル（Automation level）」**を「Full - remediate threats automatically（完全 - 脅威を自動的に修復する）」に設定します。
- 特定のデバイスセット（この場合は Windows 11 デバイス）に対してこのレベルを適用することで、検知された脅威が人間の介入なしに自動的に処理されるようになります。

質問#33 トピック4

次の表に示すリソースがあります。
Microsoft Defender for Cloud を使用する Azure サブスクリプションがあります。
  
![](https://img.examtopics.com/sc-200/image454.png)  

VM1 と Server1 を保護するには、Defender for Cloud を使用する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• Advanced Threat Protection と脆弱性評価をサポートする。  
• 各 SQL Server 2022 インスタンスを SQL 仮想マシンとして登録する。  
• 実装と管理の手間を最小限に抑える。  
  
各サーバーに何を展開すればよいでしょうか。回答するには、回答領域から適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image455.png)

**解説:**
### **回答エリアの選択**

- **VM1:** **A VM extension only**
    - （VM 拡張機能のみ）
        
- **Server1:** **Azure Connected Machine agent and VM extension**
    - （Azure Connected Machine エージェントおよび VM 拡張機能）
        
---
### **解説**
1. VM1 (Azure VM) の構成**

VM1 は既に Azure 上の仮想マシンであるため、Azure の管理フレームワーク（Azure Resource Manager）に直接統合されています。

- **SQL 仮想マシンとしての登録:** Azure VM 上の SQL Server を管理・保護するには、**SQL IaaS Agent 拡張機能**（VM 拡張機能の一種）をインストールします。これにより、自動的に「SQL 仮想マシン」リソースとして登録されます。
- **最小限の労力:** Azure VM の場合、追加の外部エージェント（Azure Arc など）をインストールする必要はなく、拡張機能を有効にするだけで「Advanced Threat Protection」や「脆弱性評価」が利用可能になります。
    
2. Server1 (オンプレミス サーバー) の構成**
Server1 はオンプレミス環境にあるため、Azure 以外のリソースを Azure 制御プレーン（ARM）に接続するための仕組みが必要です。

- **Azure Arc の利用:** オンプレミスのサーバーを Azure 上の「SQL 仮想マシン」のように管理するには、まず **Azure Connected Machine エージェント** をインストールして **Azure Arc 対応サーバー** として登録する必要があります。
- **VM 拡張機能の展開:** Azure Arc を通じて、Azure VM と同様に **SQL IaaS Agent 拡張機能** をデプロイすることが可能になります。これにより、オンプレミスの SQL Server インスタンスを Azure ポータルから一元管理し、Defender for Cloud による高度なセキュリティ機能を提供できるようになります。

質問#34 トピック4

contoso.com という Microsoft 365 サブスクリプションがあり、そこには Device1 という Windows 11 デバイスが含まれています。Device1 は Microsoft Defender for Endpoint にオンボードされています。  
  
次の操作を実行します。  
  
• Defender for Endpoint から、次の表に示すデバイスグループを作成します。  
  
![](https://img.examtopics.com/sc-200/image457.png)  
  
• Device2 という Android デバイスを Defender for Endpoint にオンボードします。  
  
各デバイスはどのデバイスグループに追加されますか？ 回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image458.png)

**正解:** ![](https://img.examtopics.com/sc-200/image459.png)

**解説:**
デバイスグループへの自動割り当て（ランク順）に関する問題です。
Defender for Endpointのデバイスグループは、**上から順に評価（ランク1が最優先）**され、最初に条件に合致したグループにデバイスが割り当てられます。

デバイス 1 = グループ 2 のみ - 最初に一致するルールが優先され、グループ 2 はグループ 3 よりも優先順位が高くなります デバイス 2 = グループ 1 のみ

