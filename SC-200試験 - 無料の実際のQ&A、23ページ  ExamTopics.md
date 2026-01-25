---
title: "SC-200試験 - 無料の実際のQ&A、23ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/23/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#94 トピック3

HOTSPOT  
\-  
  
Azureサブスクリプションを4つ持っています。サブスクリプションの1つにはMicrosoft Sentinelワークスペースが含まれています。Azure  
  
Policyを使用してサブスクリプションからデータを収集するには、Microsoft Sentinelデータコネクタをデプロイする必要があります。このソリューションでは、サブスクリプション内の新規および既存のリソースにポリシーが適用されるようにする  
  
必要があります。すべてのリソースを確実に監視するには、どのタイプのコネクタをプロビジョニングし、何を使用する必要がありますか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image231.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)

**正解:** ![](https://img.examtopics.com/sc-200/image232.png)

**解説:**
Azure Policyを使用して、複数のサブスクリプション内のすべてのリソース（新規作成含む）からデータを収集するための設定です。

1. **Connector type**: **「Azure Activity」**。Azure Activityコネクタは、サブスクリプションレベルの操作ログを収集する最も基本的なコネクタです。
2. **Use**: **「Azure Policy」**。Azure Activityコネクタの設定ページには「Launch Azure Policy Assignment Wizard」機能があり、所定のポリシー定義（"Configure Azure Activity logs to stream to specified Log Analytics workspace"）を管理グループやサブスクリプションスコープに割り当てることで、全リソースからのログ送信を強制・自動化できます。

質問#95 トピック3

Microsoft Sentinel ワークスペースが 50 個あります。Azure  
  
ポータルの 1 つのページで、すべてのワークスペースのすべてのインシデントを確認する必要があります。このソリューションでは、管理の手間を最小限に抑える必要があります。Azure  
  
ポータルのどのページを使用すればよいでしょうか。

- A. Microsoft Sentinel - インシデント
- B. Microsoft Sentinel - ワークブック
- C. マイクロソフトセンチネル
- D. Log Analytics ワークスペース

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)   [議論   17](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)  

**解説:**
50個のワークスペースのインシデントを一元的に管理する方法です。
**「Microsoft Sentinel - Incidents (インシデント)」**: Sentinelのポータルには「複数ワークスペースの表示」機能があります。インシデントブレードのフィルタで複数のワークスペースを選択するだけで、それらのワークスペースのすべてのインシデントを1つのリストに統合表示できます。特別な設定不要で、管理の手間が最小限です。

*コミュニティ投票の配分*

A（60％）

C（31％）

9%

質問#96 トピック3

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
  
• 可能な限り、最小権限の原則に従います。 •可能  
な限り、管理の労力を最小限 に抑えます。  
  
- A. カスタム詳細
- B. エンティティマッピング
- C. イベントのグループ化
- D. アラートの詳細

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)  

**解説:**
Adatumの要件「1人のユーザーがAzure Cloud Shellを複数回起動した...複数のアラートが、1つのインシデントとして統合されるようにする」を満たすための設定です。
**「Entity mapping (エンティティマッピング)」**: アラートのグループ化（インシデント統合）を行うためには、アラート間で共通するキー（この場合は「User (Account)」）が必要です。分析ルールの設定で「Entity mapping」を定義し、Accountエンティティにユーザー名をマッピングすることで、Sentinelは「同じユーザーによるアラート」であることを認識し、インシデント設定（Incident grouping）に基づいてこれらを1つのインシデントにまとめることができるようになります。

*コミュニティ投票の配分*

B（75％）

D（17％）

8%

質問#97 トピック3

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
• 可能な限り、組み込みの ASIM パーサーを使用します。ビジネス  
  
要件 -  
  
Adatum では、次のビジネス要件が示されています。  
  
• 可能な限り、最小権限の原則に従います。  
• 可能な限り、管理の労力を最小限に抑えます最初に何を作成すればよいですか?  
  
- A. インシデントトリガーを含むプレイブック
- B. アラートトリガー付きのプレイブック
- C. Azure Automationルール
- D. エンティティトリガーを含むプレイブック

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)   [議論   14](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)  

**解説:**
Adatumの要件「App1（自動化ルール）を使用できることを確認する」に関連して、最初に作成すべきリソースです。
**「Playbook with incident trigger (インシデントトリガーを含むプレイブック)」**: Sentinelの自動化ルール (Automation rule) からプレイブックを呼び出すためには、そのプレイブックが **「Microsoft Sentinel Incident」トリガー** を使用して作成されている必要があります（アラートトリガーのプレイブックは、分析ルールから直接呼び出す古い方式で主に使用されますが、新しいAutomation ruleからはインシデントトリガーが標準です）。したがって、まずインシデントトリガーを持つプレイブックを作成する必要があります。

*コミュニティ投票の配分*

A（77％）

14%

9%

質問#98 トピック3

HOTSPOT -  
  
ケース スタディ -  
  
これはケース スタディです。ケース スタディは個別に時間が計測されません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケース スタディとセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケース スタディに含まれる質問に回答するには、ケース スタディで提供される情報を参照する必要があります。ケース スタディには、ケース スタディで説明されているシナリオに関する詳細情報を提供する展示資料やその他のリソースが含まれている場合があります。各質問は、このケース スタディの他の質問とは独立しています。  
  
このケース スタディの最後に、確認画面が表示されます。この画面では、試験の次のセクションに進む前に回答を確認し、変更を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケース スタディを開始するには -  
このケース スタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケース スタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。 ケース スタディに \[すべての情報\] タブがある場合、表示される情報は、後続のタブに表示される情報と同じであることに注意してください。 質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
  
Adatum Corporation は、ニューヨーク、シカゴ、サンフランシスコに支社を持つ、米国を本拠地とする金融サービス会社です。  
  
既存の環境 -  
  
ID 環境 -  
  
オンプレミス ネットワークには、adatum.com という名前の Azure AD テナントと同期する corp.adatum.com という名前の Active Directory ドメイン サービス (AD DS) フォレストが含まれています。 すべてのユーザーとグループの管理タスクは、corp.adatum.com で実行されます。corp.adatum.com ドメインには、adatum.com と同期する Group1 という名前のグループが含まれています。  
  
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
• corp.adatum.com ユーザー アカウントのパスワード リセットの量が通常よりも多いことが検出されるようにします。  
• ASIM パーサーを使用するクエリに関連するオーバーヘッドを最小限に抑えます。  
• Group1 のメンバーがプレイブックを作成および編集できるようにします。  
• 可能な限り、組み込みの ASIM パーサーを使用します。ビジネス  
  
要件 -  
  
Adatum では、次のビジネス要件が示されています。•  
  
可能な限り、最小権限の原則に従います。 •  
可能な限り、管理の労力を最小限に抑えます。回答するには、回答エリアで適切な選択肢を選択してください。注意：正解ごとに1ポイント加算されます。  
  
![](https://img.examtopics.com/sc-200/image236.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)

**正解:** ![](https://img.examtopics.com/sc-200/image434.png)

**解説:**
Adatumの要件「パスワードリセットの量が通常よりも多いことを検出する」および「可能な限り組み込みのASIMパーサーを使用する」を満たすクエリです。

1. **`_Im_Audit`**: 監査ログ用のASIM統合パーサー関数です。ユーザー管理や認証関連のイベントを正規化して検索できます。
2. **`where Operation =~ "Password reset"`**: パスワードリセット操作をフィルタリングします（ASIMの正規化フィールド名を使用）。
3. **`summarize count() by ActorUser`**: 実行者（ActorUser）ごとにリセット回数を集計し、しきい値判定を行います。

質問#99 トピック3

HOTSPOT -  
  
ケース スタディ -  
  
これはケース スタディです。ケース スタディは個別に時間が計測されません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケース スタディとセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケース スタディに含まれる質問に回答するには、ケース スタディで提供される情報を参照する必要があります。ケース スタディには、ケース スタディで説明されているシナリオに関する詳細情報を提供する展示資料やその他のリソースが含まれている場合があります。各質問は、このケース スタディの他の質問とは独立しています。  
  
このケース スタディの最後に、確認画面が表示されます。この画面では、試験の次のセクションに進む前に回答を確認し、変更を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケース スタディを開始するには -  
このケース スタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケース スタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。 ケース スタディに \[すべての情報\] タブがある場合、表示される情報は、後続のタブに表示される情報と同じであることに注意してください。 質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
  
Adatum Corporation は、ニューヨーク、シカゴ、サンフランシスコに支社を持つ、米国を本拠地とする金融サービス会社です。  
  
既存の環境 -  
  
ID 環境 -  
  
オンプレミス ネットワークには、adatum.com という名前の Azure AD テナントと同期する corp.adatum.com という名前の Active Directory ドメイン サービス (AD DS) フォレストが含まれています。 すべてのユーザーとグループの管理タスクは、corp.adatum.com で実行されます。corp.adatum.com ドメインには、adatum.com と同期する Group1 という名前のグループが含まれています。  
  
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
• 可能な限り、組み込みの ASIM パーサーを使用します。ビジネス  
  
要件 -  
  
Adatum では、次のビジネス要件が示されています。  
  
• 可能な限り、最小権限の原則に従います。  
• 可能な限り、管理の労力を最小限に抑えますクエリはどのように設定すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。注：正しい選択ごとに1ポイント獲得できます。  
  
![](https://img.examtopics.com/sc-200/image238.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)   [議論   14](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)

**正解:** ![](https://img.examtopics.com/sc-200/image435.png)

**解説:**
Adatumの要件「Webapp1からデータを動的に取得する（Workbookクエリ）」を満たすKQL演算子です。
**`externaldata`**: KQLクエリ内から外部のデータソース（Azure Blob StorageやWeb API経由のCSV/JSONファイルなど）のアドホックデータを直接読み込むための演算子です。Workbook等で外部システムデータを動的に参照する場合に使用します。

質問#100 トピック3

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
  
Adatum では、次のビジネス要件が特定されています。•  
  
可能な限り、最小権限の原則に従います。  
• 可能な限り、管理の労力を最小限に抑えます。  
  
Server1 のイベント監視を構成する必要があります。  
  
- A. Microsoft Sentinel自動化ルール
- B. Azure Event Gridトピック
- C. Microsoft Sentinel のスケジュールされたクエリ ルール
- D. データ収集ルール（DCR）

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)  

**解説:**
Adatumの要件「Server1（オンプレミス）のセキュリティイベントログを監視する（AMAコネクタ経由）」に必要な構成要素です。
**「Data collection rule (DCR)」**: Azure Monitor Agent (AMA) を使用してWindowsイベントログを収集するには、DCR（データ収集ルール）を作成し、収集するイベントの種類（System, Security, Applicationなど）とレベル、および対象のリソース（Server1）を定義して関連付ける必要があります。

*コミュニティ投票の配分*

D（100％）

質問#101 トピック3

HOTSPOT  
\-  
  
ケース スタディ  
\-  
  
これはケース スタディです。ケース スタディは個別に時間が計測されません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケース スタディとセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケース スタディに含まれる質問に回答するには、ケース スタディで提供される情報を参照する必要があります。ケース スタディには、ケース スタディで説明されているシナリオに関する詳細情報を提供する展示資料やその他のリソースが含まれている場合があります。各質問は、このケース スタディの他の質問とは独立しています。  
  
このケース スタディの最後に、確認画面が表示されます。この画面では、試験の次のセクションに進む前に回答を確認し、変更を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケース スタディを開始するには  
\-  
このケース スタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケース スタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。 ケース スタディに \[すべての情報\] タブがある場合、表示される情報は、後続のタブに表示される情報と同じであることに注意してください。 質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要  
\-  
  
Adatum Corporation は、ニューヨーク、シカゴ、サンフランシスコに支社を持つ、米国を本拠地とする金融サービス会社です。  
  
既存の環境  
\-  
  
ID 環境  
\-  
  
オンプレミス ネットワークには、adatum.com という名前の Azure AD テナントと同期する corp.adatum.com という名前の Active Directory ドメイン サービス (AD DS) フォレストが含まれています。 すべてのユーザーとグループの管理タスクは、corp.adatum.com で実行されます。corp.adatum.com ドメインには、adatum.com と同期する Group1 という名前のグループが含まれています。  
  
ライセンスの状態  
\-  
  
Adatum のすべてのユーザーには、Microsoft 365 ES ライセンスと Azure Active Directory Premium P2 ライセンスが割り当てられています。  
  
クラウド環境  
\-  
  
クラウド環境には、Microsoft 365 サブスクリプション、adatum.com テナントにリンクされた Azure サブスクリプション、および次の表に示すリソースが含まれています。  
  
![](https://img.examtopics.com/sc-200/image233.png)  
  
オンプレミス環境  
\-  
  
オンプレミスネットワークには、次の表に示すリソースが含まれています。  
  
![](https://img.examtopics.com/sc-200/image234.png)  
  
要件  
\-  
  
計画されている変更  
\-  
  
Adatum は、次の変更を行う予定です。  
  
• 次の KQL クエリを含む rulequery1 というクエリを実装します。  
  
![](https://img.examtopics.com/sc-200/image235.png)  
  
• rulequery1 に基づいてインシデントを生成する Microsoft Sentinel のスケジュールされたルールを実装します。  
  
Microsoft Defender for Cloud の要件  
  
Adatum では、次の Microsoft Defender for Cloud の要件が特定されています。  
  
• Group1 のメンバーは、Defender for Cloud プランを有効にして、規制コンプライアンス イニシアチブを適用できる必要があります。  
• Microsoft Defender for Servers プラン 2 は、すべての Azure 仮想マシンで有効にする必要があります。 •  
Server2 は、エージェントレス スキャンから除外する必要があります。  
  
Microsoft Sentinel の要件  
  
Adatum では、次の Microsoft Sentinel の要件が特定されています。  
  
• Infoblox1 からの NXDOMAIN 応答をもたらす DNS 要求の数を返す Advanced Security Information Model (ASIM) クエリを実装します。  
• 1 人のユーザーが Azure Cloud Shell を複数回起動したことに応答して rulequery1 によって生成される複数のアラートが、単一のインシデントとして統合されるようにします。  
• Microsoft Sentinel の AMA コネクタを介して Windows セキュリティ イベントを実装  
• Azure Cloud Shell が会社の SecOps チームによって起動された場合、rulequery1 によって生成されたインシデントが自動的に閉じられるようにします。  
• Webapp1 からデータを動的に取得するクエリを含む、Workbook1 という名前のカスタム Microsoft Sentinel ブックを実装します。  
• 指定されたブレイクグラス アカウントへのサインインを検出する Microsoft Sentinel ニアリアルタイム (NRT) 分析ルールを実装します。  
• Azure ポータルで Microsoft Sentinel の Hunting ページにアクセスされたときに、HuntingQuery1 が自動的に実行されるようにします。  
• corp.adatum.com ユーザー アカウントのパスワード リセットが通常よりも多く検出されるようにします。  
• ASIM パーサーを使用するクエリに関連するオーバーヘッドを最小限に抑えます。  
• Group1 のメンバーがプレイブックを作成および編集できるようにします。  
• 可能な限り、組み込みの ASIM パーサーを使用します。ビジネス  
  
要件  
\-  
  
Adatum では、次のビジネス要件が示されています。  
  
• 可能な限り、最小権限の原則に従います。  
• 可能な限り、管理の労力を最小限に抑えます  
  
ソリューションはMicrosoft Sentinelの要件を満たしている必要があります。  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正しい選択ごとに1ポイント獲得できます。  
  
![](https://img.examtopics.com/sc-200/image240.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)

**正解:** ![](https://img.examtopics.com/sc-200/image241.png)

**解説:**
Adatumの要件「SecOpsチームがAzure Cloud Shellを起動した場合はインシデントを自動的に閉じる」ためのクエリロジックです。

1. **`let SecOpsTeam = _GetWatchlist('SecOpsTeam')`**: Sentinelのウォッチリスト機能を使用して、SecOpsチームメンバーのリストを定義・取得します。ウォッチリストを使うことで、クエリ内に固有名詞をハードコードせずに管理できます。
2. **`where Caller in (SecOpsTeam)`**: 操作したユーザー（Caller）がウォッチリストに含まれているかどうかを判定します。これを除外条件や自動クローズ条件として使用します。

質問#102 トピック3

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
• 可能な限り、組み込みの ASIM パーサーを使用します。  
  
ビジネス要件 -  
  
Adatum では、次のビジネス要件が示されています。  
  
• 可能な限り、最小権限の原則に従います。  
• 可能な限り、管理の労力を最小限に抑えます。  
  
Group1 のメンバーが Microsoft Sentinel の要件を満たせるようにする必要があります  
  
。

- A. Microsoft Sentinel Playbook オペレーター
- B. ロジックアプリ貢献者
- C. 自動化オペレーター
- D. Microsoft Sentinel Automation 貢献者

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)  

*コミュニティ投票の配分*

B（100％）

質問#103 トピック3

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
• 可能な限り、組み込みの ASIM パーサーを使用します。  
  
ビジネス要件 -  
  
Adatum では、次のビジネス要件が示されています。  
  
• 可能な限り、最小権限の原則に従います。  
• 可能な限り、管理の労力を最小限に抑えます。  
  
HuntingQuery1 の構成が Microsoft Sentinel の要件を満たしていることを確認する必要があります  
  
。

- A. HuntingQuery1 をライブストリームに追加します。
- B. ウォッチリストを作成します。
- C. Azure Automation ルールを作成します。
- D. HuntingQuery1 をお気に入りに追加します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/23/#)  

*コミュニティ投票の配分*

D（100％）

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/22/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 23 ページを表示しています。

410問中**221 - 230**問 を表示
