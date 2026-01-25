---
title: "SC-200試験 - 無料の実際のQ&A、22ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/22/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#84 トピック3

ドラッグ＆ドロップ  
\-  
  
ネットワークには、Azure AD テナントと同期するオンプレミスの Active Directory Domain Services (AD DS) ドメインが含まれています。Sentinel1  
  
という Microsoft Sentinel ワークスペースがあります。Sentinel1  
  
でユーザーおよびエンティティ行動分析 (UEBA) を有効にし、AD DS ドメインからセキュリティイベントを収集する必要があります。3  
  
つのアクションのうち、順番に実行する必要があるのはどれですか？ 回答するには、アクションリストから適切なアクションを回答領域に移動し、正しい順序に並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image207.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)

**正解:** ![](https://img.examtopics.com/sc-200/image208.png)

**解説:**
オンプレミスAD DSからセキュリティイベントを収集し、UEBAを有効にするための手順です。

1. **Instal the Azure Monitor agent on the domain controllers**: ドメインコントローラーにAMA（Azure Monitor Agent）をインストールし、イベントログをAzureに送信できるようにします（Azure Arc経由など）。
2. **Configure the Data Collection Rules (DCR)**: DCRを作成し、収集するイベントIDや送信先（Sentinelワークスペース）を定義します。
3. **Enable Entity beavior analytics**: Sentinelの設定でUEBA機能をオンにし、データソースとしてActive Directory（MDIやAMA経由）を選択します。

質問#85 トピック3

Microsoft Sentinel ワークスペースを使用しています。  
  
監査ログとサインインログを使用して、ユーザーおよびエンティティ行動分析 (UEBA) を有効にしています。Azure  
  
AD テナントで以下のエンティティが検出されました。  
  
• アプリ名: App1  
• IP アドレス: 192.168.1.2  
• コンピューター名: Device1  
• 使用クライアントアプリ: Microsoft Edge  
• メール アドレス: <user1@company.com>  
• サインイン URL: <https://www.company.com>  
  
UEBA を使用して調査できるエンティティはどれですか？

- A. IPアドレスとメールアドレスのみ
- B. アプリ名、コンピュータ名、IPアドレス、メールアドレス、使用したクライアントアプリのみ
- C. IPアドレスのみ
- D. クライアントアプリとアプリ名のみを使用

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)  

**解説:**
UEBA (User and Entity Behavior Analytics) が分析・プロファイリング対象とするエンティティの種類です。
**「B. App Name, Computer Name, IP Address, Mail Address, and Client App Used only」**: UEBAはユーザー（Mail Address/Account）だけでなく、IPアドレス、ホスト（Computer Name）、アプリケーション（App Name）、クライアント情報など、多角的なエンティティの行動を学習し、異常を検知します。提示されたすべてのエンティティが調査対象となり得ます。

*コミュニティ投票の配分*

B（90％）

10%

質問#86 トピック3

HOTSPOT -  
  
Microsoft Sentinel ワークスペースを含む Azure サブスクリプションを所有しています。Kusto  
  
クエリ言語 (KQL) を使用して、以下の要件を満たすハンティング クエリを作成する必要があります。  
  
• 同じセキュリティ プリンシパルによってネットワーク セキュリティ グループ (NSG) のルールに加えられた異常な数の変更を特定する。  
• セキュリティ プリンシパルを Microsoft Sentinel エンティティに自動的に関連付ける。  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image209.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)

**正解:** ![](https://img.examtopics.com/sc-200/image433.png)

**解説:**
NSGルールに対する異常な変更を検出し、エンティティを関連付けるハンティングクエリです。

1. **`where OperationName == "NetworkSecurityGroups_SecurityRules_CreateOrUpdate"`**: NSGルールの作成/更新操作をフィルタリングします（テーブルはAzureActivity）。
2. **`| extend AccountCustomEntity = Caller`**: クエリ結果の「Caller」（操作したユーザー）カラムを、Sentinelの標準エンティティ「Account」にマッピングします。これにより、調査グラフなどでユーザーエンティティとして認識されます。

質問#87 トピック3

HOTSPOT  
\-  
  
Microsoft Sentinel ワークスペースがあります。  
  
カスタムブックのレポートビジュアルを構成する必要があります。ソリューションは以下の要件を満たす必要があります。  
• AppDisplayName のカウントと使用状況の傾向が含まれている必要があります。  
• TrendList 列がスパークラインビジュアルで使用可能である必要があります。KQL  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image211.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)

**正解:** ![](https://img.examtopics.com/sc-200/image212.png)

**解説:**
`AppDisplayName` ごとの使用回数を集計し、かつスパークライン（時系列のミニグラフ）を描画するための列を作成するクエリです。

1. **`make_list(Count)`**: `TrendList` 列を作成するために使用します。時間ごとの集計結果などをリスト形式（配列）に変換することで、ワークブックのSparklineビジュアライゼーションに入力できるようになります。
2. **`AppDisplayName`**: `summarize` 句のグループ化キーとして使用し、アプリごとにデータを集計します。

質問#88 トピック3

ドラッグ アンド ドロップ  
\-  
  
User1 と User2 という 2 人のユーザーと、workspace1 という Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。  
  
ユーザーがワークスペース 1 で次のタスクを実行できるようにする必要があります。  
• User1 は、インシデントを無視し、ユーザーにインシデントを割り当てることができる必要があります。  
• User2 は、分析ルールを変更できる必要があります。  
  
ソリューションでは、最小権限の原則を使用する必要があります。  
  
各ユーザーにはどのロールを割り当てる必要がありますか。 回答するには、適切なロールを正しいユーザーにドラッグします。各ロールは、1 回、複数回、またはまったく使用しない場合があります。コンテンツを表示するには、ペイン間の分割バーをドラッグするか、スクロールする必要がある場合があります。  
  
注: 正しい選択ごとに 1 ポイントが与えられます。  
  
![](https://img.examtopics.com/sc-200/image213.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)

**正解:** ![](https://img.examtopics.com/sc-200/image214.png)

**解説:**
ユーザーに必要な権限を与えるためのRBACロールの割り当てです。

1. **User1 (dismiss incidents, assign incidents)**: **「Microsoft Sentinel Responder」**。インシデントの管理（クローズ、割り当て、編集）権限を持ちます。
2. **User2 (modify Analytics rules)**: **「Microsoft Sentinel Contributor」**。分析ルール（Analytics rules）の作成、編集、削除を行うにはContributor権限が必要です。Responderにはこの権限はありません。

質問#89 トピック3

Microsoft 365 Defender データコネクタを使用する Microsoft Sentinel ワークスペースがあります。Microsoft  
  
Sentinel から Microsoft 365 のインシデントを調査します。Microsoft  
  
Defender for Cloud Apps によって生成されたアラートを含めるようにインシデントを更新する必要があります。  
  
何を使用すればよいでしょうか？

- A. Microsoft Sentinel のタイムライン カードのエンティティ サイド パネル
- B. Microsoft Sentinelのインシデントページのタイムラインタブ
- C. Microsoft Sentinelのインシデントページの調査グラフ
- D. Microsoft 365 Defender ポータルのアラートページ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)   [議論   30](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)  

**解説:**
調査中のインシデントに対し、関連するDefender for Cloud Apps (旧 MCAS) のアラートを追加・統合するシナリオです。
**「Entity side panel on the timeline card of Microsoft Sentinel」**: インシデントのタイムラインや調査画面でエンティティを選択すると、サイドパネルに関連情報が表示されます。そこから、そのエンティティに関連する他のアラート（まだインシデントに含まれていないもの）を確認し、手動で現在のインシデントに追加するアクションを実行できる場合があります。
また、調査グラフ (Investigation graph) からも同様の操作が可能ですが、正解Aが選択されている文脈としては、タイムラインビューからのピボット操作を指していると考えられます。

*コミュニティ投票の配分*

A（51％）

D（26％）

B（19％）

5%

質問#90 トピック3

Microsoft Sentinel ワークスペースがあります。  
  
以下のエンティティを含むインシデントを調査しています。  
• User1 というユーザーアカウント  
• IP アドレス 192.168.10.200  
• VM1 という Azure 仮想マシン  
• Server1 というオンプレミス サーバー  
  
インシデント ページを使用して、エンティティを侵害インジケーター (IoC) として直接ラベル付けする必要があります。  
  
どのエンティティにラベルを付けることができますか？

- A. 192.168.10.200
- B. VM1
- C. サーバー1
- D. ユーザー1

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)  

**解説:**
インシデントページから直接IoC（侵害指標）としてラベル付け（Threat Intelligenceへの追加）ができるエンティティの種類です。
**「192.168.10.200 (IP Address)」**: 現在のSentinelの機能では、IPアドレスやドメイン、ファイルハッシュなどのエンティティを、調査画面から直接「脅威インテリジェンス（IoC）」に追加することができます。これにより、以後の検知に活用できます。ユーザーやVM自体をIoCとして登録することは通常ありません。

*コミュニティ投票の配分*

A（100％）

質問#91 トピック3

Microsoft Sentinelワークスペースで、サインインログにユーザーとエンティティの行動分析（UEBA）が有効になっています。  
  
対話型サインインの失敗を確実に検出する必要があります。ソリューションは管理の手間を最小限に抑える必要があります。  
  
どのようなソリューションを使用すべきでしょうか？

- A. スケジュールされたアラートクエリ
- B. アクティビティログデータコネクタ
- C. UEBAアクティビティテンプレート
- D. 狩猟に関する質問

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)   [議論   25](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)  

**解説:**
対話型サインインの失敗（Anomaly）を、最小限の管理手間で検出する方法です。
**「UEBA activity template (UEBA アクティビティテンプレート)」**: Sentinelには「Analytics rule templates」として、UEBAデータを活用した異常検知ルール（例: "Anomalous sign-in detected" など）が用意されています。これを使用することで、ゼロからクエリを書く手間を省き、UEBAの成果を活用して異常なサインイン失敗などを検出できます。

*コミュニティ投票の配分*

C（72％）

A（28％）

質問#92 トピック3

HOTSPOT  
\-  
  
ハイブリッド Azure AD テナントにリンクされ、Sentinel1 という Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。Sentinel  
  
でユーザーおよびエンティティ行動分析 (UEBA) を有効にし、Active Directory ドメイン サービス (AD DS) から収集されたデータを使用するように UEBA を構成する必要があります。  
  
どうすればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image227.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)

**正解:** ![](https://img.examtopics.com/sc-200/image228.png)

**解説:**
オンプレミスAD DSからのデータをUEBAで使用するための構成です。

1. **Connector**: **「Microsoft Defender for Identity」**。MDIはオンプレミスADのシグナルを収集する主要なソリューションであり、SentinelのUEBAエンジンの最も重要なデータソースの1つです。MDIコネクタを有効にすることで、ID関連のリスクやアクティビティがSentinelに同期されます。
2. **Agent**: **「Azure Monitor Agent (AMA)」**。Windowsセキュリティイベントログなどを補完的に直接収集する場合、ドメインコントローラーやサーバーにAMAをインストールします。（MDIセンサーとは別に、ログ収集手段としてAMAが選択されます）

質問#93 トピック3

HOTSPOT  
\-  
  
カスタムブックを含むMicrosoft Sentinelワークスペースがあります。  
  
毎日のセキュリティアラートの数をクエリする必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• 過去30日間に発生したアラートを特定する。  
• 結果をタイムチャートで表示する。  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正しい選択肢は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image229.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/22/#)

**正解:** ![](https://img.examtopics.com/sc-200/image230.png)

**解説:**
過去30日間のセキュリティアラート数を日次のタイムチャートで表示するクエリです。

1. **`SecurityAlert`**: アラート情報が格納されているテーブルです。
2. **`| where TimeGenerated > ago(30d)`**: 過去30日間にフィルタリングします。
3. **`| summarize count() by bin(TimeGenerated, 1d)`**: `bin`関数を使って`TimeGenerated`を1日単位に丸め、その単位ごとに件数をカウントします。これがタイムチャート作成の定型句です。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/21/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 22 ページを表示しています。

410問中**211 - 220**問 を表示
