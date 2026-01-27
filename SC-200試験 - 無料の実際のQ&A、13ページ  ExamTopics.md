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
1. 推奨事項トリガーを含む Azure Logic Apps の作成

まず、アクションの実体となる **Azure Logic Apps** を作成します。

- Microsoft Secure Score は推奨事項の実装によって算出されるため、**「Defender for Cloud recommendation trigger」**（推奨事項トリガー）を使用するロジックアプリを選択する必要があります。
    
- このロジックアプリ内で、IT 部門に Microsoft Teams メッセージを送信するコネクタ（アクション）を追加します。
    

2. トリガー条件の構成 (Configure a trigger condition)

すべての推奨事項に対して通知を送るとノイズが多くなるため、特定の条件（重要度が「高」のものや、特定のコンプライアンスに関わるものなど）に基づいてワークフローが起動するように**トリガー条件**を設定します。

3. ワークフロー オートメーションの構成 (Configure workflow automation)

最後に、Microsoft Defender for Cloud のポータル上で**「ワークフロー オートメーション（Workflow automation）」**を設定します。

- ここで、作成した Logic App と Defender for Cloud を紐付けます。
    
- どのサブスクリプションやリソースグループを監視対象にするかを決定し、実際に自動化を有効化する最終ステップとなります。
    

---

この手順により、新しい推奨事項（Secure Score アクション）が提示された際に、自動的に Teams へ通知が飛ぶ仕組みが完成します。

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
Azure DevOps パイプラインで Microsoft Security DevOps（MSDO）タスクを使用してセキュリティスキャンを実行する場合、YAML 形式でパラメータを指定する必要があります。

1. inputs:

YAML タスクにおいて、そのタスクに渡す設定値（引数）を定義するセクションの名前は **`inputs:`** です。これにより、タスクがどのように動作するかを制御します。

2. categories: 'secrets'

Microsoft Security DevOps 拡張機能のタスク（`MicrosoftSecurityDevOps@1` など）では、**`categories`** という入力パラメータを使用して、実行するスキャンの種類を指定します。

- **'secrets'**: この値を指定することで、コード内のパスワードや API キーなどの機密情報の露出を検出するスキャン（CredScan など）が有効になり、その結果が Defender for Cloud に送信されるようになります。
    
- 他にも `IaC`（インフラ構成のスキャン）や `artifacts` などのカテゴリを指定することが可能です。
    
---

この設定を Pipeline1 に追加することで、ビルドプロセス中にシークレットが自動的に検出され、Defender for Cloud の **DevOps Security** ダッシュボードで一元管理できるようになります。

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
この問題のポイントは、Microsoft Defender for Cloud の管理に必要な権限と、Adatum 社のビジネス要件である「最小権限の原則」を両立させることにあります。

なぜ「セキュリティ管理者」なのか

Microsoft Defender for Cloud において、以下の操作を行うには特定の権限が必要です。

- **Defender プランの有効化:** サブスクリプション レベルでセキュリティ プランを「オン」にする権限。
    
- **規制コンプライアンス イニシアチブの適用:** セキュリティ ポリシー（Azure Policy イニシアチブ）を編集・割り当てする権限。
    

**セキュリティ管理者 (Security Admin)** ロールは、以下の権限を持っています：

1. セキュリティ ポリシーの表示および**編集**。
    
2. セキュリティの状態の表示。
    
3. アラートと推奨事項の表示および破棄。
    
4. **Defender プランの管理（有効化・無効化）**。
    

これにより、Group1 は必要な管理作業を行うことができます。

他の選択肢が最適ではない理由

- **A. セキュリティ評価貢献者 (Security Assessment Contributor):** 主に特定のセキュリティ評価（脆弱性スキャンなど）の実行や表示に特化したロールであり、サブスクリプション全体のプラン有効化やポリシーの割り当てを行うには権限が不足しています。
    
- **B. 貢献者 (Contributor):** リソースの作成や管理など、セキュリティ以外の広範な権限も付与されてしまいます。今回の「セキュリティ管理」という特定の目的に対しては、権限が強すぎるため、ビジネス要件である**「最小権限の原則」**に反します。
    
- **D. オーナー (Owner):** アクセス権の管理（RBAC の設定）を含むすべての操作が可能です。最も権限が強いため、最小権限の原則の観点から真っ先に除外されます。
    

---

この構成により、Group1 は IT 管理に必要な最小限の範囲で、セキュアな環境構築とコンプライアンス維持を担当できるようになります。

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
1. エージェントのダウンロードとインストール

ログフォワーダーとして機能するマシンに **Log Analytics エージェント**をインストールします。これが、オンプレミスまたは他のクラウド環境から Microsoft Sentinel へログを転送するための通信基盤となります。

2. ポート 25226 のリスニング構成

エージェントが **TCP ポート 25226** で待機するように設定します。

- **専用ポートの使用:** Microsoft Sentinel の CEF コネクタは、標準の Syslog（ポート 514）と混同しないよう、専用の 25226 ポートを使用してメッセージを受信し、クラウドへ転送するように設計されています。
    

3. Syslog デーモンの構成と再起動

マシンの **Syslog デーモン**（rsyslog や syslog-ng）を構成し、受信したセキュリティイベントをローカルのエージェント（127.0.0.1:25226）に転送するように設定します。

- 構成完了後、設定を反映させるために **Syslog デーモンと Log Analytics エージェントの両方を再起動**する必要があります。
    

---

## 補足：他の選択肢について

- **OMS Gateway のデプロイ:** ログフォワーダーが直接インターネットに接続できない閉域網にある場合に検討されますが、標準的な構成における必須ステップではありません。
    
- **Syslog デーモンから直接 Sentinel へ送信:** Syslog デーモン自体が直接クラウドに送信するのではなく、必ずローカルにインストールされたエージェントを介して通信を行うのが正しい構成です。

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
1. エンティティ（vm1）のホバー表示

調査グラフ内で仮想マシン（vm1）などのエンティティにマウスを合わせると、そのリソースに関する**「インサイト（Insights）」**の概要が表示されます。

- **the running processes:** 図中のアラート名が「New processes ob...（検出された新しいプロセス）」となっていることから、このインシデントはプロセスの実行に関連しています。センチネルのホスト・インサイトでは、対象マシンで実行されているプロセスの数やリストを確認できるため、この選択肢が最適です。
    
- 他の選択肢（NSG ルールや 5 件のログなど）は、ホバー時のクイック表示ではなく、詳細プロパティや別途クエリを実行して確認する情報です。
    

2. インシデント関連アイテムへの移動

右側のツールバーにある各ボタンの役割は以下の通りです。

- **Timeline（タイムライン）:** インシデントに関連するアラート、ブックマーク、エンティティの動きを**時系列（Chronological order）**で表示します。インシデントに関連する個々の「アイテム（出来事）」を追跡するために使用します。
    
- **Entities:** インシデントに関与しているエンティティ（ユーザー、IP、ホストなど）の一覧を表示します。
    
- **Info:** インシデントの重大度、ステータス、所有者などの基本情報を表示します。
    
- **Insights:** 選択したエンティティに対して定義済みの分析クエリを実行し、異常な活動がないかを確認します。

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
1. Hunting ページの選択

まず、脅威ハンティングを行うための専用ページである **[Hunting（捜索）]** を選択します。ここには、特定の攻撃手法を検知するための定義済みクエリが多数用意されています。

2. 戦術（Tactics）によるフィルタリング

「資格情報アクセス（Credential Access）」は MITRE ATT&CK フレームワークにおける特定の**戦術（Tactic）**にあたります。

- **Filter by tactics** を使用して、「Credential Access」を選択することで、数百あるクエリの中から、資格情報の窃取に関連するものだけに絞り込むことができます。
    

3. Run All Queries の実行

フィルタリングによって対象を絞り込んだ状態で **[Run All Queries（すべてのクエリを実行）]** を選択します。

- これにより、現在リストに表示されている（＝資格情報アクセスに関連する）すべてのハンティングクエリが一括で実行され、異常なアクティビティがないかを確認できます。
    

---

## 補足

Adatum 社のケーススタディにある「HuntingQuery1 が自動的に実行されるようにする」という要件は、このハンティングページ内でのカスタムクエリの動作設定に関連するものですが、今回の「特定の戦術に沿ってすべてをクエリする」という手順においては、上記の標準的なフローが最適解となります。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/12/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 13 ページを表示しています。

410問中**121 - 130**問 を表示
