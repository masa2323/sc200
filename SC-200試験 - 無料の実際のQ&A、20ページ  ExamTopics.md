---
title: "SC-200試験 - 無料の実際のQ&A、20ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/20/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#64 トピック3

Microsoft Sentinel ワークスペースを含む Azure サブスクリプションをお持ちです。Microsoft  
  
Sentinel アラートに応じて自動的に実行されるプレイブックを作成する必要があります。  
  
まず何を作成すればよいでしょうか？

- A. Microsoft Sentinel のハンティングクエリ
- B. Azureロジックアプリ
- C. Microsoft Sentinelの自動化ルール
- D. Azure Functionsのトリガー

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)   [議論   14](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)  

**解説:**
Sentinelアラートに応じて自動実行されるプレイブック（Playbook）の実体です。
**「Azure Logic App」**: Sentinelのプレイブックは、Azure Logic Appとして実装されます。まずLogic Appを作成し、それにSentinelトリガー（インシデント作成時など）を設定することで、自動化ルールから呼び出せるようになります。

*コミュニティ投票の配分*

B（92％）

8%

質問#65 トピック3

HOTSPOT  
\-  
  
Workspace1 という Microsoft Sentinel ワークスペースがあります。Workspace1  
  
を構成して DNS イベントを収集し、DNS スキーマ用の Advanced Security Information Model (ASIM) 統合パーサーを展開します。ASIM  
  
DNS スキーマに対してクエリを実行し、過去 24 時間以内に送信元 IP アドレス別に 15 分間隔で集計された、応答コードが「NXDOMAIN」であるすべての DNS イベントを一覧表示する必要があります。このソリューションでは、クエリのパフォーマンスを最大化する必要があります。  
  
クエリをどのように完了すればよいでしょうか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image163.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)   [議論   19](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)

**正解:** ![](https://img.examtopics.com/sc-200/image164.png)

**解説:**
ASIM DNSスキーマ（`_Im_Dns`）に対するKQLクエリです。

1. **_Im_Dns**: ASIMのDNS用統合パーサー（正規化されたビュー）を使用します。
2. **where DnsResponseCodeName**: 応答コード名でフィルタリングします（`NXDOMAIN`など）。
3. **summarize count() by SrcIpAddr, bin(TimeGenerated, 15m)**: 送信元IPアドレスごと、および15分間隔（bin）で件数を集計します。
※パフォーマンス最大化のため、ネイティブテーブルではなくASIMビューを使う際は、フィルタリングを早めに行う（TimeGeneratedなど）のが鉄則ですが、選択肢の構成上、基本的なKQL構文を問うています。

質問#66 トピック3

HOTSPOT  
\-  
  
オンプレミスネットワークには、Windows Server を実行するサーバーが 100 台あります。Microsoft  
  
Sentinel を使用する Azure サブスクリプションを所有しています。  
  
オンプレミスサーバーから Microsoft Sentinel にカスタムログをアップロードする必要があります。  
  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image165.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)

**正解:** ![](https://img.examtopics.com/sc-200/image166.png)

**解説:**
オンプレミスサーバーからSentinelへカスタムログをアップロードする、最新かつ推奨される方法です。

1. **Install the Azure Monitor agent (AMA)**: 従来のMMA (Microsoft Monitoring Agent) は廃止予定であり、現在はAzure Monitor Agent (AMA) が推奨されます。オンプレミスサーバーにはAzure Arc経由でインストールします。
2. **Create a data collection rule (DCR)**: AMAでは、データ収集ルール (DCR) を使用して、収集するログの種類（カスタムログのパスなど）や送信先（Log Analyticsワークスペース）を定義します。これにより、MMAよりも柔軟で詳細な制御が可能です。

質問#67 トピック3

Microsoft Sentinel ワークスペースを含む Azure サブスクリプションをご利用です。このワークスペースには Microsoft Defender for Cloud データコネクタが含まれています。  
  
特定のイベントのアラートを作成する際に含める詳細情報をカスタマイズする必要があります。  
  
どうすればよいでしょうか？

- A. ユーザーおよびエンティティ行動分析 (UEBA) を有効にします。
- B. データ収集ルール (DCR) を作成します。
- C. コネクタのプロパティを変更します。
- D. スケジュールされたクエリ ルールを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)   [議論   15](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)  

**解説:**
Defender for Cloudのアラート詳細（Alert properties）をカスタマイズしてSentinelアラートを作成する方法です。
**「スケジュールされたクエリ ルールを作成します (Create scheduled query rules)」**: Sentinelのアラート作成ウィザード（分析ルール作成）において、「アラートのエンリッチメント (Alert enrichment)」>「アラートの詳細 (Alert details)」セクションを使用すると、KQLクエリの結果から特定の値をアラート名や説明、深刻度などに動的にマッピングできます。これにより、Defender for Cloudからの生データよりリッチな情報を持つSentinelアラートを生成できます。

*コミュニティ投票の配分*

D（81％）

他の

質問#68 トピック3

Workspace1 という Microsoft Sentinel ワークスペースと、DNS スキーマに基づく 200 個のカスタム Advanced Security Information Model (ASIM) パーサーがあります。  
  
この 200 個のパーサーを Workspace1 で利用できるようにする必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。  
  
まず何をすべきでしょうか？

- A. パーサーを Azure Monitor ログ ページにコピーします。
- B. DNS テンプレートに基づいて JSON ファイルを作成します。
- C. DNS テンプレートに基づいて XML ファイルを作成します。
- D. DNS テンプレートに基づいて YAML ファイルを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)  

**解説:**
大量のカスタムASIMパーサーをデプロイする際、管理作業を最小化するアプローチです。
**「DNSテンプレートに基づいてYAMLファイルを作成します」**: ASIMパーサーの開発・管理にはYAML形式の定義ファイルが推奨されています。YAMLファイルを作成し、それを`ASIM YAML to ARM` コンバータツールなどでARMテンプレート（JSON）に変換して一括デプロイするフローが、大規模管理において効率的です。JSONを手書きするのは困難であるため、YAMLが起点となります。

*コミュニティ投票の配分*

D（93％）

7%

質問#69 トピック3

HOTSPOT  
\-  
  
Microsoft Sentinel ワークスペースをご利用の場合、  
  
Microsoft Sentinel インシデントは次の図のように生成されます。  
  
![](https://img.examtopics.com/sc-200/image167.png)  
  
図に示されている情報に基づき、ドロップダウンメニューを使用して各文を完成させる選択肢を選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image168.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)   [議論   19](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)

**正解:** ![](https://img.examtopics.com/sc-200/image169.png)

**解説:**
Sentinelにおけるインシデント生成フローの理解を問う問題です。

1. **Correlation rule**: 分析ルール（相関ルール）がログデータを評価します。
2. **Alert**: ルール条件に合致すると「アラート」が生成されます（図の中間地点）。
3. **Incident**: アラートの設定に基づき、「インシデント」が生成されます（最終的なコンテナ）。
図の流れは `Log Data -> [Rule] -> [Alert] -> [Incident]` となります。

質問#70 トピック3

ドラッグ アンド ドロップ  
\-  
  
ケース スタディ  
\-  
  
これはケース スタディです。ケース スタディは個別に時間制限がありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケース スタディとセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケース スタディに含まれる質問に回答するには、ケース スタディで提供される情報を参照する必要があります。ケース スタディには、ケース スタディで説明されているシナリオに関する詳細情報を提供する展示資料やその他のリソースが含まれている場合があります。各質問は、このケース スタディの他の質問とは独立しています。  
  
このケース スタディの最後に、確認画面が表示されます。この画面では、試験の次のセクションに進む前に回答を確認し、変更を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケース スタディを開始するには  
\-  
このケース スタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケース スタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。 ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同じであることに注意してください。 質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
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
  
Microsoft Sentinel の要件とビジネス要件を満たすには、Group1 と Group2 にロールベースのアクセス制御 (RBAC) ロールを割り当てる必要があります。  
  
各グループにはどのロールを割り当てる必要がありますか。 回答するには、適切なロールを正しいグループにドラッグします。各ロールは、1 回、複数回、またはまったく使用しない場合があります。コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image177.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)

**正解:** ![](https://img.examtopics.com/sc-200/image178.png)

**解説:**
Fabrikamの要件に基づいたSentinelロールの割り当てです。

1. **Group1 (Create and run playbooks/analytics rules)**: **「Microsoft Sentinel Contributor」**。分析ルールの作成にはContributorが必要です。プレイブックの作成には別途Logic App Contributorが必要ですが、選択肢の中でSentinelの構成変更が可能なのはContributorです。
2. **Group2 (Manage incidents)**: **「Microsoft Sentinel Responder」**。インシデントのトリアージ、割り当て、クローズを行うためのロールです。

質問#71 トピック3

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
• Jupyterノートブックを使用して、プール1でハンティングクエリを実行します。  
• グループ2のメンバーがインシデントを管理できることを確認します。  
• データクエリのパフォーマンスを最大化します。  
• 収集されるデータの量を最小限に抑えます。UEBA  
  
を使用するためのMicrosoft Sentinelの要件を満たすには、SecurityEvent Log Analyticsテーブルのデータを相関させる必要があります。  
  
どのLog Analyticsテーブルを使用すればよいですか？

- A. アイデンティティ情報
- B. AADRiskyユーザー
- C. センチネル監査
- D. アイデンティティディレクトリイベント

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)  

**解説:**
UEBA機能を使用するために、SecurityEventなどのログと相関させる必要があるユーザー情報のテーブルです。
**「IdentityInfo」**: Azure AD (Entra ID) から同期されたユーザープロファイル情報（部署、役職、グループメンバーシップなど）が格納されるテーブルです。UEBAはこのテーブルを使って、ログ内のユーザーアカウントにコンテキスト情報を付与します。

*コミュニティ投票の配分*

A（68％）

D（26％）

5%

質問#72 トピック3

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
• Group1のメンバーがプレイブックを作成および実行できることを確認します。  
• Group1のメンバーが分析ルールを管理できることを確認します。  
• Jupyterノートブックを使用して、Pool1でハンティングクエリを実行します。  
• Group2のメンバーがインシデントを管理できることを確認します。  
• データクエリのパフォーマンスを最大化します。  
• 収集されるデータの量を最小限に抑えます。App1  
  
はMicrosoft Sentinelの要件を満たす必要があります。App1  
  
にはどのような構成が必要ですか？

- A. トリガー
- B. コネクタ
- C. 認可
- D. API接続

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)  

**解説:**
App1（自動化ルールで使用されるLogic Appを指していると思われます）の構成に必要な設定です。
**「Authorization (認可/権限付与)」**: SentinelからLogic Appをトリガーしたり、Logic AppからSentinelのインシデントを操作したりするには、適切な権限設定（Managed Identityへのロール割り当てなど）が必要です。また、Logic App内のSentinelコネクタ設定（Connection creation）も必要ですが、文脈として「Sentinelの要件（自動化ルールから使えること）」を満たすには、SentinelがLogic Appを実行できる権限（Sentinel Playbook Operatorなど）や、Logic AppがSentinelにアクセスする権限が重要です。選択肢C（Authorization）はこれらを包括する重要な構成要素です。

*コミュニティ投票の配分*

C（67％）

A（33％）

質問#73 トピック3

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
• Jupyterノートブックを使用して、プール1でハンティングクエリを実行します。  
• グループ2のメンバーがインシデントを管理できることを確認します。  
• データクエリのパフォーマンスを最大化します。  
• 収集されるデータの量を最小限に抑えます。Microsoft  
  
Sentinelの要件を満たすには、ハンティングクエリを実行できることを確認する必要があります。  
  
どのようなタイプのワークスペースを作成する必要がありますか？

- A. Azure Synapse Analytics
- B. Azure 機械学習
- C. ログ分析
- D. Azure データブリックス

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)   [議論   15](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/20/#)  

**解説:**
SentinelのHunting Query（特にJupyter Notebooksを使用した高度なハンティング）を実行するために作成する必要があるワークスペースです。
**「Azure Machine Learning」**: Microsoft SentinelのNotebooks機能は、Azure Machine Learningワークスペース上で動作します。そのため、Notebooksを利用して高度な分析やハンティングを行うには、AMLワークスペースの作成とリンクが必要です。
※KQLベースの標準ハンティングならLog Analyticsですが、選択肢にLog Analyticsがない場合や、高度な分析を意図している場合はAzure MLが正解です。

*コミュニティ投票の配分*

B（64％）

C（29％）

7%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/19/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 20 ページを表示しています。

410問中**191 - 200**問 を表示
