---
title: "SC-200試験 - 無料の実際のQ&A、6ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/6/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#51 トピック1

HOTSPOT -  
  
Microsoft Purview を使用する Microsoft 365 E5 サブスクリプションがあり、User1 というユーザーがいます。User1  
  
は、Microsoft Teams を使用して、会社の Microsoft OneDrive フォルダーにある Microsoft Power BI レポート ファイルを外部ユーザーと共有しました。  
  
共有された Power BI レポート ファイルを特定する必要があります。  
  
検索はどのように設定すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image192.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)   [議論   27](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)

**正解:** ![](https://img.examtopics.com/sc-200/image414.png)

**解説:**
Power BIレポートの共有アクティビティを特定するための検索設定です。

1. **監査ログ検索 (Audit log search)**: ファイルの共有やアクセス履歴を確認するには、Microsoft Purviewの監査ログ検索機能を使用します。（コンテンツ検索はファイルの中身を探すもので、共有`操作`を探すものではありません。）
2. **共有およびアクセス要求のアクティビティ (Sharing and access request activities)**: 「アクティビティ」フィルタで、共有に関連するイベント（「共有リンクの作成」や「ファイル共有」など）を選択します。

質問#52 トピック1

ドラッグ アンド ドロップ  
\-  
  
ケース スタディ  
\-  
  
これはケース スタディです。ケース スタディは個別に時間制限がありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケース スタディとセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケース スタディに含まれる質問に回答するには、ケース スタディで提供される情報を参照する必要があります。ケース スタディには、ケース スタディで説明されているシナリオに関する詳細情報を提供する展示資料やその他のリソースが含まれている場合があります。各質問は、このケース スタディの他の質問とは独立しています。  
  
このケース スタディの最後に、確認画面が表示されます。この画面では、試験の次のセクションに進む前に回答を確認し、変更を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケース スタディを開始するには  
\-  
このケース スタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケース スタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。 ケース スタディに \[すべての情報\] タブがある場合、表示される情報は、後続のタブに表示される情報と同じであることに注意してください。 質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要  
\-  
  
Litware Inc. は再生可能エネルギー会社です。  
  
Litware には、ボストンとシアトルにオフィスがあります。 Litware には、米国全土にリモート ユーザーもいます。 クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境  
\-  
  
ID 環境  
\-  
  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。  
  
Microsoft 365 環境  
\-  
  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。 Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています  
  
Azure環境  
\-  
  
Litwareは、litware.com Azure ADテナントにリンクされたAzureサブスクリプションを所有しています。このサブスクリプションには、次の表に示すように、米国東部Azureリージョンのリソースが含まれています。  
  
![](https://img.examtopics.com/sc-200/image215.png)  
  
ネットワーク環境  
\-  
  
Litware の各オフィスはインターネットに直接接続し、Azure サブスクリプションの仮想ネットワークへのサイト間 VPN 接続があります。  
  
オンプレミス環境  
\-  
  
オンプレミス ネットワークには、次の表に示すコンピューターが含まれます。  
  
![](https://img.examtopics.com/sc-200/image216.png)  
  
現在の問題  
\-  
  
ユーザーが両方のオフィスに同時に接続すると、Microsoft Defender for Cloud Apps で誤検知アラートが頻繁に生成されます。  
  
計画されている変更と要件  
  
計画されている変更  
\-  
  
Litware では、次の変更を実装する予定です。  
  
• Azure サブスクリプションに Microsoft Sentinel を作成して構成します。  
• Azure AD テスト ユーザー アカウントを使用して、Microsoft Sentinel の機能を検証します。  
  
ビジネス要件  
\-  
  
Litware では、次のビジネス要件を特定しています。  
  
• 可能な限り、最小権限の原則を使用する必要があります。  
• 他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
• Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
• すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
  
Azure Information Protection の要件  
  
機密ラベルが付いていて Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection – データ検出ダッシュボードから利用できる必要があります。  
  
Microsoft Defender for Endpoint の要件  
  
Microsoft Defender for Cloud Apps のすべての未承認アプリは、Microsoft Defender for Endpoint を使用して Windows 10 コンピューター上でブロックされる必要があります。  
  
Microsoft Defender for Cloud Apps のセキュリティ要件  
  
Microsoft Defender for Cloud Apps は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Microsoft Defender for Cloud の要件  
  
すべてのサーバーが、同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Microsoft Sentinel の要件  
  
Litware は、次の Microsoft Sentinel の要件を満たしている必要があります。  
  
• Microsoft Sentinel と Microsoft Defender for Cloud Apps を統合します。  
• admin1 という名前のユーザーが Microsoft Sentinel プレイブックを構成できるようにします。  
• カスタム クエリに基づいて Microsoft Sentinel 分析ルールを作成します。ルールは、プレイブックの実行を自動的に開始する必要があります。  
• 特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
• Azure AD テスト ユーザー アカウントによる Microsoft Office 365 への受信アクセスが検出されるとアラートを生成するテスト ルールを作成します。ルールによって生成されたアラートは、テスト ユーザー アカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。  
  
ビジネス要件を満たすようにDC1を構成する必要があります。  
  
どの3つのアクションを順番に実行する必要がありますか？回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image217.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)

**正解:** ![](https://img.examtopics.com/sc-200/image218.png)

**解説:**
DC1にMicrosoft Defender for Identityセンサーをインストールする手順です。

1. **Microsoft 365 Defenderポータルからインストーラーパッケージをダウンロードする**: まず、ポータルからセンサーのセットアップファイル（`ATPSensorSetup.exe`を含むzip）とアクセスキーを入手します。
2. **ATPSensorSetup.exeを実行する**: DC1上でインストーラーを実行します。
3. **アクセスキーを入力する**: インストールウィザードまたは構成時に、ポータルから取得したアクセスキーを入力してセンサーをワークスペースに登録します。

質問#53 トピック1

Microsoft PurviewとMicrosoft Teamsを使用するMicrosoft 365サブスクリプションをご利用です。Team1  
  
というチームがあり、Project1というプロジェクトがあります。  
  
2023年2月1日から2023年2月10日の間にTeam1のチームサイトに保存されたProject1ファイルを特定する必要があります。  
  
どのKQLクエリを実行すればよいでしょうか？

- A. (c:c)(プロジェクト1)(日付=(2023-02-01)..日付=(2023-02-10))
- B. AuditLogs -  
 | タイムスタンプが (datetime(2023-02-01)..datetime(2023-02-10)) の間  
 | ファイル名に「Project1」が含まれる
- C. プロジェクト1(c:c)(日付=2023-02-01..2023-02-10)
- D. AuditLogs -  
 | Timestamp > ago(10d)  
 | FileNameに「Project1」が含まれる

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)   [議論   22](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)  

**解説:**
特定期間にTeam1のサイトに保存されたProject1ファイルを特定するKQLクエリです。
**`Project1(c:c)(date=2023-02-01..2023-02-10)`**: これはコンテンツ検索（KQL）の構文で、`c:c` はコンテンツ（content）プロパティとコンテナ（container）プロパティなどを広範に検索するショートカット的記法（または特定の検索プロパティの組み合わせ）を示唆しており、キーワード "Project1" と日付範囲を指定しています。
選択肢BやDの `AuditLogs` はKustoクエリ（KQL）ですが、通常Advanced HuntingやSentinelで使用されるテーブル名であり、コンテンツ検索（eDiscovery）のコンテキストではキーワードクエリが使用されます。ここでは「保存されたファイルを特定する（中身やメタデータ）」という文脈から、コンテンツ検索の構文であるCが正解として選ばれています。（※ただし、実務的なKQLとしては `LastModifiedTime` や `Created` プロパティを使うのが一般的ですが、試験特有の構文として理解する必要があります。）

*コミュニティ投票の配分*

C（60％）

B（35％）

5%

質問#54 トピック1

Microsoft Defender for Endpoint を使用する Microsoft 365 E5 サブスクリプションをお持ちです。AlertInfo  
  
、AlertEvidence、DeviceLogonEvents テーブルをリンクするクエリを作成する必要があります。ソリューションは、テーブル内のすべての行を返す必要があります。  
  
どの演算子を使用すればよいでしょうか？

- A. 検索 \*
- B. ユニオン種別 = 内部
- C. 結合の種類 = 内部
- D. hint.remote を評価する =

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)  

**解説:**
Advanced Huntingで複数のテーブル（AlertInfo, AlertEvidence, DeviceLogonEvents）を結合し、すべての行（一致するもの）を返すには `join` 演算子を使用します。
**`union`** (A) はテーブルの行を縦に積み上げる（結合ではなく統合）操作です。
**`join kind=inner`** (B) は、指定したキー列の値が両方のテーブルに存在する場合にのみ行を結合して返します。設問の「リンクする」という目的には `join` が適切です。（※選択肢Cの "結合の種類" は日本語訳の揺らぎと思われますが、構文としては `join kind=inner` が正しいためBが選択されます。）

*コミュニティ投票の配分*

B（83％）

C（17％）

質問#55 トピック1

100台のWindows 10デバイスを含むMicrosoft 365 E5サブスクリプションを所有しています。  
  
これらのデバイスをMicrosoft Defender 365にオンボードします  
  
。Microsoft 365 Defenderポータルから、オンボードしたデバイスへのリモートシェル接続を開始できることを確認する必要があります。  
  
まず何をすべきでしょうか？

- A. Microsoft 365 Defender のアクセス許可を変更します。
- B. デバイス グループを作成します。
- C. Microsoft 365 Defender ポータルのエンドポイント設定の高度な機能から、自動調査を有効にします。
- D. ロールベースのアクセス制御 (RBAC) を構成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)   [議論   31](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)  

**解説:**
オンボードしたデバイスへのリモートシェル接続（ライブ応答 / Live Response）を開始するには、まずMicrosoft 365 Defenderポータルの設定でこの機能を有効にする必要があります。
**「設定」 > 「エンドポイント」 > 「高度な機能 (Advanced features)」** に移動し、**「ライブ応答 (Live Response)」** をオンにします。
RBACの設定も重要ですが、機能自体が有効化されていなければ権限があっても使用できません。

*コミュニティ投票の配分*

C（53％）

D（47％）

質問#56 トピック1

HOTSPOT  
\-  
  
Microsoft Defender for Endpoint を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
以下の要件を満たす検出ルールを作成する必要があります。  
  
• 重大なソフトウェア脆弱性を持つデバイスが過去 1 時間以内にアクティブだった場合にトリガーされる  
• 重複する結果の数を制限する  
  
KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択肢は 1 つにつき 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image219.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)

**正解:** ![](https://img.examtopics.com/sc-200/image220.png)

**解説:**

1. **`DeviceTvmSoftwareVulnerabilities`**: ソフトウェアの脆弱性情報を持つテーブルから開始します。
2. **`join kind=inner DeviceLogonEvents on DeviceName`**: デバイスのログオンイベント情報（アクティブ状態の確認用）と結合します。`inner`結合により、脆弱性があり、かつログオンイベントがあるデバイスのみが残ります。
3. **`where VulnerabilitySeverityLevel == 'Critical'`**: 重大な（Critical）脆弱性を持つものにフィルタリングします。
4. **`and Timestamp > ago(1h)`**: 過去1時間以内にログオンイベントがあった（アクティブだった）ものに絞り込みます。（`Timestamp`は`DeviceLogonEvents`由来）

質問#57 トピック1

HOTSPOT  
\-  
  
Microsoft Teams を使用する Microsoft 365 E5 サブスクリプションをご利用です。Microsoft  
  
Purview コンプライアンス ポータルを使用して、ユーザーの Teams チャットのコンテンツ検索を実行する必要があります。ソリューションでは、検索範囲を最小限に抑える必要があります。  
  
コンテンツ検索はどのように構成すればよいでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image221.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)

**正解:** ![](https://img.examtopics.com/sc-200/image222.png)

**解説:**
User1のTeamsチャットコンテンツを検索し、範囲を最小限にする設定です。

1. **場所**: **「Exchangeメールボックス」** を選択します。Teamsのチャット履歴（1対1、グループチャット）は、参加者のExchange Onlineメールボックス内の隠しフォルダに保存されるため、User1のメールボックスを検索対象にします。（Teamsチャット自体を場所として選ぶのではなく、メールボックスを選びます。）
2. **クエリ**: **`Type: "Instant messages"`**（または `Kind:im`）を指定します。これにより、メールやカレンダーアイテムなどを除外し、Teamsチャット（インスタントメッセージ）のみを抽出できます。

質問#58 トピック1

Microsoft 365 E5 サブスクリプションに Linux デバイス 100 台が含まれており、デバイスは Microsoft Defender 365 にオンボードされています。Microsoft  
  
365 Defender ポータルを使用して、デバイスから調査パッケージの収集を開始する必要があります。  
  
どのような対応アクションを実行すればよいでしょうか？

- A. ウイルススキャンを実行する
- B. 自動調査を開始する
- C. 調査パッケージの収集
- D. ライブレスポンスセッションを開始する

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)   [議論   19](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)  

**解説:**
Linuxデバイスから調査情報を収集するには、Defender for Endpointの応答アクションである **「調査パッケージの収集 (Collect investigation package)」** を使用します。
これはWindowsだけでなく、macOSやLinuxでもサポートされている主要なトリアージアクションです。自動調査（Automated investigation）は現在Linuxでは限定的あるいはサポート対象外の機能が含まれる場合があるため、手動でのパッケージ収集が最も確実な初期対応です。

*コミュニティ投票の配分*

C（71％）

D（29％）

質問#59 トピック1

機密ファイルが外部に共有された場合にアラートを生成し、修復アクションをトリガーするように、Microsoft Defender for Cloud Apps を構成する必要があります。Microsoft  
  
365 Defender ポータルで実行する必要がある 2 つのアクションはどれですか？ 正解はそれぞれ解答の一部を示しています。  
  
注: 正解は 1 点です。

- A. \[設定\] から \[クラウド アプリ\] を選択し、\[Microsoft Information Protection\] を選択してから、\[このテナントからの Microsoft Information Protection の機密ラベルとコンテンツ検査警告のファイルのみをスキャンする\] を選択します。
- B. クラウド アプリから \[ファイル\] を選択し、\[ファイルの種類\] を \[ドキュメント\] にフィルターします。
- C. \[設定\] から \[クラウド アプリ\] を選択し、\[Microsoft Information Protection\] を選択して \[ファイル\] を選択し、ファイル監視を有効にします。
- D. クラウド アプリから \[ファイル\] を選択し、アプリを Office 365 にフィルターします。
- E. クラウド アプリから \[ファイル\] を選択し、検索から \[新しいポリシー\] を選択します。
- F. \[設定\] から \[クラウド アプリ\] を選択し、\[Microsoft Information Protection\] を選択して、\[新しいファイルで Microsoft Information Protection の機密ラベルとコンテンツ検査の警告を自動的にスキャンする\] を選択します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)

**正解：** CF [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)  

**解説:**
機密ファイルが外部共有された際にアラートと修復を行うためのDefender for Cloud Apps設定です。

1. **F. Information Protection連携の有効化**: 「設定」 > 「クラウドアプリ」 > 「Information Protection」で、**「新しいファイルでMicrosoft Information Protectionの機密ラベル...を自動的にスキャンする」** を選択し、DCAがファイルのラベル情報を読めるようにします。
2. **C. ファイル監視の有効化**: 同設定メニューで「ファイル」を選択し、ファイル監視を有効にします。（※選択肢の表現が少し独特ですが、ファイルポリシーを作成する前提として、これらの基盤設定が必要です。あるいは、Cが「ファイルポリシーの作成」を意図している場合もありますが、Fの設定は必須です。）
※一般的には「ファイルポリシーを作成する」というアクションが必要ですが、選択肢の中で設定手順として正しい組み合わせを選びます。

*コミュニティ投票の配分*

CF（100％）

質問#60 トピック1

Microsoft Purview を使用する Microsoft 365 サブスクリプションをご利用です。  
  
会社には Project1 というプロジェクトがあります。  
  
件名に Project1 という単語が含まれるすべてのメールメッセージを特定する必要があります。このソリューションでは、Project1 に携わったユーザーのメールボックスのみを検索する必要があります。  
  
どうすればよいでしょうか？

- A. ユーザーデータ検索を実行します。
- B. 記録管理処分を作成します。
- C. 監査検索を実行します。
- D. コンテンツ検索を実行します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/6/#)  

**解説:**
件名に "Project1" を含むメールを、特定の関与ユーザーのメールボックスのみから検索するには、Microsoft Purviewの **「コンテンツ検索 (Content search)」** を使用します。
コンテンツ検索では、検索対象の場所（特定のユーザーメールボックス）を指定し、キーワードクエリ（`Subject:"Project1"`）を使用して条件に合致するアイテムを抽出できます。「ユーザーデータ検索」という特定の機能名はPurviewにはなく（DSRなどのコンテキストではありますが）、一般的なメール検索にはコンテンツ検索が標準的です。

*コミュニティ投票の配分*

D（86％）

14%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/5/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 6 ページ目を表示しています。

410問中**51 - 60**問 を表示
