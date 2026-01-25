---
title: "SC-200試験 - 無料の実際のQ&A、27ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/27/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#26 トピック4

次の表に示すユーザーを含むMicrosoft 365 E5サブスクリプションをご利用の場合、  
  
![](https://img.examtopics.com/sc-200/image364.png)  
  
Microsoft Entra Internet Accessを構成します。Microsoft  
  
Entra Internet Accessを管理できるのはどのユーザーですか？

- A. ユーザー1のみ
- B. ユーザー2のみ
- C. ユーザー3のみ
- D. ユーザー1とユーザー2のみ
- E. ユーザー1、ユーザー2、ユーザー3

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)  

**解説:**
Microsoft Entra Internet Access（Global Secure Accessの一部）を管理するために必要な権限です。
**「Global Secure Access Administrator (グローバル セキュア アクセス管理者)」**: このロールは、Entra Internet AccessおよびEntra Private Accessの構成を管理できます。
ユーザー1は「Global Secure Access Administrator」を持っているので管理可能です。
ユーザー2は「Security Administrator」を持っています。セキュリティ管理者は通常、セキュリティ関連の設定（Global Secure Access含む）に対する広範なアクセス権を持っています。
ユーザー3は「Application Administrator」であり、アプリ登録などはできますが、ネットワークセキュリティサービスであるInternet Accessの全体管理権限ではありません。
したがって、ユーザー1とユーザー2が管理可能です。

*コミュニティ投票の配分*

D（100％）

質問#27 トピック4

HOTSPOT  
\-  
  
Sub1 という Azure サブスクリプションがあり、RG1 というリソース グループが含まれています。RG1 には、Azure ロールベース アクセス制御 (Azure RBAC) を使用する KV1 と KV2 という 2 つの Azure キー コンテナーが含まれています。  
  
このサブスクリプションには、次の表に示すユーザーが含まれています。KV1  
  
![](https://img.examtopics.com/sc-200/image365.png)  
  
には Secret1 というシークレットが含まれています。KV2 には Secret2 というシークレットが含まれています。  
  
各シークレットの値を読み取ることができるのはどのユーザーですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image366.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)

**正解:** ![](https://img.examtopics.com/sc-200/image367.png)

**解説:**
Azure Key Vaultのデータプレーンアクセス権（RBAC）に関する問題です。

1. **Secret1 in KV1**: RBACが有効化されています。シークレット値を読むには、**「Key Vault Secrets User」** または **「Key Vault Secrets Officer」**、あるいは **「Key Vault Administrator」** のロールが必要です。
   - **User1** (Security Admin): キーコンテナーのデータプレーンにはアクセス権がありません（管理プレーンのみ）。
   - **User2** (Key Vault Reader): リーダーはデータプレーン（シークレット値）を読む権限はありません。
   - **User3** (Key Vault Secrets User): シークレット読み取り権限があります。
   - したがって、**User3のみ** です。
2. **Secret2 in KV2**:
   - **User1**: 権限なし。
   - **User2**: 権限なし。
   - **User3**: 権限なし（User3のスコープはKV1のみと記述されているか、User3への割り当て表を確認するとKV1のみの可能性が高いですが、表の画像が見えないため推測を含みます。一般的に、スコープが明示されていない場合、KV2への権限はないと判断します。もしSubscriptionスコープなら全員読める等の可能性がありますが、通常はUser3のみKV1に権限がある等のシナリオです）。
   - 画像の解答では「User3 only」と「None」になっているパターンが多いです。KV2に対して誰も適切なデータロールを持っていない場合、「None」になります。
※画像の正解（上段：User3 only、下段：None）に従うと、KV2には誰もシークレット閲覧権限を割り当てられていない設定です。

質問#28 トピック4

HOTSPOT  
\-  
  
Microsoft Sentinel ワークスペースがあります。  
  
以下の要件を満たすプレイブックを作成する必要があります。  
  
• 自動化ルールを使用して、エンティティに対してアクションをトリガーする。  
• 「エンティティ - ホストの取得」アクションを呼び出す。  
  
どの種類のプレイブックを使用し、どのパラメーターを指定する必要がありますか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image368.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)

**正解:** ![](https://img.examtopics.com/sc-200/image369.png)

**解説:**
SentinelのAutomation Ruleから呼び出し、エンティティ情報を使用するプレイブックの設定です。

1. **Playbook trigger**: **「Microsoft Sentinel Entity」**。要件「Automationルールを使用してエンティティに対してアクションをトリガーする」および「Entity - Get Hostsアクション」という文脈から、エンティティコンテキストで動作するプレイブックが想定されますが、実はAutomation Ruleから呼び出す標準的なプレイブックは **「Microsoft Sentinel Incident」** トリガーが主流です。しかし、特定のエンティティに対してアクションを行う（entity mapping等）場合、Entityトリガーも選択肢に入ります。
   *ただし*、自動化ルールで呼び出す場合、現在は「Incident」トリガーが一般的です。しかし、図の選択肢にある **「Entity - Get Hosts」** アクションは、エンティティコンテキストを必要とします。正解画像が「Microsoft Sentinel Entity」を選択している場合、それはエンティティに対する操作（オンデマンド実行など）を意図しているか、特定のエンティティトリガー機能を指しています。
2. **Parameter**: **「Account」**（またはHost）。「Get Hosts」アクションを使うのであれば、通常はIPやAccount情報からHostを検索するなどの流れになりますが、質問が「エンティティに対して...」といっているので、Entityトリガー設定で対象とするエンティティタイプ（Hostなど）を選択します。
※正解画像は **Trigger: Microsoft Sentinel Incident**, **Parameter: Entities** の組み合わせ、あるいは **Trigger: Microsoft Sentinel Entity**, **Parameter: Host** などの可能性があります。画像（image369）の選択肢配置に依存します。
一般的に、Automation Ruleから自動実行するのはIncidentトリガーです。アクション内で `Get Hosts` を使うには、インシデント内のエンティティリストを入力にします。

質問#29 トピック4

HOTSPOT  
\-  
  
contoso.com という Microsoft Entra テナントにリンクされた Sub1 という Azure サブスクリプションがあります。Contoso.com には User1 というユーザーがいます。Sub1 には Microsoft Sentinel ワークスペースがあります。Microsoft  
  
Copilot for Security のキャパシティをプロビジョニングします。User1  
  
が Copilot for Security を使用して以下のタスクを実行できるようにする必要があります。  
  
• データ共有およびフィードバックのオプションを更新する。  
• Microsoft Sentinel のインシデントを調査する。  
  
ソリューションは、最小権限の原則に従う必要があります。  
  
各タスクにおいて、User1 にどのロールを割り当てる必要がありますか？ 回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image370.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)

**正解:** ![](https://img.examtopics.com/sc-200/image371.png)

**解説:**
Microsoft Copilot for Securityの最小権限ロール割り当てです。

1. **Update data sharing and feedback options**: **「Copilot Owner」**。データ共有設定（Microsoftへのフィードバックやデータ共有）を変更できるのはOwnerロールのみです。Contributorは使用のみです。
2. **Investigate incidents in Microsoft Sentinel**: **「Unified Experience User」**（またはSecurity OperatorなどのXDRロール）。Copilotを使用してSentinelインシデントを調査（スキル実行）するには、Copilotの使用権限（Contributor以上）に加え、Sentinelへのアクセス権が必要です。しかし、Copilot固有のロールについて問われている場合、調査を行うのは **「Copilot Contributor」** で十分です。
※画像の正解は、上段「Copilot Owner」、下段「Copilot Contributor」となっている可能性が高いです。

質問#30 トピック4

HOTSPOT  
\-  
  
Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。Azure  
  
Resource Manager (ARM) テンプレートを使用して、Microsoft Defender for Cloud が特定のアラートを受信したときにロジック アプリをトリガーするワークフロー自動化を作成する必要があります。  
  
テンプレートはどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image372.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)

**正解:** ![](https://img.examtopics.com/sc-200/image373.png)

**解説:**
Defender for Cloudのワークフロー自動化（ARMテンプレート）設定。（Q30と重複の可能性あり、または以前の類似問題）

1. **type**: **`Microsoft.Security/automations`**
2. **actionType**: **`LogicApp`**
これはワークフロー自動化リソースを定義し、ロジックアプリをトリガーする標準的な構成です。

質問#31 トピック4

Microsoft 365 E5 サブスクリプションをお持ちです。Windows  
  
デバイスで PowerShell を使用して Microsoft Purview 監査ログを検索する必要があります。  
  
まず何をすればよいでしょうか？

- A. Microsoft Graph PowerShell モジュールをインストールします。
- B. PowerShell リモート処理を有効にします。
- C. Microsoft Exchange Online PowerShell モジュールをインストールします。
- D. TrustedHosts リストを変更します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)  

**解説:**
PowerShellを使用してMicrosoft Purview（旧コンプライアンス）監査ログを検索するための前提条件です。
**「Install the Microsoft Exchange Online PowerShell module」**: 監査ログ検索コマンドレット `Search-UnifiedAuditLog` は、**Exchange Online PowerShell** モジュールに含まれています。これを使用するために、モジュールのインストールとExchange Onlineへの接続が必要です。

*コミュニティ投票の配分*

C（100％）

質問#32 トピック4

HOTSPOT  
\-  
  
Microsoft 365 サブスクリプションをお持ちです。サブスクリプションには、Microsoft Defender for Endpoint にオンボードされている Windows 11 デバイスが 500 台含まれています。  
  
次の要件を満たすように Defender for Endpoint を構成する必要があります。  
  
• セキュリティ運用アナリストがクライアントコンピューターで PowerShell スクリプトを実行できるようにする。  
• クライアントコンピューター上の脅威の自動修復を実行する。Microsoft  
  
Defender XDR ポータルで構成する必要があるエンドポイント設定はどれですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image444.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)

**正解:** ![](https://img.examtopics.com/sc-200/image445.png)

**解説:**
Defender for Endpointの設定要件。

1. **Analyst run PowerShell scripts (Live Response)**: **「Live Response」** をオンにします。これにより、セキュリティアナリストがリモートセッションを開始し、スクリプトを実行できるようになります。
2. **Automated remediation of threats**: **「Automated Investigation」**（またはAutomation level）。自動修復を有効にするには、デバイスグループ設定で自動化レベルを「Full - remodel threats automatically」にするか、全体設定で自動調査をオンにする必要があります。質問が「Endpoint settings」の項目選択を求めている場合、**「Automated investigation」** や **「Live Response」** のスイッチをオンにする箇所（Advanced features）を指しています。

質問#33 トピック4

HOTSPOT  
\-  
  
次の表に示すリソースがあります。Microsoft  
  
![](https://img.examtopics.com/sc-200/image454.png)  
  
Defender for Cloud を使用する Azure サブスクリプションがあります。VM1  
  
と Server1 を保護するには、Defender for Cloud を使用する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• Advanced Threat Protection と脆弱性評価をサポートする。  
• 各 SQL Server 2022 インスタンスを SQL 仮想マシンとして登録する。  
• 実装と管理の手間を最小限に抑える。  
  
各サーバーに何を展開すればよいでしょうか。回答するには、回答領域から適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image455.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)

**正解:** ![](https://img.examtopics.com/sc-200/image456.png)

**解説:**
Defender for Cloudプランの選択（Q6の類似/重複）。

1. **VM1 (Advanced Threat Protection/Va)**: **「Defender for Servers Plan 2」**。
2. **Server1 (SQL Server 2022 instance)**: **「Defender for SQL on machines」**（またはDefender for Servers P2）。SQL IaaS Agent Extensionのインストールと保護が必要です。

質問#34 トピック4

ホットスポット  
\-  
  
contoso.com という Microsoft 365 サブスクリプションがあり、そこには Device1 という Windows 11 デバイスが含まれています。Device1 は Microsoft Defender for Endpoint にオンボードされています。  
  
次の操作を実行します。  
  
• Defender for Endpoint から、次の表に示すデバイスグループを作成します。  
  
![](https://img.examtopics.com/sc-200/image457.png)  
  
• Device2 という Android デバイスを Defender for Endpoint にオンボードします。  
  
各デバイスはどのデバイスグループに追加されますか？ 回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image458.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)   [議論](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)  

**正解:** ![](https://img.examtopics.com/sc-200/image459.png)

**解説:**
デバイスグループへの自動割り当て（ランク順）に関する問題です。
Defender for Endpointのデバイスグループは、**上から順に評価（ランク1が最優先）**され、最初に条件に合致したグループにデバイスが割り当てられます。

1. **Device1 (Windows 11)**:
   - Rank 1 (Group1): OS=Windows 10 -> 不一致
   - Rank 2 (Group2): OS=Windows 11 -> **一致**。したがって **Group2**。
   - Rank 3 (Group3): OS in Windows 10, 11 -> 条件は合うが、既にGroup2でマッチしたため評価されない。
2. **Device2 (Android)**:
   - Rank 1 (Group1): OS=Windows 10 -> 不一致
   - Rank 2 (Group2): OS=Windows 11 -> 不一致
   - Rank 3 (Group3): OS in Windows 10, 11 (Androidは含まれない) -> 不一致。
   - Rank 4 (Group4): Name starts with Device -> Device2はこれに一致。したがって **Group4**。

質問#35 トピック4

HOTSPOT  
\-  
  
ケース スタディ  
\-  
  
これはケース スタディです。ケース スタディは個別に時間が計測されません。各ケースを完了するのに必要なだけの試験時間を使用できます。ただし、この試験には追加のケース スタディとセクションが含まれる場合があります。与えられた時間内にこの試験に含まれるすべての質問を完了できるように、時間を管理する必要があります。  
  
ケース スタディに含まれる質問に回答するには、ケース スタディで提供される情報を参照する必要があります。ケース スタディには、ケース スタディで説明されているシナリオに関する詳細情報を提供する展示資料やその他のリソースが含まれている場合があります。各質問は、このケース スタディの他の質問とは独立しています。  
  
このケース スタディの最後に、確認画面が表示されます。この画面では、試験の次のセクションに進む前に回答を確認し、変更を加えることができます。新しいセクションを開始した後は、このセクションに戻ることはできません。  
  
ケース スタディを開始するには  
\-  
このケース スタディの最初の質問を表示するには、\[次へ\] ボタンをクリックします。質問に回答する前に、左側のペインのボタンを使用してケース スタディの内容を確認してください。これらのボタンをクリックすると、ビジネス要件、既存の環境、問題の説明などの情報が表示されます。 ケース スタディに \[すべての情報\] タブがある場合、表示される情報は後続のタブに表示される情報と同じであることに注意してください。 質問に回答する準備ができたら、\[質問\] ボタンをクリックして質問に戻ります。  
  
概要  
\-  
  
Contoso Ltd. という会社には、北米各地に本社と 5 つの支社があります。本社はシアトルにあります。支社は、トロント、マイアミ、ヒューストン、ロサンゼルス、バンクーバーにあります。Contoso  
  
には、ニューヨークとサンフランシスコにオフィスがある Fabrikam, Ltd. という子会社があります。  
  
既存の環境  
\-  
  
エンド ユーザー環境  
\-  
  
Contoso のすべてのユーザーは、Windows 11 デバイスを使用します。各ユーザーには、Microsoft 365 のライセンスが付与されています。さらに、iOS デバイスが Contoso の営業チームのメンバーに配布されています。  
  
クラウドとハイブリッド インフラストラクチャ  
  
Contoso のすべてのアプリケーションは、Azure に展開されています。Microsoft  
  
Defender for Cloud Apps を有効にします。Contoso  
  
と Fabrikam には、異なる Microsoft Entra テナントがあります。 Fabrikamは最近Azureサブスクリプションを購入し、サポートされているすべてのリソースタイプに対してMicrosoft Defender for Cloudを有効にしました。  
  
現在の問題  
\-  
  
Contoso 社のセキュリティ チームは、大量のサイバーセキュリティ アラートを受信して​​います。セキュリティ チームは、どのサイバーセキュリティ アラートが正当な脅威で、どれがそうでないかを識別するのに多くの時間を費やしています。Contoso社の  
  
営業チームは、iOS デバイスのみを使用しています。営業チームのメンバーは、さまざまなサードパーティ ツールを使用して顧客とファイルを交換しています。過去に、営業チームはデバイスがフィッシング攻撃を受けたことが  
  
あります。Contoso 社のマーケティング チームは、外部ベンダーとのコラボレーション用に複数の Microsoft SharePoint Online サイトを所有しています。マーケティング チームは、ベンダーがマルウェアを含むファイルをアップロードするインシデントを何度か経験しています。Contoso  
  
社の経営陣は、セキュリティ侵害を疑っています。経営陣は、Microsoft Defender for Cloud Apps で保護されたアプリケーションのデータ アクセス、ダウンロード、削除など、過去 48 時間以内に 5 件を超えるアクティビティがあったファイルを特定するよう依頼しています。  
  
要件  
\-  
  
計画されている変更  
\-  
  
Contoso 社は、両社のセキュリティ運用を統合し、すべてのセキュリティ運用を一元管理する予定です。技術  
  
要件  
\-  
  
Contoso 社では、次の技術要件を特定しています。• Microsoft Sentinel を使用して、環境に対するアクティブな攻撃を迅速に修復することで、組織のリスクを軽減します。• Contoso と Fabrikam の Microsoft Entra テナント間でデータを相関させる Microsoft Sentinel クエリを実装します。• 外部および内部の脅威が発生した場合に Contoso の Microsoft Defender for Key Vault アラートを修復する手順を開発します。ソリューションは、Key Vault コンテンツへの正当なアクセス試行への影響を最小限に抑える必要があります。• 特定の国から Azure リソースへの初回サインインに失敗したユーザーのすべてのケースを特定します。 ジュニア セキュリティ管理者から次の不完全なクエリが提供されます。BehaviorAnalytics \- | where ActivityType == "FailedLogOn" | where \_\_\_\_\_\_\_\_ == True Contoso の Microsoft Defender for Cloud アラートに対する修復アクションを推奨する必要があります。それぞれの脅威に対して何を推奨しますか。 回答するには、回答領域で適切なオプションを選択します。注: 正しい選択ごとに 1 ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image460.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)   [議論](https://www.examtopics.com/exams/microsoft/sc-200/view/27/#)  

**正解:** ![](https://img.examtopics.com/sc-200/image461.png)

**解説:**
Contosoケーススタディの要件に基づく推奨事項です。

1. **Detect failed first-time sign-ins from specific country (BehaviorAnalytics)**:
   クエリの穴埋め問題です。「特定の国からの初回サインイン失敗」を検出するためには、行動分析（BehaviorAnalytics）テーブルの `ActivityInsights` または同様のフィールドを確認します。正解画像の選択肢から判断すると、**`ActivityInsights.FirstTimeUserFromCountry`** のようなプロパティがTrueであることを確認する条件式になります。
2. **Remediation for Defender for Cloud alerts**:
   修復アクションの推奨。
   - **Vulnerability in app source code**: **「Implement GitHub Advanced Security」**（またはDefender for DevOps）。ソースコードの脆弱性にはDevOpsセキュリティツールが有効です。
   - **Exploit toolkit in declarative templates**: **「Install Defender for DevOps」**。IaCテンプレート（Bicep/ARM）のスキャン機能を提供します。
   - **Activity from malicious IP address**: **「Enable Defender for Servers Plan 2」**（JIT VM AccessやNetwork Hardeningなど）。
   - **Exposed secrets**: **「Configure secret scanning」**（GitHub Advanced Security or Defender for DevOps）。
※画像の解答配置に合わせて選択します。通常、DevOps関連の脅威にはDefender for DevOps機能が推奨されます。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/26/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 27 ページを表示しています。

410問中**261 - 270**問 を表示
