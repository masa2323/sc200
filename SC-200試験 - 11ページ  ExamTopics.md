質問#35 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。  
  
セキュリティ アラート ビューをフィルター処理して、以下のアラートを表示する必要があります。  
  
• 通常とは異なるユーザーによるキー コンテナーへのアクセス  
• 通常とは異なる場所からのログオン  
• あり得ない移動アクティビティ  
  
どの重大度を使用すればよいですか？

- A. Informational
- B. Low
- C. Medium
- D. High

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
特定のアラートタイプ（通常とは異なるユーザー/場所/移動）をフィルタリングするための重大度設定です。
**「Medium (中)」**: 「Unusual user accessed a key vault（通常とは異なるユーザーによるKey Vaultへのアクセス）」や「Impossible travel activity（あり得ない移動）」といった、アノマリー（異常）検知ベースのアラートは、通常「Medium」重大度に分類されます。
High（高）はマルウェアの実行など、より確実で即時性の高い脅威に割り当てられます。

質問#36 トピック2

サードパーティのセキュリティ情報イベント管理（SIEM）ソリューションを使用して、Microsoft Defender for Cloud のアラートを確認する予定です。MITRE ATT&CK の権限昇格戦術の使用を示すアラートを見つける必要があります。  
  
どの JSON キーを検索すればよいでしょうか？

- A. Description
- B. Intent
- C. ExtendedProperies
- D. Entities

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
SIEMでDefender for Cloudアラートを取り込む際、MITRE ATT&CKの戦術（Privilege Escalationなど）を識別するために使用されるJSONキーです。
**「Intent」**: Defender for CloudのアラートJSONスキーマには `Intent` というプロパティがあり、ここに攻撃の意図（Kill Chain Intent）としてMITRE ATT&CKの戦術名（例: "Privilege Escalation"）がマッピングされます。
`ExtendedProperties` にも詳細情報が含まれますが、戦術の分類として標準的に使用されるトップレベルのフィールドは `Intent` です。

質問#37 トピック2

オンプレミスサーバーが50台あります。Microsoft Defender for Cloudを使用するAzureサブスクリプションがあります。Defender for Cloudの展開では、Microsoft Defender for Serversと自動プロビジョニングが有効になっています。  
  
オンプレミスサーバーをサポートするには、Defender for Cloudを構成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 脅威と脆弱性の管理を提供する。  
• データ収集ルールをサポートする。  
  
これらの3つのアクションのうち、順番に実行する必要があるのはどれですか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序で並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image131.png)

**正解:** ![](https://img.examtopics.com/sc-200/image418.png)

**解説:**
この構成の鍵は、オンプレミスサーバーを **Azure Arc** 対応サーバーとして定義し、最新の監視エージェントを導入することにあります。

1. スクリプトの生成と Arc 接続
オンプレミスリソースを Azure の管理下に置くには、まず Azure Arc を使用する必要があります。ポータルからインストールスクリプトを生成し、各サーバーで実行することで、**Azure Connected Machine エージェント**がインストールされます。これにより、オンプレミスサーバーが Azure 上のリソース（Arc サーバー）として認識されるようになります。

2. データ収集ルール (DCR) のサポート
要件にある「データ収集ルール (DCR)」をサポートするためには、従来の Log Analytics エージェントではなく、**Azure Monitor エージェント (AMA)** をインストールする必要があります。

- **Log Analytics agent (旧称 MMA)**: DCR をサポートしておらず、現在は非推奨（廃止予定）に向かっています。
    
- **Azure Monitor agent (AMA)**: DCR を使用して、どのデータを収集し、どこに送信するかをきめ細かく制御できます。
    
3. 脅威と脆弱性の管理 (TVM)
Microsoft Defender for Servers（プラン1またはプラン2）が有効で、サーバーが Azure Arc に接続されている場合、Microsoft Defender for Endpoint の拡張機能が自動的にデプロイされます。これにより、要件である「脅威と脆弱性の管理（TVM）」機能が提供されます。

まとめ：なぜこの 3 つか？

- **Azure Connected Machine agent**: オンプレミスを Azure に「繋ぐ」ために必須。
- **Azure Monitor agent**: 「データ収集ルール (DCR)」に対応するために必須。
- **Log Analytics agent**: DCR をサポートしないため、今回の要件では選択しません。

質問#38 トピック2
  
Microsoft Defender for Cloud を使用する Azure サブスクリプションがあり、app1 という Azure ロジック アプリが含まれています。  
  
特定の Defender for Cloud セキュリティ アラートが生成されたときに、app1 が起動するようにする必要があります。Azure Resource Manager (ARM) テンプレートをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image133.png)

**解説:**
このテンプレートは、Defender for Cloud の「ワークフロー自動化（Workflow Automation）」リソースを定義しています。

1. リソースタイプ ("Microsoft.Security/automations")

- **Microsoft.Security/automations**: これは Microsoft Defender for Cloud におけるワークフロー自動化リソースを定義するための正しいリソース種類です。これにより、特定のアラートや推奨事項をトリガーとして、後続のアクションを紐付けることができます。
- **Microsoft.Automation/automationAccounts**: Azure Automation アカウントを定義するためのもので、今回のワークフロー自動化の定義には使用しません。
- **Microsoft.Logic/workflows**: これはロジックアプリ本体を定義するための種類です。
    
2. コールバック URL の取得 (triggers)

- ロジックアプリを外部から（この場合は Defender for Cloud から）呼び出すには、そのロジックアプリの「トリガー」エンドポイントの URL が必要です。
- `listCallbackURL` 関数を使用して URL を動的に取得する場合、対象となるリソースパスの階層として、ロジックアプリ名の後に **triggers** を指定する必要があります（例：`Microsoft.Logic/workflows/triggers`）。
- テンプレート内の `'manual'` という記述は、ロジックアプリ側のトリガー名（通常は HTTP 要求の受信時トリガーなど）を指しています。

質問#39 トピック2

サポートされているすべてのリソースタイプに対してMicrosoft Defender for Cloudが有効になっているAzureサブスクリプションがあります。LA1 というAzureロジックアプリを作成します。LA1 を使用して、Defender for Cloudで検出されたセキュリティリスクを自動的に修復する予定です。Defender for CloudでLA1をテストする必要があります。  
  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正しい選択ごとに1ポイントが加算されます。  
  
![](https://img.examtopics.com/sc-200/image159.png)

**正解：**

**Set the LA1 trigger to:**
- **When a Defender for Cloud Recommendation is created or triggered**

**Trigger the execution of LA1 from:**
- **Recommendations**

**理由：**

1. **トリガーの設定について：**
    - ドキュメントには、Logic Appデザイナーで以下のDefender for Cloudトリガーがサポートされていると記載されています：
        - "When a Microsoft Defender for Cloud recommendation is created or triggered"
        - "When a Defender for Cloud Alert is created or triggered"
        - "When a Defender for Cloud regulatory compliance assessment is created or triggered"
    - 質問では「セキュリティリスクを自動的に修復する」とあります。セキュリティリスクの修復は**Recommendations（推奨事項）**に基づいて行われます
2. **実行のトリガー場所について：**
    
    - ドキュメントの「Manually trigger a logic app」セクションに明確に記載されています：
    
    > "You can also manually run logic apps when you view any security alert or recommendation. To manually run a logic app, open an alert or a recommendation, and then select **Trigger logic app**."
    
    - つまり、Logic Appをテストするには：
        - **Recommendations**（推奨事項）を開く
        - または **Security alerts**（セキュリティアラート）を開く
        - そこから「Trigger logic app」を選択する
3. **なぜRecommendationsが正解か：**
    - セキュリティリスクの「修復」は推奨事項（Recommendations）に基づいて行われます
    - アラートは脅威の検出であり、推奨事項は設定の改善や脆弱性の修正を示します
    - 自動修復の目的に最も適しているのはRecommendationsです

**不正解の選択肢：**

- "When a response to a Defender for Cloud alert is triggered" - これはレガシートリガーで、ドキュメントでは使用しないよう推奨されています
- "Security alerts" - アラートからもトリガーできますが、「修復」という目的にはRecommendationsの方が適切です
- "Regulatory compliance standards" - コンプライアンス評価からもトリガーできますが、一般的なセキュリティリスクの修復にはRecommendationsが適切です

質問#40 トピック2

Microsoft Defender for Cloud が有効になっている Azure サブスクリプションをお持ちです。Windows 10 を実行し、Log Analytics エージェントがインストールされた仮想マシンがあります。  
  
この仮想マシンに対して、アラートを生成する攻撃をシミュレートする必要があります。  
  
まず何をすべきでしょうか？

- A. Log Analytics トラブルシューティング ツールを実行します。
- B. 実行ファイルをコピーし、ファイル名を ASC\_AlertTest\_662jfi039N.exe に変更します。
- C. Microsoft Monitoring Agent の設定を変更します。
- D. MMASetup 実行可能ファイルを実行し、--foo 引数を指定します。

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
Windows VMでDefender for Cloudのアラート生成攻撃をシミュレートする標準的な方法です。
**「実行ファイルをコピーし、ファイル名を ASC_AlertTest_662jfi039N.exe に変更する」**: 正規の実行ファイル（cmd.exeやcalc.exeなど）をコピーし、この特定の名前（`ASC_AlertTest_662jfi039N.exe`）に変更して実行すると、Defender for Cloudはこれをテスト用のアクティビティとして検知し、テストアラートを生成します。

質問#41 トピック2

新しいAzureサブスクリプションを作成し、Azure Monitorのログ収集を開始します。Windows Serverを実行しているAzure仮想マシンに悪意のあるファイルが存在する場合、Microsoft Defender for Cloudがアラートをトリガーすることを検証する必要があります。  
  
どの3つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
  
注：回答の選択肢は複数選択可能です。正しい順序を選択した場合、ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image161.png)

**正解:** ![](https://img.examtopics.com/sc-200/image420.png)

**解説:**
この手順は、Microsoft が提供する「アラートの検証（シミュレーション）」の公式ドキュメントに基づいた標準的な検証フローです。

1. 強化されたセキュリティ機能の有効化
Microsoft Defender for Cloud の無料版（基本機能）では、高度な脅威検出機能が提供されません。サーバーの脅威を検出するには、**Microsoft Defender for Servers（強化されたセキュリティ機能）** をサブスクリプション レベルで有効にする必要があります。

2. 検証用ファイルの配置と名前変更
Defender for Cloud には、特定のファイル名を検知するとテスト用のアラートを生成する仕組みがあります。任意の実行ファイル（calc.exe など）を VM にコピーし、ファイル名を **`ASC_AlertTest_662jfi039N.exe`** に変更します。この文字列は Microsoft がシミュレーション用に予約している固有の ID です。

3. 実行と引数の指定
ファイル名を変更しただけではアラートがトリガーされない場合があります。コマンド プロンプトを開き、作成したファイルを実行します。その際、適当な引数（例：`ASC_AlertTest_662jfi039N.exe -arg`）を指定して実行することで、不審なプロセスの実行として Defender が検知し、セキュリティ アラートがトリガーされます。

補足
- **メールのしきい値設定**: 「アラート通知」を受信するための設定であり、アラートそのものを「トリガー」させるための手順ではないため、今回の回答には含めません。
    
- **ファイル名の重要性**: `AlertTest.exe` などの一般的な名前では、この特定のテスト ロジックは動作しません。

質問#42 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションがあり、Windows Server を実行する仮想マシンが 100 台含まれています。  
  
これらの仮想マシンからイベントデータを収集するように Defender for Cloud を構成する必要があります。このソリューションでは、管理の手間とコストを最小限に抑える必要があります。  
  
実行すべきアクションは 2 つあります。正解はそれぞれソリューションの一部です。  
  
注: 正解は 1 つにつき 1 ポイントです。

- A. Defender for Cloud によって作成されたワークスペースから、データ収集レベルを「共通」に設定します。
- B. Microsoft Endpoint Manager 管理センターから、自動登録を有効にします。
- C. Azure ポータルから、Azure Event Grid サブスクリプションを作成します。
- D. Defender for Cloud によって作成されたワークスペースから、データ収集レベルをすべてのイベントに設定します。
- E. Azure ポータルの Defender for Cloud から、仮想マシンの自動プロビジョニングを有効にします。

**正解:** AE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
多数のVM (100台) からイベントデータを収集し、コストと管理の手間を抑える構成です。

1. **E. AzureポータルのDefender for Cloudから、仮想マシンの自動プロビジョニングを有効にします**: エージェント（Log AnalyticsエージェントまたはAMA）のインストールを自動化し、管理の手間を削減します。
2. **A. Defender for Cloudによって作成されたワークスペースから、データ収集レベルを「共通 (Common)」に設定します**: 「All events」はすべてのセキュリティイベントを収集するためデータ量が膨大になりコストがかかります。「Common」は監査に必要な標準的なイベントセットであり、コスト対効果の高い推奨設定です。

質問#43 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションがあり、User1 というユーザーがいます。User1 が Microsoft Defender for Cloud のセキュリティポリシーを変更できるようにする必要があります。このソリューションでは、最小権限の原則を適用する必要があります。User1 にはどのロールを割り当てる必要がありますか？

- A. セキュリティオペレーター
- B. セキュリティ管理者
- C. オーナー
- D. 貢献者

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
Defender for Cloudのセキュリティポリシーを変更できる最小特権のロールです。
**「セキュリティ管理者 (Security Admin)」**: セキュリティポリシーの表示と編集（更新）、アラートや推奨事項の管理が可能です。
「セキュリティ閲覧者 (Security Reader)」(A) は表示のみ。「所有者 (Owner)」(C) や「貢献者 (Contributor)」(D) も変更可能ですが、ポリシー管理以外の多くの権限（リソースの作成・削除など）を持つため、最小特権の原則に反します。

質問#44 トピック2

AzureサブスクリプションにUser1というユーザーがいます。User1にはAzure Active Directory Premium Plan 2のライセンスが割り当てられています。  
  
過去90日間にUser1のIDが侵害されたかどうかを特定する必要があります。  
  
どのようなツールを使用すればよいでしょうか？

- A. リスク検出レポート
- B. 危険なユーザーの報告
- C. アイデンティティセキュリティスコアの推奨事項
- D. 危険なサインインレポート

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/11/#)  

**解説:**
過去90日間にIDが侵害されたかどうかを特定するツールです。
**「危険なユーザーの報告 (Risky users report)」**: このレポートは、リスクレベル（高/中/低）やリスクの状態（修復済み、無視など）を含む、リスクのあるユーザーの履歴を提供します。ユーザーが「侵害された (Compromised)」と判定された履歴を確認するのに適しています。
「リスク検出レポート (Risk detection report)」(A) も90日間のデータを提供しますが、こちらは個々のリスクイベント（「匿名のIPアドレスからのサインイン」など）のリストであり、ユーザー全体として侵害されたかどうかの判断には「危険なユーザー」レポートが集約的で適しています。
