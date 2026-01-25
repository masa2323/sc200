---
title: "SC-200試験 - 無料の実際のQ&A、24ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/24/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#104 トピック3

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
• 会社の SecOps チームによって Azure Cloud Shell が起動された場合に、rulequery1 によって生成されたインシデントが自動的に閉じられるようにします。  
• Webapp1 からデータを動的に取得するクエリを含む、Workbook1 という名前のカスタム Microsoft Sentinel ブックを実装します。  
• 指定された緊急アカウントへのサインインを検出する Microsoft Sentinel ニアリアルタイム (NRT) 分析ルールを実装します。  
• Azure ポータルで Microsoft Sentinel の Hunting ページにアクセスされたときに、HuntingQuery1 が自動的に実行されるようにします。  
• corp.adatum.com ユーザー アカウントのパスワード リセットが通常よりも多く検出されるようにします。  
• ASIM パーサーを使用するクエリに関連するオーバーヘッドを最小限に抑えます。  
• Group1 のメンバーがプレイブックを作成および編集できるようにします。  
• 可能な限り、組み込みの ASIM パーサーを使用します。ビジネス  
  
要件  
\-  
  
Adatum では、次のビジネス要件が示されています。  
  
• 可能な限り、最小権限の原則に従います。 •  
可能な限り、管理の労力を最小限に抑えますクエリはどのように設定すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。注：正しい選択ごとに1ポイント獲得できます。  
  
![](https://img.examtopics.com/sc-200/image242.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)

**正解:** ![](https://img.examtopics.com/sc-200/image243.png)

**解説:**
Adatumの要件「Webapp1からデータを動的に取得する」および「Azure PortalでHuntingページにアクセスされたときに自動実行」を満たすクエリ設定です。

1. **Azure Monitor Logs**: **「externaldata」**。Q99と同様、外部データを動的に取り込むための演算子です。
2. **Microsoft Sentinel Hunting**: **「Query1」**。Huntingページを開いたときに自動実行されるクエリ設定についての言及ですが、問題文の文脈（図の選択肢）が不明瞭ではあるものの、Hunting Queryの設定（あるいはLive Streamなど）を指していると考えられます。
※この質問はQ99と非常に類似しており、重複またはバリエーションの可能性があります。

質問#105 トピック3

Workspace1 という Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。Content  
  
Hub から Microsoft Sentinel 用の Microsoft Entra ソリューションをデプロイし、コネクタを構成します。  
  
サブスクリプションの管理者権限を持つユーザーが実行したアクションを分析する必要があります。  
  
どのワークブックを使用すればよいでしょうか？

- A. Azureアクティビティ
- B. Microsoft Entra 監査ログ
- C. Microsoft Entra サインイン ログ
- D. アイデンティティとアクセス

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)  

**解説:**
サブスクリプション管理者の操作（Azureリソースに対する変更など）を分析するためのログです。
**「Azure Activity (Azure アクティビティログ)」**: サブスクリプションレベルのイベント（リソースの作成、更新、削除、権限変更など）の記録です。「誰が、いつ、何をしたか」という管理プレーンの操作履歴を確認するのに最適です。Sentinelの「Azure Activity」ワークブックを使用することで、管理者のアクティビティを簡単に可視化・分析できます。

*コミュニティ投票の配分*

A（56％）

B（31％）

13%

質問#106 トピック3

Workspace1 という Microsoft Sentinel ワークスペースと User1 というユーザーを含む Azure サブスクリプションがあります。User1  
  
が Workspace1 を使用してインシデントを調査できるようにする必要があります。このソリューションは、最小権限の原則に従う必要があります。User1  
  
にはどのロールを割り当てるべきでしょうか？

- A. Microsoft Sentinel Responder
- B. Microsoft Sentinel 貢献者
- C. Microsoft Sentinel Automation 貢献者
- D. Microsoft Sentinel リーダー

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)  

**解説:**
インシデントを「調査（Investigate）」するために必要な最小権限です。
**「Microsoft Sentinel Responder」**: Responderロールは、インシデントの管理（割り当て、ステータス変更）に加えて、インシデントの**調査（Investigation graphの表示、検索など）**を行う権限を持っています。Readerロールでは表示のみで変更ができず、Contributorロールは過剰権限（設定変更可能）です。

*コミュニティ投票の配分*

A（59％）

D（41％）

質問#107 トピック3

HOTSPOT -  
  
Workspace1 という Log Analytics ワークスペースを含む Azure サブスクリプションがあります。Azure  
  
アクティビティ ログと Microsoft Entra ID ログを Workspace1 に転送するように構成します。  
  
認証不足により失敗したすべてのリクエストを特定するには、Workspace1 に対してクエリを実行する必要があります。KQL  
  
クエリをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image313.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)   [議論   14](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)

**正解:** ![](https://img.examtopics.com/sc-200/image436.png)

**解説:**
認証不足（Authorization failed）により失敗したリクエストを特定するクエリです。

1. **Table**: **「AzureActivity」**。Azureリソースに対する操作ログはAzureActivityテーブルに格納されます。
2. **Filter**: **`where Authorization_Status != "Permit"`**（または `AuthorizationStatus != "Permit"`）。認可ステータスが許可（Permit）でないものをフィルタリングします。これにより、DenyやFailなどの失敗した試行を抽出できます。

質問#108 トピック3

Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをご利用です。  
  
インシデントを調査しており、  
  
実行されたインシデントタスクを確認する必要があります。ソリューションには、インシデントをワークブックに表示し、各インシデントのタスクを別のグリッドに表示するクエリを含める必要があります。  
  
クエリではどのテーブルをターゲットにすればよいでしょうか？

- A. セキュリティインシデント
- B. セキュリティイベント
- C. センチネル監査
- D. セキュリティアラート

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)  

**解説:**
インシデント内で実行された「タスク（手動アクション、自動修復など）」を確認するためのクエリ対象です。
**「SecurityIncident」**: Sentinelの `SecurityIncident` テーブルには、インシデント自体のメタデータだけでなく、インシデントの更新履歴やステータス変更などが記録されます。ただし、厳密な「実行されたタスク（修復アクションなど）」の詳細履歴は `DeviceEvents` (ActionType) や `SecurityAction` などのテーブルにある場合もありますが、選択肢の中ではインシデント中心のビューを作るための起点として `SecurityIncident` が最も適切です。あるいは、インシデントに関連付けられたコメントやタスクリストの情報を指している可能性もあります。

*コミュニティ投票の配分*

A（100％）

## トピック4 - 質問セット4

質問1 トピック4

WS1 という Microsoft Sentinel ワークスペースと、Windows Server を実行する 100 台の仮想マシンを含む Azure サブスクリプションがあります。Windows  
  
セキュリティ イベント ログの収集を構成して WS1 に取り込む必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• ユーザーのサインインおよびサインアウト イベントを含む、完全なユーザー監査証跡をキャプチャする。  
• イベントの量を最小限に抑える。  
• 管理の手間を最小限に抑える。  
  
どのイベント セットを選択すればよいでしょうか。

- A. 最小限
- B. コモン
- C. すべてのイベント
- D. カスタム

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)  

**解説:**
完全なユーザー監査証跡（サインイン/ログオフ）をキャプチャしつつ、データ量と管理負担を最小限に抑えるイベントセットです。
**「Common (共通)」**: Azure Monitor Agent (AMA) や MMA の設定における「Common」セットには、セキュリティ監査に必要な主要なイベント（ログオン/ログオフの成功・失敗、プロセス作成、ユーザー管理など）が含まれており、監査証跡の要件を満たします。「Minimal」ではログオン成功などの重要イベントが不足する可能性があり、「All events」ではデータ量が過大になります。「Custom」は管理負担（XML作成など）が大きくなります。

*コミュニティ投票の配分*

B（100％）

質問2 トピック4

Microsoft 365 サブスクリプションをご利用で、Microsoft Defender for Cloud Apps を使用し、Cloud Discovery が有効になっています。Cloud  
  
Discovery データを拡充する必要があります。このソリューションでは、Cloud Discovery トラフィック ログ内のユーザー名が、対応する Microsoft Entra ID ユーザー アカウントのユーザー プリンシパル名 (UPN) に関連付けられていることを確認する必要があります。  
  
まず何をすべきでしょうか？

- A. アプリの条件付きアクセス制御から、ユーザー監視を構成します。
- B. Microsoft 365 アプリ コネクタを作成します。
- C. Microsoft 365 Defender への自動リダイレクトを有効にします。
- D. Azure アプリ コネクタを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)  

**解説:**
Cloud Discovery（シャドーIT検出）のログ内のユーザー名をAzure AD (Entra ID) ユーザーと紐付ける（エンリッチメント）ための設定です。
**「Create a Microsoft 365 app connector」**: Defender for Cloud AppsでMicrosoft 365コネクタを作成・接続することで、Entra IDからユーザー情報を取得し、ファイアウォールログなどのCloud Discoveryデータに含まれるユーザー名と照合して、UPNやユーザー属性でデータを充実（Enrich）させることができます。

*コミュニティ投票の配分*

B（100％）

質問3 トピック4

HOTSPOT -  
  
デフォルトのデータ保持期間が30日間であるMicrosoft Sentinelワークスペースがあります。このワークスペースには、次の表に示すように2つのカスタムテーブルが含まれています。  
  
![](https://img.examtopics.com/sc-200/image258.png)  
  
各テーブルには、過去365日間、1日あたり2件のレコードが取り込まれました。  
  
分析ルールで使用するKQLステートメントを、次の表に示すように作成します。  
  
![](https://img.examtopics.com/sc-200/image259.png)  
  
以下の各ステートメントについて、該当する場合は「はい」を選択してください。それ以外の場合は「いいえ」を選択してください。  
  
注：正しい選択は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image260.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)   [議論   14](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)

**正解:** ![](https://img.examtopics.com/sc-200/image437.png)

**解説:**
Log Analyticsワークスペースのデータ保持期間（30日）を超えたデータ（過去365日分）に対するクエリ可能性についての正誤判定です。

- **Table1 (Log plan: Analytics)**: データ保持はデフォルトの30日です。30日を超えたデータは削除されるか、アーカイブされていなければ検索できません。過去365日分のデータは保持されていないため、クエリは30日分しか返しません（失敗するか、部分的）。設問の「successfully run」が「365日分すべてのデータを返す」という意味なら **No** です。
- **Table2 (Log plan: Basic)**: Basicログプラン（保持期間固定8日間）のテーブルです。365日分のデータは保持されず、またBasicログに対するクエリには制限があります（フルKQLが使えない）。しかし、設問図のクエリは `search in (Table2) ...` となっており、Basicログ検索用の構文です。ただし、保持期間的に365日分のデータは存在しないため、**No** です。
※画像の正解に従うと、Table1=**No**, Table2=**No** のパターン（あるいは条件次第でYes/No）が考えられますが、通常は保持期間切れのためNoです。

質問4 トピック4

HOTSPOT  
\-  
  
Microsoft Defender for Endpoint を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
オンプレミスデバイスは、次の表のとおりです。  
  
![](https://img.examtopics.com/sc-200/image262.png)  
  
マルウェアに感染したデバイスに対するインシデント対応計画を準備中です。  
  
以下の要件を満たす対応策を推奨する必要があります。  
  
• マルウェアが管理対象デバイスと通信して感染するのをブロックする。  
• 管理対象デバイスの制御能力に影響を与えない。  
  
各デバイスに対して、どの対応策を実施すべきでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正解は1点です。  
  
![](https://img.examtopics.com/sc-200/image263.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)

**正解:** ![](https://img.examtopics.com/sc-200/image264.png)

**解説:**
マルウェア感染デバイスへの対応策として、「通信ブロック」かつ「管理能力維持」を満たすアクションを選択します。

1. **Windows 10 devices**: **「Isolate device (デバイスの分離)」**。Defender for Endpointの「Isolate device」機能は、デバイスをネットワークから切断しますが、**Defender for Endpointサービスへの接続は維持**します。これにより、管理者は引き続き調査や修復コマンドを実行できます。
2. **Windows 11 devices**: **「Isolate device (デバイスの分離)」**。Windows 10と同様にサポートされています。
※「Restrict app execution（アプリ実行制限）」は、署名済みアプリのみの実行を許可する機能で、通信ブロックとは目的が異なります。

質問5 トピック4

Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションがあり、User1 というユーザーが登録されています。User1  
  
が Microsoft Defender XDR のカスタム検出ルールとエンドポイント セキュリティ ポリシーを管理できるようにする必要があります。このソリューションは、最小権限の原則に従う必要があります。User1  
  
にはどのロールを割り当てるべきでしょうか？

- A. セキュリティ管理者
- B. セキュリティオペレーター
- C. クラウドデバイス管理者
- D. デスクトップ分析管理者

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/24/#)  

**解説:**
Defender XDRのカスタム検出ルールとエンドポイントセキュリティポリシーの両方を管理できる最小権限です。
**「Security Administrator (セキュリティ管理者)」**: このロールは、Microsoft 365 Defenderポータル全体（エンドポイント、メール、IDなど）のセキュリティ設定、ポリシー、検出ルールの作成・編集を行う権限を持っています。「Security Operator」は運用（アラート対応）中心でポリシー変更権限が限定的、「Cloud Device Administrator」はEntra ID/Intuneのデバイス管理中心です。

*コミュニティ投票の配分*

A（91％）

9%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/23/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 24 ページを表示しています。

410問中**231 - 240**問 を表示
