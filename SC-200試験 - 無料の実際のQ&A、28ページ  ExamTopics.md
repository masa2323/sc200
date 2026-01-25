---
title: "SC-200試験 - 無料の実際のQ&A、28ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/28/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#36 トピック4

Microsoft 365 E5 サブスクリプションがあり、500 台の Windows 11 デバイスが含まれています。Microsoft  
  
Defender for Endpoint の展開では、以下の設定になっています。  
  
• 検出モード: 基本  
• ライブレスポンス: 無効  
• ブロックモードでの EDR の有効化: オフ  
• 改ざん防止: オフ  
  
Microsoft Defender XDR に自動攻撃阻止機能を実装する必要があります。  
  
どうすればよいでしょうか？

- A. 検出モードを標準検出に変更します。
- B. ライブレスポンスをオンに設定します。
- C. 改ざん防止をオンに設定します。
- D. ブロック モードで EDR を有効にするをオンに設定します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

*コミュニティ投票の配分*

D（100％）

質問#37 トピック4

Microsoft Security Copilot を使用している Microsoft 365 サブスクリプションをお持ちです。Copilot  
  
用のカスタム GPT プラグインを構成する予定です。  
  
どの GPT モデルを使用すればよいでしょうか？

- A. gpt-4o
- B. o1-ミニ
- C. ダヴィンチ-002
- D. gpt-35-ターボ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**解説:**
Security Copilotのカスタムプラグインで使用するGPTモデルです。
**「gpt-4o」**: Microsoft Copilot for Securityは、OpenAIの最新モデル（**GPT-4**や**GPT-4o**）を使用しています。カスタムプラグイン（OpenAIプラグイン互換）を作成する場合、Copilot for Securityがベースとしているモデルとの互換性や推奨モデルとして、**GPT-4**系が選択肢になります。GPT-3.5-turboやDavinciは古いモデルです。

*コミュニティ投票の配分*

A（100％）

質問#38 トピック4

Microsoft Security Copilot をご利用の Azure サブスクリプションをお持ちです。  
  
セキュリティ コンピューティング ユニットの数を一時的に増やす必要があります。  
  
課金対象となる最短の期間はどのくらいですか？

- A. 1秒
- B. 1分
- C. 1時間
- D. 1日

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**解説:**
Microsoft Copilot for Security（Security Copilot）のコンピュートユニット（SCU）の課金単位です。
SCUはプロビジョニングされた容量に基づいて**1時間単位**で課金されます。一時的に増良した場合、最短でも1時間分の料金が発生します。

質問#39 トピック4

HOTSPOT  
\-  
  
Workspace1 という Microsoft Sentinel ワークスペースがあります。Workspace1  
  
の AzureActivity テーブルの保持期間は以下のとおりです。  
  
• Interactive: 180 日  
• Total: 180 日  
  
以下の要件を満たすように保持期間を変更する必要があります。  
  
• テーブルへのデータ保存にかかるコストを最小限に抑える。  
• テーブルデータの利用可能期間を最大化する。  
  
各保持期間をどのように構成すればよいでしょうか？ 回答するには、回答エリアから適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image462.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**正解:** ![](https://img.examtopics.com/sc-200/image463.png)

**解説:**
Log Analyticsワークスペースのデータ保持期間とアーカイブ設定です。AzureActivityテーブルの180日分のデータを、コスト最小化かつ利用期間最大化の要件で構成します。

1. **Interactive Retention**: **「90 days」**。Azure Sentinel (Microsoft Sentinel) を利用している場合、最初の90日間（AzureActivityなどは無料の場合があるが、通常ワークスペース設定に依存）はデータ取り込み料に含まれるか、比較的安価ですが、長期のインタラクティブ保持は高価です。コストを最小化するため、必要最低限（デフォルトの30日や、無料枠の90日など）に設定します。ここでは選択肢次第ですが、アーカイブへの移行を早めるなら短くします。
2. **Total Retention**: **「730 days」**（またはそれ以上）。アーカイブ層（Archive Tier）は非常に安価です。インタラクティブ期間が終わった後、アーカイブ期間としてデータを保持することで「利用可能期間を最大化」しつつ「コストを最小化」できます。Log Analyticsでは最大7年（一部12年）まで保持可能です。選択肢にある最大値（730日など）を選びます。
※画像の正解を確認すると、Interactiveを**90日**（Sentinel特典で無料範囲）、Totalを**730日**（アーカイブ活用）に設定していると思われます。

## トピック5 - 質問セット5

質問1 トピック5

Microsoft 365 サブスクリプションがあり、以下のリソースが含まれています。  
  
• Microsoft 365 E5 ライセンスが割り当てられたユーザー 100 人  
• Microsoft Entra テナントに参加している Windows 11 デバイス 100 台  
  
ユーザーは Web 上の Outlook を使用して Microsoft Exchange Online メールボックスにアクセスします。  
  
ユーザーアカウントが侵害された場合に、Web 上の Outlook セッション トークンを取り消せるようにする必要があります。どのような設定が必要ですか？

- A. Microsoft Entraのセキュリティデフォルト
- B. Microsoft Entra 認証済み ID
- C. Microsoft Entraの条件付きアクセスポリシー
- D. Microsoft Entra ID 保護

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

*コミュニティ投票の配分*

C（100％）

質問2 トピック5

Microsoft Defender for Cloud を使用する Azure サブスクリプションをお持ちです。  
  
以下のリスクを軽減するには、Defender for Cloud を構成する必要があります。  
  
• アプリケーション ソースコード内の脆弱性  
• 宣言型テンプレート内のエクスプロイトツールキット  
• 悪意のある IP アドレスからの操作  
• 公開されたシークレット  
  
使用すべき 2 つの Defender for Cloud サービスはどれですか？ 正解はそれぞれソリューションの一部を示しています。  
  
注: 正解は 1 点です。

- A. Microsoft Defender for Resource Manager
- B. Microsoft Defender for DNS
- C. Microsoft Defender for App Service
- D. Microsoft Defender for Servers
- E. DevOps 向け Microsoft Defender

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)

**正解:** AE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

**解説:**
Defender for Cloudのサービス選択。

1. **Vulnerabilities in application source code** & **Exploit toolkits in declarative templates** & **Exposed secrets**: これらはすべて開発段階（CI/CD、コードリポジトリ）のリスクです。**「Microsoft Defender for DevOps」** がこれらをスキャン・検出します（GitHub Advanced SecurityやAzure DevOps連携）。
2. **Operations from malicious IP addresses**: サーバーやリソースに対するネットワーク攻撃や不審な通信の検出です。**「Microsoft Defender for Servers」**（またはApp Service, Key Vaultなど）が脅威検出を行いますが、最も一般的な「悪意あるIPからの操作」はサーバーワークロードに対するものです。あるいは、DNSレベルでの保護を提供する **「Microsoft Defender for DNS」** もありますが、ソースコード脆弱性とセットで問われている場合、サーバー保護がペアになることが多いです。
※正解のAEは **A (Defender for Resource Manager)** と **E (Defender for DevOps)** です。
   - **Defender for DevOps**: ソースコード、テンプレート、シークレット用。
   - **Defender for Resource Manager**: Azureリソースに対する管理操作（ARM API）への攻撃を検知します。「宣言型テンプレート（ARM/Bicep）」の展開自体や、不審なリソース変更操作などを監視対象としますが、テンプレート内のエクスプロイトなどはDevOpsの領域です。しかし、正解がAを含んでいる場合、「悪意あるIPからの操作」が管理操作（コントロールプレーン）に対するものを指している可能性があります。

*コミュニティ投票の配分*

AE（73％）

13%

7%

質問3 トピック5

HOTSPOT -  
  
Microsoft Defender for DevOps を使用する Azure DevOps 組織があるとします。この組織には、Repo1 という Azure DevOps リポジトリと、Pipeline1 という Azure Pipelines パイプラインが含まれています。Pipeline1 は、Repo1 に保存されているコードのビルドとデプロイに使用されます。Pipeline1 の  
  
実行時に、Microsoft Defender for Cloud が Repo1 内のコードに対してシークレットスキャンを実行できるようにする必要があります。  
  
組織に何をインストールし、Pipeline1 の YAML ファイルに何を追加すればよいでしょうか。回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image244.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)

**正解:** ![](https://img.examtopics.com/sc-200/image438.png)

**解説:**
Azure DevOpsパイプラインでのDefender for DevOpsシークレットスキャン設定です。

1. **Install in organization**: **「Microsoft Security DevOps」**（Microsoft Security DevOps Azure DevOps extension）。Azure DevOps Marketplaceから拡張機能をインストールする必要があります。
2. **Add to the YAML file**: **「MicrosoftSecurityDevOps@1」** タスク。パイプライン定義（YAML）にMSDOタスクを追加してスキャンを実行させます。

質問4 トピック5

HOTSPOT  
\-  
  
Azure DevOps組織があり、Repo1というAzure Reposリポジトリが含まれており、Microsoft Defender for DevOpsにオンボードされています。Infrastructure  
  
as Code (IaC)ファイルを作成し、Repo1に保存します。IaCファイルは、BicepファイルとHelm Chartsとしてフォーマットされています。IaC  
  
ファイル内の構成ミスを特定するには、Defender for DevOpsを構成する必要があります。  
  
それぞれのファイルの種類には、どのスキャンツールを使用すべきでしょうか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image246.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)

**正解:** ![](https://img.examtopics.com/sc-200/image247.png)

**解説:**
Defender for DevOps（MSDO）で使用されるIaCスキャンツールです。

1. **Bicep files**: **「Template Analyzer」**。MicrosoftのTemplate Analyzerは、ARMテンプレートおよびBicepファイルのセキュリティ構成ミスをスキャンするために使用されます。
2. **Helm Charts**: **「Terrascan」**。Terrascanは、Terraform, Helm, K8s, DockerfileなどのIaCスキャンをサポートしています。Checkovも有名ですが、MicrosoftのMSDO統合ではTerrascanが採用されています（または両方サポートされていますが、選択肢にある方を選びます）。

質問5 トピック5

HOTSPOT -  
  
Microsoft 365 E5 サブスクリプションをご利用で、Microsoft 365 Defender for Endpoint を使用しています。Microsoft  
  
365 Defender ポータルを使用して、Windows サーバーへのリモートシェル接続を開始できることを確認する必要があります。  
  
何を構成すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image248.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論   15](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)

**正解:** ![](https://img.examtopics.com/sc-200/image439.png)

**解説:**
Defender for Endpointでリモートシェル接続（Live Response）を有効にする設定です。

1. **Setting**: **「Live Response」**。Advanced features設定でLive Responseを有効にする必要があります。サーバーに対しては「Live Response for Servers」の設定がある場合もあります。
2. **Setting**: **「Live Response for Servers」**（もし個別の設定として存在する場合）。または **「Automated investigation」** ではなく、Live Responseに関連する別の設定（例: 未署名スクリプトの実行許可など）が問われることもありますが、基本はLive Responseスイッチです。
※正解画像の選択肢配置によりますが、**Turn on Live Response** が必須です。

質問6 トピック5

オンプレミスデバイスが500台あります。Microsoft  
  
Defender 365を利用するMicrosoft 365 E5サブスクリプションを保有しています。Microsoft  
  
Defender 365にデバイスを100台オンボードします  
  
。管理されていないオンプレミスデバイスを特定する必要があります。オンボードされた特定のデバイスのみが検出を実行するようにソリューションを設定する必要があります。  
  
まず何をすべきでしょうか？

- A. デバイス グループを作成します。
- B. 除外を作成します。
- C. 検出モードを基本に設定します。
- D. タグを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)   [議論   24](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/28/#)  

*コミュニティ投票の配分*

D（50％）

C（37％）

13%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/27/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 28 ページを表示しています。

410問中**271 - 280**問 を表示
