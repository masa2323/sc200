---
title: "SC-200試験 - 無料の実際のQ&A、13ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/13/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#55 トピック2

ドラッグ＆ドロップ -  
  
Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。  
  
新しい Microsoft Secure Score アクションが生成されたときに、会社の IT 部門に Microsoft Teams メッセージを送信するワークフローを作成する必要があります。  
  
どの 3 つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答領域に移動し、正しい順序に並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image223.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)   [議論   28](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)

**正解:** ![](https://img.examtopics.com/sc-200/image422.png)

**解説:**
Secure Scoreの更新（新しいアクションの生成）をトリガーにIT部門へ通知を送るLogic Appワークフローの作成手順です。

1. **Azureポータルで、空のロジックアプリを作成します**: まず、ワークローの基盤となるLogic Appリソースを作成する必要があります。
2. **Defender for Cloudのワークフロー自動化から、ワークフロー自動化を作成します**: Defender for Cloudの設定画面で「Workflow automation」を作成し、トリガー条件（Secure Scoreの推奨事項の変更など）と実行するLogic Appを紐付けます。
3. **ロジックアプリデザイナーから、Microsoft Teamsのアクションを追加します**: Logic Appの中身として、通知先となるTeamsへの投稿アクションを定義します。

質問#56 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションがあり、Windows Server を実行する仮想マシンが 100 台含まれています。  
  
これらの仮想マシンからイベントデータを収集するように Defender for Cloud を構成する必要があります。このソリューションでは、管理の手間とコストを最小限に抑える必要があります。  
  
実行すべきアクションは 2 つあります。正解はそれぞれソリューションの一部です。  
  
注: 正解は 1 つにつき 1 ポイントです。

- A. セキュリティ イベント ストレージを共通に設定して、自動プロビジョニングを構成します。
- B. Microsoft Endpoint Manager 管理センターから、自動登録を有効にします。
- C. Azure ポータルから、Azure Event Grid サブスクリプションを作成します。
- D. セキュリティ イベント ストレージを \[すべてのイベント\] に設定して、自動プロビジョニングを構成します。
- E. Azure ポータルの Defender for Cloud から、Microsoft Defender for Servers を有効にします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)

**正解:** AE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)  

**解説:**
100台のVMからイベントデータを収集し、コストと管理負荷を最小限に抑える構成です。

1. **A. Common (共通) に設定**: 「All events」は全イベントを収集するため高コストです。「Common」は監査に必要な標準セットであり、コスト対効果が高い設定です。
2. **E. 自動プロビジョニングを有効にする**: Defender for Cloudの設定で自動プロビジョニングを有効にすることで、全VMへのエージェント（AMA/Log Analyticsエージェント）導入を自動化し、管理負荷を最小化します。

*コミュニティ投票の配分*

AE（92％）

8%

質問#57 トピック2

Microsoft Defender for Cloud を使用する Azure サブスクリプションがあります。Amazon  
  
Web Services (AWS) サブスクリプションもあります。サブスクリプションには、Windows Server を実行する複数の仮想マシンが含まれています。  
  
これらの仮想マシンで Microsoft Defender for Servers を有効にする必要があります。  
  
実行すべき 2 つのアクションはどれですか？ 正解はそれぞれ解答の一部です。  
  
注: 正解は 1 点です。

- A. Defender for Cloud からエージェントレス スキャンを有効にします。
- B. 仮想マシンを Microsoft Defender for Endpoint にオンボードします。
- C. Defender for Cloud から AWS コネクタを構成します。
- D. 各仮想マシンに Azure 仮想マシン エージェント (VM エージェント) をインストールします。
- E. Defender for Cloud から自動プロビジョニングを構成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)

**正解:** CE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)  

**解説:**
AWS VMとオンプレミスVM（文脈上含まれる場合や、Azure外リソース全般）でDefender for Serversを有効にするための手順です。

1. **C. AWSコネクタを構成します**: AWS環境をDefender for Cloudに接続するために必要です。これによりAzure Arcの自動デプロイなどが可能になります。
2. **E. 自動プロビジョニングを構成します**: 接続されたAWS VMやオンプレミス・他クラウドサーバーに対して、必要なエージェント（Log Analyticsエージェント/AMA、およびAzure Arcエージェント）を自動的にインストールする設定を有効にします。
（※選択肢Dの「VMエージェント」はAzure VM専用です。Azure外サーバーにはAzure Arcエージェントが必要です。）

*コミュニティ投票の配分*

CE（100％）

質問#58 トピック2

HOTSPOT  
\-  
  
Sub1 という Azure サブスクリプションと AzDO1 という Azure DevOps 組織があります。AzDO1 には Defender for Cloud が使用されており、Pipeline1 という YAML パイプラインを持つプロジェクトが含まれています。Pipeline1  
  
は、発見されたオープンソースソフトウェアの脆弱性の詳細を Defender for Cloud に出力します。  
  
シークレットスキャンの結果を Defender for Cloud に出力するように Pipeline を構成する必要があります。Pipeline1  
  
に何を追加すればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image225.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)

**正解:** ![](https://img.examtopics.com/sc-200/image226.png)

**解説:**
Azure DevOpsパイプラインでシークレットスキャン（CredScan等）を実行し、結果をDefender for Cloudに統合する構成です。

1. **Task**: **「Microsoft Security DevOps」**。この拡張機能タスクをパイプラインに追加することで、セキュリティスキャンを実行できます。
2. **Output format**: **「Sarif」**。セキュリティスキャンの結果はSARIF (Static Analysis Results Interchange Format) 形式で出力され、Defender for Cloudの「DevOps Security」ダッシュボードに取り込まれて表示されます。

質問#59 トピック2

sub1 という名前の Azure サブスクリプションを作成します。sub1  
  
内に、workspace1 という名前の Log Analytics ワークスペースを作成します。Microsoft  
  
Defender for Cloud を有効にし、workspace1 を使用するように Defender for Cloud を構成します。workspace1  
  
にレポートを送信する Azure 仮想マシンからセキュリティ イベント ログを収集する必要があります。  
  
どうすればよいでしょうか。

- A. Defender for Cloud から、Microsoft Defender for Servers プランの設定を変更します。
- B. サブ1でプロバイダーを登録します。
- C. Defender for Cloud からワークフロー自動化を作成します。
- D. ワークスペース1 でワークブックを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)  

**解説:**
特定のLog Analyticsワークスペース（workspace1）にレポートするAzure VMからセキュリティイベントログを収集する方法です。
**「Defender for Cloudから、Microsoft Defender for Serversプランの設定を変更します」**: Defender for Serversプランをワークスペースレベルで有効にするか、サブスクリプションレベルの設定で対象ワークスペースへの自動プロビジョニングとデータ収集設定（Common/Allなど）を構成することで、イベントログの収集が開始されます。

*コミュニティ投票の配分*

A（91％）

9%

質問#60 トピック2

ケーススタディ -  
  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同じであることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
  
Adatum Corporation は、ニューヨーク、シカゴ、サンフランシスコに支社を持つ、米国を拠点とする金融サービス企業です。  
  
既存の環境 -  
  
ID 環境 -  
  
オンプレミス ネットワークには、adatum.com という Azure AD テナントと同期する corp.adatum.com という Active Directory ドメイン サービス (AD DS) フォレストが含まれています。すべてのユーザーとグループの管理タスクは、corp.adatum.com で実行されます。corp.adatum.com ドメインには、adatum.com と同期する Group1 というグループが含まれています。  
  
ライセンスの状態 -  
  
Adatum のすべてのユーザーには、Microsoft 365 ES ライセンスと Azure Active Directory Premium P2 ライセンスが割り当てられています。  
  
クラウド環境 -  
  
クラウド環境には、Microsoft 365 サブスクリプション、adatum.com テナントにリンクされた Azure サブスクリプション、および次の表に示すリソースが含まれています。  
  
![](https://img.examtopics.com/sc-200/image233.png)  
  
オンプレミス環境 -  
  
オンプレミスネットワークには、次の表に示すリソースが含まれています。  
  
![](https://img.examtopics.com/sc-200/image234.png)  
  
要件 -  
  
計画されている変更 -  
  
Adatum は以下の変更を行う予定です。  
  
• 次の KQL クエリを含む、rulequery1 というクエリを実装します。  
  
![](https://img.examtopics.com/sc-200/image235.png)  
  
• rulequery1 に基づいてインシデントを生成する Microsoft Sentinel のスケジュールされたルールを実装します。  
  
Microsoft Defender for Cloud の要件  
  
Adatum では、次の Microsoft Defender for Cloud の要件が識別されています。  
  
• Group1 のメンバーは、Defender for Cloud プランを有効にして、規制コンプライアンス イニシアチブを適用できる必要があります。  
• Microsoft Defender for Servers プラン 2 は、すべての Azure 仮想マシンで有効にする必要があります。  
• Server2 は、エージェントレス スキャンから除外する必要があります。  
  
Microsoft Sentinel の要件 -  
  
Adatum では、次の Microsoft Sentinel の要件が識別されています。  
  
• Infoblox1 からの NXDOMAIN 応答をもたらす DNS 要求の数を返す Advanced Security Information Model (ASIM) クエリを実装します。  
• 1 人のユーザーが Azure Cloud Shell を複数回起動したことに応答して rulequery1 によって生成される複数のアラートが、1 つのインシデントとして統合されるようにします。  
• Microsoft Sentinel の AMA コネクタを介して Windows セキュリティ イベントを実装し、Server1 のセキュリティ イベント ログを監視するように構成します。  
• Azure Cloud Shell が会社の SecOps チームによって起動された場合、rulequery1 によって生成されたインシデントが自動的に閉じられるようにします。  
• Webapp1 からデータを動的に取得するクエリを含む、Workbook1 という名前のカスタム Microsoft Sentinel ブックを実装します。  
• 指定された緊急アカウントへのサインインを検出する Microsoft Sentinel ニアリアルタイム (NRT) 分析ルールを実装します。  
• Azure ポータルで Microsoft Sentinel の Hunting ページにアクセスされたときに、HuntingQuery1 が自動的に実行されるようにします。  
• corp.adatum.com ユーザー アカウントのパスワード リセットが通常よりも多く検出されるようにします。  
• ASIM パーサーを使用するクエリに関連するオーバーヘッドを最小限に抑えます。  
• Group1 のメンバーがプレイブックを作成および編集できるようにします。  
• 可能な限り、組み込みの ASIM パーサーを使用します。ビジネス 要件  
  
\-  
  
Adatum では、次のビジネス要件が示されています。  
  
• 可能な限り、最小権限の原則に従います。  
• 可能な限り、管理の労力を最小限に抑えます。  
  
- A. Microsoft Antimalware拡張機能
- B. Windows 用の Azure Automanage マシン構成拡張機能
- C. Azureリソースロック
- D. Azureリソースタグ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)  

**解説:**
Adatumのビジネス要件「管理の労力を最小限に抑える」および「整理・管理」の観点で最適なAzure機能です。
**「Azureリソースタグ (Azure resource tags)」**: リソースにメタデータ（タグ）を付与することで、コスト管理（部門ごとの課金分析など）やリソースの論理的なグループ化が可能になります。ポリシーでタグ付けを強制すれば、管理負荷を抑えつつ一貫性を保てます。
リソースロック（C）は誤削除防止には有効ですが、コスト管理や柔軟な整理には直接寄与しません。

*コミュニティ投票の配分*

D（100％）

質問#61 トピック2

ケーススタディ -  
  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同じであることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
  
Adatum Corporation は、ニューヨーク、シカゴ、サンフランシスコに支社を持つ、米国を拠点とする金融サービス企業です。  
  
既存の環境 -  
  
ID 環境 -  
  
オンプレミス ネットワークには、adatum.com という Azure AD テナントと同期する corp.adatum.com という Active Directory ドメイン サービス (AD DS) フォレストが含まれています。すべてのユーザーとグループの管理タスクは、corp.adatum.com で実行されます。corp.adatum.com ドメインには、adatum.com と同期する Group1 というグループが含まれています。  
  
ライセンスの状態 -  
  
Adatum のすべてのユーザーには、Microsoft 365 ES ライセンスと Azure Active Directory Premium P2 ライセンスが割り当てられています。  
  
クラウド環境 -  
  
クラウド環境には、Microsoft 365 サブスクリプション、adatum.com テナントにリンクされた Azure サブスクリプション、および次の表に示すリソースが含まれています。  
  
![](https://img.examtopics.com/sc-200/image233.png)  
  
オンプレミス環境 -  
  
オンプレミスネットワークには、次の表に示すリソースが含まれています。  
  
![](https://img.examtopics.com/sc-200/image234.png)  
  
要件 -  
  
計画されている変更 -  
  
Adatum は以下の変更を行う予定です。  
  
• 次の KQL クエリを含む、rulequery1 というクエリを実装します。  
  
![](https://img.examtopics.com/sc-200/image235.png)  
  
• rulequery1 に基づいてインシデントを生成する Microsoft Sentinel のスケジュールされたルールを実装します。  
  
Microsoft Defender for Cloud の要件  
  
Adatum では、次の Microsoft Defender for Cloud の要件が識別されています。  
  
• Group1 のメンバーは、Defender for Cloud プランを有効にして、規制コンプライアンス イニシアチブを適用できる必要があります。  
• Microsoft Defender for Servers プラン 2 は、すべての Azure 仮想マシンで有効にする必要があります。  
• Server2 は、エージェントレス スキャンから除外する必要があります。  
  
Microsoft Sentinel の要件 -  
  
Adatum では、次の Microsoft Sentinel の要件が識別されています。  
  
• Infoblox1 からの NXDOMAIN 応答をもたらす DNS 要求の数を返す Advanced Security Information Model (ASIM) クエリを実装します。  
• 1 人のユーザーが Azure Cloud Shell を複数回起動したことに応答して rulequery1 によって生成される複数のアラートが、1 つのインシデントとして統合されるようにします。  
• Microsoft Sentinel の AMA コネクタを介して Windows セキュリティ イベントを実装し、Server1 のセキュリティ イベント ログを監視するように構成します。  
• 会社の SecOps チームによって Azure Cloud Shell が起動された場合に、rulequery1 によって生成されたインシデントが自動的に閉じられるようにします。  
• Webapp1 からデータを動的に取得するクエリを含む、Workbook1 という名前のカスタム Microsoft Sentinel ブックを実装します。  
• 指定された緊急アカウントへのサインインを検出する Microsoft Sentinel ニアリアルタイム (NRT) 分析ルールを実装します。  
• Azure ポータルで Microsoft Sentinel の Hunting ページにアクセスされたときに、HuntingQuery1 が自動的に実行されるようにします。  
• corp.adatum.com ユーザー アカウントのパスワード リセットが通常よりも多く検出されるようにします。  
• ASIM パーサーを使用するクエリに関連するオーバーヘッドを最小限に抑えます。  
• Group1 のメンバーがプレイブックを作成および編集できるようにします。  
• 可能な限り、組み込みの ASIM パーサーを使用します。  
  
ビジネス要件 -  
  
Adatum では、次のビジネス要件が示されています。  
  
• 可能な限り、最小権限の原則に従います。•可能な限り、管理の労力を最小限に  
抑えます。  
  
- A. セキュリティ評価貢献者
- B. 貢献者
- C. セキュリティ管理者
- D. オーナー

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)   [議論   24](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)  

**解説:**
Webapp1からデータを動的に取得するクエリを含むブック（Workbook1）を実装するための権限に関連する問題のようですが、正解が「Owner」となっている点と、設問文の要件（Group1メンバーがプレイブック作成編集、等）との整合性を見ると、これはロール割り当てに関する問題の一部かもしれません。
ただし、Adatumの要件として**「Group1のメンバーがプレイブックを作成および編集」**できるようにし、**「最小権限」**を守る場合、通常は **「Logic App Contributor (ロジック アプリ 投稿者)」** が正解になります。
※提示された正解D（Owner）は最小権限の原則に反します。もし選択肢にLogic App Contributorがない場合や、文脈が特殊な場合（Webapp1へのアクセス権も含む等）を除き、一般的にはLogic App Contributorが推奨されます。コミュニティ投票ではDとC（Security Admin）に分かれていますが、Sentinelプレイブックの作成権限はLogic Appリソースに対する書き込み権限が必要です。

*コミュニティ投票の配分*

D（61％）

C（39％）

## トピック3 - 質問セット3

質問1 トピック3

ドラッグ＆ドロップ -  
Common Event Format (CEF) メッセージを Azure Sentinel に送信する外部ソリューションを接続する予定です。  
ログフォワーダーをデプロイする必要があります。3  
つのアクションのうち、どのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
選択して配置してください。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0010700001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0010800001.png) 参照:  
<https://docs.microsoft.com/en-us/azure/sentinel/connect-cef-agent?tabs=rsyslog>

**解説:**
SentinelにCEFメッセージを送信するログフォワーダーのデプロイ手順です。

1. **Log in to a dedicated Linux machine...**: まず、フォワーダー専用のLinuxサーバー（VM）にログインします。
2. **Run the following command... (Python script)**: Sentinelポータル（「Data Connectors」>「Common Event Format (CEF)」ページ）から取得したインストール用コマンド（Pythonスクリプト `cef_installer.py` 等を実行するワンライナー）を実行します。これにより、Syslogデーモン（rsyslog/syslog-ng）の設定とAMAエージェントのインストール・設定が自動で行われます。
3. **If you are using a third-party...**: 必要に応じて、サードパーティ製セキュリティソリューション側の設定で、ログ転送先をこのフォワーダーのIPアドレスに設定します（これはフォワーダー自体のデプロイ後のステップです）。
（※画像の正解順序は、Linuxマシンへのログイン →Pythonインストーラ実行 →（必要なら）デーモン再起動確認等の流れになります）

質問2 トピック3

ホットスポット -  
Azure Sentinel から、以下の図に示すように、重大度の高いインシデントの調査ウィンドウを開きます。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0010900001.jpg)  
ドロップダウンメニューを使用して、図に示された情報に基づいて各文を完成させる選択肢を選択してください。  
注: 正解は1つにつき1ポイントです。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0011000001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)   [議論   27](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)

**正解:** ![](https://img.examtopics.com/sc-200/image423.png)

**解説:**
Sentinelのインシデント調査画面（Investigation graphや詳細画面）に関する知識です。

1. **The number of alerts**: **「Timeline (タイムライン)」**タブ（またはウィジェット）。インシデントに関連付けられたアラートやブックマークの時系列と数が表示されます。
2. **The source IP address**: **「Entities (エンティティ)」**タブ（またはウィジェット）。インシデントに関与したエンティティ（ユーザー、IP、ホスト、ファイルハッシュなど）の一覧が表示されます。

質問3 トピック3

ドラッグ＆ドロップ -  
Azure Sentinel をデプロイしています。  
不審な資格情報アクセスアクティビティをすべてクエリする必要があります。  
どの 3 つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答領域に移動し、正しい順序に並べ替えてください。  
選択して配置します。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0011100001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/13/#)

**正解：** ![](https://www.examtopics.com/assets/media/exam-media/04261/0011200001.png) 参考： https : //davemccollough.com/2020/11/28/threat-hunting-with-azure-sentinel/  

**解説:**
Sentinelで不審な認証情報アクセス（Credential Access）アクティビティをクエリ・調査する手順です。

1. **From the Logs blade...**: ログ検索画面（Logsブレード）に移動します。
2. **Run a query...**: `SecurityEvent` や `SigninLogs` などのテーブルに対し、不審なアクティビティ（Event ID 4624/4625の異常発生など）を抽出するクエリを実行します。
3. **Select the user account...**: クエリ結果から、調査対象の特定のユーザーアカウントやエンティティを特定・選択し、さらなるドリルダウンやエンティティページへの移動を行います。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/12/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 13 ページを表示しています。

410問中**121 - 130**問 を表示
