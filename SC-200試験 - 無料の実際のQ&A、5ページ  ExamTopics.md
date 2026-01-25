---
title: "SC-200試験 - 無料の実際のQ&A、5ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/5/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#41 トピック1

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft 365 Defender をご利用いただいています。Microsoft  
  
が発見した新たな攻撃手法を確認し、サブスクリプション内の脆弱なリソースを特定する必要があります。ソリューションは管理作業を最小限に抑える必要があります。Microsoft  
  
365 Defender ポータルではどのブレードを使用すればよいでしょうか？

- A. 高度な狩猟
- B. 脅威分析
- C. インシデントとアラート
- D. 学習ハブ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)  

**解説:**
Microsoftが発見した新たな攻撃手法（新しい脅威、キャンペーンなど）に関する情報を確認し、自社の環境（サブスクリプション）内のどのリソースが脆弱であるか（軽減策が未適用のデバイスなど）を特定するには、**「脅威分析 (Threat Analytics)」** ブレードを使用します。
脅威分析には、アナリストレポート、関連するアラート、および影響を受ける資産や軽減策のステータスが含まれており、管理者は効率的にリスクを把握し対処できます。

*コミュニティ投票の配分*

B（100％）

質問#42 トピック1

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
• Jupyter Notebookを使用して、Pool1でハンティングクエリを実行します。  
• Group2のメンバーがインシデントを管理できることを確認します。  
• データクエリのパフォーマンスを最大化します。  
• 収集されるデータの量を最小限に抑えます。Microsoft  
  
Defender for Identityの誤検知アラートを調査するために必要な労力を最小限に抑える必要があります。  
  
何を確認する必要がありますか？

- A. ステータス更新時間
- B. ソースコンピュータの解決方法
- C. アラートステータス
- D. ソースコンピュータの確実性

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)  

**解説:**
Microsoft Defender for Identity での誤検知（False Positive）を減らし、調査の労力を最小限に抑えるには、アラートのコンテキスト情報、特に **「ソースコンピュータの確実性 (Source computer certainty)」** を確認することが重要です。
DCSync攻撃などのアラートでは、攻撃元が特定できているかどうかが信頼性に大きく関わります。確実性が低い場合、それはネットワークマッピングの問題や一時的な情報の欠落による誤検知の可能性があります。

**解説:**
Microsoft Defender for Identity での誤検知（False Positive）を減らし、調査の労力を最小限に抑えるには、アラートのコンテキスト情報、特に **「ソースコンピュータの確実性 (Source computer certainty)」** を確認することが重要です。
DCSync攻撃などのアラートでは、攻撃元が特定できているかどうかが信頼性に大きく関わります。確実性が低い場合、それはネットワークマッピングの問題や一時的な情報の欠落による誤検知の可能性があります。

*コミュニティ投票の配分*

D（81％）

他の

質問#43 トピック1

HOTSPOT  
\-  
  
Microsoft Defender 365 を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
ネットワークには、Azure AD と同期するオンプレミスの Active Directory Domain Services (AD DS) ドメインが含まれています。デバイス  
  
と AD DS ドメイン コントローラーに記録された直近 100 件のサインイン試行を特定する必要があります。KQL  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image183.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)   [議論   16](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)

**正解:** ![](https://img.examtopics.com/sc-200/image184.png)

**解説:**
デバイスへのサインインイベントを取得する基本的なKQLクエリです。

1. **`DeviceLogonEvents`**: デバイス上のログオンイベントを含むテーブル。
2. **`where LogonType == 'Interactive'`**: ユーザーがキーボードや画面を使って直接サインインした「対話型」ログオンに絞り込みます。
3. **`limit 100`**: 結果を最新の100件（または任意の100件）に制限します。

質問#44 トピック1

HOTSPOT  
\-  
  
Microsoft Defender 365 を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
ネットワークには、Azure AD と同期するオンプレミスの Active Directory Domain Services (AD DS) ドメインが含まれています。AD  
  
DS ユーザーによる LDAP 要求を識別し、AD DS オブジェクトを列挙する必要があります。KQL  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image185.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)

**正解:** ![](https://img.examtopics.com/sc-200/image186.png)

**解説:**
AD DSに対するLDAPクエリを調査するためのKQLクエリです。

1. **`IdentityQueryEvents`**: Active DirectoryなどのIDシステムに対して行われたクエリイベント（LDAPクエリなど）を記録するテーブルです。（※古い資料では `IdentityDirectoryEvents` が使われることもありましたが、正解画像の選択肢にある場合は `IdentityQueryEvents` がより具体的です。ただし、選択肢の画像が `IdentityDirectoryEvents` を指している場合、`ActionType == "LDAP query"` でフィルタリングします。）
2. **`where ActionType == 'LDAP query'`**: LDAPクエリイベントに絞り込みます。
3. **`project AccountName, Query, ...`**: 必要な列を表示します。

質問#45 トピック1

Microsoft Defender 365 を使用する Microsoft 365 E5 サブスクリプションをお持ちです。Microsoft  
  
Defender for Cloud Apps の統合監査ログのデータを使用して脅威を調査できるようにする必要があります。  
  
まず何を設定すればよいでしょうか？

- A. ユーザーエンリッチメント設定
- B. Azureコネクタ
- C. Office 365コネクタ
- D. 自動ログアップロード設定

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)  

**解説:**
Microsoft Defender for Cloud Apps (MDCA) で統合監査ログ（Unified Audit Log）のデータを使用して脅威を調査するには、Microsoft 365（Office 365）とMDCAを接続する必要があります。
これを行うには、**「Office 365コネクタ (Office 365 connector)」** を設定します（現在は「アプリコネクタ」設定でOffice 365を接続します）。これにより、Office 365のアクティビティログがMDCAに取り込まれ、調査やポリシー適用が可能になります。

*コミュニティ投票の配分*

C（90％）

10%

質問#46 トピック1

51 HOTSPOT  
  
次のKQLクエリを含むカスタム検出ルールがあります。  
  
![](https://img.examtopics.com/sc-200/image187.png)  
  
以下の各文について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注：正しい選択ごとに1ポイント獲得できます。  
  
![](https://img.examtopics.com/sc-200/image188.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)   [議論   29](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)

**正解:** ![](https://img.examtopics.com/sc-200/image413.png)

**解説:**
カスタム検出ルール（Custom detection rules）の動作に関する問題です。

1. **ルールがアラートをトリガーするか？ -> はい**: カスタム検出ルールの主な目的は、作成したクエリ条件に一致するイベントが見つかった場合にアラートを作成することです。
2. **ルールが応答アクションをトリガーするか？ -> はい**: ルール設定で、デバイスの分離（Isolate device）やファイルの検疫などの応答アクションを自動的に実行するように構成できます。
3. **アラートのリスクレベルを変更できるか？ -> はい**: アラートの重大度（Severity）をルール作成時に指定（高、中、低、情報）できます。

**解説:**
カスタム検出ルール（Custom detection rules）の動作に関する問題です。

1. **ルールがアラートをトリガーするか？ -> はい**: カスタム検出ルールの主な目的は、作成したクエリ条件に一致するイベントが見つかった場合にアラートを作成することです。
2. **ルールが応答アクションをトリガーするか？ -> はい**: ルール設定で、デバイスの分離（Isolate device）やファイルの検疫などの応答アクションを自動的に実行するように構成できます。
3. **アラートのリスクレベルを変更できるか？ -> はい**: アラートの重大度（Severity）をルール作成時に指定（高、中、低、情報）できます。

**解説:**
カスタム検出ルール（Custom detection rules）の動作に関する問題です。

1. **ルールがアラートをトリガーするか？ -> はい**: カスタム検出ルールの主な目的は、作成したクエリ条件に一致するイベントが見つかった場合にアラートを作成することです。
2. **ルールが応答アクションをトリガーするか？ -> はい**: ルール設定で、デバイスの分離（Isolate device）やファイルの検疫などの応答アクションを自動的に実行するように構成できます。
3. **アラートのリスクレベルを変更できるか？ -> はい**: アラートの重大度（Severity）をルール作成時に指定（高、中、低、情報）できます。

質問#47 トピック1

Microsoft Defender for Servers プラン 1 を使用する Azure サブスクリプションがあり、Server1 というサーバーが含まれています。  
  
エージェントレス スキャンを有効にしています。Server1  
  
がスキャンされないようにする必要があります。このソリューションでは、管理の手間を最小限に抑える必要があります。  
  
どうすればよいでしょうか？

- A. 除外タグを作成します。
- B. サブスクリプションを Defender for Servers プラン 2 にアップグレードします。
- C. ガバナンス ルールを作成します。
- D. 排他グループを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)   [議論   20](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)  

**解説:**
Defender for Servers Plan 2（またはCSPM）の機能である「エージェントレススキャン (Agentless scanning)」から特定のサーバーを除外するには、**「除外タグ (Exclusion tag)」** を使用します。
スキャン設定画面で、除外したいマシンに付与されているタグとその値を指定することで、そのタグを持つマシンをスキャンの対象外にすることができます。これは管理の手間が少ない方法です。

*コミュニティ投票の配分*

A（64％）

B（36％）

質問#48 トピック1

機密ファイルが外部に共有された場合にアラートを生成し、修復アクションをトリガーするように、Microsoft Defender for Cloud Apps を構成する必要があります。Microsoft  
  
365 Defender ポータルで実行する必要がある 2 つのアクションはどれですか？ 正解はそれぞれ解答の一部を示しています。  
  
注: 正解は 1 点です。

- A. \[設定\] から \[Information Protection\] を選択し、\[Azure Information Protection\] を選択してから、\[このテナントからの Azure Information Protection 分類ラベルとコンテンツ検査警告のファイルのみをスキャンする\] を選択します。
- B. クラウドアプリから「ファイル」を選択し、「ファイルの種類」を「ドキュメント」にフィルターします。B.  
 「設定」から「情報保護」を選択し、「ファイル」を選択して、ファイル監視を有効にします。
- D. クラウド アプリから \[ファイル\] を選択し、アプリを Office 365 にフィルターします。
- E. クラウド アプリから \[ファイル\] を選択し、検索から \[新しいポリシー\] を選択します。
- F. \[設定\] から \[Information Protection\] を選択し、\[Azure Information Protection\] を選択してから、\[Azure Information Protection 分類ラベルとコンテンツ検査の警告について新しいファイルを自動的にスキャンする\] を選択します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)   [議論   13](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)

**正解：** BF [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)  

**解説:**
機密ファイルの外部共有を検出し、修復アクションをトリガーするには、以下の手順が必要です。

1. **F. Information Protectionの設定**: 「設定」>「Information Protection」で、**「Azure Information Protectionの分類ラベルとコンテンツ検査の警告について新しいファイルを自動的にスキャンする」** を有効にする必要があります。これにより、ファイルの中身やラベルをスキャンできるようになります。
2. **B. ファイルポリシーの作成**: 「ポリシー」メニューから **「ファイルポリシー (File policy)」** を作成します（選択肢Bは少し表現が変則的ですが、要はファイル監視を行うポリシーの設定です）。このポリシー内で、「アクセスレベルが外部/公開」かつ「機密ラベルがついている」などの条件を設定し、修復アクション（アラート送信、検疫など）を定義します。

*コミュニティ投票の配分*

EF（67％）

体脂肪（33％）

質問#49 トピック1

HOTSPOT  
\-  
  
ネットワークには、Azure AD と同期するオンプレミスの Active Directory Domain Services (AD DS) ドメインが含まれています。Microsoft  
  
Defender 365 を使用する Microsoft 365 E5 サブスクリプションを所有しています。  
  
会社の財務部門のユーザーによる対話型認証の試行をすべて特定する必要があります。KQL  
  
クエリをどのように完了すればよいでしょうか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image190.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)   [議論   15](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)

**正解:** ![](https://img.examtopics.com/sc-200/image191.png)

**解説:**
財務部門（Finance）のユーザーによる対話型認証（Interactive authentication）を特定するクエリです。

1. **`IdentityLogonEvents`**: IDログオンイベントテーブルを使用します。
2. **`where Application == 'Active Directory'`**: オンプレミスADのイベントを対象とする場合、このフィルタが入ることがあります（または`IdentityDirectoryEvents`を使うケースもありますが、ログオンタイプと部門で絞るならこちら）。
3. **`where LogonType == 'Interactive'`**: 対話型ログオンに絞り込みます。
4. **`where Department == 'Finance'`**: ユーザーの部門属性が'Finance'であるログに絞り込みます。（※`Department`情報はエンリッチメントデータとして利用可能な場合があります。）

**解説:**
財務部門（Finance）のユーザーによる対話型認証（Interactive authentication）を特定するクエリです。

1. **`IdentityLogonEvents`**: IDログオンイベントテーブルを使用します。
2. **`where Application == 'Active Directory'`**: オンプレミスADのイベントを対象とする場合、このフィルタが入ることがあります（または`IdentityDirectoryEvents`を使うケースもありますが、ログオンタイプと部門で絞るならこちら）。
3. **`where LogonType == 'Interactive'`**: 対話型ログオンに絞り込みます。
4. **`where Department == 'Finance'`**: ユーザーの部門属性が'Finance'であるログに絞り込みます。（※`Department`情報はエンリッチメントデータとして利用可能な場合があります。）

**解説:**
財務部門（Finance）のユーザーによる対話型認証（Interactive authentication）を特定するクエリです。

1. **`IdentityLogonEvents`**: IDログオンイベントテーブルを使用します。
2. **`where Application == 'Active Directory'`**: オンプレミスADのイベントを対象とする場合、このフィルタが入ることがあります（または`IdentityDirectoryEvents`を使うケースもありますが、ログオンタイプと部門で絞るならこちら）。
3. **`where LogonType == 'Interactive'`**: 対話型ログオンに絞り込みます。
4. **`where Department == 'Finance'`**: ユーザーの部門属性が'Finance'であるログに絞り込みます。（※`Department`情報はエンリッチメントデータとして利用可能な場合があります。）

質問#50 トピック1

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft Defender for Endpoint をご利用いただいています。  
  
マルウェアアラートをトリガーしたデバイスを特定し、アラートに関連する証拠を収集する必要があります。このソリューションでは、結果に基づいて影響を受けたデバイスのデバイス分離を開始できるようにする必要があります。Microsoft  
  
365 Defender ポータルでは何を使用すればよいでしょうか？

- A. 事件
- B. 修復
- C. 調査
- D. 高度な狩猟

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)   [議論   40](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/5/#)  

*コミュニティ投票の配分*

D（64％）

A（30％）

7%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/4/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 5 ページ目を表示しています。

410問中**41 - 50**問 目を表示
