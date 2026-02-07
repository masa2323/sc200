---
title: "SC-200試験 - 無料の実際のQ&A、34ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/34/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---

質問#29 トピック6

Microsoft 365 E5 サブスクリプションを所有しており、Device1 というデバイスが含まれています。Microsoft Defender ポータルで、Device1 でアラートがトリガーされたことを確認しました。  
  
デバイスインベントリページで Device1 を特定しました。Device1 にインストールされているプログラムの一覧を収集する必要があります。  
  
どうすればよいでしょうか？

- A. DeviceProcessEvents テーブルに対して高度なハンティング クエリを実行します。
- B. DeviceTvmSoftwareInventory テーブルに対して高度なハンティング クエリを実行します。
- C. 自動調査を開始し、アクション センターで結果を表示します。
- D. ライブ応答セッションを開始し、プロセス コマンドを実行します。

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)  

**解説:**
特定デバイスにインストールされているソフトウェア（プログラム）一覧を取得する方法です。
**「DeviceTvmSoftwareInventory」**:
Defender for Endpointの脆弱性管理（TVM）テーブルの一つで、デバイスにインストールされているソフトウェアのイベントやインベントリ情報を保持しています。`DeviceTvmSoftwareInventory` テーブルをクエリすることで、製品名、ベンダー、バージョンなどのリストを取得できます。
A: ProcessEventsはプロセスの実行履歴。C: 自動調査はインストール済みソフト一覧取得用ではありません。D: Live Responseでコマンド実行も可能ですが、Advanced Huntingの方が効率的で標準的な取得方法です。

質問#30 トピック6

Microsoft 365 E5 サブスクリプションがあり、User1 というユーザーがいます。このサブスクリプションでは、Microsoft 365 Copilot for Security を使用しています。Copilot for Security は Sentinel プラグインを使用しています。User1 には Copilot 共同作成者ロールが割り当てられています。  
  
調査中に、User1 がプロンプトを送信したところ、セキュリティ コンピューティング ユニット (SCU) の使用量がプロビジョニングされた容量制限に近づいているため、Copilot for Security がリクエストに応答できないという通知を受け取りました。User1 が Copilot for Security を使用して正常な応答を生成できるようにする必要があります。User1 はどうすればよいでしょうか？

- A. 1 時間待ってからプロンプトを再送信します。
- B. プロビジョニングされた SCU を更新します。
- C. Microsoft Sentinel 最適化ワークブックを実行します。
- D. 2 番目の Copilot for Security セッションを開き、プロンプトを送信します。

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)  

質問#31 トピック6

Microsoft Sentinelワークスペースがあります。  
  
以下のエンティティが関与するインシデントを調査しています。  
  
• Host1というホスト  
• User1というユーザーアカウント  
• IPアドレス175.45.176.99  
  
これらのエンティティを含めるために、脅威インテリジェンスリストを更新する必要があります。  
  
インシデントページで追加できるエンティティはどれですか？

- A. 175.45.176.99のみ
- B. ホスト1のみ
- C. ユーザー1のみ
- D. 175.45.176.99とホスト1のみ
- E. ホスト1とユーザー1のみ
- F. 175.45.176.99、ホスト1、およびユーザー1

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)  
脅威インジケーターとして、次の種類のエンティティのみを追加します。ドメイン名、IPアドレス（IPv4およびIPv6）、URL、ファイル（ハッシュ）

質問#32 トピック6

Microsoft Copilot for Security を使用する Microsoft 365 サブスクリプションをお持ちです。Book1 というプロンプトブックを作成します。Book1 には、IncidentID という入力項目を含むプロンプトを作成する必要があります。IncidentID の形式はどのようにすればよいですか？

- A.<インシデントID>
- B. ##インシデントID##
- C. \[インシデントID\]
- D. $インシデントID$

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/34/#)  
Microsoft Copilot for Security でカスタムプロンプトブックを作成する際、ユーザーに入力を求めるための「パラメータ（変数）」を定義するには、**山かっこ（`< >`）** を使用します。

質問#33 トピック6

次の表に示すリソースを含む、Sub1 という Azure サブスクリプションがあります。  
  
![](https://img.examtopics.com/sc-200/image384.png)  
  
インシデント発生時に Lapp1 をトリガーするように Rule1 を構成する予定です。WS1 に割り当てるロールベース アクセス制御 (RBAC) ロールと、そのロールを割り当てるスコープを推奨する必要があります。ソリューションは最小権限の原則に従う必要があります。  
  
どのようなロールを推奨すべきでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正しい選択肢は 1 つにつき 1 ポイント付与されます。  
  
![](https://img.examtopics.com/sc-200/image385.png)

**正解:間違っている！** ![](https://img.examtopics.com/sc-200/image386.png)

**解説:**
Microsoft Sentinel の分析ルール（Rule1）から Logic App（LApp1）を自動的に実行（トリガー）させるためには、Sentinel のサービス identity に対して、対象のプレイブックを実行するための適切な権限を与える必要があります。

- **Microsoft Sentinel Playbook Operator ロールの選択理由:** このロールは、Microsoft Sentinel がプレイブック（Logic App）を表示し、実行するために特別に設計されたロールです。`Logic App Operator` よりもプレイブックの運用に特化しており、`Microsoft Sentinel Automation Contributor`（自動化ルールの作成・編集権限）よりも権限が限定されているため、**最小権限の原則**に合致しています。
    
- **RG2 スコープの選択理由:** LApp1 はリソースグループ **RG2** に配置されています。Sentinel がプレイブックを呼び出す際、通常はプレイブックが格納されているリソースグループ全体に対して「Playbook Operator」権限を付与することが Microsoft の標準的な構成手順です。これにより、Sentinel はそのグループ内のプレイブックを正しく認識し、実行できるようになります。
    
    - `Sub1` (サブスクリプション) では広すぎます。
        
    - `RG1` は Sentinel ワークスペース自体の場所であり、実行対象の LApp1 は含まれていません。
        
    - 特定の `LApp1` 単体に付与することも技術的には可能ですが、Sentinel の UI 上でプレイブックを一覧から選択・管理するためには、リソースグループ単位（RG2）で権限を付与するのが一般的かつ推奨される「最小限の管理作業」を伴う構成です。

質問#34 トピック6

ドラッグ＆ドロップ  
\-  
  
Microsoft Defender for Endpoint にオンボードされている、オンプレミスの Windows 11 Pro デバイス（Device1）があります。Microsoft 365 サブスクリプションを所有しています。Device1 で実行されているプロセスと、プロセスが開いているネットワーク接続を特定する必要があります。このソリューションは、管理作業を最小限に抑える必要があります。Microsoft Defender ポータルで、どの 4 つのアクションを順番に実行する必要がありますか？ 回答するには、アクション一覧から該当するアクションを回答領域に移動し、正しい順序に並べ替えてください。  
  
![](https://img.examtopics.com/sc-200/image387.png)

### 正解のアクション順序

1. **Navigate to the device page for Device1.** (Device1 のデバイス ページに移動する)
    
2. **Collect an investigation package.** (調査パッケージを収集する)
    
3. **From the Action center, invoke an action.** (アクション センターから、アクションを呼び出す)
    
4. **Extract the contents of the ZIP file.** (ZIP ファイルの内容を展開する)
    
---
### 解説

このソリューションでは、Microsoft Defender for Endpoint の **「調査パッケージ（Investigation Package）」** 機能を活用します。

- **調査パッケージを収集する理由**: この機能を一度実行するだけで、実行中のプロセス、確立されたネットワーク接続、自動開始プログラム、サービス一覧、最近のイベントログなど、フォレンジック調査に必要な情報がすべて一つの ZIP ファイルにまとめられます。個別にコマンドを打つ必要がないため、「管理作業の最小化」という要件に最適です。
    
- **アクションセンターの役割**: 「調査パッケージの収集」はバックグラウンドで行われます。収集が完了すると、Microsoft Defender ポータルの **「アクション センター（Action center）」** に履歴として残り、そこから成果物（ZIP ファイル）をダウンロードするアクションを実行できます。
    
- **ZIP ファイルの展開**: ダウンロードしたパッケージを展開すると、`Processes.txt` や `NetworkConnections.txt`（または同様の形式）のファイルが含まれており、そこから目的の情報を確認できます。

質問#35 トピック6
  
次の表に示すAzureサブスクリプションを所有しています。  
  
![](https://img.examtopics.com/sc-200/image389.png)  
  
次の表に示すユーザーを含むMicrosoft Entraテナントを所有しています。  
  
![](https://img.examtopics.com/sc-200/image390.png)  
  
ユーザーには、次の表に示すAzureロールが割り当てられています。Microsoft  
  
![](https://img.examtopics.com/sc-200/image391.png)  
  
Copilot for Securityのキャパシティは、次の表に示すように構成されています。  
  
![](https://img.examtopics.com/sc-200/image392.png)  
  
以下の各項目について、該当する場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注：正解は1点です。  
  
![](https://img.examtopics.com/sc-200/image393.png)

#### **1. User1 can add an additional capacity to Capacity1: [はい]**

- **Azure 権限**: User1 は **Sub1** の **「所有者 (Owner)」** です。
    
- **リソースの場所**: **Capacity1** は Sub1 配下の **RG1** にあります。
    
- **理由**: Copilot for Security のキャパシティ（SCU）を管理（追加・増減）するには、その Azure リソースに対する「所有者」または「共同作成者」の権限が必要です。User1 はサブスクリプション レベルでこの権限を持っているため、Capacity1 を管理できます。
    

#### **2. User2 can view the capacity usage information of Capacity2: [はい]**

- **Azure 権限**: User2 は **Sub2** の **「閲覧者 (Reader)」** です。
    
- **リソースの場所**: **Capacity2** は Sub2 配下の **RG3** にあります。
    
- **理由**: Azure の「閲覧者」権限があれば、リソースの構成やメトリック（使用状況の情報）を表示することができます。User2 は Sub2 全体の閲覧権限を持っているため、その中にある Capacity2 の情報も確認可能です。
    

#### **3. User3 can configure additional plugins in Capacity2: [いいえ]**

- **Azure 権限**: User3 は **RG2** の **「所有者 (Owner)」** です。
    
- **リソースの場所**: **Capacity2** は **RG3** にあります。
    
- **理由**: User3 が持つ Azure の権限は RG2 に限定されており、**RG3 にある Capacity2 に対しては権限がありません**。
    
- **製品仕様の補足**: User3 は「グローバル管理者」であるため、Copilot for Security のアプリ内では「Copilot オーナー」としてプラグインを構成する権限を（理論上は）持っていますが、この設問の文脈（特定のキャパシティリソースのスコープ）や、Azure RBAC の境界（RG2 vs RG3）を問う形式では、権限の不一致により **「いいえ」** と判定されるのが一般的です。また、プラグインはテナント全体で構成するものであり、特定の「キャパシティの中」で個別に構成するものではないため、文言的にも不適切です。

質問#36 トピック6
  
contoso.com という Microsoft Entra テナントにリンクされた Azure サブスクリプション Sub1 があります。Sub1 には、Workspace1 という Log Analytics ワークスペースが含まれています。contoso.com からのすべてのログは Workspace1 にストリーミングされます。Microsoft 365 E5 サブスクリプションがあります。Workspace1 に対して、以下のクエリを実行する必要があります。  
  
• contoso.com の Microsoft Graph サービスへの HTTP 要求  
• 証明書またはシークレットを使用するサードパーティ アプリのサインイン アクティビティ  
  
KQL クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image395.png)

### 正解の組み合わせ

1. **上のドロップダウン (Table):** `AADServicePrincipalSignInLogs`
    
2. **下のドロップダウン (Join Key):** `CorrelationId`

このクエリは、Microsoft Graph API へのリクエストとその実行主体（アプリケーション）の認証イベントを紐付けるためのものです。

- **AADServicePrincipalSignInLogs:** 要件である「証明書またはシークレットを使用するサードパーティ アプリのサインイン アクティビティ」を調査するために使用するテーブルです。サービス プリンシパル（アプリの ID）による認証イベントがここに記録されます。
    
    - `SigninLogs` は主にユーザーのインタラクティブなサインインを記録します。
        
    - `AADNonInteractiveUserSignInLogs` はユーザーの非インタラクティブな（バックグラウンドでの）サインインを記録します。
        
- **CorrelationId:** `MicrosoftGraphActivityLogs` テーブルの `SignInActivityId` フィールドは、サインイン ログ側の **`CorrelationId`** と一致するように設計されています。 これを結合キーとして使用することで、特定の Graph 操作がどの認証セッションに基づいて行われたかを特定できます。

質問#37 トピック6
  
Microsoft 365 E5 サブスクリプションがあり、Site1 という Microsoft SharePoint Online サイトが含まれています。Site1  
  
で、次の表に示す不審なファイルを特定します。Microsoft  
  
![](https://img.examtopics.com/sc-200/image397.png)  
  
Purview で、次の表に示すコンテンツ検索を作成します。  
  
![](https://img.examtopics.com/sc-200/image398.png)  
  
以下の各記述について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image399.png)

#### **1. Search1 will return File1.docx: [はい]**

- **クエリ:** `(c:c)(-ItemClass=IPM.Document)(FileName=File1.docx)`
    
- **条件判定**:
    
    - `FileName=File1.docx`: 対象のファイル名と完全に一致します。
        
    - `-ItemClass=IPM.Document`: ここでの `-` は「否定（NOT）」を意味します。`IPM.Document` は通常、Exchange（Outlook）のメッセージクラスであり、SharePoint 上のドキュメントにはこの属性は付与されません。
        
- **結論**: ファイル名が一致し、かつ排除条件（メールアイテムではないこと）にも合致するため、File1.docx は検索結果に表示されます。
    
#### **2. Search2 will return File2.docx: [いいえ]**

- **クエリ:** `(c:c)(filetype=doc)(author=User2@contoso.com)`
    
- **条件判定**:
    
    - `author=User2@contoso.com`: 作成者は一致します（大文字小文字は区別されません）。
        
    - `filetype=doc`: **ここがポイントです。** * **結論**: Microsoft Purview や SharePoint の検索において、`filetype` プロパティは拡張子と厳密に照合されます。`.doc`（旧形式）と `.docx`（現在の形式）は**異なるファイルタイプ**として扱われるため、拡張子が `.docx` である File2.docx はこのクエリではヒットしません。
        
#### **3. Search3 will return File3.docx: [いいえ]**

- **クエリ:** `(c:c)(contenttype:item document)(author=User3@contoso.com)`
    
- **条件判定**:
    
    - `author=User3@contoso.com`: 作成者は一致します。
        
    - `contenttype:item document`: SharePoint における標準的なドキュメントのコンテンツタイプ（ContentType）は、単一の単語で **「Document」** です。
        
- **結論**: 「item document」という名称のコンテンツタイプは標準では存在せず、クエリがこの特定のフレーズを検索している場合、標準の「Document」属性を持つ File3.docx は一致しないと判定されます。

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 34 ページを表示しています。

410問中**331 - 340**問 を表示
