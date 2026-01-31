---
title: "SC-200試験 - 無料の実際のQ&A、ページ2 | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/2/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問11 トピック1

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
Defender for Identity と Active Directory の統合を構成しています。Microsoft  
Defender for Identity ポータルから、攻撃者が悪用できる複数のアカウントを構成する必要があります。  
解決策: Azure AD Identity Protection から、サインインリスクポリシーを構成します。  
これは目標を達成していますか?  

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)  

**解説:**
ハニートークンアカウント（Honeytoken account）は、Defender for Identity ポータルではなく、Microsoft 365 Defender ポータル（現在のMicrosoft Defender XDR）の設定にある「エンティティタグ」から構成します。
ユーザーが提案した「Azure AD Identity Protection のサインインリスクポリシー」は、リアルタイムのリスク検出には有効ですが、特定の「おとりアカウント」を設定するハニートークンの要件とは異なります。したがって、この解決策は目標を達成しません。

*コミュニティ投票の配分*

B（100％）

質問12 トピック1

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
Defender for Identity と Active Directory の統合を構成しています。Microsoft  
Defender for Identity ポータルから、攻撃者が悪用できる複数のアカウントを構成する必要があります。  
解決策: アカウントを Active Directory グループに追加し、そのグループを機密グループとして追加します。  
これで目標は達成されますか?  

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)  

**解説:**
Defender for Identity でハニートークンアカウント（Honeytoken account）を設定する場合、Active Directory グループを使用して構成するのではなく、Microsoft Defender ポータル上で特定のエンティティ（ユーザー）に対して直接タグ付けを行います（Entity tags）。機密グループ（Sensitive Group）は、管理者権限などを持つ高リスクなグループを監視するためのものであり、攻撃をおびき寄せるためのおとり（ハニートークン）とは目的と設定方法が異なります。

*コミュニティ投票の配分*

B（100％）

質問13 トピック1

Microsoft Defender for Office 365 に「安全な添付ファイル」ポリシーを実装しています。  
ユーザーから、添付ファイルを含むメールメッセージの  
受信に予想よりも時間がかかるという報告を受けています。セキュリティを損なうことなく、添付ファイルを含むメッセージの配信時間を短縮する必要があります。添付ファイルはマルウェアスキャンの対象となり、マルウェアを含むメッセージはブロックする必要があります。  
「安全な添付ファイル」ポリシーではどのような設定を行うべきでしょうか？  

- A. ダイナミックデリバリー
- B. 置き換える
- C. リダイレクトをブロックして有効にする
- D. リダイレクトを監視して有効にする

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)   [議論   15](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)  

**解説:**
**ダイナミックデリバリー (Dynamic Delivery)** は、安全な添付ファイル（Safe Attachments）ポリシーの機能の1つで、添付ファイルのスキャンが完了する前に、まずメール本文だけを受信者に配信します。
ユーザーは本文をすぐに読むことができ、添付ファイルの部分には「スキャン中」である旨のプレースホルダーが表示されます。スキャンが完了し安全と判断されれば、添付ファイルが利用可能になります。これにより、セキュリティを確保しつつ、メール受信の遅延を感じさせないユーザーエクスペリエンスを提供できます。

*コミュニティ投票の配分*

A（100％）

質問14 トピック1

ホットスポット -  
ユーザーが悪意のあるメールを受信するケースが増加しているとの報告を受けました。Microsoft  
365 Defender で高度なハンティングクエリを作成し、メール受信者のアカウントが侵害されたかどうかを特定する必要があります。クエリは、既知の悪意のあるメールを受信して​​から1時間以内に受信者が行った直近20件のサインインを返す必要があります。  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
注：正しい選択肢は1つにつき1ポイントです。  
ホットエリア：  
![](https://www.examtopics.com/assets/media/exam-media/04261/0002400001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)   [議論   22](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)

**==正解:==** ![](https://www.examtopics.com/assets/media/exam-media/04261/0002500001.png) 参照:  

**解説:**

このクエリは、悪意のあるメールを受信したユーザーが、その直後に不審なサインインを行っていないかを特定するためのものです。

1. メールの特定: `EmailEvents`

`MaliciousEmails` という変数にメールの情報を格納しています。

- **理由**: フィルタ条件として `MalwareFilterVerdict == "Malware"`（マルウェア検知結果）が指定されています。この列は、メールの配信やフィルタリング結果を記録する **`EmailEvents`** テーブルに含まれます。
    
- 補足: `EmailAttachmentInfo` は添付ファイルの詳細、`IdentityLogonEvents` はサインイン情報なので、メール自体のフィルタリング結果を追うには適しません。
    

2. サインイン情報の結合: `IdentityLogonEvents`

`join` 句の中で、メール受信者のその後の行動を確認するためのテーブルを指定します。

- **理由**: 後続の `project` 行で `LogonTime` や `DeviceName` を取得しようとしていることから、デバイスへのサインイン（ログオン）履歴を保持する **`IdentityLogonEvents`** が正解となります。
    

3. 直近レコードの抽出: `top 20`

クエリの最後で、条件に合致したレコードの中から 20 件を取り出します。

- **理由**: 要件は「直近（most recent）20 件」です。
    
    - **`top 20`**: 指定した列（`LogonTime desc`）で並べ替えた上で上位 20 件を取得するため、「直近の 20 件」を正確に返します。
        
    - `take 20`: 並べ替えに関係なく任意の 20 件を返すため、今回の要件には適しません。
        
    - `select 20`: KQL にはこの用途の演算子は存在しません。

質問15 トピック1

画像ファイルを利用した潜在的な攻撃に関するセキュリティ情報を受け取りました。  
攻撃を防ぐには、Microsoft Defender for Endpoint で侵害の兆候 (IoC) を作成する必要があります。  
どの種類の兆候を使用すべきでしょうか？  

- A. アクションがアラートのみに設定されているURL/ドメインインジケーター
- B. アクションが「警告してブロック」に設定されているURL/ドメインインジケーター
- C. アクションが「警告とブロック」に設定されているファイルハッシュインジケータ
- D. アクションが「警告とブロック」に設定されている証明書インジケータ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)  

**解説:**
画像ファイルを用いた攻撃を防ぐためには、そのファイルのハッシュ値（File Hash）に基づいた侵害の兆候（IoC: Indicator of Compromise）を作成するのが最も確実です。
アクションとして **「警告とブロック (Alert and Block)」** を選択することで、該当するファイルが検出された場合に、管理者にアラートを通知すると同時に、そのファイルの実行や読み込みをブロックし、攻撃を未然に防ぐことができます。URL/ドメインインジケーターはWebサイトへのアクセス制御に使用され、ファイルそのもののブロックにはファイルハッシュが適しています。

*コミュニティ投票の配分*

C（100％）

質問16 トピック1

会社では以下のサービスを展開しています。✑  
Microsoft Defender for Identity  
✑ Microsoft Defender for Endpoint  
✑ Microsoft Defender for Office 365  
セキュリティアナリストに Microsoft 365 セキュリティセンターを使用する権限を与える必要があります。アナリストは、Microsoft Defender for Endpoint によって生成された保留中のアクションを承認または拒否できる必要があります。ソリューションでは、最小権限の原則を使用する必要があります。  
アナリストに割り当てるべき 2 つのロールはどれですか。正解はそれぞれソリューションの一部を示しています。  
注: 正解を選択するごとに 1 ポイントが加算されます。  

- A. Azure Active Directory (Azure AD) のコンプライアンス データ管理者
- B. Microsoft Defender for Endpoint のアクティブ修復アクションの役割
- C. Azure Active Directory (Azure AD) のセキュリティ管理者ロール
- D. Azure Active Directory (Azure AD) のセキュリティ リーダー ロール

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)   [議論   26](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)

**正解** [：](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)BD🗳️  

**解説:**
最小権限の原則に従い、セキュリティアナリストがMicrosoft Defender for Endpointの保留中のアクションを承認・拒否できるようにするには、以下のロールが必要です。

- **B. Microsoft Defender for Endpoint の「アクティブ修復アクション (Active remediation actions)」ロール**: これはDefender for Endpoint内の特定の権限で、修復アクション（ファイルの隔離や実行ブロックなど）を承認するために必須です。
- **D. Azure AD のセキュリティ リーダー (Security Reader) ロール**: セキュリティセンター内の情報やアラートを表示するために必要です。「セキュリティ管理者」ロールも可能ですが、権限が強すぎるため最小権限の原則に反します。
（※選択肢Dが「セキュリティリーダー」ではなく「Global Reader」の場合もありますが、文脈上は「閲覧権限+修復実行権限」の組み合わせが正解となります。）

*コミュニティ投票の配分*

BD（82％）

紀元前（18％）

質問17 トピック1

ホットスポット -  
Microsoft Defender を使用する Microsoft 365 E5 サブスクリプションと、Azure Sentinel を使用する Azure サブスクリプションを所有しています。  
既知の悪意のあるメール送信者から送信されたメールに含まれるファイルを含むすべてのデバイスを特定する必要があります。クエリは SHA256 ハッシュの一致に基づいて実行されます。  
どのようにクエリを完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
注: 正しい選択ごとに 1 ポイント獲得できます。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0002700001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)

**正解:** ![](https://www.examtopics.com/assets/media/exam-media/04261/0002800001.jpg) 参照:  

**解説:**
1. フィルタ条件：`where isnotempty (SHA256)`

`EmailAttachmentInfo` テーブルには、ハッシュ値が記録されていない添付ファイルが含まれる場合があります。ハッシュ値がないレコードを結合処理に進めると、クエリのパフォーマンスが低下したり、意図しない一致が発生したりするため、あらかじめ値が存在するものだけに絞り込みます。今回の調査は「SHA256 ハッシュの一致」に基づいているため、この列を対象にします。

2. 結合キー：`on SHA256`

メールのデータ（左側）とデバイスのファイルイベント（右側）を紐付けるための「共通の鍵」を指定します。

- **`EmailAttachmentInfo`**: メールの添付ファイルが持つハッシュ値を保持。
    
- **`DeviceFileEvents`**: デバイス上で作成・修正されたファイルのハッシュ値を保持。 問題文の要件通り、これらを一致させるために **`SHA256`** を指定します。

質問18 トピック1

機密ファイルが外部で共有された場合にアラートを生成し、修復アクションをトリガーするようにMicrosoft Cloud App Securityを構成する必要があります。Cloud  
App Securityポータルで実行する必要がある2つのアクションはどれですか？ 正解はそれぞれ解答の一部を示しています。  
注：正解は1つにつき1ポイントです。  

- A. \[設定\] から \[Information Protection\] を選択し、\[Azure Information Protection\] を選択してから、\[このテナントからの Azure Information Protection 分類ラベルとコンテンツ検査警告のファイルのみをスキャンする\] を選択します。
- B. \[ファイルの調査\] を選択し、\[アプリを Office 365 にフィルターします。
- C. \[ファイルの調査\] を選択し、検索から \[新しいポリシー\] を選択します。
- D. \[設定\] から \[Information Protection\] を選択し、\[Azure Information Protection\] を選択してから、\[Azure Information Protection 分類ラベルとコンテンツ検査の警告について新しいファイルを自動的にスキャンする\] を選択します。
- E. \[設定\] から \[情報保護\] を選択し、\[ファイル\] を選択して、ファイル監視を有効にします。
- F. \[ファイルの調査\] を選択し、\[ファイルの種類\] を \[ドキュメント\] にフィルターします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)   [議論   37](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)

**正解：** DE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)  

**解説:**
Cloud App Security (Defender for Cloud Apps) で機密ファイルの外部共有を検出し対処するには、ファイルポリシーとInformation Protectionとの連携設定が必要です。

- **D**: 設定（Settings）の「Information Protection」→「Azure Information Protection」で、**「新しいファイルを自動的にスキャンする (Automatically scan new files...)」** を有効にします。これにより、新しくアップロードや変更されたファイルも監視対象になります（ファイル監視）。
- **C**: **「ファイルの調査 (Files)」** メニューではなく、**「ポリシー (Policies)」** メニューから「ファイルポリシー (File policy)」を新規作成します。（※正解選択肢の記述が少し変則的ですが、要点は「新しいファイルをスキャンする設定をオンにする」ことと、「ファイルポリシーを作成して外部共有を検知する」ことです。）
※一般的な手順としては、「設定でAIPスキャンを有効化」し、「ファイルポリシーを作成して、フィルタで『アクセスレベル＝外部/公開』かつ『分類ラベル＝機密』などを指定」します。選択肢Eの「ファイル監視を有効にする」もDと同義の操作を指している可能性があります。

*コミュニティ投票の配分*

ドイツ（77％）

CE（17％）

3%

質問19 トピック1

ホットスポット -  
Microsoft 365 サブスクリプションを購入しました。Microsoft  
Cloud App Security を構成する予定です。  
ボットネットネットワークから Microsoft 365 アプリへの接続を検出する、カスタムテンプレートベースのポリシーを作成する必要があります。  
どのようなポリシーを使用すべきでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
注: 正解は1つにつき1ポイントです。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0003000001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)   [議論   53](https://www.examtopics.com/exams/microsoft/sc-200/view/2/#)

**正解:** ![](https://img.examtopics.com/sc-200/image410.png)

**解説:**
ボットネットネットワークからの接続を検出するには、**「アクティビティポリシー (Activity policy)」** を使用します。

- **テンプレート**: 「ボットネットネットワークからのログオンを検出する (Potential botnet activity / Detect logon from a botnet)」といったテンプレートを選択します。
- **一致するカテゴリー**: 検出対象のIPアドレスカテゴリーとして **「ボットネット (Botnet)」**（または「脅威インテリジェンス」に含まれる不正なIP）を指定します。
これにより、既知のボットネットIPからのアクセス試行を検知し、アラートを発行することができます。

質問#20 トピック1

あなたの会社はイスタンブールにオフィスを1つ構え、Microsoft 365 サブスクリプションを契約しています。  
条件付きアクセスポリシーを使用して多要素認証（MFA）を強制適用する予定です。  
リモートワークするすべてのユーザーに MFA を適用する必要があります。  
このソリューションにはどのような内容を含めるべきですか？  

- A. 詐欺警告
- B. ユーザーリスクポリシー
- C. 名前の付いた場所
- D. サインインユーザーポリシー

**正解:** C

**解説:**
リモートワーク（社外）からのアクセスに対してのみMFAを強制し、オフィス（社内）からのアクセスではMFAを要求しない、といった制御を行うには、**「名前付きの場所 (Named locations)」** を使用します。

1. **名前付きの場所**を定義する: 本社のIPアドレス範囲を「信頼できる場所 (Trusted location)」として登録します。
2. **条件付きアクセスポリシー**を作成する:
    - 条件（Conditions）: 場所（Locations）で「すべての場所」を含め、「信頼できる場所」を除外（Exclude）します。
    - 許可（Grant）: 「多要素認証を要求する (Require multi-factor authentication)」を選択します。
これにより、「信頼できる場所以外（＝リモートワークなど）」からのアクセス時のみMFAが強制されます。
