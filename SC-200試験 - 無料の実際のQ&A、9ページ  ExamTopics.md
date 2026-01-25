---
title: "SC-200試験 - 無料の実際のQ&A、9ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/9/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問15 トピック2

Log Analytics ワークスペースを含む Azure サブスクリプションをお持ちです。Azure  
リソースに対して、ジャストインタイム (JIT) VM アクセスとネットワーク検出を有効にする必要があります。Azure  
Defender はどこで有効にすればよいですか？  

- A. サブスクリプションレベル
- B. ワ​​ークスペースレベル
- C. リソースレベル

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)   [議論   16](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)  

**解説:**
JIT (Just-in-Time) VMアクセスとネットワーク検出を有効にするには、**「サブスクリプションレベル (Subscription level)」** でAzure Defender (Defender for Servers) を有効にする必要があります。
個別のリソースやワークスペース単位ではなく、サブスクリプションまたは管理グループ単位でDefenderプラン（特にServersプラン）をオンにすることで、その配下にあるVMに対してJITアクセスやアダプティブネットワークハードニングなどの高度な保護機能が利用可能になります。

*コミュニティ投票の配分*

A（100％）

質問16 トピック2

Azure Defenderを使用しています。  
機密情報を含むAzure Storageアカウントを所有しています。  
不審なIPアドレスから誰かがストレージアカウントにアクセスした場合、PowerShellスクリプトを実行する必要があります。  
実行すべきアクションは2つあります。正解はそれぞれ解決策の一部を示しています。  
注：正解は1つにつき1ポイントです。  

- A. Azure Security Center からワークフロー自動化を有効にします。
- B. 手動トリガーを持つ Azure ロジック アプリを作成します。
- C. Azure Security Center アラート トリガーを持つ Azure ロジック アプリを作成します。
- D. HTTP トリガーを持つ Azure ロジック アプリを作成します。
- E. Azure Active Directory (Azure AD) からアプリ登録を追加します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)

**正解:** AC [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)  

**解説:**
不審なIPからのアクセス時にPowerShellスクリプトを自動実行するソリューションです。

1. **C. Azure Security Center アラート トリガーを持つ Azure ロジック アプリを作成します**: セキュリティアラート（「不審なIPアドレスからのアクセス」など）をトリガーとして動作するLogic Appを作成します。このLogic App内で、PowerShellスクリプトを実行するアクション（Azure Automation Runbookの呼び出しやAzure Functionsの実行など）を定義します。
2. **A. Azure Security Center からワークフロー自動化を有効にします**: 作成したLogic Appを、特定のアラート条件が発生したときに自動的に起動するように、Defender for Cloud側で「ワークフロー自動化」設定を行います。

*コミュニティ投票の配分*

AC（100％）

質問17 トピック2

ホットスポット -  
2つの仮想マシン（vm1とvm2）を含むAzureサブスクリプションのセキュリティ体制を管理しています。Azure  
Security Centerのセキュリティスコアは、Security Centerの図に表示されます（「Security Center」タブをクリックしてください）。Azure  
![](https://www.examtopics.com/assets/media/exam-media/04261/0007000001.jpg)  
Policyの割り当ては、Policiesの図に示されているように構成されています（「Policies」タブをクリックしてください）。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0007100001.jpg)  
以下の各項目について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
注：正しい選択は1点です。  
ホットエリア：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0007200001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)   [議論   13](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0007200002.png) 参照:  

**解説:**
セキュリティスコアとポリシー設定に基づく判断です。

1. **vm1**: ポリシー「Secure management ports (管理ポートをセキュリティで保護する)」が「Unhealthy (異常)」状態です。これは通常、JITアクセスが有効になっていないか、NSGで管理ポート（RDP/SSH）が制限なしに開放されていることを意味します。したがって、管理ポートへの無制限のアクセスを制限する必要があります => **「はい」**。
2. **vm2**: 同ポリシーが「Healthy (正常)」状態です。これは要件を満たしていることを意味します => **「いいえ」**。
3. **ネットワークセキュリティグループ (NSG)**: JIT VMアクセスや管理ポートの保護を実装するには、NSG（またはAzure Firewall）が必須です。セキュリティポリシーの推奨事項に従い、ポートを閉じてJIT経由でのみ開くように構成するため、NSGを作成・構成する必要があります => **「はい」**。

<https://techcommunity.microsoft.com/t5/azure-security-center/security-control-restrict-unauthorized-network-access/ba-p/1593833> <https://techcommunity.microsoft.com/t5/azure-security-center/security-control-secure-management-ports/ba-p/1505770>

質問18 トピック2

ドラッグ＆ドロップ -  
お使いの環境に影響を与える新たな共通脆弱性識別子（CVE）の脆弱性について通知を受けました。  
文書化されたアクティブなエクスプロイトが存在する場合、Microsoft Defender セキュリティ センターを使用して、影響を受けるシステムの担当チームに修復を依頼する必要があります。  
どの 3 つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
選択して配置:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0007300001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0007400001.png) 参考:  

**解説:**
Defender Vulnerability Management (MDVM) を使用して脆弱性の修復を依頼するプロセスです。

1. **セキュリティに関する推奨事項を選択する**: まず、対処すべき特定の脆弱性に関する推奨事項（セキュリティ・レコメンデーション）を選択します。
2. **修復をリクエストする (Request remediation)**: 推奨事項の詳細画面から「修復オプション」を選択し、ITチームへのチケット作成（Microsoft Intune接続など）を行います。
3. **修復リクエストの設定を構成する**: チケットの優先度、期日、メモなどを入力・選択し、リクエストを確定します。このアクションにより、IT管理者のコンソール（Endpoint Manager等）にタスクが作成されます。

<https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/microsoft-defender-atp-remediate-apps-using-mem/ba-p/1599271>

質問19 トピック2

Azure Security Center を使用しています。Security  
Center でセキュリティアラートを受信しました。Security  
Center でアラートを解決するための推奨事項を確認する必要があります。  
どうすればよいでしょうか？  

- A. 「セキュリティ アラート」からアラートを選択し、「アクションを実行」を選択して、「将来の攻撃を防ぐ」セクションを展開します。
- B. \[セキュリティ アラート\] から \[アクションの実行\] を選択し、\[脅威の軽減\] セクションを展開します。
- C. 規制コンプライアンスからレポートをダウンロードします。
- D. 「推奨事項」から CSV レポートをダウンロードします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)   [議論   42](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)  

**解説:**
アラートを解決するための推奨事項を確認するための直接的な方法は、アラートの詳細ページからアクションを取ることです。
**「[セキュリティアラート] から [アクションの実行] を選択し、[脅威の軽減 (Mitigate the threat)] セクションを展開します」**: これが正解です。ここには、現在のアラートに対処するための具体的な手順（手動または自動）が表示されます。
「将来の攻撃を防ぐ (Prevent future attacks)」セクション（選択肢A）は、同様の攻撃が再発しないように環境を強化するための推奨事項であり、現在のアラート自体の解決（Mitigation）とは区別されます。

*コミュニティ投票の配分*

B（73％）

A（27％）

質問#20 トピック2

Azure Security Center には、テスト用に使用されている 10 台の仮想マシンに対する抑制ルールが設定されています。これらの仮想マシンは Windows Server を実行しています。  
これらの仮想マシンで発生した問題のトラブルシューティングを行っています。Security  
Center で、過去 5 日間にこれらの仮想マシンによって生成されたアラートを確認する必要があります。  
どうすればよいでしょうか？  

- A. 抑制ルールのルール有効期限を変更します。
- B. 抑制ルールの状態を「無効」に変更します。
- C. セキュリティアラートページのフィルターを変更します。
- D. 仮想マシン上の Windows イベント ログを表示します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)   [議論   52](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)  

**解説:**
抑制ルール（Suppression rules）が適用されているアラートは、デフォルトのビューでは非表示になります。これらを確認するにはフィルタ設定を変更する必要があります。
**「セキュリティアラートページのフィルターを変更します」**: アラート一覧ページにはフィルタ機能があり、通常は「アクティブ」なアラートのみが表示されています。フィルタ条件でステータスに **「破棄済み (Dismissed)」** を含めることで、抑制ルールによって自動的に破棄されたアラートを表示し、確認することができます。（※抑制ルールはアラートを「Dismissed」状態にします。）
抑制ルール自体を無効化（B）すると、今後のアラートは表示されますが、過去に抑制されたものが自動的にアクティブに戻るわけではないため、過去のアラートを確認するにはフィルタ変更が適切です。

*コミュニティ投票の配分*

C（77％）

B（23％）

質問#21 トピック2

ホットスポット -  
アプリケーション開発中に複数のAzure FunctionsアプリからアクセスされるAzure Storageアカウントがあります。  
このストレージアカウントのAzure Defenderアラートを非表示にする必要があります。  
抑制ルールでは、どのエンティティタイプとフィールドを使用すべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
注：正解は1つにつき1ポイントです。  
ホットエリア：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0007600001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0007700001.jpg) 参照:  

**解説:**
Azure Storageアカウントに対するアラートを抑制するための設定です。

1. **Entities (エンティティ)**: ルールの適用範囲を指定します。特定のストレージアカウントを対象とするため、**「Azure Storage account」** を選択します。
2. **Field (フィールド)**: エンティティを特定するための識別子です。**「ResourceId」** （またはResource IDの一部）を指定して、特定のストレージアカウントを一意に識別し、ルールを適用します。

<https://techcommunity.microsoft.com/t5/azure-security-center/suppression-rules-for-azure-security-center-alerts-are-now/ba-p/1404920>

質問#22 トピック2

Azureサブスクリプションを作成します。  
そのサブスクリプションでAzure Defenderを有効にします。  
オンプレミスのコンピューターを保護するには、Azure Defenderを使用する必要があります。オンプレミス  
のコンピューターでは、どのような対策を講じるべきでしょうか？  

- A. Log Analytics エージェントをインストールします。
- B. Dependency Agent をインストールします。
- C. Hybrid Runbook Worker ロールを構成します。
- D. Connected Machine エージェントをインストールします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)   [議論   42](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)  

**解説:**
オンプレミスのコンピューターをAzure Defender (Defender for Cloud) で保護する最初のステップとして推奨されるのは、Azure Arcへのオンボードです。
**「Connected Machineエージェントをインストールします」**: これにより、オンプレミスサーバーが「Azure Arc対応サーバー」としてAzureリソースのように管理できるようになります。Defender for Serversプランを利用するためには、まずArcに接続することが前提となります（その後、Log AnalyticsエージェントやAzure Monitorエージェントが拡張機能としてデプロイされ、ログ収集を行います）。
Log Analyticsエージェント（A）を直接インストールする方法も以前は一般的でしたが、現在のAzure Defenderのカバレッジと管理機能をフルに活用するには、Connected MachineエージェントによるArc化が標準的なアプローチです。

*コミュニティ投票の配分*

D（63％）

A（37％）

質問#23 トピック2

セキュリティ管理者は、ストレージアカウントへのマルウェアのアップロードやブルートフォース攻撃の成功の可能性といったアクティビティについて、Azure Defender からメールアラートを受け取ります。  
マルウェア対策アクションの失敗や疑わしいネットワークアクティビティといったアクティビティについては、メールアラートは受け取りません。アラートは  
Azure Security Center に表示されます。  
セキュリティ管理者がすべてのアクティビティについてメールアラートを受信できるようにする必要があります。Security  
Center の設定では、どのような構成を行う必要がありますか？  

- A. 電子メール通知の重大度レベル
- B. クラウドコネクタ
- C. Azure Defenderプラン
- D. 脅威検出の統合設定

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)  

**解説:**
デフォルトでは、高重大度（High severity）のアラートのみがサブスクリプション所有者にメール通知される設定になっていることが多いです。
中・低重大度のアラート（「マルウェア対策アクションの失敗」などは重大度が低い場合があります）も含めてメールを受信するには、Security Centerの **「電子メール通知 (Email notifications)」** 設定で、通知対象の **「重大度レベル (Severity level)」** を変更する必要があります（例: 「High」から「Low」または「Medium」に下げる）。

*コミュニティ投票の配分*

A（100％）

質問#24 トピック2

ドラッグ＆ドロップ -  
Azure Functions アプリがあり、Azure Security Center で通常のアクティビティに対して毎日数千件のアラートが生成されます。Security  
Center でこれらのアラートを自動的に非表示にする必要があります。Security  
Center で、どの 3 つの操作を順番に実行すればよいでしょうか。正解はそれぞれ解答の一部です。  
注: 正解は 1 点です。  
選択して配置:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0008000001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/9/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0008100001.jpg) 参照:  

**解説:**
通常のアクティビティによる大量のアラートを自動的に非表示にするには、抑制ルールを作成します。

1. **「セキュリティアラート」からアラートを選択する**: まず、抑制したい対象のアラート（ノイズとなっているアラート）を選択します。
2. **「アクションの実行」を選択する**: アラートの詳細画面からアクションメニューを開きます。
3. **「抑制ルールを作成する」を選択する**: 「類似のアラートを抑制する」オプションからルール作成画面へ進み、条件を定義してルールを保存します。

<https://techcommunity.microsoft.com/t5/azure-security-center/suppression-rules-for-azure-security-center-alerts-are-now/ba-p/1404920>

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/8/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 9 ページ目を表示しています。

410問 中**81 - 90** 問を表示
