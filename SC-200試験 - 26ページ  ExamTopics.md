---
title: "SC-200試験 - 無料の実際のQ&A、26ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/26/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問16 トピック4

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft Copilot for Security を使用しています。Copilot for Security はデフォルト設定になっています。User  
  
というユーザーが Copilot for Security を使用して以下のタスクを実行できるようにする必要があります。  
  
• ファイルのアップロード。  
• 使用状況ダッシュボードの表示。  
• プロンプトブックを全ユーザーと共有。  
  
このソリューションは、最小権限の原則に従う必要があります  
  
。User にはどのようなロールを割り当てるべきでしょうか？

- A. 副操縦士オーナー
- B. クラウドアプリケーション管理者
- C. セキュリティ管理者
- D. 副操縦士 貢献者

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)   [議論   8](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
Microsoft Copilot for Securityにおける管理者権限の割り当てです。
**「Copilot Owner (副操縦士オーナー)」**: プロンプトブックの共有（Everyoneへの共有）や、使用状況ダッシュボードの表示、設定変更（ファイルのアップロード機能の制御など）を行える最も強力なロールです。「Copilot Contributor」はプロンプトの実行や作成はできますが、全社的な共有や設定管理には制限があります。
※ファイルのアップロード自体はContributorでも可能ですが、プロンプトブックを「全ユーザーと共有」する権限やダッシュボード閲覧などの管理機能を持つのはOwnerです。

*コミュニティ投票の配分*

A（83％）

D（17％）

質問17 トピック4

HOTSPOT  
\-  
  
Sub1 という Azure サブスクリプションがあります。Sub1 には、SW1 という Microsoft Sentinel ワークスペースと、Windows Server を実行する VM1 という仮想マシンが含まれています。SW1 は、AMA コネクタ経由で Wi​​ndows セキュリティ イベントを使用して、VM1 からセキュリティ ログを収集します。VM1  
  
から収集されるイベントの範囲を制限する必要があります。ソリューションでは、監査失敗イベントのみが収集されるようにする必要があります。  
  
コネクタのフィルター式はどのように完成させるべきでしょうか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image341.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)

**正解:** ![](https://img.examtopics.com/sc-200/image342.png)

**解説:**
AMAコネクタを使用して「監査失敗（Audit Failure）」イベントのみを収集するためのXPathクエリです。
**`Security!*[System[(Keywords band 4503599627370496)]]`**: これは「Audit Failure」に対応するイベントログのキーワード（Keyword）です。
Securityログにおいて、

- Audit Success = `Keywords band 9007199254740992`
- Audit Failure = `Keywords band 4503599627370496`
というビットマスクを使用するのが定石です。
また、`EventID=4625` のように特定のイベントIDセットでフィルタする方法もありますが、質問の選択肢（図）がXPathのキーワードフィルタ形式を示している場合、この数値を覚えている必要があります。

質問18 トピック4

Microsoft 365 E5 サブスクリプションと Microsoft Sentinel ワークスペースをご利用の場合、  
  
以下のソースからデータを結合する KQL クエリを作成する必要があります。  
  
• Microsoft Graph  
• Microsoft Entra ID Protection を使用して検出されたリスクの高いユーザー  
  
このソリューションでは、返されるデータの量を最小限に抑える必要があります。  
  
クエリはどのように開始すればよいでしょうか？

- A. ![](https://img.examtopics.com/sc-200/image343.png)
- B. ![](https://img.examtopics.com/sc-200/image344.png)
- C. ![](https://img.examtopics.com/sc-200/image345.png)
- D. ![](https://img.examtopics.com/sc-200/image346.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
Microsoft Graphからのデータと、Entra ID Protectionのリスクユーザー情報を結合し、かつデータ量を最小限にするクエリです。
**`IdentityInfo | where RiskState == "AtRisk"`**: `IdentityInfo` テーブル（UEBAやEntra IDデータが同期されるテーブル）からリスク状態が "AtRisk" のユーザーをまずフィルタリングします。その後、Graphデータなどと結合（join）するのが効率的です。選択肢Bがこのパターン（まずフィルタしてから結合）を示していると考えられます（図の詳細が見えないため推測ですが、KQLの最適化原則「フィルタ・ファースト」に従うのが正解です）。選択肢Aのように全データを結合してからフィルタするのは非効率です。

*コミュニティ投票の配分*

B（60％）

A（30％）

10%

質問19 トピック4

Microsoft 365 E5 サブスクリプションをご利用です。  
  
統合監査ログをクエリする PowerShell スクリプトがあります。  
  
サーバー側のページングが原因で、クエリは最初のページの結果しか返さないことがわかりました。  
  
すべての結果を取得する必要があります。  
  
結果のどのプロパティをクエリすればよいでしょうか？

- A. @odata.context
- B. @odata.count
- C. @odata.nextLink
- D. @odata.deltaLink

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
Microsoft Graph APIなど（この場合はOffice 365管理APIや監査ログ検索）で、サーバー側ページングにより分割された結果の続きを取得するためのプロパティです。
**`@odata.nextLink`**: ODataプロトコルに準拠したAPIレスポンスにおいて、次のページのデータを取得するためのURLが含まれるプロパティです。PowerShellスクリプトで全データを取得するには、このプロパティが存在する限りループしてリクエストを繰り返す処理が必要です。

*コミュニティ投票の配分*

C（100％）

質問#20 トピック4

Microsoft 365 E5 サブスクリプションがあり、Group1 と Group2 という 2 つのグループが含まれており、Microsoft Copilot for Security を使用しています。Copilot  
  
for Security のロール割り当てを以下の要件を満たすように構成する必要があります。  
  
• Group1 のメンバーがプロンプトを実行し、Microsoft Defender XDR セキュリティ インシデントに応答できるようにします。  
• Group2 のメンバーがプロンプトを実行できるようにします。  
• 最小権限の原則に従います。Copilot  
  
共同作成者ロールから Everyone を削除します。  
  
次に実行する必要がある 2 つのアクションはどれですか。正解はそれぞれソリューションの一部です。  
  
注: 正解はそれぞれ 1 ポイントです。

- A. グループ 1 にセキュリティ オペレータ ロールを割り当てます。
- B. グループ 2 に副操縦士所有者の役割を割り当てます。
- C. グループ1に副操縦士オーナーの役割を割り当てる
- D. グループ2にセキュリティ オペレータ ロールを割り当てます。
- E. Copilot Contributor ロールを Group2 に割り当てます。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)

**正解:** AE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
Copilot for Securityのロール割り当て（最小権限）です。

1. **Group1 (execute prompts and respond to incidents)**: **「Security Operator」**（または選択肢A）。本来、CopilotのロールとEntraロールは別ですが、Copilotの使用権限（Contributor）と、XDRでのインシデント対応権限（Security Operator）はセットで考える必要があります。Copilot ContributorだけではXDRのアクション（インシデントクローズなど）は実行できません。また、質問文の「Security Operator role」はEntra IDのロールを指しており、これによりXDRへのアクセス権が付与されます。CopilotへのアクセスにはContributorロールが必要です。
2. **Group2 (execute prompts only)**: **「Copilot Contributor」**（選択肢E）。プロンプトを実行するだけであれば、Copilot Contributorロールが適切です（Ownerは過剰）。

ただし、選択肢の構成として「Copilot用のロール」と「Entra/Defender用のロール」が混在している場合：

- Group1: XDR操作も必要 -> Security Operator (A) でXDR権限を持ち、かつCopilotも使える（Copilotロールが別途必要だが、選択肢にない場合はSecurity Operatorに含まれる権限や、併用を示唆）。もしCopilot固有ロールで選ぶならContributorだが、XDR対応要件があるのでSecurity Operatorが優先か、あるいは両方必要。設問が「2つのアクション」を求めているので、Group1用に1つ、Group2用に1つを選ぶなら AとE。
※公式ドキュメントでは、Security Operatorロールを持つユーザーはCopilotを使用可能です（もちろんCopilotのアクセス権設定次第ですが）。

*コミュニティ投票の配分*

AE（82％）

CE（18％）

質問#21 トピック4

Microsoft 365 E5 サブスクリプションをご利用で、DB1 というデータベースサーバーが含まれています。DB1 は Microsoft Defender XDR にオンボードされています。  
  
攻撃対象領域マップに DB1 が表示されるようにする必要があります。  
  
どのような設定が必要ですか？

- A. 資産ルール
- B. 重要な資産ルール
- C. センシティブエンティティタグ
- D. ハニートークンエンティティタグ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
DB1を「攻撃対象領域マップ（Attack Surface Map）」に表示させるための設定です。
**「Critical asset rule (重要な資産ルール)」**: Defender for CloudやDefender External Attack Surface Management (EASM) において、特定のリソースを重要資産として定義・分類することで、マップ上で優先的に表示・管理できるようになります。単なるタグ付けではなく、資産の重要度定義（Criticality）を行う必要があります。

*コミュニティ投票の配分*

B（70％）

C（30％）

質問#22 トピック4

HOTSPOT  
\-  
  
App1というバックグラウンドプロセスを実行し、Azure Connected MachineエージェントがインストールされたオンプレミスのLinuxサーバーがあります。WS1  
  
というMicrosoft Sentinelワークスペースがあります。AMA  
  
コネクタ経由のSyslogを使用してApp1に関連するメッセージを収集する、DCR1というデータ収集ルール（DCR）を構成する必要があります。ソリューションは次の要件を満たす必要があります。  
  
• 優先度が「重大」のメッセージのみを収集する。  
• 収集するデータの量を最小限に抑える。DCR1  
  
には、どの機能とログレベルを構成する必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注：正しい選択ごとに1ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image357.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)

**正解:** ![](https://img.examtopics.com/sc-200/image358.png)

**解説:**
Linuxサーバーから「Critical」レベルのSyslogメッセージのみを収集するDCR設定です。

1. **Facility**: **「LOG_USER」**（またはApp1が使用するファシリティ）。App1などの一般的なユーザープロセスは `LOG_USER` ファシリティを使用することが多いです。
2. **Minimum log level**: **「CRITICAL」**。収集する最小ログレベルをCRITICALに設定することで、それ以上（Emergencyなど）のメッセージのみが収集され、InfoやDebugなどの不要なデータは除外されます。これによりデータ量を最小限に抑えられます。

質問#23 トピック4

HOTSPOT  
\-  
  
オンプレミスネットワークにはHyper-Vクラスターが含まれています。クラスターには、次の表に示す仮想マシンが含まれています。SW1  
  
![](https://img.examtopics.com/sc-200/image359.png)  
  
という名前のMicrosoft Sentinelワークスペースがあります。  
  
データ収集ルール（DCR）の構成は次のとおりです。  
  
• 名前: DCR1  
• 送信先: SW1  
• プラットフォームの種類: すべて  
• データ収集エンドポイント: なし  
• データソース: Windowsイベントログ、Linux syslog  
  
以下の各項目について、該当する場合は「はい」を選択してください。それ以外の場合は「いいえ」を選択してください。  
  
注: 正解は1点です。  
  
![](https://img.examtopics.com/sc-200/image360.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)

**正解:** ![](https://img.examtopics.com/sc-200/image361.png)

**解説:**
DCR1の設定（Platform: All, Data source: Windows/Syslog）に基づいて、ログ収集対象となるVMを判定します。AMA（Azure Monitor Agent）が必要です。

1. **VM1 (Azure/Win10, AMA installed)**: **「Yes」**。AMAがインストールされており、DCRの対象（Windowsイベントログ）と合致します。
2. **VM2 (Azure/Win11, MMA installed)**: **「No」**。**DCRはAMAのみ**をサポートします。Legacy Log Analytics Agent (MMA) はDCRを使用しません（ワークスペース設定を使用）。
3. **VM3 (On-premises/Linux, Azure Arc, AMA installed)**: **「Yes」**。Azure Arc経由で管理され、AMAがインストールされているため、DCRによるSyslog収集の対象になります。

質問#24 トピック4

Microsoft 365 E5 サブスクリプションをお持ちです。Microsoft  
  
Defender for Cloud Apps によって生成されたシグナルを使用するように、Microsoft Defender XDR の自動攻撃阻止を構成する必要があります。Microsoft  
  
Defender ポータルで Defender for Cloud Apps に対して実行する必要がある 2 つのアクションはどれですか？ 正解はそれぞれ解答の一部です。  
  
注: 正解は 1 点です。

- A. Microsoft 365 コネクタを有効にします。
- B. 自動ログアップロード用のログコレクターを追加します。
- C. アプリガバナンスをオンにします。
- D. Cloud Discovery ユーザー エンリッチメントを展開します。
- E. 情報保護から、ファイル監視を有効にします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)

**正解:** AC [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
Defender XDRの「自動攻撃阻止（Automatic Attack Disruption）」が、Defender for Cloud Appsのシグナルを使用できるようにするための設定です。

1. **Enable Microsoft 365 connector (A)**: Defender for Cloud AppsをMicrosoft 365（XDR）と接続することで、アラートやシグナルの共有が可能になります。これが前提条件です。
2. **Switch on App governance (C)**: アプリガバナンス（App Governance）を有効にすることで、OAuthアプリの異常な動作や過剰な権限行使などのシグナルがXDRに供給され、攻撃阻止（例えば、悪意あるアプリの無効化やユーザーアカウントの停止）のトリガーとして使用されます。

*コミュニティ投票の配分*

AC（78％）

11%

11%

質問#25 トピック4

HOTSPOT  
\-  
  
Sub1 という Azure サブスクリプションがあり、このサブスクリプションには Vault1 という Azure Key Vault と Automation1 という Azure Automation アカウントが含まれています。Automation1  
  
が Vault1 にアクセスできることを確認する必要があります。solution1 は次の要件を満たす必要があります。  
  
• Automation1 が削除された場合、Vault1 に付与されたアクセス許可も自動的に削除されるようにする。  
• Automation1 で作成された Runbook が、Vault1 に保存されているシークレット値を読み取れるようにする。  
• 最小権限の原則に従う。Automation1  
  
にはどのような構成が必要でしょうか。また、Automation1 が Vault1 にアクセスするために使用する組み込みロールはどれでしょうか。回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image362.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)   [議論   1](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)

**正解:** ![](https://img.examtopics.com/sc-200/image363.png)

**解説:**
Azure Automationアカウント（Automation1）がKey Vault（Vault1）にアクセスするための構成です。

1. **Identity configuration**: **「System assigned」**。Automationアカウントのシステム割り当てマネージドIDを有効にします。これにより、Automationアカウントが削除されたときに、関連付けられたIDおよびKey Vaultでのアクセス許可も自動的に削除されます（要件「Automation1が削除された場合、アクセス許可も削除」を満たす）。ユーザー割り当てIDはIDリソースが独立して残るため不適です。
2. **Role**: **「Key Vault Secrets User」**。シークレット値を「読み取る」だけであれば、Contributorなどの強力な権限は不要です。Key Vault Secrets Userは、シークレットの取得（Get）が可能であり、最小権限の原則に従います。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/25/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 26 ページを表示しています。

410問中**251 - 260**問 を表示
