質問5 トピック2

新しいAzureサブスクリプションにLinux仮想マシンをプロビジョニングします。Azure  
Defenderを有効にし、仮想マシンをAzure Defenderにオンボードします。  
仮想マシンへの攻撃がAzure Defenderでアラートをトリガーすることを確認する必要があります。  
仮想マシンで実行する必要がある2つのBashコマンドはどれですか？正解はそれぞれ解答の一部です。  
注：正解は1つにつき1ポイントです。  

- A. cp /bin/echo ./asc\_alerttest\_662jfi039n
- B. ./alerttest eicarパイプのテスト
- C. cp /bin/echo ./alerttest
- D. ./asc\_alerttest\_662jfi039n eicarパイプのテスト

**正解：** AD [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/8/#)  

**解説:**
Microsoft Defender for Endpoint (Linux用) のオンボードとテストアラートの生成手順です。

1. **A. `cp /bin/echo ./asc_alerttest_662jfi039n`**: テスト用の実行ファイルを作成します。`echo` コマンドを特定のファイル名（`asc_alerttest_662jfi039n`）としてコピーします。Defenderはこのファイル名を検知してアラートをトリガーするように設計されています。
2. **D. `./asc_alerttest_662jfi039n eicar pipe test`**: コピーしたファイルを実行し、引数として特定の文字列を渡すことで、シミュレートされた攻撃として検知させます。
※EICARテストファイル自体を作成する方法もありますが、Defender for Cloud (Azure Defender) の文脈では、この特定のファイル名を利用したテスト手法がドキュメントで案内されています。

質問6 トピック2

sub1 という名前の Azure サブスクリプションを作成します。sub1 内に、workspace1 という名前の Log Analytics ワークスペースを作成します。Azure Security Center を有効にし、Security Center が workspace1 を使用するように構成します。workspace1 にレポートする Azure 仮想マシンからセキュリティ イベント ログを収集する必要があります。
どうすればよいでしょうか。  

- A. セキュリティセンターからデータ収集を有効にする
- B. サブ1でプロバイダーを登録します。
- C. セキュリティ センターからワークフロー自動化を作成します。
- D. ワークスペース1 でワークブックを作成します。

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/8/#)  

**解説:**
Security Center (Defender for Cloud) で特定のワークスペースを使用するように構成した後、VMからのセキュリティイベントログ収集を開始するには、**「Security Centerからデータ収集を有効にする (Enable data collection from Security Center)」** 必要があります。
具体的には、Microsoft Defender for Serversプランを有効にし、自動プロビジョニング設定でLog Analyticsエージェントのインストールとワークスペースへの接続を構成します。「データ収集」設定内で、収集するイベントのレベル（All events, Common, Minimalなど）を選択します。

質問7 トピック2

新しいAzureサブスクリプションを作成し、Azure Monitorのログ収集を開始します。  
疑わしいIPアドレスからのAzure仮想マシンへのサインインに関連する潜在的な脅威を検出するために、Azure Security Centerを構成する必要があります。ソリューションでは、構成を検証する必要があります。
3 つのアクションのうち、どのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序で並べ替えてください。  
選択して配置：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0005900001.png)  

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0006000001.png)

**解説:**
Azure Security Centerのアラート構成を検証する手順です。

1. **実行可能ファイルをコピーする (Copy the executable)**: ユーザーのデバイス上で、任意の無害な実行ファイル（例: calc.exeなど）をコピーします。
2. **ファイルの名前を変更する (Rename the file)**: コピーしたファイルの名前を、Security Centerがテスト用として認識する特定の名前（例: `ASC_AlertTest_662jfi039n.exe`）に変更します。
3. **ファイルを実行する (Run the file)**: 名前を変更したファイルを実行します。引数を付ける手順もありますが、まずはこの実行アクションが基本です。これにより、Security Centerは脅威を検知し、構成されたアラートが正しく機能しているかを検証できます。

質問8 トピック2

会社ではAzure Security CenterとAzure Defenderを使用しています。  
  
会社のセキュリティ運用チームから、セキュリティアラートに関するメール通知が届かないと言われました。  
メール通知を有効にするには、Security Centerでどのような設定をすればよいでしょうか？  

- A. セキュリティソリューション
- B. セキュリティポリシー
- C. 価格と設定
- D. セキュリティアラート
- E. アズールディフェンダー

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/8/#)  

**解説:**
Azure Security Center (Defender for Cloud) でセキュリティアラートのメール通知設定を行う場所は、**「環境設定 (Environment settings)」** ブレード（以前の名称では「価格と設定 (Pricing & settings)」）です。
対象のサブスクリプションを選択し、設定メニューから **「メール通知 (Email notifications)」** を選択することで、通知先のメールアドレス、通知するアラートの重大度、サブスクリプション所有者への通知有無などを構成できます。

質問9 トピック2

AzureとGoogle Cloudにリソースがあります。Google Cloud Platform (GCP)のデータをAzure Defenderに取り込む必要があります。  
これらのアクションはどの順序で実行すればよいですか？ 回答するには、アクションリストからすべてのアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
選択して配置してください。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0006100001.png)  

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0006200001.png)

**解説:**
GCP (Google Cloud Platform) プロジェクトをAzure Defender (Defender for Cloud) にオンボードし、監査ログを取り込む手順です。

1. **GCPセキュリティコマンドセンターで、Security Health Analyticsを有効にする**: GCP側のセキュリティ検出機能を有効にします。
2. **GCP Cloud Consoleで専用のサービスアカウントを作成する**: Azure DefenderがGCPリソースにアクセスし、ログを読み取るための権限を持つサービスアカウントを作成します。
3. **Azure Security Centerで、GCPコネクタを追加する**: Defender for Cloudポータルで「クラウドコネクタ」を選択し、GCPアカウントを接続します。この際、作成したサービスアカウントの認証情報を使用します。
（※手順は更新されることがありますが、コネクタ作成と権限付与（サービスアカウント）は必須ステップです。）

質問10 トピック2

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。質問セットによっては、複数の正解が存在する場合もあれば、正解が存在しない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Azure Security Center を使用しています。Security  
Center でセキュリティアラートを受信しました。Security Center でアラートを解決するための推奨事項を確認する必要があります。  
解決策: 規制コンプライアンスからレポートをダウンロードします。  
これは目標を達成していますか?  

- A. はい
- B. いいえ

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/8/#)  

**解説:**
アラートを解決するための具体的な推奨事項を確認する場合、**「規制コンプライアンスレポート」** をダウンロードするのは非効率であり、直接的な解決策へのリンクが含まれているとは限りません。
アラートの解決には、アラート詳細ページの「脅威の軽減 (Mitigate the threat)」や「将来の攻撃を防ぐ (Prevent future attacks)」セクション、またはSecurity Centerの「推奨事項」ブレードを直接確認するのが適切です。

質問11 トピック2

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Azure Security Center を使用しています。Security  
Center でセキュリティ アラートを受信しました。Security Center でアラートを解決するための推奨事項を確認する必要があります。  
解決策: \[セキュリティ アラート\] からアラートを選択し、\[アクションの実行\] を選択して、\[脅威の軽減\] セクションを展開します。  
これで目標は達成されましたか?  

- A. はい
- B. いいえ

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/8/#)  

**解説:**
セキュリティアラートの解決策として、アラート詳細から **「脅威の軽減 (Mitigate the threat)」** セクション（または「アクションの実行 (Take action)」）を展開して確認する方法は適切です。
ここには、特定された脅威に対処するための手動手順や、関連するリソースへのリンク、自動修復オプション（利用可能な場合）などが提示されます。

質問12 トピック2

Azure サブスクリプションをお持ちで、サポート対象のすべてのリソースタイプに対して Azure Defender が有効になっています。  
サードパーティのセキュリティ情報イベント管理 (SIEM) ソリューションから高重大度アラートを取得できるように、アラートの継続的なエクスポートを構成する必要があります。  
アラートをどのサービスにエクスポートすればよいですか？  

- A. Azure Cosmos DB
- B. Azure イベント グリッド
- C. Azure イベントハブ
- D. Azure データレイク

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/8/#)  

**解説:**
サードパーティのSIEMソリューションに高重大度アラートを継続的かつリアルタイムに近い形でエクスポートするには、**「Azure Event Hubs」** を使用します。
Azure Defender (Security Center) の「継続的エクスポート (Continuous Export)」機能で、エクスポート先としてEvent Hubを選択し、ストリーミングデータとしてSIEMに送信します。多くのSIEM製品はEvent Hubからのデータ取り込みをサポートしています。

質問13 トピック2

Azure Defender for Key Vault のアラートに対応する責任があります。  
アラートの調査中に、Tor 出口ノードから Key Vault への不正アクセス試行を発見しました。  
この脅威を軽減するには、どのような設定を行う必要がありますか？  

- A. Key Vault ファイアウォールと仮想ネットワーク
- B. Azure Active Directory (Azure AD) のアクセス許可
- C. キー コンテナーのロールベースのアクセス制御 (RBAC)
- D. キーコンテナーのアクセスポリシー設定

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/8/#)  

**解説:**
Tor出口ノードなどの不審なIPアドレスからのKey Vaultへの不正アクセス試行を軽減する最善の方法は、**「Key Vaultファイアウォールと仮想ネットワーク (Key Vault firewalls and virtual networks)」** を構成することです。
ファイアウォールを有効にし、アクセスを許可する特定の仮想ネットワークや信頼できるIPアドレス範囲のみに制限することで、Torノードを含むインターネット上の任意のIPからのアクセスを遮断できます。

質問14 トピック2

Azure Resource Manager テンプレートを使用して、Azure Security Center が特定のセキュリティアラートを受信した際に自動修復をトリガーするワークフロー自動化を作成する必要があります。  
必要な Azure リソースをプロビジョニングするテンプレートの部分をどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正解は 1 点です。  

![](https://www.examtopics.com/assets/media/exam-media/04261/0006600001.png)  

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0006700001.png)

**解説:**
ARMテンプレートでワークフロー自動化（Logic Appのトリガー）を定義する設定です。

1. **`type`: `Microsoft.Security/automations`**: Security Centerのオートメーションリソースタイプを指定します。
2. **`actionType`: `LogicApp`**: アクションの種類としてLogic Appを指定します。
3. **`trigger`: `Alert`**: トリガー条件として「アラート（Alert）」を指定します（特定のセキュリティアラート受信時に発火するため）。`State`Change`トリガーもありますが、アラート受信そのものをトリガーにする場合はAlertが一般的です。
