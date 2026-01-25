---
title: "SC-200試験 - 無料の実際のQ&A、12ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/12/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#45 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。Amazon  
  
Web Services (AWS) アカウントには、EC2-1 という名前の Amazon Elastic Compute Cloud (EC2) インスタンスが含まれています。EC2-1 を  
  
Defender for Cloud にオンボードする必要があります。EC2-1  
  
には何をインストールすればよいですか？

- A. Log Analyticsエージェント
- B. Azure Connected Machine エージェント
- C. 統合された Microsoft Defender for Endpoint ソリューション パッケージ
- D. Microsoft 監視エージェント

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)   [議論   26](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
AWS EC2インスタンスをDefender for Cloudにオンボードするために必要なエージェントです。
**「Azure Connected Machineエージェント (Azure Connected Machine agent)」**: AWS上のEC2インスタンスをAzure Arc対応サーバーとして接続することで、Defender for Cloud（Defender for Servers）の保護対象とすることができます。EC2インスタンスにインストールする最初のエージェントはこれです。なお、Azure Monitorエージェント (AMA) は、Arc接続後に拡張機能としてデプロイされます。

*Community vote distribution*

B (70%)

A (30%)

質問#46 トピック2

Microsoft Defender for Cloud を使用し、RG1 というリソース グループを含む Azure サブスクリプションがあります。RG1 には、Windows Server 2019 を実行する 20 台の仮想マシンが含まれています。RG1  
  
内の仮想マシンに対して、ジャストインタイム (JIT) アクセスを構成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 最大要求時間を 2 時間に制限する。  
• プロトコル アクセスをリモート デスクトップ プロトコル (RDP) のみに制限する。  
• 管理作業を最小限に抑える。  
  
では、どのようなソリューションを使用すべきでしょうか。

- A. Azure AD 特権 ID 管理 (PIM)
- B. Azureポリシー
- C. アズール・バスティオン
- D. アズールフロントドア

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)   [議論   39](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
管理作業を最小限に抑えつつ、RDPアクセスのJIT (Just-In-Time) 制御を2時間制限で構成する場合の選択肢です。
**「Azure Policy」**: JIT VMアクセスを大規模に適用し、構成を強制するための推奨される方法です。Azure Policyを使用することで、すべてのVM（または特定のリソースグループ内のVM）に対してJITを有効にするポリシー定義を割り当てることができます。個別に設定する手間を省き、管理を効率化できます。
※JITの時間はデフォルト3時間ですが、設定で変更可能です。要件の「2時間」もポリシーパラメータやDefender for Cloudの設定で対応できます。

*Community vote distribution*

B (74%)

C (26%)

質問#47 トピック2

HOTSPOT  
\-  
  
Microsoft Defender for Cloud を使用する Azure サブスクリプションを所有しています。GCP1  
  
という Google Cloud Platform (GCP) 組織を作成します。  
  
ネイティブ クラウド コネクタを使用して、GCP1 を Defender for Cloud にオンボードする必要があります。このソリューションでは、今後作成されるすべての GCP プロジェクトが自動的にオンボードされるようにする必要があります。  
  
このソリューションには何を含めるべきですか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image170.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image171.png)

**解説:**
GCP組織をDefender for Cloudにオンボードし、新しいプロジェクトも自動的に対象にするための設定です。

1. **Azure Arcの自動プロビジョニング**: Azure Arcエージェントを自動的にインストールする設定を有効にします。これにより、GCP上のVMが自動的にAzure Arcに接続され、管理対象となります。
2. **Microsoft Defender for Containersの自動プロビジョニング**: コンテナ保護（GKEなど）も要件に含まれる場合（設問には明示されていませんが、完全な保護には通常含まれます）、これも有効にします。しかし、より重要なのは**「監査ログ (Audit logs)」**の設定です。GCPコネクタの設定で、「GCP監査ログをDefener for Cloudに送信する」構成を行うことで、組織レベルでの監視が可能になります。
※画像選択肢の詳細は不明ですが、Defender for CloudのGCPコネクタ設定における「自動プロビジョニング（Auto provisioning）」設定画面での適切なオプションを選択する問題です。

質問#48 トピック2

VM1 という仮想マシンを含む Azure サブスクリプションがあり、Microsoft Defender for Cloud を使用しています。Microsoft  
  
Defender for Cloud では、Azure Monitor エージェントを使用するように自動プロビジョニングが設定されています。VM1  
  
での PowerShell の不審な使用に関する誤検知アラートを抑制するカスタムアラート抑制ルールを作成する必要があります。  
  
まず何をすべきでしょうか？

- A. Microsoft Defender for Cloud から、アラートを Log Analytics ワークスペースにエクスポートします。
- B. Microsoft Defender for Cloud からワークフロー自動化を追加します。
- C. VM1 で PowerShell アラートをトリガーします。
- D. VM1 で、Get-MPThreatCatalog コマンドレットを実行します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
誤検知（False Positive）のアラートに対する抑制ルールを作成する前に必要なステップです。
**「VM1でPowerShellアラートをトリガーします」**: アラート抑制ルールを作成するには、まず対象となるアラートがDefender for Cloud上に存在している必要があります。既存のアラートを選択して「同様のアラートを抑制する」アクションを実行するのが標準的な手順です。そのため、まだアラートが発生していない場合は、まずアラートをトリガーさせる必要があります。

質問#49 トピック2

HOTSPOT  
\-  
  
ケーススタディ  
\-  
  
これはケーススタディです。ケーススタディは個別に時間制限がありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディとセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する展示資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
  
このケーススタディの最後に、確認画面が表示されます。この画面では、試験の次のセクションに進む前に回答を確認し、変更を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには  
\-  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。 ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同じであることに注意してください。 質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要  
\-  
  
Fabrikam, Inc. は金融サービス会社です。  
  
この会社には、ニューヨーク、ロンドン、シンガポールに支社があります。 Fabrikam には、世界中にリモート ユーザーがいます。リモート ユーザーは、支社への VPN 接続を使用して、クラウド リソースなどの会社のリソースにアクセスします。  
  
既存の環境  
\-  
  
ID 環境  
\-  
  
ネットワークには、fabrikam.com という名前の Azure AD テナントと同期する fabrikam.com という名前の Active Directory ドメイン サービス (AD DS) フォレストが含まれています。 フォレストを同期するために、Fabrikam は、パススルー認証が有効でパスワード ハッシュ同期が無効な Azure AD Connect を使用します。  
  
fabrikam.com フォレストには、Group1 と Group2 という 2 つのグローバル グループが含まれています。  
  
Microsoft 365 環境  
\-  
  
Fabrikam の全ユーザーには、Microsoft 365 E5 ライセンスと Azure Active Directory Premium Plan 2 ライセンスが割り当てられています。Fabrikam  
  
は Microsoft Defender for Identity と Microsoft Defender for Cloud Apps を実装し、ログコレクターを有効にしています。Azure  
  
環境  
\-  
  
Fabrikam には、次の表に示すリソースが含まれる Azure サブスクリプションがあります。  
  
![](https://img.examtopics.com/sc-200/image172.png)  
  
アマゾン ウェブ サービス (AWS) 環境  
  
Fabrikam には、Account1 という名前のアマゾン ウェブ サービス (AWS) アカウントがあります。Account1 には、カスタム Windows Server 2022 を実行する 100 個の Amazon Elastic Compute Cloud (EC2) インスタンスが含まれています。イメージには Microsoft SQL Server 2019 が含まれていますが、エージェントはインストールされていません。  
  
現在の問題  
\-  
  
ユーザーが VPN 接続を使用すると、Microsoft 365 Defender によって、誤検知であるあり得ない移動アラートが大量に生成されます。  
  
Defender for Identity によって、誤検知である DCSync 攻撃の疑いアラートが大量に生成されます。  
  
要件  
\-  
  
計画されている変更  
\-  
  
Fabrikam では、次のサービスを実装する予定です。  
  
• Microsoft Defender for Cloud  
• Microsoft Sentinel  
  
ビジネス要件  
\-  
  
Fabrikam では、次のビジネス要件が特定されています。  
  
• 可能な限り、最小権限の原則を使用します。  
• 管理の労力を最小限に抑えます。  
  
Microsoft Defender for Cloud Apps の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud Apps の要件を特定しています。  
  
• あり得ない移動アラート ポリシーが各ユーザーの以前のアクティビティに基づいていることを確認します。  
• 誤検知であるあり得ない移動アラートの量を減らします。  
  
Microsoft Defender for Identity の要件  
  
誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Defender for Cloud の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud の要件を特定しています。  
  
• Group2 のメンバーが、セキュリティ ポリシーを変更できることを確認  
します。 • Group1 のメンバーが、Azure サブスクリプション レベルで規制コンプライアンス ポリシー イニシアチブを割り当てることができることを確認します。  
• Account1 の既存および将来のリソースへの Azure Arc 対応サーバーの Azure Connected Machine エージェントの展開を自動化します。  
• 誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Sentinel の要件  
  
Fabrikam では、次の Microsoft Sentinel の要件を特定しています。  
  
• 組み込みの Advanced Security Information Model (ASIM) 統合パーサーを使用して、過去 7 日間の NXDOMAIN DNS 要求を照会します。  
• AWS EC2 インスタンスから、ローカルグループメンバーシップの変更を含む Windows セキュリティイベントログエントリを収集します。  
• ユーザーおよびエンティティ行動分析 (UEBA) を使用して、Azure AD ユーザーの異常なアクティビティを特定します。  
• UEBA を使用して、侵害された Azure AD ユーザー資格情報の潜在的な影響を評価します。  
• App1 が Microsoft Sentinel 自動化ルールで使用できることを確認します。  
• 過去 30 日間に生成されたインシデントの平均トリアージ時間を特定します。  
• 過去 30 日間に生成されたインシデントのクローズにかかる平均時間を特定します。  
• Group1 のメンバーがプレイブックを作成して実行できることを確認します。  
• Group1 のメンバーが分析ルールを管理できることを確認します。  
• Jupyter ノートブックを使用して、Pool1 でハンティング クエリを実行します。  
• Group2 のメンバーがインシデントを管理できることを確認します。  
• データ クエリのパフォーマンスを最大化します。  
• 収集されるデータの量を最小限に抑えます。  
  
Microsoft Defender for Cloud Apps の要件を満たす必要があります。  
  
何をすればよいですか。 回答するには、回答領域で適切なオプションを選択します。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image173.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image174.png)

**解説:**
Fabrikamの要件である「あり得ない移動（Impossible Travel）アラートの誤検知削減」と「ユーザーの過去のアクティビティに基づく」設定です。

1. **At minimum, create**: **「One alert policy」**。あり得ない移動の検知は、通常1つのポリシー（Atypical travel）で構成・調整します。ユーザーごとに個別のポリシーを作成する必要はありません。
2. **Set the Sensitivity level slider to**: **「Low」**。ポリシーの感度（Sensitivity）スライダーを「低（Low）」に設定すると、システムはユーザーの過去のアクティビティパターン（学習期間のデータ）をより強く考慮し、偏差が小さい場合はアラートを抑制します。これにより誤検知を減らすことができます。

質問#50 トピック2

HOTSPOT -  
  
ケーススタディ -  
  
これはケーススタディです。ケーススタディは個別に時間制限がありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディとセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する展示資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
  
このケーススタディの最後に、確認画面が表示されます。この画面では、試験の次のセクションに進む前に回答を確認し、変更を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。 ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同じであることに注意してください。 質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
  
Fabrikam, Inc. は金融サービス会社です。  
  
この会社には、ニューヨーク、ロンドン、シンガポールに支社があります。 Fabrikam には、世界中にリモート ユーザーがいます。リモート ユーザーは、支社への VPN 接続を使用して、クラウド リソースなどの会社のリソースにアクセスします。  
  
既存の環境 -  
  
ID 環境 -  
  
ネットワークには、fabrikam.com という名前の Azure AD テナントと同期する fabrikam.com という名前の Active Directory ドメイン サービス (AD DS) フォレストが含まれています。 フォレストを同期するために、Fabrikam は、パススルー認証が有効でパスワード ハッシュ同期が無効な Azure AD Connect を使用します。  
  
fabrikam.com フォレストには、Group1 と Group2 という 2 つのグローバル グループが含まれています。  
  
Microsoft 365 環境 -  
  
Fabrikam の全ユーザーには、Microsoft 365 E5 ライセンスと Azure Active Directory Premium Plan 2 ライセンスが割り当てられています。Fabrikam  
  
は Microsoft Defender for Identity と Microsoft Defender for Cloud Apps を実装し、ログコレクターを有効にしています。Azure  
  
環境 -  
  
Fabrikam は、次の表に示すリソースを含む Azure サブスクリプションを保有しています。Amazon  
  
![](https://img.examtopics.com/sc-200/image172.png)  
  
Web Services (AWS) 環境  
  
Fabrikam には Account1 という名前の Amazon Web Services (AWS) アカウントがあります。Account1 には、カスタム Windows Server 2022 を実行する 100 個の Amazon Elastic Compute Cloud (EC2) インスタンスが含まれています。イメージには Microsoft SQL Server 2019 が含まれていますが、エージェントはインストールされていません。  
  
現在の問題 -  
  
ユーザーが VPN 接続を使用すると、Microsoft 365 Defender によって、誤検知であるあり得ない移動アラートが大量に生成されます。Defender  
  
for Identity によって、誤検知である DCSync 攻撃の疑いアラートが大量に生成されます。  
  
要件 -  
  
計画されている変更 -  
  
Fabrikam では、次のサービスを実装する予定です。  
  
• Microsoft Defender for Cloud  
• Microsoft Sentinel  
  
ビジネス要件 -  
  
Fabrikam では、次のビジネス要件を特定しています。  
  
• 可能な限り、最小権限の原則を使用します。  
• 管理の労力を最小限に抑えます。  
  
Microsoft Defender for Cloud Apps の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud Apps の要件を特定しています。  
  
• あり得ない移動アラート ポリシーが各ユーザーの以前のアクティビティに基づいていることを確認します。  
• 誤検知であるあり得ない移動アラートの量を減らします。  
  
Microsoft Defender for Identity の要件  
  
誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Defender for Cloud の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud の要件を特定しています。  
  
• Group2 のメンバーがセキュリティ ポリシーを変更できること  
を確認します。 • Group1 のメンバーが、Azure サブスクリプション レベルで規制コンプライアンス ポリシー イニシアチブを割り当てることができることを確認します。  
• Account1 の既存および将来のリソースへの Azure Arc 対応サーバー用の Azure Connected Machine エージェントの展開を自動化します。  
• 誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Sentinel の要件 -  
  
Fabrikam では、次の Microsoft Sentinel の要件を特定しています。 •  
  
組み込みの Advanced Security Information Model (ASIM) 統合パーサーを使用して、過去 7 日間のNXDOMAIN DNS 要求  
をクエリします。 • AWS EC2 インスタンスから、ローカル グループ メンバーシップの変更を含む Windows セキュリティ イベント ログ エントリを収集します。 •  
ユーザーおよびエンティティの動作分析 (UEBA)  
を使用して、Azure AD ユーザーの異常なアクティビティを特定します  
• App1 が Microsoft Sentinel 自動化ルールで使用できることを確認します。  
• 過去 30 日間に生成されたインシデントのトリアージにかかる平均時間を特定します。  
• 過去 30 日間に生成されたインシデントのクローズにかかる平均時間を特定します。  
• Group1 のメンバーがプレイブックを作成して実行できることを確認します。  
• Group1 のメンバーが分析ルールを管理できることを確認します。  
• Jupyter ノートブックを使用して、Pool1 でハンティング クエリを実行します。  
• Group2 のメンバーがインシデントを管理できることを確認します。  
• データ クエリのパフォーマンスを最大化します。  
• 収集されるデータの量を最小限に抑えます。  
  
Microsoft Defender for Cloud の要件とビジネス要件を満たすには、Group1 と Group2 にロールベースのアクセス制御 (RBAC) ロールを割り当てる必要があります。  
  
各グループにはどのロールを割り当てる必要がありますか。 回答するには、回答領域で適切なオプションを選択します。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image175.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)   [議論   20](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image421.png)

**解説:**
Fabrikamの要件（Group2: ポリシー変更、Group1: イニシアチブ割り当て）を満たす最小権限のロール割り当てです。

1. **Group1 (Assign regulatory compliance policy initiatives)**: **「Resource Policy Contributor (リソース ポリシーの貢献者)」** (またはOwner/Contributor)。イニシアチブ（ポリシーセット）の割り当てには、`Microsoft.Authorization/policyAssignments/write` 権限が必要です。Resource Policy Contributorはこの操作に特化したロールです。Security Adminでは割り当てまではできない場合があります。
2. **Group2 (Modify security policies)**: **「Security Admin (セキュリティ管理者)」**。Defender for Cloud内のセキュリティポリシー設定の変更には、Security Adminロールが最適かつ最小権限です。

質問#51 トピック2

ケーススタディ -  
  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
  
Fabrikam, Inc. は金融サービス会社です。  
  
この会社には、ニューヨーク、ロンドン、シンガポールに支社があります。Fabrikam には、世界中にリモート ユーザーがいます。リモート ユーザーは、支社への VPN 接続を使用して、クラウド リソースを含む会社のリソースにアクセスします。  
  
既存の環境 -  
  
ID 環境 -  
  
ネットワークには、fabrikam.com という名前の Azure AD テナントと同期する fabrikam.com という名前の Active Directory ドメイン サービス (AD DS) フォレストが含まれています。フォレストを同期するために、Fabrikam は、パススルー認証が有効でパスワード ハッシュ同期が無効な Azure AD Connect を使用します。fabrikam.com  
  
フォレストには、Group1 と Group2 という 2 つのグローバル グループが含まれています。Microsoft  
  
365 環境 -  
  
Fabrikam のすべてのユーザーには、Microsoft 365 E5 ライセンスと Azure Active Directory Premium Plan 2 ライセンスが割り当てられています。  
  
Fabrikam は Microsoft Defender for Identity と Microsoft Defender for Cloud Apps を実装し、ログコレクターを有効にしています。Azure  
  
環境 -  
  
Fabrikam は、次の表に示すリソースを含む Azure サブスクリプションを保有しています。Amazon  
  
![](https://img.examtopics.com/sc-200/image172.png)  
  
Web Services (AWS) 環境  
  
Fabrikam には Account1 という名前の Amazon Web Services (AWS) アカウントがあります。Account1 には、カスタム Windows Server 2022 を実行する 100 個の Amazon Elastic Compute Cloud (EC2) インスタンスが含まれています。イメージには Microsoft SQL Server 2019 が含まれていますが、エージェントはインストールされていません。  
  
現在の問題 -  
  
ユーザーが VPN 接続を使用すると、Microsoft 365 Defender によって、誤検知であるあり得ない移動アラートが大量に生成されます。Defender  
  
for Identity によって、誤検知である DCSync 攻撃の疑いアラートが大量に生成されます。  
  
要件 -  
  
計画されている変更 -  
  
Fabrikam では、次のサービスを実装する予定です。  
  
• Microsoft Defender for Cloud  
• Microsoft Sentinel  
  
ビジネス要件 -  
  
Fabrikam では、次のビジネス要件を特定しています。  
  
• 可能な限り、最小権限の原則を使用します。  
• 管理の労力を最小限に抑えます。  
  
Microsoft Defender for Cloud Apps の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud Apps の要件を特定しています。  
  
• あり得ない移動アラート ポリシーが各ユーザーの以前のアクティビティに基づいていることを確認します。  
• 誤検知であるあり得ない移動アラートの量を減らします。  
  
Microsoft Defender for Identity の要件  
  
誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Defender for Cloud の要件  
  
Fabrikam では、次の Microsoft Defender for Cloud の要件を特定しています。  
  
• Group2 のメンバーがセキュリティ ポリシーを変更できること  
を確認します。 • Group1 のメンバーが、Azure サブスクリプション レベルで規制コンプライアンス ポリシー イニシアチブを割り当てることができることを確認します。  
• Account1 の既存および将来のリソースへの Azure Arc 対応サーバー用の Azure Connected Machine エージェントの展開を自動化します。  
• 誤検知アラートを調査するために必要な管理作業を最小限に抑えます。  
  
Microsoft Sentinel の要件 -  
  
Fabrikam では、次の Microsoft Sentinel の要件を特定しています。 •  
  
組み込みの Advanced Security Information Model (ASIM) 統合パーサーを使用して、過去 7 日間のNXDOMAIN DNS 要求  
をクエリします。 • AWS EC2 インスタンスから、ローカル グループ メンバーシップの変更を含む Windows セキュリティ イベント ログ エントリを収集します。 •  
ユーザーおよびエンティティの動作分析 (UEBA)  
を使用して、Azure AD ユーザーの異常なアクティビティを特定します  
• App1 が Microsoft Sentinel 自動化ルールで使用できることを確認します。  
• 過去 30 日間に生成されたインシデントのトリアージにかかる平均時間を特定します。  
• 過去 30 日間に生成されたインシデントのクローズにかかる平均時間を特定します。  
• グループ1のメンバーがプレイブックを作成および実行できることを確認します。  
• グループ1のメンバーが分析ルールを管理できることを確認します。  
• Jupyter Notebookを使用して、プール1でハンティングクエリを実行します。  
• グループ2のメンバーがインシデントを管理できることを確認します。  
• データクエリのパフォーマンスを最大化します。  
• 収集されるデータの量を最小限に抑えます。Microsoft  
  
Defender for Cloudの要件を満たすには、アカウント1にネイティブクラウドコネクタを展開する必要があります。  
  
アカウント1でまず何をすべきでしょうか？

- A. Defender for Cloud 用の AWS ユーザーを作成します。
- B. AWS Security Hub を設定します。
- C. AWS Systems Manager (SSM) エージェントをデプロイします。
- D. Defender for Cloud のアクセス制御 (IAM) ロールを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)   [議論   29](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
AWSアカウント（Account1）にネイティブクラウドコネクタを展開する際、AWS側で最初に行うべき設定です。
**「Configure AWS Security Hub (AWS Security Hubを設定します)」**: Defender for Cloudのネイティブコネクタ（CSPM機能など）は、AWS Security Hubからのデータ収集に依存する場合や、統合の一部として連携します。また、コネクタ作成時にAWS側でIAMロールを作成しますが、推奨事項やセキュリティ基準の評価を行うためにSecurity Hubの有効化が前提または推奨されるステップとなります。
（※注：最新のコネクタ（エージェントレススキャン等）ではSecurity Hubが必須でない場合もありますが、従来の構成や試験の文脈ではSecurity Hubとの連携がキーポイントになることが多いです。または純粋にIAMロール作成が最初のステップですが、選択肢の中でAWSサービス側の準備としてはSecurity Hubが該当します。）

*Community vote distribution*

B (41%)

C (25%)

D (20%)

14%

質問#52 トピック2

次の表に示すリソースがあります。Microsoft  
  
![](https://img.examtopics.com/sc-200/image194.png)  
  
Defender for Cloud を使用する Azure サブスクリプションがあります。  
  
各リソースで Microsoft Defender for Servers を有効にする必要があります。Azure  
  
Arc エージェントのインストールが必要なリソースはどれですか？

- A. サーバー3のみ
- B. Server1とServer4のみ
- C. Server1、Server2、Server4のみ
- D. サーバー1、サーバー2、サーバー3、およびサーバー4

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
Microsoft Defender for Serversを有効にするためにAzure Arcエージェントのインストールが必要なリソースを特定します。

- **Server1 (AWS EC2)**: Azure外のVMなので、**必要**。
- **Server2 (Azure VM)**: Azureネイティブのリソースなので、Arcエージェントは**不要**（VMエージェントを使用）。
- **Server3 (Azure VM with SQL)**: Azureネイティブなので、Arcエージェントは**不要**。
- **Server4 (Physical Server)**: オンプレミスの物理サーバーなので、**必要**。
したがって、Arcエージェントが必要なのは **Server1 と Server4** です。
（※正解選択肢が C (Server1, Server2, Server4) となっていますが、Server2はAzure VMであれば不要なはずです。ただし、Server2が「Azure VM」と明記されているにも関わらずCが正解とされる場合、設問の前提（OS要件や管理形態）に特殊な条件があるか、あるいはServer2が管理されていない（エージェントが壊れている等）とみなされている可能性があります。標準的な知識では **Server1とServer4** ですが、選択肢の構成上Cが選ばれているようです。ここでは解説として「Azure外のリソースにはArcが必要、Azure VMには不要」という原則を押さえておいてください。）

*Community vote distribution*

C (100%)

質問#53 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。Account1  
  
という GitHub アカウントがあり、10 個のリポジトリが含まれています。Defender  
  
for Cloud が Account1 のリポジトリにアクセスできることを確認する必要があります。Microsoft  
  
Defender for Cloud ポータルでまず何をすべきでしょうか？

- A. 統合を有効にします。
- B. プランを有効にします。
- C. 環境を追加します。
- D. セキュリティポリシーを有効にします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)  

**解説:**
GitHubリポジトリをDefender for Cloudに統合する最初のステップです。
**「環境を追加します (Add environment)」**: Defender for Cloudの「環境設定 (Environment settings)」ブレードから、「環境を追加 (Add environment)」を選択し、「GitHub」を選んで接続ウィザードを開始します。これにより、GitHub組織またはアカウントとの接続（コネクタ）を作成します。

*Community vote distribution*

C (100%)

質問#54 トピック2

HOTSPOT  
\-  
  
Microsoft Defender for Cloud を使用する Sub1 という Azure サブスクリプションがあります。AzDO1  
  
という Azure DevOps 組織があります。Sub1  
  
と AzDO1 を統合する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• Defender for Cloud を使用して、パイプラインで公開されているシークレットを検出する。  
• 管理作業を最小限に抑える。  
  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正解は 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image195.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/12/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image196.png)

**解説:**
Azure DevOpsパイプラインで公開されているシークレットを検出し、管理負荷を最小限に抑えるソリューションです。

1. **Select an extension**: **「Microsoft Security DevOps」** (MSDO)。Azure DevOpsのマーケットプレイスからこの拡張機能をインストールし、パイプラインタスクとして使用することで、シークレットスキャン（CredScan等を含む）や静的解析を実行し、結果をDefender for Cloudに統合できます。
※ 最新では「GitHub Advanced Security for Azure DevOps」が推奨される場合もありますが、SC-200のコンテキストや選択肢（MSDO）に基づくとこれが正解です。
2. **Configure the extension**: **「Connect Azure DevOps to Microsoft Defender for Cloud」**。MSDO拡張機能を使用する前提として（または使用後に結果を表示するために）、Defender for Cloud側でDevOps環境（コネクタ）を設定し、Azure DevOps組織を接続する必要があります。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/11/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 12 ページ目を表示しています。

410問中**111 - 120**問 を表示
