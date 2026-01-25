---
title: "SC-200試験 - 無料の実際のQ&A、40ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/40/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#41 トピック7

オンプレミスのWindows 11 Proデバイスが1,000台あり、Microsoft Defender for Endpointにオンボードされています。Microsoft  
  
Defender XDRを使用するMicrosoft 365サブスクリプションを所有しています。  
  
攻撃者がデバイス上で以下の操作を実行したことが判明しました。  
  
• レジストリベースのウイルス対策除外のファイルシステムパスを変更した  
• 悪意のあるファイルをファイルシステムパスにダウンロードした  
  
デバイス上でライブレスポンスセッションを開始します。  
  
悪意のあるファイルを削除する必要があります。  
  
どのコマンドを実行すればよいでしょうか？

- A. 収集する
- B. getfile
- C. 元に戻す
- D. 修復する

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)  

**解説:**
Live Responseセッションで悪意のあるファイルを削除するコマンド。
**「Remediate (修復する)」**。
Live Responseには、ファイル削除などの修復アクションを実行する `remediate` コマンドが用意されています（プラットフォームやバージョンによりますが、選択肢の中で「悪意のあるファイルを処理する」コマンドとして最も適切です）。
`collect` は収集、`getfile` はダウンロード、`undo` は操作の取り消しです。
*補足*: 実際のLive Responseコマンド（Windows）では `Remediate` というコマンド自体よりも、アクションとして「Remediate」を選択するか、PowerShellで `Remove-Item` 等を使いますが、試験の選択肢として「Remediate」が正解とされています（おそらく自動修復アクションをトリガーする意図、あるいは抽象化されたコマンド）。

*コミュニティ投票の配分*

D（100％）

質問#42 トピック7

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションがあります。すべてのエンドポイントデバイスは Microsoft Defender for Endpoint にオンボードされています。Azure  
  
サブスクリプションには Workspace1 という Microsoft Sentinel ワークスペースが含まれています。すべての Microsoft Defender XDR イベントは Workspace1 に取り込まれます。Microsoft  
  
Entra テナントがあります。  
  
デバイスログで既知の脆弱性を検索する、query1 という KQL クエリを作成します。query1  
  
が 1 時間ごとに実行されるようにする必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。  
  
どのような構成を行うべきでしょうか。

- A. カスタム検出ルール
- B. 自動調査および対応（AIR）
- C. ウォッチリスト
- D. 自動化ルール

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)  

**解説:**
デバイスログ（Device Logs）で既知の脆弱性を検索するKQLクエリ（query1）を1時間ごとに定期実行する構成。
**「Custom detection rule (カスタム検出ルール)」**。
Defender XDR（旧Defender 365）のAdvanced Huntingにおいて、作成したクエリを「Detection rule」として保存することで、スケジュール実行（1時間、3時間、12時間、24時間など）を設定し、ヒットした場合にアラートやインシデントを作成できます。
「管理作業を最小限」という要件にも合致します（単にスケジュールを作成するだけ）。
Automation ruleはインシデント発生後の処理であり、Watchlistはデータ参照用、AIRはアラート後の調査です。

*コミュニティ投票の配分*

A（100％）

## トピック8 - テストレット1

質問1 トピック8

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Contoso Ltd. という会社には、北米各地に本社と 5 つの支社があります。本社はシアトルにあります。支社は、トロント、マイアミ、ヒューストン、ロサンゼルス、バンクーバーにあります。Contoso  
には、ニューヨークとサンフランシスコに支社がある Fabrikam, Ltd. という子会社があります。  
  
既存の環境 -  
  
エンド ユーザー環境 -  
Contoso のすべてのユーザーは、Windows 10 デバイスを使用しています。各ユーザーには、Microsoft 365 のライセンスが付与されています。また、Contoso の営業チームのメンバーには iOS デバイスが配布されています。  
  
クラウドとハイブリッド インフラストラクチャ -  
Contoso のすべてのアプリケーションは Azure にデプロイされています。Microsoft  
Cloud App Security を有効にします。Contoso  
と Fabrikam は、異なる Azure Active Directory (Azure AD) テナントを持っています。  
  
現在の問題 -  
Contoso 社のセキュリティチームは、多数のサイバーセキュリティアラートを受信して​​います。セキュリティチームは、どのサイバーセキュリティアラートが正当な脅威で、どれがそうでないかを特定するのに多くの時間を費やしています。  
Contoso の営業チームは、iOS デバイスのみを使用しています。営業チームのメンバーは、さまざまなサードパーティ ツールを使用して顧客とファイルを交換しています。過去に、営業チームはデバイスがフィッシング攻撃を受けたことがあります。Contoso  
のマーケティング チームには、外部ベンダーとのコラボレーション用に複数の Microsoft SharePoint Online サイトがあります。マーケティング チームでは、ベンダーがマルウェアを含むファイルをアップロードするインシデントが何度か発生しています。Contosoの経営陣は、セキュリティ侵害の疑いがあります。経営陣は、Microsoft Cloud App Security で保護されたアプリケーションのデータ アクセス、ダウンロード、削除など、  
過去 48 時間以内に 6 件を超えるアクティビティがあったファイルを特定するよう依頼しています。要件 -計画されている変更 - Contoso は、両社のセキュリティ操作を統合し、すべてのセキュリティ操作を一元管理する予定です。技術要件 - Contoso では、次の技術要件を特定しています。Azure仮想マシンがブルート フォース攻撃を受けている場合にアラートを受信します。Azure Sentinel を使用して、環境に対するアクティブな攻撃を迅速に修復することで、組織のリスクを軽減します。Contoso と Fabrikam の Azure AD テナント間でデータを相関させる Azure Sentinel クエリを実装します。Fabrikamの Azure Defender for Key Vault アラートを、外部攻撃者や自社の Azure AD アプリケーションへの潜在的な侵害が発生した場合に修復する手順を開発します。特定の国から初めて Azure リソースへのサインインに失敗したユーザーのケースをすべて特定します。ジュニアセキュリティ管理者から、次の不完全なクエリが提供されます。BehaviorAnalytics \- | where ActivityType == "FailedLogOn" | where \_\_\_\_\_\_\_\_ == True  
  
質問 Microsoft Defender for Endpoint を使用するとどのチームの問題が解決できますか?  

- A. エグゼクティブ
- B. 販売
- C. マーケティング

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)  

**解説:**
**Contosoケーススタディ (Topic 8 Question 1):**
Microsoft Defender for Endpointを使用して解決できるチームの問題。
**「Sales (販売チーム)」**。
課題（Current Issues）に以下の記述があります：
「Contoso's sales team uses iOS devices only... The sales team members use various third-party tools to exchange files with customers. In the past, the **sales team has experienced phishing attacks on the devices**（営業チームはデバイス上でフィッシング攻撃を受けたことがあります）」
Defender for EndpointはiOSデバイスにも対応しており（Defender for Endpoint for iOS）、Web保護機能によってフィッシングサイトへのアクセスをブロックできます。
したがって、営業チームのフィッシング問題に対処できます。
Marektingチームの問題はマルウェアを含むファイルのアップロード（SharePoint）であり、これはDefender for Office 365の領域です。

*コミュニティ投票の配分*

B（63％）

C（38％）

質問2 トピック8

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Contoso Ltd. という会社には、北米各地に本社と 5 つの支社があります。本社はシアトルにあります。支社は、トロント、マイアミ、ヒューストン、ロサンゼルス、バンクーバーにあります。Contoso  
には、ニューヨークとサンフランシスコに支社がある Fabrikam, Ltd. という子会社があります。  
  
既存の環境 -  
  
エンド ユーザー環境 -  
Contoso のすべてのユーザーは、Windows 10 デバイスを使用しています。各ユーザーには、Microsoft 365 のライセンスが付与されています。また、Contoso の営業チームのメンバーには iOS デバイスが配布されています。  
  
クラウドとハイブリッド インフラストラクチャ -  
Contoso のすべてのアプリケーションは Azure にデプロイされています。Microsoft  
Cloud App Security を有効にします。Contoso  
と Fabrikam は、異なる Azure Active Directory (Azure AD) テナントを持っています。  
  
現在の問題 -  
Contoso 社のセキュリティチームは、多数のサイバーセキュリティアラートを受信して​​います。セキュリティチームは、どのサイバーセキュリティアラートが正当な脅威で、どれがそうでないかを特定するのに多くの時間を費やしています。  
Contoso の営業チームは、iOS デバイスのみを使用しています。営業チームのメンバーは、さまざまなサードパーティ ツールを使用して顧客とファイルを交換しています。過去に、営業チームはデバイスがフィッシング攻撃を受けたことがあります。Contoso  
のマーケティング チームには、外部ベンダーとのコラボレーション用に複数の Microsoft SharePoint Online サイトがあります。マーケティング チームでは、ベンダーがマルウェアを含むファイルをアップロードするインシデントが何度か発生しています。Contosoの経営陣は、セキュリティ侵害の疑いがあります。経営陣は、Microsoft Cloud App Security で保護されたアプリケーションのデータ アクセス、ダウンロード、削除など、  
過去 48 時間以内に 6 件を超えるアクティビティがあったファイルを特定するよう依頼しています。要件 -計画されている変更 - Contoso は、両社のセキュリティ操作を統合し、すべてのセキュリティ操作を一元管理する予定です。技術要件 - Contoso では、次の技術要件を特定しています。Azure仮想マシンがブルート フォース攻撃を受けている場合にアラートを受信します。Azure Sentinel を使用して、環境に対するアクティブな攻撃を迅速に修復することで、組織のリスクを軽減します。Contoso と Fabrikam の Azure AD テナント間でデータを相関させる Azure Sentinel クエリを実装します。Fabrikamの Azure Defender for Key Vault アラートを、外部攻撃者や自社の Azure AD アプリケーションへの潜在的な侵害が発生した場合に修復する手順を開発します。特定の国から初めて Azure リソースへのサインインに失敗したユーザーのケースをすべて特定します。ジュニアセキュリティ管理者から、次の不完全なクエリが提供されます。BehaviorAnalytics \- | where ActivityType == "FailedLogOn" | where \_\_\_\_\_\_\_\_ == True  
  
質問 Microsoft Defender for Office 365 を使用するとどのチームの問題が解決できますか?  

- A. エグゼクティブ
- B. マーケティング
- C. セキュリティ
- D. 販売

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)  

**解説:**
**Contosoケーススタディ (Topic 8 Question 2):**
Microsoft Defender for Office 365を使用して解決できるチームの問題。
**「Marketing (マーケティングチーム)」**。
課題（Current Issues）に以下の記述があります：
「The marketing team has multiple Microsoft SharePoint Online sites... The marketing team has experienced several incidents in which **vendors uploaded files that contain malware**（ベンダーがマルウェアを含むファイルをアップロードした）」
Defender for Office 365（旧ATP）には「Safe Attachments for SharePoint, OneDrive, and Microsoft Teams」機能があり、SharePoint Onlineにアップロードされたファイルのマルウェア検知とブロックが可能です。
したがって、マーケティングチームの問題を解決できます。

*コミュニティ投票の配分*

B（79％）

C（21％）

## トピック9 - テストレット2

質問1 トピック9

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Litware Inc. は再生可能エネルギー企業です。Litware  
には、ボストンとシアトルにオフィスがあります。Litware には、米国全土にリモート ユーザーがいます。クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境 -  
  
ID 環境 -  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。Microsoft  
  
365 環境 -  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています。Microsoft Cloud  
App Security の組み込み異常検出ポリシーはすべて有効になっています。サブスクリプションには、次の表に示すように、米国東部のAzureリージョンのリソースが含まれています。ネットワーク環境 - Litwareの各オフィスはインターネットに直接接続し、Azureサブスクリプション内の仮想ネットワークへのサイト間VPN接続を備えています。オンプレミス環境 -オンプレミスネットワークには、次の表に示すコンピューターが含まれています。  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0000600001.png)  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0000600002.png)  
  
現在の問題 -  
ユーザーが両方のオフィスに同時に接続すると、Cloud App Security で誤検知アラートが頻繁に生成されます。  
計画されている変更と要件  
  
計画されている変更 -  
Litware では、次の変更を実装する予定です。  
Azure サブスクリプションで Azure Sentinel を作成して構成します。  
Azure AD テスト ユーザー アカウントを使用して、Azure Sentinel の機能を検証します。  
  
ビジネス要件 -  
Litware では、次のビジネス要件を特定しています。  
可能な限り、最小権限の原則を使用する必要があります。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0000600005.png)  
他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
Azure Information Protection の要件  
セキュリティ ラベルが付いており、Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection の「データ検出ダッシュボード」からアクセスできる必要があります。  
Microsoft Defender for Endpoint の要件  
Microsoft Defender for Endpoint を使用して、Windows 10 コンピューター上のすべての Cloud App Security 未承認アプリをブロックする必要があります。  
Microsoft Cloud App Security の要件  
Cloud App Security は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Azure Defender の要件 -  
すべてのサーバーが同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Azure Sentinel の要件 -  
Litware は、次の Azure Sentinel の要件を満たす必要があります。  
Azure Sentinel と Cloud App Security を統合します。  
admin1 というユーザーが Azure Sentinel プレイブックを構成できるようにします。  
カスタム クエリに基づいて Azure Sentinel 分析ルールを作成します。 ルールは、プレイブックの実行を自動的に開始する必要があります。  
特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
Microsoft Office 365 への受信アクセス時にアラートを生成するテスト ルールを作成します。 Azure AD テストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。 質問 Azure Information Protection の要件を実装する必要があります。  
最初に何を構成すればよいでしょうか？  

- A. Microsoft Defender セキュリティ センターのデバイス正常性とコンプライアンス レポートの設定
- B. Azure ポータルからの Azure Information Protection のスキャナー クラスター
- C. Azure ポータルからの Azure Information Protection のコンテンツ スキャン ジョブ
- D. Microsoft Defender セキュリティ センターの設定から高度な機能を選択する

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)   [議論   16](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)  

**解説:**
**Litwareケーススタディ (Topic 9 Question 1):**
**要件:** 「セキュリティラベルが付いており、Windows 10コンピュータに保存されているすべてのファイルは、Azure Information Protection（AIP）の『データ検出ダッシュボード』からアクセス（可視化）できる必要があります。」
**解決策:** 「Microsoft Defender Security Centerの設定から**Advanced features（高度な機能）**を選択する」。
**解説:**
Defender for EndpointとAzure Information Protection（現在はMicrosoft Purview Information Protection）を統合する設定です。
Defender for Endpointの高度な機能設定で「Microsoft Purview Information Protection」統合を有効にすると、Defender for Endpointのエージェントがデバイス上のファイルをスキャンし、検出された機密情報やラベル情報をAIP/Purview側に報告します。これにより、追加のスキャナー（AIP Scanner）を各PCに展開することなく、ダッシュボードでデータを可視化できます。これはWindows 10/11に組み込まれているDefenderセンサーを利用するため、最も効率的です。
AIP Scannerは主にオンプレミスのファイルサーバー用です。

*コミュニティ投票の配分*

D（83％）

B（17％）

質問2 トピック9

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Litware Inc. は再生可能エネルギー企業です。Litware  
には、ボストンとシアトルにオフィスがあります。Litware には、米国全土にリモート ユーザーがいます。クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境 -  
  
ID 環境 -  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。Microsoft  
  
365 環境 -  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています。Microsoft Cloud  
App Security の組み込み異常検出ポリシーはすべて有効になっています。サブスクリプションには、次の表に示すように、米国東部のAzureリージョンのリソースが含まれています。ネットワーク環境 - Litwareの各オフィスはインターネットに直接接続し、Azureサブスクリプション内の仮想ネットワークへのサイト間VPN接続を備えています。オンプレミス環境 -オンプレミスネットワークには、次の表に示すコンピューターが含まれています。  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0000600001.png)  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0000600002.png)  
  
現在の問題 -  
ユーザーが両方のオフィスに同時に接続すると、Cloud App Security で誤検知アラートが頻繁に生成されます。  
計画されている変更と要件  
  
計画されている変更 -  
Litware では、次の変更を実装する予定です。  
Azure サブスクリプションで Azure Sentinel を作成して構成します。  
Azure AD テスト ユーザー アカウントを使用して、Azure Sentinel の機能を検証します。  
  
ビジネス要件 -  
Litware では、次のビジネス要件を特定しています。  
可能な限り、最小権限の原則を使用する必要があります。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0000600005.png)  
他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
Azure Information Protection の要件  
セキュリティ ラベルが付いており、Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection の「データ検出ダッシュボード」からアクセスできる必要があります。  
Microsoft Defender for Endpoint の要件  
Microsoft Defender for Endpoint を使用して、Windows 10 コンピューター上のすべての Cloud App Security 未承認アプリをブロックする必要があります。  
Microsoft Cloud App Security の要件  
Cloud App Security は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Azure Defender の要件 -  
すべてのサーバーが同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Azure Sentinel の要件 -  
Litware は、次の Azure Sentinel の要件を満たす必要があります。  
Azure Sentinel と Cloud App Security を統合します。  
admin1 というユーザーが Azure Sentinel プレイブックを構成できるようにします。  
カスタム クエリに基づいて Azure Sentinel 分析ルールを作成します。 ルールは、プレイブックの実行を自動的に開始する必要があります。  
特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
Microsoft Office 365 への受信アクセス時にアラートを生成するテスト ルールを作成します。 Azure AD テストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。 質問 Cloud App Securityの要件を満たし、報告された問題を解決するには、異常検出ポリシーの設定を変更する必要があります。  
どのポリシーを変更すればよいですか？  

- A. 疑わしいIPアドレスからのアクティビティ
- B. 匿名IPアドレスからのアクティビティ
- C. 不可能な旅行
- D. 危険なサインイン

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)   [議論   15](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)  

**解説:**
**Litwareケーススタディ (Topic 9 Question 2):**
**問題:** 「ユーザーが両方のオフィス（ボストンとシアトル）に同時に接続すると、Cloud App Security（MDA）で誤検知アラートが頻繁に生成されます。」
**解決策:** Cloud App Securityの異常検出ポリシーを変更する。
**「Impossible travel (あり得ない移動)」**。
ユーザーが地理的に離れた2つの場所（ボストンとシアトル）から短時間に「同時に」接続している場合、物理的に移動不可能な距離であれば「Impossible travel」アラートがトリガーされます。
VPNを使用している場合、VPNゲートウェイの場所としてIPアドレスが認識されるため、ユーザーがVPNと直接接続などを併用したり、異なるVPNゲートウェイに接続したりすると発生しがちです。
この誤検知を減らすには、VPNのIPアドレスを「Corporate IP address」として登録するか、Impossible Travelポリシーの感度を調整する、あるいはVPN接続を考慮した設定変更が必要です。質問は「どのポリシーを変更すべきか」なので、原因となっている **Impossible travel** ポリシーが正解です。

*コミュニティ投票の配分*

C（86％）

14%

質問3 トピック9

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Litware Inc. は再生可能エネルギー企業です。Litware  
には、ボストンとシアトルにオフィスがあります。Litware には、米国全土にリモート ユーザーがいます。クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境 -  
  
ID 環境 -  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。Microsoft  
  
365 環境 -  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています。Microsoft Cloud  
App Security の組み込み異常検出ポリシーはすべて有効になっています。サブスクリプションには、次の表に示すように、米国東部のAzureリージョンのリソースが含まれています。ネットワーク環境 - Litwareの各オフィスはインターネットに直接接続し、Azureサブスクリプション内の仮想ネットワークへのサイト間VPN接続を備えています。オンプレミス環境 -オンプレミスネットワークには、次の表に示すコンピューターが含まれています。  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0000600001.png)  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0000600002.png)  
  
現在の問題 -  
ユーザーが両方のオフィスに同時に接続すると、Cloud App Security で誤検知アラートが頻繁に生成されます。  
計画されている変更と要件  
  
計画されている変更 -  
Litware では、次の変更を実装する予定です。  
Azure サブスクリプションで Azure Sentinel を作成して構成します。  
Azure AD テスト ユーザー アカウントを使用して、Azure Sentinel の機能を検証します。  
  
ビジネス要件 -  
Litware では、次のビジネス要件を特定しています。  
可能な限り、最小権限の原則を使用する必要があります。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0000600005.png)  
他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
Azure Information Protection の要件  
セキュリティ ラベルが付いており、Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection の「データ検出ダッシュボード」からアクセスできる必要があります。  
Microsoft Defender for Endpoint の要件  
Microsoft Defender for Endpoint を使用して、Windows 10 コンピューター上のすべての Cloud App Security 未承認アプリをブロックする必要があります。  
Microsoft Cloud App Security の要件  
Cloud App Security は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Azure Defender の要件 -  
すべてのサーバーが同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Azure Sentinel の要件 -  
Litware は、次の Azure Sentinel の要件を満たす必要があります。  
Azure Sentinel と Cloud App Security を統合します。  
admin1 というユーザーが Azure Sentinel プレイブックを構成できるようにします。  
カスタム クエリに基づいて Azure Sentinel 分析ルールを作成します。 ルールは、プレイブックの実行を自動的に開始する必要があります。  
特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
Microsoft Office 365 への受信アクセス時にアラートを生成するテスト ルールを作成します。 Azure AD テストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。 質問 ドラッグ＆ドロップ -  
ビジネス要件を満たすようにDC1を構成する必要があります。  
どの4つのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
選択して配置：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0000900001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)

**Correct Answer:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0000900002.png)

**解説:**
**Litwareケーススタディ (Topic 9 Question 3):**
**要件:** 「すべてのドメインコントローラ（DC1など）は、Microsoft Defender for Identity（MDI）を使用して保護する必要があります。」
**手順:**

1. **Log in to <https://security.microsoft.com> (or portal.atp.azure.com)**: MDIポータル（現在はDefender XDRポータル）にアクセスし、ワークスペース（インスタンス）を作成します。
2. **Create the instance**: MDIインスタンスを作成します（まだない場合）。
3. **Connect the instance to Active Directory**: （これは以前の手順で、現在はセンサーインストール時に行われますが、手順としてはディレクトリサービスアカウントの設定などを指します）。
4. **Download and install the sensor**: DC1にMDIセンサーパッケージをダウンロードしてインストールします。
現在のDefender for Identityのデプロイフローでは、「ポータルでインスタンス作成（自動）→ ディレクトリサービスアカウント設定 → センサーパッケージダウンロード → DCにインストール」となります。
古い手順（選択肢）に基づくと：Global Adminでログイン -> インスタンス作成 -> AD接続 -> センサーインストール、の順が妥当です。

Step 2: Create the instance -  
Step 3. Connect the instance to Active Directory  
Step 4. Download and install the sensor.  
Reference:  
<https://docs.microsoft.com/en-us/defender-for-identity/install-step1> <https://docs.microsoft.com/en-us/defender-for-identity/install-step4>

## トピック10 - テストレット3

質問1 トピック10

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Litware Inc. は再生可能エネルギー企業です。Litware  
には、ボストンとシアトルにオフィスがあります。Litware には、米国全土にリモート ユーザーがいます。クラウド リソースなどの Litware リソースにアクセスするために、リモート ユーザーはどちらかのオフィスに VPN 接続を確立します。  
  
既存の環境 -  
  
ID 環境 -  
ネットワークには、litware.com という名前の Azure Active Directory (Azure AD) テナントに同期する litware.com という名前の Active Directory フォレストが含まれています。Microsoft  
  
365 環境 -  
Litware には、litware.com Azure AD テナントにリンクされた Microsoft 365 E5 サブスクリプションがあります。Microsoft Defender for Endpoint は、Windows 10 を実行するすべてのコンピューターに展開されています。Microsoft Cloud  
App Security の組み込み異常検出ポリシーはすべて有効になっています。サブスクリプションには、次の表に示すように、米国東部のAzureリージョンのリソースが含まれています。ネットワーク環境 - Litwareの各オフィスはインターネットに直接接続し、Azureサブスクリプション内の仮想ネットワークへのサイト間VPN接続を備えています。オンプレミス環境 -オンプレミスネットワークには、次の表に示すコンピューターが含まれています。  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0004600001.png)  
  
![](https://www.examtopics.com/assets/media/exam-media/04261/0004600002.png)  
  
現在の問題 -  
ユーザーが両方のオフィスに同時に接続すると、Cloud App Security で誤検知アラートが頻繁に生成されます。  
計画されている変更と要件  
  
計画されている変更 -  
Litware では、次の変更を実装する予定です。  
Azure サブスクリプションで Azure Sentinel を作成して構成します。  
Azure AD テスト ユーザー アカウントを使用して、Azure Sentinel の機能を検証します。  
  
ビジネス要件 -  
Litware では、次のビジネス要件を特定しています。  
可能な限り、最小権限の原則を使用する必要があります。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0004600005.png)  
他のすべての要件が満たされている限り、コストを最小限に抑える必要があります。  
Log Analytics によって収集されたログは、ユーザー アクティビティの完全な監査証跡を提供する必要があります。  
すべてのドメイン コントローラーは、Microsoft Defender for Identity を使用して保護する必要があります。  
Azure Information Protection の要件  
セキュリティ ラベルが付いており、Windows 10 コンピューターに保存されているすべてのファイルは、Azure Information Protection の「データ検出ダッシュボード」からアクセスできる必要があります。  
Microsoft Defender for Endpoint の要件  
Microsoft Defender for Endpoint を使用して、Windows 10 コンピューター上のすべての Cloud App Security 未承認アプリをブロックする必要があります。  
Microsoft Cloud App Security の要件  
Cloud App Security は、テナント レベルのデータに基づいてユーザー接続が異常かどうかを識別する必要があります。  
  
Azure Defender の要件 -  
すべてのサーバーが同じ Log Analytics ワークスペースにログを送信する必要があります。  
  
Azure Sentinel の要件 -  
Litware は、次の Azure Sentinel の要件を満たす必要があります。  
Azure Sentinel と Cloud App Security を統合します。  
admin1 というユーザーが Azure Sentinel プレイブックを構成できるようにします。  
カスタム クエリに基づいて Azure Sentinel 分析ルールを作成します。 ルールは、プレイブックの実行を自動的に開始する必要があります。  
特定の IP アドレスからのデータ アクセスを表すイベントにメモを追加して、ハンティング中に調査グラフ内を移動するときに IP アドレスを参照できるようにします。  
Microsoft Office 365 への受信アクセス時にアラートを生成するテスト ルールを作成します。 Azure AD テストユーザーアカウントによる不正なアクセスが検出されました。ルールによって生成されたアラートは、テストユーザーアカウントごとに 1 つのインシデントとして、個別のインシデントにグループ化する必要があります。 質問 ホットスポット -  
Azure Defender の要件とビジネス要件を満たすには、Azure Defender を実装する必要があります。  
ソリューションには何を含めるべきですか？回答するには、回答エリアから適切な選択肢を選択してください。  
注: 正解は1つにつき1ポイントです。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0004800001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)

**Correct Answer:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0004800002.png)

**解説:**
**Litwareケーススタディ (Topic 10 Question 1):**
**要件:** 「すべてのサーバーが同じLog Analyticsワークスペースにログを送信する（Azure Defenderの要件）」
**解決策:**
Server settings: **On the Log Analytics workspace, enable Azure Defender**.
（正解画像の左側）：Log AnalyticsワークスペースレベルでAzure Defender（現在のMicrosoft Defender for CloudのEnhanced Security features）を有効にします。これにより、そのワークスペースに接続されているすべてのサーバー（エージェント経由）に対してDefender機能（脆弱性評価、脅威検出など）が有効になり、ログも集約されます。
Agent settings: **Install the Microsoft Monitoring Agent (MMA) / Azure Monitor Agent (AMA)** on Server1, Server2, Server3.
（正解画像の右側）：オンプレミスサーバー（Server1-3）からログを送信するには、エージェントのインストールが必要です。

## トピック11 - テストレット4

質問1 トピック11

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Contoso Ltd. という会社には、北米各地に本社と 5 つの支社があります。本社はシアトルにあります。支社は、トロント、マイアミ、ヒューストン、ロサンゼルス、バンクーバーにあります。Contoso  
には、ニューヨークとサンフランシスコに支社がある Fabrikam, Ltd. という子会社があります。  
  
既存の環境 -  
  
エンド ユーザー環境 -  
Contoso のすべてのユーザーは、Windows 10 デバイスを使用しています。各ユーザーには、Microsoft 365 のライセンスが付与されています。また、Contoso の営業チームのメンバーには iOS デバイスが配布されています。  
  
クラウドとハイブリッド インフラストラクチャ -  
Contoso のすべてのアプリケーションは Azure にデプロイされています。Microsoft  
Cloud App Security を有効にします。Contoso  
と Fabrikam は、異なる Azure Active Directory (Azure AD) テナントを持っています。  
  
現在の問題 -  
Contoso 社のセキュリティチームは、多数のサイバーセキュリティアラートを受信して​​います。セキュリティチームは、どのサイバーセキュリティアラートが正当な脅威で、どれがそうでないかを特定するのに多くの時間を費やしています。  
Contoso の営業チームは、iOS デバイスのみを使用しています。営業チームのメンバーは、さまざまなサードパーティ ツールを使用して顧客とファイルを交換しています。過去に、営業チームはデバイスがフィッシング攻撃を受けたことがあります。Contoso  
のマーケティング チームには、外部ベンダーとのコラボレーション用に複数の Microsoft SharePoint Online サイトがあります。マーケティング チームでは、ベンダーがマルウェアを含むファイルをアップロードするインシデントが何度か発生しています。Contosoの経営陣は、セキュリティ侵害の疑いがあります。経営陣は、Microsoft Cloud App Security で保護されたアプリケーションのデータ アクセス、ダウンロード、削除など、  
過去 48 時間以内に 6 件を超えるアクティビティがあったファイルを特定するよう依頼しています。要件 -計画されている変更 - Contoso は、両社のセキュリティ操作を統合し、すべてのセキュリティ操作を一元管理する予定です。技術要件 - Contoso では、次の技術要件を特定しています。Azure仮想マシンがブルート フォース攻撃を受けている場合にアラートを受信します。Azure Sentinel を使用して、環境に対するアクティブな攻撃を迅速に修復することで、組織のリスクを軽減します。Contoso 社と Fabrikam 社の Azure AD テナント間でデータを相関させる Azure Sentinel クエリを実装してください。外部および内部の脅威が発生した場合に、Contoso 社の Azure Defender for Key Vault アラートを修復するための手順を開発してください。このソリューションは、Key Vault コンテンツへの正当なアクセス試行への影響を最小限に抑える必要があります。特定の国から初めて Azure リソースにサインインできなかったユーザーのケースをすべて特定してください。ある若手セキュリティ管理者から、次のような不完全なクエリが提出されました。BehaviorAnalytics \- | where ActivityType == "FailedLogOn" | where \_\_\_\_\_\_\_\_ == True  
  
質問 ホットスポット -  
Fabrikam の Azure Defender アラートに対する修復アクションを推奨する必要があります。  
それぞれの脅威に対して、どのような対策を推奨すべきでしょうか？回答するには、回答エリアで適切な選択肢を選択してください。  
注: 正解は 1 点です。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0005100001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)

**Correct Answer:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0005200001.jpg)

**解説:**
**Contosoケーススタディ (Topic 11 Question 1):**
**要件:** 「外部および内部の脅威が発生した場合に、Key Vaultアラートを修復するための手順を開発してください。正当なアクセスへの影響を最小限に抑える。」
**推奨アクション:**

1. **External threat (外部脅威)**: **Azure Firewall** や **NSG** でIPをブロックするアプローチもありますが、Key Vaultへのアクセス制御としては **Azure Logic App** (Sentinel Playbook) を使用して、アラートトリガーでファイアウォールルールを動的に更新したり、アクセス権を剥奪したりするのが「手順の開発」として柔軟です。
   ただし、正解画像（image052...）の内容が不明確ですが、一般的に自動修復には Logic App が使われます。
   あるいは、Key Vault自体のFirewall設定でアクセス元を制限する？
   *正解画像の推測*:
   - External threat: **Block access via the firewall** (IP制限).
   - Internal threat: **Modify the access policy** (Access Policy変更で権限削除).
   Azure Logic Appを使うとこれらを自動化できますが、具体的なアクションとしては上記が適切です。
2. **Internal threat (内部脅威)**:
   内部ユーザーのアカウント侵害や不正使用の場合、IPブロックは効果が薄いため、**Access Policy**（またはRBACロール）を変更して、ユーザーやアプリのアクセス権を取り消すのが適切です。

   *選択肢の再確認が必要です*: 画像の選択肢が見えませんが、要件「外部および内部の脅威... Key Vaultアラートを修復」に対しては、
   - External: Block IP address (Firewall)
   - Internal: Change Access Policy
   これらを自動化するために **Azure Logic Apps** を使用するのが一般的です。

<https://docs.microsoft.com/en-us/azure/key-vault/general/security-features> <https://docs.microsoft.com/en-us/azure/key-vault/general/secure-your-key-vault>

質問2 トピック11

紹介情報 ケーススタディ -  
これはケーススタディです。ケーススタディは個別に試験時間が制限されることはありません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケーススタディやセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
ケーススタディに含まれる質問に回答するには、ケーススタディで提供される情報を参照する必要があります。ケーススタディには、ケーススタディで説明されているシナリオに関する詳細情報を提供する資料やその他のリソースが含まれている場合があります。各質問は、このケーススタディの他の質問とは独立しています。  
このケーススタディの最後に、確認画面が表示されます。この画面で回答を確認し、次のセクションに進む前に修正を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケーススタディを開始するには -  
このケーススタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケーススタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同一であることに注意してください。質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要 -  
Contoso Ltd. という会社には、北米各地に本社と 5 つの支社があります。本社はシアトルにあります。支社は、トロント、マイアミ、ヒューストン、ロサンゼルス、バンクーバーにあります。Contoso  
には、ニューヨークとサンフランシスコに支社がある Fabrikam, Ltd. という子会社があります。  
  
既存の環境 -  
  
エンド ユーザー環境 -  
Contoso のすべてのユーザーは、Windows 10 デバイスを使用しています。各ユーザーには、Microsoft 365 のライセンスが付与されています。また、Contoso の営業チームのメンバーには iOS デバイスが配布されています。  
  
クラウドとハイブリッド インフラストラクチャ -  
Contoso のすべてのアプリケーションは Azure にデプロイされています。Microsoft  
Cloud App Security を有効にします。Contoso  
と Fabrikam は、異なる Azure Active Directory (Azure AD) テナントを持っています。  
  
現在の問題 -  
Contoso 社のセキュリティチームは、多数のサイバーセキュリティアラートを受信して​​います。セキュリティチームは、どのサイバーセキュリティアラートが正当な脅威で、どれがそうでないかを特定するのに多くの時間を費やしています。  
Contoso の営業チームは、iOS デバイスのみを使用しています。営業チームのメンバーは、さまざまなサードパーティ ツールを使用して顧客とファイルを交換しています。過去に、営業チームはデバイスがフィッシング攻撃を受けたことがあります。Contoso  
のマーケティング チームには、外部ベンダーとのコラボレーション用に複数の Microsoft SharePoint Online サイトがあります。マーケティング チームでは、ベンダーがマルウェアを含むファイルをアップロードするインシデントが何度か発生しています。Contosoの経営陣は、セキュリティ侵害の疑いがあります。経営陣は、Microsoft Cloud App Security で保護されたアプリケーションのデータ アクセス、ダウンロード、削除など、  
過去 48 時間以内に 6 件を超えるアクティビティがあったファイルを特定するよう依頼しています。要件 -計画されている変更 - Contoso は、両社のセキュリティ操作を統合し、すべてのセキュリティ操作を一元管理する予定です。技術要件 - Contoso では、次の技術要件を特定しています。Azure仮想マシンがブルート フォース攻撃を受けている場合にアラートを受信します。Azure Sentinel を使用して、環境に対するアクティブな攻撃を迅速に修復することで、組織のリスクを軽減します。Contoso 社と Fabrikam 社の Azure AD テナント間でデータを相関させる Azure Sentinel クエリを実装してください。外部および内部の脅威が発生した場合に、Contoso 社の Azure Defender for Key Vault アラートを修復するための手順を開発してください。このソリューションは、Key Vault コンテンツへの正当なアクセス試行への影響を最小限に抑える必要があります。特定の国から初めて Azure リソースにサインインできなかったユーザーのケースをすべて特定してください。ある若手セキュリティ管理者から、次のような不完全なクエリが提出されました。BehaviorAnalytics \- | where ActivityType == "FailedLogOn" | where \_\_\_\_\_\_\_\_ == True  
  
質問 Azure仮想マシンの技術要件を満たすソリューションを推奨する必要があります。  
推奨内容には何を含めるべきですか？  

- A. ジャストインタイム（JIT）アクセス
- B. アズールディフェンダー
- C. Azure ファイアウォール
- D. Azure アプリケーション ゲートウェイ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/40/#)  

**解説:**
**Contosoケーススタディ (Topic 11 Question 2):**
**技術要件:** 「Azure仮想マシンがブルートフォース攻撃を受けている場合にアラートを受信します。」
**推奨ソリューション:**
**「B. Azure Defender (Microsoft Defender for Cloud)」**。
Azure Defender for Servers（現在のDefender for Cloudプラン）は、VMに対するブルートフォース攻撃（RDP/SSH総当たり）を検出し、アラートを出力します。また、Just-in-Time (JIT) VM Access機能もAzure Defenderの一部として提供され、攻撃面を減らすのに役立ちますが、アラート検出の主体はAzure Defenderです。
A (JIT): 予防策ですが、検出機能（アラート）そのものではありません（JITリクエスト等はログになりますが）。要件は「アラートを受信する」ことなので、検出エンジンであるAzure Defenderが正解です。

*Community vote distribution*

B (100%)

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/39/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 40 ページを表示しています。

410問中**391 - 400**問 を表示
