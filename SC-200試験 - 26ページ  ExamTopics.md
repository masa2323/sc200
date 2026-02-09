質問16 トピック4

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft Copilot for Security を使用しています。Copilot for Security はデフォルト設定になっています。User というユーザーが Copilot for Security を使用して以下のタスクを実行できるようにする必要があります。  
  
• ファイルのアップロード。  
• 使用状況ダッシュボードの表示。  
• プロンプトブックを全ユーザーと共有。  
  
このソリューションは、最小権限の原則に従う必要があります  
  
。User にはどのようなロールを割り当てるべきでしょうか？

- A. 副操縦士オーナー
- B. クラウドアプリケーション管理者
- C. セキュリティ管理者
- D. 副操縦士 貢献者

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
Microsoft Copilot for Security には主に「オーナー」と「貢献者」の 2 つのアプリ内ロールがあります。今回の要件を照らし合わせると、なぜ**オーナー**が必要なのかが明確になります。

| **要件**                | **副操縦士 貢献者 (Contributor)** | **副操縦士 オーナー (Owner)** |
| --------------------- | -------------------------- | --------------------- |
| **ファイルのアップロード**       | ○                          | ○                     |
| **使用状況ダッシュボードの表示**    | ×                          | **○**                 |
| **プロンプトブックを全ユーザーと共有** | × (個人用のみ)                  | **○ (組織全体)**          |

質問17 トピック4

Sub1 という Azure サブスクリプションがあります。Sub1 には、SW1 という Microsoft Sentinel ワークスペースと、Windows Server を実行する VM1 という仮想マシンが含まれています。SW1 は、AMA コネクタ経由で Wi​​ndows セキュリティ イベントを使用して、VM1 からセキュリティ ログを収集します。VM1 から収集されるイベントの範囲を制限する必要があります。ソリューションでは、監査失敗イベントのみが収集されるようにする必要があります。  
  
コネクタのフィルター式はどのように完成させるべきでしょうか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image341.png)

**解説:**
Windows イベントログにおいて、**Audit Failure**（監査失敗）はキーワード **`0x8010000000000000`** で識別されます（監査成功は `0x8020000000000000`）。このキーワード情報は、イベント XML の **`System`** セクション内に保持されています。

- **XPath の構造:** 正しい XPath フィルターは `Security!*[System[Keywords='0x8010000000000000']]` となります。
    
- **UI の選択:** この試験形式の UI では、階層を指定するために `System[` を選択し、属性パスを完成させるために `System` を組み合わせて、最終的な XML パスを `System` ノードにマッピングさせるのが一般的です。

質問18 トピック4

Microsoft 365 E5 サブスクリプションと Microsoft Sentinel ワークスペースをご利用の場合、以下のソースからデータを結合する KQL クエリを作成する必要があります。  
  
• Microsoft Graph  
• Microsoft Entra ID Protection を使用して検出されたリスクの高いユーザー  
  
このソリューションでは、返されるデータの量を最小限に抑える必要があります。  
  
クエリはどのように開始すればよいでしょうか？

- A. ![](https://img.examtopics.com/sc-200/image343.png)
- B. ![](https://img.examtopics.com/sc-200/image344.png)
- C. ![](https://img.examtopics.com/sc-200/image345.png)
- D. ![](https://img.examtopics.com/sc-200/image346.png)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
Microsoft Graphからのデータと、Entra ID Protectionのリスクユーザー情報を結合し、かつデータ量を最小限にするクエリです。
**`IdentityInfo | where RiskState == "AtRisk"`**: `IdentityInfo` テーブル（UEBAやEntra IDデータが同期されるテーブル）からリスク状態が "AtRisk" のユーザーをまずフィルタリングします。その後、Graphデータなどと結合（join）するのが効率的です。選択肢Bがこのパターン（まずフィルタしてから結合）を示していると考えられます（図の詳細が見えないため推測ですが、KQLの最適化原則「フィルタ・ファースト」に従うのが正解です）。選択肢Aのように全データを結合してからフィルタするのは非効率です。

質問19 トピック4

Microsoft 365 E5 サブスクリプションをご利用です。
統合監査ログをクエリする PowerShell スクリプトがあります。  
サーバー側のページングが原因で、クエリは最初のページの結果しか返さないことがわかりました。すべての結果を取得する必要があります。  
  
結果のどのプロパティをクエリすればよいでしょうか？

- A. @odata.context
- B. @odata.count
- C. @odata.nextLink
- D. @odata.deltaLink

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
Microsoft Graph APIなど（この場合はOffice 365管理APIや監査ログ検索）で、サーバー側ページングにより分割された結果の続きを取得するためのプロパティです。
**`@odata.nextLink`**: ODataプロトコルに準拠したAPIレスポンスにおいて、次のページのデータを取得するためのURLが含まれるプロパティです。PowerShellスクリプトで全データを取得するには、このプロパティが存在する限りループしてリクエストを繰り返す処理が必要です。

質問#20 トピック4

Microsoft 365 E5 サブスクリプションがあり、Group1 と Group2 という 2 つのグループが含まれており、Microsoft Copilot for Security を使用しています。Copilot for Security のロール割り当てを以下の要件を満たすように構成する必要があります。  
  
• Group1 のメンバーがプロンプトを実行し、Microsoft Defender XDR セキュリティ インシデントに応答できるようにします。  
• Group2 のメンバーがプロンプトを実行できるようにします。  
• 最小権限の原則に従います。
• Copilot 共同作成者ロールから Everyone を削除します。  
  
次に実行する必要がある 2 つのアクションはどれですか。正解はそれぞれソリューションの一部です。  
  
注: 正解はそれぞれ 1 ポイントです。

- A. グループ 1 にセキュリティ オペレータ ロールを割り当てます。
- B. グループ 2 に副操縦士所有者の役割を割り当てます。
- C. グループ1に副操縦士オーナーの役割を割り当てる
- D. グループ2にセキュリティ オペレータ ロールを割り当てます。
- E. Copilot Contributor ロールを Group2 に割り当てます。

**正解:** AE [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
Copilot for Securityのロール割り当て（最小権限）です。

1. **Group1 (execute prompts and respond to incidents)**: **「Security Operator」**（または選択肢A）。本来、CopilotのロールとEntraロールは別ですが、Copilotの使用権限（Contributor）と、XDRでのインシデント対応権限（Security Operator）はセットで考える必要があります。Copilot ContributorだけではXDRのアクション（インシデントクローズなど）は実行できません。また、質問文の「Security Operator role」はEntra IDのロールを指しており、これによりXDRへのアクセス権が付与されます。CopilotへのアクセスにはContributorロールが必要です。
2. **Group2 (execute prompts only)**: **「Copilot Contributor」**（選択肢E）。プロンプトを実行するだけであれば、Copilot Contributorロールが適切です（Ownerは過剰）。

ただし、選択肢の構成として「Copilot用のロール」と「Entra/Defender用のロール」が混在している場合：

- Group1: XDR操作も必要 -> Security Operator (A) でXDR権限を持ち、かつCopilotも使える（Copilotロールが別途必要だが、選択肢にない場合はSecurity Operatorに含まれる権限や、併用を示唆）。もしCopilot固有ロールで選ぶならContributorだが、XDR対応要件があるのでSecurity Operatorが優先か、あるいは両方必要。設問が「2つのアクション」を求めているので、Group1用に1つ、Group2用に1つを選ぶなら AとE。
※公式ドキュメントでは、Security Operatorロールを持つユーザーはCopilotを使用可能です（もちろんCopilotのアクセス権設定次第ですが）。

質問#21 トピック4

Microsoft 365 E5 サブスクリプションをご利用で、DB1 というデータベースサーバーが含まれています。DB1 は Microsoft Defender XDR にオンボードされています。  
  
攻撃対象領域マップに DB1 が表示されるようにする必要があります。  
  
どのような設定が必要ですか？

- A. 資産ルール
- B. 重要な資産ルール
- C. センシティブエンティティタグ
- D. ハニートークンエンティティタグ

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
DB1を「攻撃対象領域マップ（Attack Surface Map）」に表示させるための設定です。
**「Critical asset rule (重要な資産ルール)」**: Defender for CloudやDefender External Attack Surface Management (EASM) において、特定のリソースを重要資産として定義・分類することで、マップ上で優先的に表示・管理できるようになります。単なるタグ付けではなく、資産の重要度定義（Criticality）を行う必要があります。

質問#22 トピック4
  
App1というバックグラウンドプロセスを実行し、Azure Connected MachineエージェントがインストールされたオンプレミスのLinuxサーバーがあります。
WS1 というMicrosoft Sentinelワークスペースがあります。
AMA コネクタ経由のSyslogを使用してApp1に関連するメッセージを収集する、DCR1というデータ収集ルール（DCR）を構成する必要があります。ソリューションは次の要件を満たす必要があります。  
  
• 優先度が「重大」のメッセージのみを収集する。  
• 収集するデータの量を最小限に抑える。DCR1  
  
には、どの機能とログレベルを構成する必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注：正しい選択ごとに1ポイントが付与されます。  
  
![](https://img.examtopics.com/sc-200/image357.png)

**正解:** ![](https://img.examtopics.com/sc-200/image358.png)

**解説:**
この問題のポイントは、Linux の標準的な Syslog ファシリティの理解と、収集されるログレベルの階層構造（重大度）にあります。
1. Facility: なぜ LOG_DAEMON なのか

- **バックグラウンドプロセス:** 問題文にある「App1」はバックグラウンドプロセスとして実行されています。Linux において、特定のカテゴリ（認証、cron、カーネルなど）に属さないシステムサービスやバックグラウンドプロセス（デーモン）のメッセージは、通常 **`LOG_DAEMON`** ファシリティを使用して出力されます。
    
- 他の選択肢（`LOG_AUTH` = 認証、`LOG_CRON` = 定時実行、`LOG_KERN` = カーネル）は用途が限定されているため、汎用的なバックグラウンドプロセスには適しません。

2. Log level: なぜ LOG_ERR なのか

Syslog の重大度は、数値が小さいほど緊急度が高くなります。Microsoft Sentinel の DCR 構成でログレベルを選択する場合、通常は「選択したレベル以上の重大度（数値がそれ以下のもの）」が収集されます。

|**重大度 (Severity)**|**レベル名**|**内容**|
|---|---|---|
|0|Emergency|システムが使用不能|
|1|Alert|直ちに行動が必要|
|**2**|**Critical**|**重大な状態（今回のターゲット）**|
|3|Error|エラー状態|
|4|Warning|警告状態|

- **要件の充足:** 今回の要件は「優先度が『Critical（レベル 2）』のメッセージを収集する」ことです。
    
- **選択肢の比較:**
    
    - **`LOG_EMERG` (0):** これを選択するとレベル 0 のみ収集され、レベル 2 の **Critical メッセージが漏れてしまいます**。
        
    - **`LOG_ERR` (3):** これを最小レベルとして選択すると、3 (Error), **2 (Critical)**, 1 (Alert), 0 (Emergency) が収集されます。選択肢の中で、Critical を含みつつ、データの量を最小限（`LOG_WARN` や `LOG_DEBUG` よりも絞る）に抑えることができるのはこのレベルです。

質問#23 トピック4

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

**解説:**
この問題の鍵は、**「オンプレミスサーバーを Azure リソースとして DCR に登録するための要件」**にあります。

1. Server1 および Server3 が「いいえ」の理由

- **Azure Arc の必要性:** オンプレミスのサーバーを DCR の「リソース」として追加し、Azure Monitor Agent (AMA) で管理するには、そのサーバーが **Azure Arc 対応サーバー**（Azure Connected Machine エージェントがインストールされている状態）である必要があります。
    
- **エージェントの欠如:** Server1 と Server3 は AMA はインストールされていますが、Azure Connected Machine エージェントが「Not installed」です。この状態では Azure ポータル上で「リソース」として認識・選択できないため、DCR に追加することはできません。
    
2. Server2 が「はい」の理由

- **リソースとしての認識:** Server2 は Azure Connected Machine エージェントがインストールされているため、Azure Arc 対応サーバーとして Azure 上で「リソース」として扱えます。
    
- **AMA の自動デプロイ:** 現在 AMA はインストールされていませんが、Arc 対応サーバーを DCR に関連付けると、拡張機能として **AMA が自動的にインストール**されます。
    
- **ログの収集:** DCR1 のデータソースには「Windows event logs」が含まれているため、追加後に特定のイベントを収集することが可能です。

質問#24 トピック4

Microsoft 365 E5 サブスクリプションをお持ちです。
Microsoft Defender for Cloud Apps によって生成されたシグナルを使用するように、Microsoft Defender XDR の自動攻撃阻止を構成する必要があります。Microsoft Defender ポータルで Defender for Cloud Apps に対して実行する必要がある 2 つのアクションはどれですか？ 正解はそれぞれ解答の一部です。  
  
注: 正解は 1 点です。

- A. Microsoft 365 コネクタを有効にします。
- B. 自動ログアップロード用のログコレクターを追加します。
- C. アプリガバナンスをオンにします。
- D. Cloud Discovery ユーザー エンリッチメントを展開します。
- E. 情報保護から、ファイル監視を有効にします。

**正解:** AC [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/26/#)  

**解説:**
Defender XDRの「自動攻撃阻止（Automatic Attack Disruption）」が、Defender for Cloud Appsのシグナルを使用できるようにするための設定です。

1. **Enable Microsoft 365 connector (A)**: Defender for Cloud AppsをMicrosoft 365（XDR）と接続することで、アラートやシグナルの共有が可能になります。これが前提条件です。
2. **Switch on App governance (C)**: アプリガバナンス（App Governance）を有効にすることで、OAuthアプリの異常な動作や過剰な権限行使などのシグナルがXDRに供給され、攻撃阻止（例えば、悪意あるアプリの無効化やユーザーアカウントの停止）のトリガーとして使用されます。

質問#25 トピック4
  
Sub1 という Azure サブスクリプションがあり、このサブスクリプションには Vault1 という Azure Key Vault と Automation1 という Azure Automation アカウントが含まれています。Automation1 が Vault1 にアクセスできることを確認する必要があります。solution1 は次の要件を満たす必要があります。  
  
• Automation1 が削除された場合、Vault1 に付与されたアクセス許可も自動的に削除されるようにする。  
• Automation1 で作成された Runbook が、Vault1 に保存されているシークレット値を読み取れるようにする。  
• 最小権限の原則に従う。Automation1  
  
にはどのような構成が必要でしょうか。また、Automation1 が Vault1 にアクセスするために使用する組み込みロールはどれでしょうか。回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image362.png)

**正解:** ![](https://img.examtopics.com/sc-200/image363.png)

**解説:**
Azure Automationアカウント（Automation1）がKey Vault（Vault1）にアクセスするための構成です。

1. **Identity configuration**: **「System assigned」**。Automationアカウントのシステム割り当てマネージドIDを有効にします。これにより、Automationアカウントが削除されたときに、関連付けられたIDおよびKey Vaultでのアクセス許可も自動的に削除されます（要件「Automation1が削除された場合、アクセス許可も削除」を満たす）。ユーザー割り当てIDはIDリソースが独立して残るため不適です。
2. **Role**: **「Key Vault Secrets User」**。シークレット値を「読み取る」だけであれば、Contributorなどの強力な権限は不要です。Key Vault Secrets Userは、シークレットの取得（Get）が可能であり、最小権限の原則に従います。
