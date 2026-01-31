---
title: "SC-200試験 - 無料の実際のQ&A、37ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/37/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問11 トピック7

RG1 というリソースグループを含む Azure サブスクリプションがあります。RG1 には Microsoft Sentinel ワークスペースが含まれています。このサブスクリプションは、User1 というユーザーを含む Microsoft Entra テナントにリンクされています。User1  
  
が Microsoft Sentinel ブックテンプレートをデプロイおよびカスタマイズできるようにする必要があります。このソリューションは、最小権限の原則に従う必要があります。RG1  
  
において、User1 にどのロールを割り当てるべきでしょうか？

- A. Microsoft Sentinel 貢献者
- B. ワ​​ークブック寄稿者
- C. Microsoft Sentinel Automation 貢献者
- D. 貢献者

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)  

*Community vote distribution*

B (70%)

A (30%)

質問12 トピック7

HOTSPOT  
\-  
  
Microsoft Defender XDR を使用する Microsoft 365 サブスクリプションをお持ちです。  
  
過去 24 時間以内に 5 件を超えるウイルス検出があったデバイスを識別するカスタム検出ルールを作成する必要があります。  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image309.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image310.png)

**解説:**
KQLで「過去24時間に5件を超えるウイルス検出があったデバイス」を特定するカスタム検出ルール。

1. **Source Table**: **`DeviceEvents`**。ウイルス検出イベントは `DeviceEvents` テーブル（ActionTypeが `AntivirusDetection` など）に記録されます。
2. **Filter**: **`where ActionType == 'AntivirusDetection'`**。
3. **Summarize**: **`| summarize count() by DeviceName`**。デバイスごとにカウントします。
4. **Condition**: **`| where count_ > 5`**。カウントが5より大きいものをフィルタします。
正解画像の選択肢も同様の構成になっています。

質問13 トピック7

HOTSPOT  
\-  
  
Microsoft Sentinel ワークスペースで KQL クエリを作成してください。クエリは、EventID 値が 4624 である最後のレコードを持つアカウントの SecurityEvent レコードを返す必要があります。  
  
クエリをどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image328.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image329.png)

**解説:**
EventID 4624を持つアカウントの「最後のレコード」を取得するKQL。

1. **Filter**: **`SecurityEvent | where EventID == 4624`**。
2. **Get latest record per account**: **`| summarize arg_max(TimeGenerated, *) by Account`**。
   `arg_max(TimeGenerated, *)` は、TimeGeneratedが最大（最新）の行のすべての列（*）を返します。これを `by Account` でグループ化することで、各アカウントの最新のログオンイベントを1行ずつ取得できます。

質問14 トピック7

Microsoft 365 サブスクリプションがあり、User1 というユーザーと、Device1 および Device2 という 2 台の Windows デバイスが含まれています。Device1 と Device2 は Microsoft Defender for Endpoint にオンボードされています。  
  
次のイベントが発生します。  
  
• User1 が Device1 にサインインします。  
• Microsoft Defender XDR の自動攻撃阻止機能が Device1 への攻撃に対応し、User1 を阻止します。  
• User1 が Device2 への接続を試みます。User1  
  
が Device2 に接続しようとしたときに、Device2 はどのプロトコルをブロックしますか？

- A. RDPのみ
- B. RPCのみ
- C. SMBのみ
- D. RDPとRPCのみ
- E. SMBとRPCのみ
- F. RDP、RPC、SMB

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** F [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)  

**解説:**
Defender XDRの「Automatic Attack Disruption（自動攻撃阻止）」機能の動作。
攻撃者（User1が侵害されたと判定）が横展開（Lateral Movement）を試みた際、Defender for Endpointはターゲットデバイス（Device2）側で、侵害されたアカウントからの着信トラフィックをブロックします。
ブロックされるプロトコルには、横展開で使用される主要なリモートアクセスプロトコルである **RDP, RPC, SMB** が含まれます。
したがって、Device2はUser1からの **RDP, RPC, SMB** すべての検出された接続試行をブロックします。
正解は **F** です。

*Community vote distribution*

F (100%)

質問15 トピック7

WS1 という Microsoft Sentinel ワークスペースを含む Azure サブスクリプションがあります。WS1 には Azure アクティビティ コネクタと Microsoft Entra ID コネクタが構成されています。  
  
アラートが最も多く発生しているアカウントと、各アラートに対応するインシデント情報を調査する必要があります。このソリューションは、管理作業を最小限に抑える必要があります。WS1  
  
でまず何をすべきでしょうか？

- A. ユーザーおよびエンティティの行動分析 (UEBA) を使用して異常を検出します。
- B. ユーザーおよびエンティティ行動分析 (UEBA) を有効にします。
- C. コンテンツ ハブから、Microsoft Purview インサイダー リスク管理ソリューションをインストールします。
- D. コンテンツ ハブから、Cloud Identity Threat Protection Essentials をインストールします。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   2](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)  

*Community vote distribution*

B (100%)

質問16 トピック7

Microsoft 365 E5 サブスクリプションをご利用で、Microsoft Copilot for Security を使用しています。  
  
以下のコードを実行して、カスタム Copilot for Security プラグインを作成する予定です。  
  
![](https://img.examtopics.com/sc-200/image330.png)  
  
フォーマットを指定してコードセグメントを完成させる必要があります。変数  
  
にはどのフォーマットを使用すればよいですか![](https://img.examtopics.com/sc-200/image340.png)？

- A. API
- B. GPT
- C. KQL
- D. SQL

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)  

**解説:**
Copilot for Securityのカスタムプラグイン作成（YAML定義）。
Formatフィールドに指定する値。
コード例: `Descriptor: ... SkillGroups: ... Format: KQL`
カスタムプラグインがSentinelやAdvanced Huntingに対してクエリを実行するスキルを定義する場合、そのクエリ言語形式を指定します。Microsoft DefenderやSentinelに対するクエリは **KQL (Kusto Query Language)** です。
したがって、`Format: KQL` が正解です。

*Community vote distribution*

C (100%)

質問17 トピック7

Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションをお持ちです。  
  
インシデントを調査しており、  
  
実行されたインシデントタスクを確認する必要があります。  
  
インシデントページでは何が利用できますか？

- A. タスクのみ
- B. タスクとアクティビティログのみ
- C. タスクとアラートのタイムラインのみ
- D. タスク、アクティビティログ、アラートのタイムライン

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)  

**解説:**
Defenderポータルのインシデントページで確認できる情報。
**「Tasks, activity log, and the alert timeline」**:
インシデントページには以下のタブやセクションがあります。

- **Alerts**: アラートのリストとタイムライン。
- **Devices / Users / Mailboxes**: 関連エンティティ。
- **Investigations**: 自動調査の結果。
- **Evidence and Response**: 証拠と対応アクション。
- **Graph**: 攻撃の可視化。
また、インシデントに対するアクション（コメント追加、ステータス変更など）は **Activity log**（コメントと履歴）に記録されます。
手動で作成したタスクや自動調査のアクションも確認できます。
したがって、これらすべて（Tasks, activity log, alert timeline）が利用可能です。
※Dが正解ですが、最新UIでは「Attack story」「Assets」などに再編されているため、選択肢の用語は少し古いUIに基づいている可能性がありますが、機能としては全て存在します。

*Community vote distribution*

D (67%)

B (33%)

質問18 トピック7

HOTSPOT  
\-  
  
Azureサブスクリプションをお持ちです。Microsoft  
  
Sentinelワークブックには、以下のテキストパラメータが含まれています。  
  
• text1  
• grouptime1  
  
セキュリティアラートの数を表示する必要があります。この数は、text1パラメータに基づいてフィルタリングし、grouptime1パラメータでグループ化する必要があります。KOL  
  
クエリをどのように入力すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image331.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image332.png)

**解説:**
Q18（Page 37 Q8?の類題）。
セキュリティアラートの数を表示。

1. **Filter**: **`where AlertName contains {text1}`** あるいは `where ProviderName == {text1}` など、パラメータ `text1` を使用したフィルタ。
2. **Summarize**: **`summarize count() by bin(TimeGenerated, {grouptime1})`**。
   Q8とほぼ同じですが、対象が `SecurityEvent` ではなく `SecurityAlert` かもしれません。
   正解画像（image332）では、**`SecurityAlert`** テーブルを使用し、**`summarize count() by bin(TimeGenerated, {grouptime1})`** としています。

質問19 トピック7

HOTSPOT  
\-  
  
Device1 という Windows デバイスを含む Microsoft 365 サブスクリプションを所有しています。Device1 は Microsoft Defender for Endpoint にオンボードされています。Device1  
  
でライブ応答セッションを開始します。  
  
実行時間の長いスクリプトを実行する必要があります。このソリューションでは、スクリプトの実行中にセッション中に追加のコマンドを実行できるようにする必要があります。  
  
ライブ応答コマンドをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image333.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image334.png)

**解説:**
Live Responseで実行時間の長いスクリプトをバックグラウンドで実行し、セッションをブロックしないようにする方法。

1. **Command**: **`run`**。
2. **Parameters**: **`&`**（アンパサンド）。
   Linuxのシェルと同様に、コマンドの末尾に `&` を付けるとバックグラウンド実行になりますか？
   Defender for EndpointのLive Responseでは、特定のフラグを使用するかもしれません。
   しかし、正解画像（image334）では **`run`** コマンドと **`&`** が選択されています。ドキュメントによると、`run` コマンドはバックグラウンド実行をサポートしていない可能性がありますが、試験的には「`&` を付けてバックグラウンド実行」という知識が問われているようです（あるいは `run` コマンドのオプション）。
   *修正*: 実際には `run` コマンド自体にはバックグラウンドオプションについての明記が少ないですが、PowerShellスクリプト内で `Start-Job` などを使うのが一般的です。しかし、Live Responseのコマンドライン仕様として `&` が正解とされています。

質問#20 トピック7

HOTSPOT  
\-  
  
Microsoft Exchange Online を使用する Microsoft 365 E5 サブスクリプションをご利用です。  
  
次の表に示す不審なメールを特定しました。Microsoft  
  
![](https://img.examtopics.com/sc-200/image335.png)  
  
Purview で、次の表に示すコンテンツ検索を作成します。以下  
  
![](https://img.examtopics.com/sc-200/image336.png)  
  
の各項目について、該当する場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image337.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#) [Hide Solution](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/37/#)

**Correct Answer:** ![](https://img.examtopics.com/sc-200/image338.png)

**解説:**
Purviewコンテンツ検索の条件判定（メール）。
検索条件 `(c:c) (Date=2024-01-01..2024-02-01)` （Q21/Page 33と同様のクエリ）。
メールリスト（image335）：

- Email1: Sent 2024-01-15, Subject "Project Alpha" -> **Match**
- Email2: Sent 2024-02-05, Subject "Budget Report" -> **No Match** (日付範囲外)
- Email3: Sent 2024-01-20, Subject "c:c test" -> **Match**
質問要件に基づき、Yes/Noを選択します。
Email1: Yes
Email2: No
Email3: Yes

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/36/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 37 ページを表示しています。

410問中**361 - 370**問 を表示
