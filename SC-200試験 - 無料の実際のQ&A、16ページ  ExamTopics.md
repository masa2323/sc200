---
title: "SC-200試験 - 無料の実際のQ&A、16ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/16/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
トピック3

Azure Security Center によって生成されたセキュリティアラートを視覚的に表示するカスタム Azure Sentinel クエリを作成する予定です。  
棒グラフを表示するためのクエリを作成する必要があります。  
クエリには何を含めるべきですか？  

- A. 延長する
- B. ビン
- C. カウント
- D. ワークスペース

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)  

**解説:**
棒グラフ（Bar chart）を表示するためにデータを集計する際に使用する演算子です。
**「count (カウント)」**: 棒グラフの各バーの高さ（件数）を計算するために `count()` 関数（通常は `summarize count() by ...` の形式で）を使用します。
※時系列の棒グラフであれば `bin` も必要になりますが、単にカテゴリごとの分布（例：アラート重大度ごとの件数）を表示する場合など、`count` が主要な集計要素となります。設問が時系列に限定していないため、集計の基本となるCが正解とされています。

*コミュニティ投票の配分*

C（94％）

6%

質問#25 トピック3

Azure Sentinel を使用しています。Azure  
Storage アカウントキーが列挙されるたびに、ほぼリアルタイムでアラートを受信する必要があります。  
実行すべき 2 つのアクションはどれですか？ 正解はそれぞれ解答の一部です。  
注: 正解は 1 点です。  

- A. ライブストリームを作成する
- B. データコネクタを追加する
- C. 分析ルールを作成する
- D. ハンティングクエリを作成します。
- E. ブックマークを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)   [議論   48](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)

**正解:** BC [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)  

**解説:**
Storageアカウントキーの列挙をほぼリアルタイムで検出しアラートを受け取るための手順です。

1. **B. データコネクタを追加する**: まず、Azure Storageのアクティビティログ（Azure Activity）をSentinelに取り込む必要があります。
2. **C. 分析ルールを作成する**: 取り込んだログに対して、「List Storage Account Keys」などの操作を検出するクエリを含む「NRT (Near-Real-Time) 分析ルール」または通常の分析ルールを作成し、アラートを生成するように設定します。
※Livestream (A) はリアルタイム監視には使えますが、アラートの自動生成機能はありません。

*コミュニティ投票の配分*

紀元前（45％）

AD（37％）

他の

質問#26 トピック3

ホットスポット -  
Azure Sentinel をデプロイします。Azure  
上の Microsoft Teams と Linux 仮想マシンを監視するには、Azure Sentinel にコネクタを実装する必要があります。ソリューションは管理作業を最小限に抑える必要があります。  
各ワークロードにはどの種類のデータコネクタを使用すべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正解は 1 点です。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0013000001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0013100001.jpg) 参照:  
<https://docs.microsoft.com/en-us/azure/sentinel/connect-office-365> <https://docs.microsoft.com/en-us/azure/sentinel/connect-syslog>

**解説:**
各ワークロードに適したデータコネクタの選択です。

1. **Microsoft Teams**: **「Office 365」**。TeamsのログはOffice 365の監査ログの一部として収集されるため、Office 365データコネクタを使用します。
2. **Linux virtual machines**: **「Syslog」**。Linuxサーバーのログ収集には、Syslogエージェント（AMAまたはLegacy Agent）を使用し、Syslogデータコネクタ経由でSentinelに送信するのが標準的です。

質問#27 トピック3

Azure Sentinel で 127 件を超えるアラートを含むインシデントを調査しています。  
インシデントには、さらに調査が必要なアラートが 8 件あります。  
これらのアラートを別の Azure Sentinel 管理者にエスカレーションする必要があります。  
アラートを管理者に伝えるには、どうすればよいでしょうか？  

- A. Microsoftインシデント作成ルールを作成する
- B. インシデントのURLを共有する
- C. スケジュールされたクエリルールを作成する
- D. インシデントの割り当て

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)   [議論   14](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)  

**解説:**
インシデントに含まれる特定のアラートのエスカレーション（担当者変更）に関する設問ですが、Sentinelではアラート単位で個別に所有者を割り当てる機能はありません。インシデント全体に対して所有者を割り当てます。
**「インシデントの割り当て (Assign the incident)」**: インシデントの所有者（Owner）を別の管理者や専門家に変更することで、そのインシデント（および含まれるアラート群）の調査を引き継ぐことができます。
※「アラートを別の管理者にエスカレーションしたい」という要件に対して、最も実用的な機能としてインシデントの再割り当てが正解となります。

*コミュニティ投票の配分*

D（85％）

B（15％）

質問#28 トピック3

Azure Sentinel を構成しています。Azure  
Sentinel でサインインリスクイベントを表すインシデントが発生するたびに、Microsoft Teams メッセージをチャネルに送信する必要があります。Azure  
Sentinel で実行する必要がある 2 つのアクションはどれですか？ 正解はそれぞれ解決策の一部を示しています。  
注: 正解は 1 点です。  

- A. エンティティ動作分析を有効にします。
- B. インシデントをトリガーした分析ルールにプレイブックを関連付けます。
- C. Fusion ルールを有効にします。
- D. プレイブックを追加します。
- E. ワークブックを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)   [議論   29](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)

**正解** [：](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)BD🗳️  

**解説:**
サインインリスクイベント発生時にTeams通知を送る構成です。

1. **D. プレイブックを追加します**: Teamsへの投稿アクションを含むプレイブックを作成します。
2. **B. インシデントをトリガーした分析ルールにプレイブックを関連付けます**: 分析ルールの自動化設定、または自動化ルール(Automation rule)を使用して、インシデント作成時にプレイブックが実行されるように設定します。

*コミュニティ投票の配分*

BD（71％）

AB（21％）

8%

質問#29 トピック3

ドラッグ＆ドロップ -  
Azure Sentinel 分析ルールを使用して、Amazon Web Services (AWS) ログで特定の条件を検索し、インシデントを生成する必要があります。  
どの 3 つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
選択して配置:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0013300001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)

**Correct Answer:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0013400001.jpg) Reference:  
<https://docs.microsoft.com/en-us/azure/sentinel/detect-threats-custom>

**解説:**
AWSログからインシデントを生成する手順です。

1. **Connect AWS CloudTrail**: まず、AWSコネクタを使用してCloudTrailログをSentinelに取り込みます。
2. **Analytics rulesの作成**: 「Analytics」ブレードに移動し、「Create」>「Scheduled query rule」を選択します。
3. **Configure rule logic**: クエリ（KQL）やスケジュール、しきい値などを設定し、インシデント生成を有効にします。

質問#30 トピック3

環境は次のとおりです:  
  
Azure Sentinel -  
![](https://www.examtopics.com/assets/media/exam-media/04261/0013400002.png)  
✑ Microsoft 365 サブスクリプション  
✑ Microsoft Defender for Identity  
✑ Azure Active Directory (Azure AD) テナント  
すべての Active Directory メンバー サーバーおよびドメイン コントローラーからセキュリティ ログを収集するように Azure Sentinel を構成します。  
スタンドアロン センサーを使用して Microsoft Defender for Identity をデプロイします。Active  
Directory で機密性の高いグループが変更されたときにそれを検出できるようにする必要があります。  
実行する必要がある 2 つのアクションはどれですか。正解はそれぞれソリューションの一部を示します。  
注: 正解を選択するごとに 1 ポイントが加算されます。  

- A. ドメイン コントローラーの詳細な監査ポリシー構成設定を構成します。
- B. ドメイン コントローラーの組織単位 (OU) のアクセス許可を変更します。
- C. Microsoft 365 コンプライアンス センターで監査を構成します。
- D. ドメイン コントローラーで Windows イベント転送を構成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)

**Correct Answer:** AD [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)  

**解説:**
Microsoft Defender for Identity (MDI) の**スタンドアロンセンサー**を使用して、Active Directoryの機密グループ変更を検出するための設定です。スタンドアロンセンサーはドメインコントローラーに直接インストールされないため、イベントログをリモートで収集する必要があります。

1. **A. ドメイン コントローラーの詳細な監査ポリシー構成設定を構成します**: グループ変更イベント（Event ID 4728, 4729など）が生成されるように、監査ポリシーを適切に設定します。
2. **D. ドメイン コントローラーで Windows イベント転送を構成します**: スタンドアロンセンサーの場合、ドメインコントローラーからセンサーサーバーへ必要なWindowsイベントログを転送するために、Windows Event Forwarding (WEF) を構成する必要があります。

*Community vote distribution*

AD (100%)

質問#31 トピック3

Azure Sentinel を使用しています。  
セキュリティアナリストにカスタム Azure Sentinel ワークブックのクエリを編集する権限を付与するには、組み込みロールを使用する必要があります。このソリューションでは、最小権限の原則を適用する必要があります。  
アナリストにはどのロールを割り当てるべきでしょうか？  

- A. Azure Sentinel コントリビューター
- B. セキュリティ管理者
- C. Azure Sentinel レスポンダー
- D. ロジックアプリ貢献者

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)

**Correct Answer:** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)  

**解説:**
Sentinelワークブックの編集権限を持ち、かつ最小権限のロールです。
**「Azure Sentinel Contributor (Sentinel 共同作成者)」**: このロールは、ワークブック、分析ルール、その他のSentinelリソースを作成・編集する権限を持っています。
Responder（C）はインシデント管理が可能ですが、ワークブックの編集権限はありません。Security Admin（B）は権限が強すぎます。Logic App Contributor（D）はプレイブック用です。

*Community vote distribution*

A (100%)

質問#32 トピック3

Azure Sentinel でハンティングクエリを作成します。  
ハンティングクエリがクエリに一致を検出するとすぐに、Azure Portal で通知を受け取る必要があります。ソリューションは最小限の労力で実現する必要があります。  
どのようなツールを使用すればよいでしょうか？  

- A. プレイブック
- B. ノートブック
- C. ライブストリーム
- D. ブックマーク

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)   [議論   21](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)  

**解説:**
ハンティングクエリの一致をAzure Portalですぐに通知するための、最小労力の方法です。
**「ライブストリーム (Live Stream)」**: クエリをLive Streamセッションとして実行すると、新しいイベントがクエリに一致するたびにAzure Portal上で通知が表示されます。プレイブックのような複雑な設定なしで、一時的なリアルタイム監視を行うのに適しています。
※注: Live Streamは将来的に非推奨になる可能性がありますが、この設問の文脈（最小労力での通知）では正解となります。

*Community vote distribution*

C (56%)

A (44%)

質問#33 トピック3

Sub1 という Azure サブスクリプションと Microsoft 365 サブスクリプションがあります。Sub1 は、contoso.com という Azure Active Directory (Azure AD) テナントにリンクされています。workspace1  
という Azure Sentinel ワークスペースを作成します。workspace1 で、contoso.com 用の Azure AD コネクタと、Microsoft 365 サブスクリプション用の Office 365 コネクタをアクティブ化します。contoso.com  
への疑わしいサインインとそれに続く異常な Microsoft Office 365 アクティビティを含む、段階的な攻撃を検出するには、Fusion ルールを使用する必要があります。  
実行する必要がある 2 つのアクションはどれですか？ 正解はそれぞれソリューションの一部です。  
注: 正解はそれぞれ 1 ポイントです。  

- A. Office 365 コネクタ テンプレートに基づいてカスタム ルールを作成します。
- B. Azure Security Center に基づいて Microsoft インシデント作成ルールを作成します。
- C. Microsoft Cloud App Security コネクタを作成します。
- D. Azure AD Identity Protection コネクタを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)   [議論   63](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)

**Correct Answer:** CD [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/16/#)  

**解説:**
Fusionルールを使用して「疑わしいサインイン」と「異常なOffice 365アクティビティ」を含む段階的な攻撃を検出するために必要なコネクタです。

1. **Connectors**: Fusionエンジンは、複数のソースからの信号を相関させます。このシナリオでは、Azure AD Identity Protectionからの「疑わしいサインイン」信号と、Microsoft Defender for Cloud Apps (旧 MCAS) からの「異常なOffice 365アクティビティ」信号が必要です。
2. **C. Microsoft Cloud App Security コネクタを作成します**: Office 365のアクティビティ分析と異常検知に必要です。
3. **D. Azure AD Identity Protection コネクタを作成します**: リスキーなサインインの検出とアラート生成に必要です。
（※Office 365コネクタもログ収集には必要ですが、Fusionの高度な相関ロジックの入力としては、Identity ProtectionとMCASのアラート情報の重要性が高いとされます。）

*Community vote distribution*

CD (56%)

AD (42%)

2%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/15/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 16 ページを表示しています。

410問中**151 - 160**問 を表示
