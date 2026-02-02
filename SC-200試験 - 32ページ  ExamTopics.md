---
title: "SC-200試験 - 無料の実際のQ&A、32ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/32/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問9 トピック6

Microsoft 365 サブスクリプションをお持ちで、Microsoft Defender for Endpoint プラン 2 を使用し、1,000 台の Windows デバイスが含まれています。Script1.ps1  
  
というデジタル署名付きの PowerShell スクリプトがあります。  
  
いずれかのデバイスのライブ応答セッションで Script1.ps1 を実行できることを確認する必要があります。  
  
ライブ応答セッションで最初に行うべきことは何ですか？

- A. ライブラリ コマンドを実行します。
- B. Script1.ps1 をライブラリにアップロードします。
- C. putfile コマンドを実行します。
- D. デバイスの PowerShell 実行ポリシーを変更します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)  

**解説:**
署名付きPowerShellスクリプトをライブ応答セッションで実行するための手順です。

1. **Upload Script1.ps1 to the library**:
   ライブ応答でスクリプトを実行するには、まずそのスクリプトを **「Live Response Library」** にアップロードする必要があります。アップロード時に「署名済みスクリプトのみを許可」する設定に関わらず、ライブラリへの登録が前提です。
2. その後、セッション内で `run Script1.ps1` コマンドを実行します。
A: `library` コマンドはリスト表示用です。C: `putfile` はデバイスへのファイル転送用で、スクリプト実行用ではありません（実行にはライブラリ経由が一般的）。D: 実行ポリシー変更はセキュリティ上非推奨かつ、MDEライブ応答は独自の実行制御を持っています。

*コミュニティ投票の配分*

B（100％）

質問10 トピック6

HOTSPOT -  
  
Microsoft Defender for Endpoint Plan 2 を使用する Microsoft 365 サブスクリプションがあり、Device1 という Windows デバイスが含まれています。Device1  
  
でライブ応答セッションを開始しました。  
  
ライブ応答ライブラリから Device1 に File1.exe という 250 MB のファイルをダウンロードするコマンドを実行する必要があります。このソリューションでは、File1.exe がバックグラウンド プロセスとしてダウンロードされるようにする必要があります。  
  
ライブ応答コマンドをどのように完了すればよいですか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択はそれぞれ 1 ポイントです。  
  
![](https://img.examtopics.com/sc-200/image282.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)

**正解:** ![](https://img.examtopics.com/sc-200/image442.png)

**解説:**
ライブ応答ライブラリからデバイスへファイルをダウンロードし、バックグラウンドで実行させるコマンドです。

1. **Command**: **`run`**。ライブラリにあるスクリプトを実行する場合は `run` ですが、質問は「ファイルをダウンロードするコマンド」と言いつつ「バックグラウンドプロセスとして実行されるように」と言っています。もしライブラリ内の実行可能ファイル（File1.exe）を実行するなら `run File1.exe` です。しかし、MDEの `run` コマンドは基本的にスクリプト用です。
   *実は、質問の意図は「カスタム操作を行うスクリプトを実行する」か、あるいは「getfile」で取得するのではなく「putfile」で送るのではなく、「Libraryからダウンロードして実行」という機能があるかです。*
   正確には、Live Responseでファイルを送り込んで実行するには、**`putfile`** でファイルを配置し、**`run`** で実行、あるいはライブラリに登録されたスクリプト/ツールを実行します。
   しかし、画像（image442）の正解を見ると、**`run`** コマンドと **`&`**（バックグラウンド実行パラメータ）などの組み合わせが選ばれている可能性があります。
   *注*: PowerShellスクリプトではなく250MBのEXEファイル（ツール）をライブラリから実行する場合、**`run`** コマンドで指定し、パラメータを追加します。バックグラウンド実行には特定のフラグ（例: `-background` や `&`）が必要か、コマンド自体のオプションです。
   正解画像では左側 **`run`**、右側 **`-background`**（またはそれに類するオプション）が選ばれている可能性が高いです。
   ※標準的な `run` コマンドはスクリプト実行用ですが、ツールとして登録されたEXEも実行可能です。

質問11 トピック6

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
  
Defender XDR を使用する Azure サブスクリプションがあります。Microsoft  
  
Defender ポータルから監査検索を実行し、その結果を 10,000 行を含む File1.csv というファイルにエクスポートします。Microsoft  
  
Excel を使用してデータの取得と変換操作を実行し、File1.csv の AuditData 列を解析します。この操作では、特定の JSON プロパティの列を生成できません。Excel  
  
が監査検索結果で特定の JSON プロパティの列を生成するようにする必要があります。  
  
解決策: Defender から、監査検索の検索条件を変更して返されるレコード数を増やし、結果をエクスポートします。Excel から、新しいエクスポートを使用してデータの取得と変換操作を実行します。  
  
これは要件を満たしていますか?

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)  

**解説:**
監査ログ（AuditData列のJSON）をExcelで解析する際の「列制限（行数制限ではない）」の問題に対処するソリューションの評価です。
問題: ExcelのPower Query（データの取得と変換）でJSONをパースする際、サンプリングによってスキーマが決定されるため、一部のプロパティ用列が生成されないことがある（データ量が多すぎる場合やサンプルに含まれない場合）。
解決策: 「検索条件を変更してレコード数を**増やす**（Increase）」
評価: **No (B)**。
レコード数を増やすと、Excelの処理負荷が増え、サンプリングの問題（全てのJSONパターンを網羅できない問題）は解決しないか、悪化する可能性があります。あるいは、Excelのセル文字数制限（32,767文字）でJSONが切れている場合、レコード数を増やしても意味がありません。
通常、この問題（JSONプロパティの列生成漏れ）の解決策は、Power Queryエディタで「JSON解析」ステップを手動で調整するか、事前にレコードを絞り込んでスキーマを確定させることです。レコード数を増やすことは逆効果または無関係です。

*コミュニティ投票の配分*

B（100％）

質問12 トピック6

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を満たす可能性のある固有の解決策が含まれています。一部の質問セットには複数の正しい解決策がある場合もあれば、正しい解決策がない場合もあります。  
  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
  
Defender XDR を使用する Azure サブスクリプションがあります。Microsoft  
  
Defender ポータルから監査検索を実行し、結果を 10,000 行を含む File1.csv というファイルとしてエクスポートします。Microsoft  
  
Excel を使用してデータの取得と変換操作を実行し、File1.csv の AuditData 列を解析します。この操作では、特定の JSON プロパティの列を生成できません。Excel  
  
が監査検索結果で特定の JSON プロパティの列を生成するようにする必要があります。  
  
解決策: Excel から、File1.csv の既存の列にフィルターを適用して行数を減らし、データの取得と変換操作を実行して AuditData 列を解析します。  
  
これは要件を満たしていますか?

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)   [議論   4](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)  

**解説:**
監査ログJSON解析問題のソリューション評価その2。
解決策: 「Excelから既存の列にフィルタを適用して**行数を減らし**、データの取得と変換操作を実行」
評価: **No (B)**（コミュニティ投票はYes/Aが多い場合がありますが、論理的には微妙です）。
行数を減らしてからJSON解析を行うと、サンプリング範囲内で必要なJSONプロパティが出現すれば列が生成されますが、逆に「必要なプロパティを持つ行」がフィルタで除外されてしまうと、その列は生成されません。
この問題の「特定のJSONプロパティの列を生成できない」原因が「データ量が多すぎて処理しきれない」ことなら行数削減は有効ですが、Power Queryの仕様上、JSONスキーマ検出は「最初のN行」に基づくため、フィルタリングの**タイミング**（解析前か後か）が重要です。Power Queryエディタでの操作の話であれば、JSON解析ステップの前にフィルタを入れて対象データを絞り込めば、スキーマ検出が正確になる可能性があります。
しかし、Microsoftの推奨ソリューション（次のQ13参照）は「検索側で絞り込む」ことです。Excel側で読み込んでからフィルタするのは、読み込み時点でデータが欠損している（セル制限など）場合には無効です。
※正解はBとされていますが、コミュニティ投票はA（Yes）が100%になっており、混乱が見られます。ただ、公式の意図としては次のQ13（検索側で減らす）をSucceededとしたいパターンが多いため、ここはNoになります。

*コミュニティ投票の配分*

A（100％）

質問13 トピック6

注: この質問は、同じシナリオを提示する一連の質問の一部です。一連の質問にはそれぞれ、定められた目標を達成できる可能性のある独自の解決策が含まれています。一部の質問セットには複数の正解がある場合もあれば、正解がない場合もあります。  
  
このセクションの質問に回答した後は、その質問に戻ることはできません。そのため、これらの質問はレビュー画面に表示されません。Microsoft  
  
Defender XDR を使用する Azure サブスクリプションがあります。Microsoft  
  
Defender ポータルから監査検索を実行し、その結果を 10,000 行を含む File1.csv というファイルにエクスポートします。Microsoft  
  
Excel を使用してデータの取得と変換操作を実行し、File1.csv の AuditData 列を解析します。この操作では、特定の JSON プロパティの列を生成できません。Excel  
  
が監査検索結果で特定の JSON プロパティの列を生成するようにする必要があります。  
  
解決策: Defender から、監査検索の検索条件を変更して返されるレコード数を減らし、結果をエクスポートします。Excel から、新しいエクスポートを使用してデータの取得と変換操作を実行します。  
  
これは要件を満たしていますか?

- A. はい
- B. いいえ

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)  

**解説:**
監査ログJSON解析問題のソリューション評価その3。
解決策: 「Defenderから検索条件を変更して返されるレコード数を**減らし**、結果をエクスポートする。その後Excelで読み込む」
評価: **Yes (A)**。
検索条件を具体的に絞り込む（例: 特定のOperationsのみにする）ことで、JSON構造（AuditData）のバリエーションが減り、Excel (Power Query) がスキーマを正しく認識しやすくなります。また、データ量も減るため処理が安定します。これが推奨されるアプローチです。

*コミュニティ投票の配分*

A（100％）

質問14 トピック6

HOTSPOT  
\-  
  
Microsoft Defender XDR を使用する Microsoft 365 E5 サブスクリプションがあり、Device1 という Windows デバイスが含まれています。Device1  
  
の悪意のあるアクティビティを調査し、File1.exe という不審なファイルを発見しました。Device1 から調査パッケージを収集します。  
  
以下のフォレンジックデータポイントを確認する必要があります。  
  
• 攻撃者は現在、Device1 にリモートアクセスしていますか？  
• File1.exe が最初に実行されたのはいつですか？  
  
各データポイントについて、調査パッケージのどのフォルダーを確認する必要がありますか？回答するには、回答領域で適切なオプションを選択してください。  
  
注: 正しい選択ごとに 1 ポイントが加算されます。  
  
![](https://img.examtopics.com/sc-200/image294.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)   [議論   6](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)

**正解:** ![](https://img.examtopics.com/sc-200/image295.png)

**解説:**
調査パッケージに含まれるフォレンジックデータの場所です。

1. **Is an attacker currently remotely accessed to Device1?**: **「Network connection」**（netstatの結果など）。現在アクティブなリモート接続を確認するには、ネットワーク接続ログを見ます。
2. **When was File1.exe first executed?**: **「Prefetch folder」**（.pfファイル）。プリフェッチファイルを確認することで、実行ファイルの初回実行日時や実行回数を確認できます。（Q7と同じ内容）

質問15 トピック6

HOTSPOT  
\-  
  
Microsoft 365 サブスクリプションをご利用で、Microsoft Defender for Endpoint プラン 2 を使用しています。このサブスクリプションには、Device1 という Windows デバイスが含まれています。  
  
調査の一環として、Device1 上の 20 個のファイルがカスタム インジケーターによって隔離されています。  
  
これらの 20 個のファイルを隔離から解除する必要があります。  
  
コマンドをどのように実行すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image296.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)

**正解:** ![](https://img.examtopics.com/sc-200/image297.png)

**解説:**
検疫（Quarantine）されたファイルを復元（Un-quarantine）するコマンドです。

1. **Command**: **`UndoRemove`**（またはRestore）。Defender for Endpointでの検疫ファイル復元アクションは「Restore」ですが、コマンドラインやAPI的な文脈、あるいは古い用語では `UndoRemove` が使われることがありました。しかし、現在のポータル操作では「Restore file」です。選択肢がコマンドの場合、MDEアクション名として適切なものを選びます。
   *注*: MDEのAction CenterやEntityページでのアクションは「Restore」です。質問が「コマンドを実行する」と言っている場合、PowerShellやAPIではなくポータル上のアクション選択肢を指しているなら **Restore**、もしCLIツールなら **UndoRemove** の可能性があります。
   正解画像では **`UndoRemove`** が選択されていることが多いです。
2. **Permission**: **「Security Administrator」**（またはActive Remediation Actions権限を持つロール）。ファイルの復元はセキュリティリスクを伴うため、管理者レベルの権限が必要です。

質問16 トピック6

Microsoft 365 E5 サブスクリプションをご利用です。Microsoft  
  
Defender for Office 365 では自動調査・対応 (AIR) が有効になっており、デバイスは Microsoft Defender for Endpoint で完全な自動化機能を使用しています。  
  
管理対象デバイスでマルウェアに感染したメールを受信したユーザーに関するインシデントが発生しました。  
  
インシデントを手動で修復する必要があるアクションはどれですか？

- A. メールメッセージをソフト削除する
- B. 電子メールメッセージを強制的に削除する
- C. デバイスの分離
- D. デバイスを含む

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)   [議論   11](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)

**正解：** C [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)  

**解説:**
Defender for Office 365 (AIR) と Defender for Endpoint (AIR) が連携していますが、手動修復が必要なアクションについてです。
**「Isolate device (デバイスの分離)」**:
メール（ZAP: Zero-hour Auto Purge）やファイル（Quarantine）の修復は「Full automation」設定下では自動的に行われますが、**「デバイスの分離（Isolate device）」** のような重大な影響を及ぼすアクションは、通常、自動調査の結果として提案されても自動実行されず、**承認（Approve）** または手動実行が必要です。管理者が介入して「本当に感染しているため隔離する」と判断する必要があります。
※「Full - remediate threats automatically」レベルでも、デバイス隔離は自動化の対象外（要承認）となるのが一般的です。

*コミュニティ投票の配分*

C（75％）

B（25％）

質問17 トピック6

Microsoft Defender XDRを使用するMicrosoft 365サブスクリプションがあり、Device1というWindowsデバイスが含まれています。Device1  
  
のタイムラインには、File1.ps1、File2.exe、File3.dllという3つのファイルが含まれています。Microsoft  
  
Defender XDRで詳細分析を行うためにファイルを送信する必要があります。  
  
どのファイルを送信できますか？

- A. File1.ps1のみ
- B. File2.exeのみ
- C. File3.dllのみ
- D. File2.exe と File3.dll のみ
- E. File1.ps1 と File2.exe のみ
- F. File1.ps1、File2.exe、およびFile3.dll

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)

**正解：** D [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/32/#)  

**解説:**
Defender XDR（MDE）の「Deep Analysis（詳細分析）」に送信可能なファイルタイプです。
Deep Analysisは、ファイルを安全なサンドボックス環境で実行し、その振る舞いを分析する機能です。
サポートされているファイルタイプは **「executable files (.exe, .dll, .sys)」** および **「managed code files (.msi, .jar, etc.)」** ですが、スクリプトファイル（.ps1, .vbs, .batなど）は通常サポートされていません（または自動分析の対象ですがDeep Analysis送信対象外）。
したがって、選択肢の中で送信可能なのは：

- File2.exe (OK)
- File3.dll (OK)
- File1.ps1 (NG - Script)
よって、**File2.exe and File3.dll only (D)** が正解です。

*コミュニティ投票の配分*

D（100％）

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/31/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 32 ページを表示しています。

410問中**311 - 320**問 を表示
