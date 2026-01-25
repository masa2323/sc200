---
title: "SC-200試験 - 無料の実際のQ&A、18ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/18/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#44 トピック3

Azure サブスクリプションには、app1 という Azure ロジック アプリと、Azure Active Directory (Azure AD) コネクタを備えた Microsoft Sentinel ワークスペースが含まれています。Microsoft  
Sentinel が Azure AD 生成のアラートを検出したときに、app1 が起動するようにする必要があります。  
まず何を作成すればよいでしょうか？  

- A. リポジトリ接続
- B. ウォッチリスト
- C. 分析ルール
- D. 自動化ルール

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)   [議論   14](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
Azure ADのアラート（Identity Protectionなど）がSentinelに取り込まれた際にLogic Appを自動実行する設定です。
**「自動化ルール (Automation rule)」**: Sentinelにて「インシデント作成時」または「アラート作成時」をトリガーとする自動化ルールを作成し、アクションとして「プレイブックの実行（Run playbook）」を選択します。これにより、特定の条件（Azure ADからのアラートなど）に合致した場合にLogic App（プレイブック）を自動起動できます。

*コミュニティ投票の配分*

D（66％）

C（34％）

質問#45 トピック3

Microsoft Sentinelワークスペースをご利用の場合、  
2つ以上のアラートまたはアクティビティで構成される高度な多段階攻撃を検出するために使用するルールを特定する必要があります。このソリューションは、管理作業を最小限に抑える必要があります。  
どのタイプのルールをクエリすればよいでしょうか？  

- A. 融合
- B. マイクロソフトセキュリティ
- C. ML行動分析
- D. 予定

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)   [議論   5](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
複数のアラートやアクティビティを相関分析し、高度な多段階攻撃を検出するルールです。
**「Fusion」**: Sentinelの機械学習ベースの相関エンジンです。異なる製品（Defender for Cloud, Azure AD Identity Protectionなど）からのシグナルを組み合わせ、キルチェーンの各段階にまたがる攻撃キャンペーンを自動的に検出します。デフォルトで有効化されており、管理作業は最小限で済みます。

*コミュニティ投票の配分*

A（100％）

質問#46 トピック3

Microsoft Sentinel を使用する Azure サブスクリプションがあり、100 台の Linux 仮想マシンが含まれています。Microsoft  
Sentinel を使用してこれらの仮想マシンを監視する必要があります。ソリューションは、以下の要件を満たす必要があります。✑  
管理作業を最小限に抑える。✑  
FOG データの読み取りに必要な解析を最小限に抑える。  
どのような構成が必要ですか？  

- A. Log Analytics データコレクター API
- B. REST API統合
- C. 共通エバートフォーマット（CEF）コネクタ
- D. Syslogコネクタ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)   [議論   36](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
100台のLinux VMを監視し、管理と解析の手間を最小限にする構成です。
**「Common Event Format (CEF) connector」**: Syslogメッセージの一種ですが、標準化されたフィールドを持つCEF形式を使用することで、Sentinel側での追加の解析作業（Parsersの作成など）を最小限に抑えられます。Syslogコネクタ（標準Syslog）では、非構造化データのParsingが必要になる場合がありますが、CEFなら`CommonSecurityLog`テーブルにきれいに格納されます。

*コミュニティ投票の配分*

C（65％）

D（35％）

質問#47 トピック3

ホットスポット -  
Microsoft Defender for Cloud の強化されたセキュリティ機能が有効になっている Azure サブスクリプションが 100 個あります。すべてのサブスクリプションは単一の Azure  
Active Directory (Azure AD) テナントにリンクされています。Defender  
for Cloud のログを Syslog サーバーにストリーミングする必要があります。このソリューションでは、管理作業を最小限に抑える必要があります。  
どうすればよいでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
注: 正しい選択は 1 ポイントです。  
ホットエリア:  
![](https://www.examtopics.com/assets/media/exam-media/04261/0015200001.png)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)   [議論   16](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)

**正解:** ![](https://img.examtopics.com/sc-200/image426.png)

**解説:**
Defender for CloudのログをSyslogサーバーにストリーミングする構成です。

1. **Azure Event Hubs**: 「連続エクスポート (Continuous Export)」機能を使用して、Defender for Cloudのアラートや推奨事項をAzure Event Hubにストリーミングします。これがSyslogなど外部への出口となります。
2. **Azure Logic App**: （※選択肢の画像構成によってはAzure Functionの場合もありますが、Event Hubからデータを取り出しSyslogサーバーへ転送するためにLogic AppやFunctionなどのコンピュートリソースを使用するのが一般的です。ただし、標準的な構成では「Event Hub + Logic App/Function」または「SentinelのSyslogコネクタ経由」などが考えられますが、Defender for Cloudからの直接エクスポートとしてはEvent Hubが必須です。）
※正解画像の選択肢が不明瞭ですが、**「Continuous export」**を設定し、ターゲットとして**「Event Hub」**を選択する構成が最小労力の鍵です。

質問#48 トピック3

ドラッグ＆ドロップ -  
100台のLinux仮想マシンを含むAzureサブスクリプションがあります。  
仮想マシンからイベントログを収集するには、Microsoft Sentinelを構成する必要があります。3  
つのアクションのうち、どのアクションを順番に実行する必要がありますか？ 回答するには、アクションリストから適切なアクションを回答エリアに移動し、正しい順序に並べ替えてください。  
選択して配置してください。  
![](https://www.examtopics.com/assets/media/exam-media/04261/0015300001.jpg)  

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)   [議論   14](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)

**正解:** ![](https://img.examtopics.com/sc-200/image427.png)

**解説:**
Linux VMからイベントログを収集する手順です（AMA/Legacy Agentのどちらか）。

1. **Install the MMA/AMA agent**: Linux VMにエージェント（Log AnalyticsエージェントまたはAzure Monitorエージェント）をインストールします。
2. **Configure the Syslog data connector**: Sentinel（またはLog Analyticsワークスペース）の設定で、収集するSyslogファシリティと重要度レベル（Severity）を構成します。
3. **（該当なし）**: 手順としてはエージェント導入と収集設定の2ステップが主ですが、3つ選ぶ必要がある場合、「ワークスペースIDとキーの取得」などが含まれる可能性があります。

質問#49 トピック3

Microsoft Sentinel を使用する Azure サブスクリプションをご利用です。  
  
ハンティングクエリを使用して新たな脅威を検出しました。Microsoft  
  
Sentinel が脅威を自動的に検出できるようにする必要があります。ソリューションは管理の手間を最小限に抑える必要があります。  
  
どうすればよいでしょうか？

- A. 分析ルールを作成します。
- B. クエリをワークブックに追加します。
- C. ウォッチリストを作成します。
- D. プレイブックを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)   [議論   13](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
Huntingクエリで見つけた脅威を、今後は自動的に検出する（ルール化する）ための方法です。
**「分析ルールを作成します (Create an analytics rule)」**: Huntingクエリの結果画面から「新しいアラート ルール (New alert rule)」を作成することで、そのクエリロジックをスケジュールされた分析ルールとして保存できます。これにより、同様の脅威を継続的かつ自動的に検出できるようになります。

*コミュニティ投票の配分*

A（100％）

質問#50 トピック3

Microsoft Sentinel ワークスペースがあります。  
  
次の図に示すように、Query1 というクエリがあります。Parser1  
  
![](https://img.examtopics.com/sc-200/image135.png)  
  
というカスタム パーサーを作成する予定です。Parser1  
  
で Query1 を使用する必要があります。  
  
まず何をすべきでしょうか。

- A. 5行目を削除します。
- B. 2行目を削除します。
- C. 3 行目で、!contains 演算子を !has 演算子に置き換えます。
- D. 4 行目で、TimeGenerated 述語を削除します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
既存のクエリ（Query1）を元にParser（関数）を作成する際、修正すべき点です。
**「2行目を削除します」**: 画像のコードを参照すると、2行目はおそらく具体的な値をフィルタリングしている箇所（例: `| where HostName == "SpecificHost"`）や、テスト用の制限などと考えられます。汎用的なParserとして機能させるには、特定のテスト条件を削除し、引数を受け取れるようにするか、あるいは純粋なデータ整形ロジックのみにする必要があります。
※一般論として、Parser（Function）にする際、特定の値をハードコードしている行は削除またはパラメータ化します。

*コミュニティ投票の配分*

B（87％）

13%

質問#51 トピック3

Microsoft Sentinel を使用する Azure サブスクリプションをお持ちです。  
  
サインイン情報を時系列で視覚化するカスタムレポートを作成する必要があります。  
  
まず何を作成すればよいでしょうか？

- A. 狩猟に関する質問
- B. ワ​​ークブック
- C. ノートブック
- D. プレイブック

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
データを可視化するカスタムレポートを作成する機能です。
**「ワークブック (Workbook)」**: Sentinelにおけるデータの可視化、レポート作成、ダッシュボード機能の標準ツールです。KQLクエリの結果をグラフ、チャート、グリッドとして表示し、インタラクティブなレポートを作成できます。

*コミュニティ投票の配分*

B（100％）

質問#52 トピック3

Microsoft Sentinelワークスペースを使用しています。  
  
あるアカウントへのサインイン失敗に関するアラートが複数回発生しています。  
  
これらのアラートは誤検知であることが判明しました。  
  
このアカウントに対して、今後サインイン失敗アラートが生成されないようにする必要があります。このソリューションは、以下の要件を満たす必要があります。  
  
• 他のアカウントに対してもサインイン失敗アラートが生成されるようにする。  
• 管理作業を最小限に抑える。  
  
どうすればよいでしょうか？

- A. 分析ルールを変更します。
- B. ウォッチリストを作成します。
- C. エンティティ動作にアクティビティ テンプレートを追加します。
- D. 自動化ルールを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)   [議論   33](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)  

**解説:**
特定のアカウントに対する誤検知アラート（サインイン失敗）を停止し、他のアカウントは監視を継続する、かつ管理負荷を低くする方法です。
**「分析ルールを変更します」**: KQLクエリに特定のアカウントを除外する条件（例: `and UserPrincipalName != "user@example.com"`）を追加するのが最も確実で処理負荷も低い方法です。
※Automation rule（D）でもクローズは可能ですが、アラート自体は生成されてしまうため「生成されないようにする」という要件には分析ルールの修正が適しています。頻繁な変更がある場合はWatchlistの使用も検討されますが、選択肢の中ではAが基本です。

*コミュニティ投票の配分*

A（59％）

D（32％）

9%

質問#53 トピック3

HOTSPOT -  
  
Microsoft 365 E5 サブスクリプションがあり、User1 と User2 という 2 人のユーザーがいます。  
  
次の図に示すようなハンティングクエリがあります。  
  
![](https://img.examtopics.com/sc-200/image136.png)  
  
ユーザーは以下のアクションを実行します。  
  
• User1 が User2 にグローバル管理者ロールを割り当てます。  
• User1 が User3 という新しいユーザーを作成し、そのユーザーに Microsoft Teams ライセンスを割り当てます。  
• User2 が User4 という新しいユーザーを作成し、そのユーザーにセキュリティ閲覧者ロールを割り当てます。  
• User2 が User5 という新しいユーザーを作成し、そのユーザーにセキュリティオペレーターロールを割り当てます。  
  
以下の各ステートメントについて、該当する場合は「はい」を選択します。それ以外の場合は「いいえ」を選択します。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image137.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)   [議論   37](https://www.examtopics.com/exams/microsoft/sc-200/view/18/#)

**正解:** ![](https://img.examtopics.com/sc-200/image428.png)

**解説:**
AuditLogsに対するHuntingクエリの結果判定です。
クエリは `AuditLogs | where OperationName == "Add member to role" ...` と `... "Add user"` のような操作を対象にしています。

1. **User1 assigned the Global Administrator role to User2?**: **No**。User1がUser2にロールを割り当てた場合、InitiatedBy（Actor）がUser1、TargetResources（Target）がUser2になりますが、クエリの `TargetResources` のプロパティ展開ロジックが正しくユーザーIDやロールIDを抽出できているか確認が必要です。
2. **User3 created?**: **Yes/No**。ユーザー作成イベントが含まれているかによります。
3. **User4 assigned Security Reader?**: **Yes/No**。
※このHuntingクエリは `TargetResources` 内の `modifiedProperties` を解析しようとしていますが、通常 `Add member to role` イベントでは、対象ユーザーやロール情報は `TargetResources` 直下や特定のプロパティにあります。クエリが正しくターゲットを特定できているかどうかがポイントです。

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/17/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 18 ページを表示しています。

410問中**171 - 180**問 を表示
