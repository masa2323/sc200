---
title: "SC-200試験 - 無料の実際のQ&A、19ページ | ExamTopics"
source: "https://www.examtopics.com/exams/microsoft/sc-200/view/19/"
author:
published:
created: 2026-01-18
description: "Free, Actual and Latest Practice Test for those who are preparing for Microsoft Security Operations Analyst    ."
tags:
  - "clippings"
---
質問#54 トピック3
  
次のKQLクエリがあります。  
  
![](https://img.examtopics.com/sc-200/image139.png)  
  
以下の各文について、正しい場合は「はい」を選択してください。そうでない場合は「いいえ」を選択してください。  
  
注：正しい選択は1点です。  
  
![](https://img.examtopics.com/sc-200/image140.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   20](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image429.png)

**解説:**
1. The `UserName` field is set as the account entity. (**はい**)
クエリの最終行に `AccountCustomEntity = UserName` という記述があります。これは、Microsoft Sentinel の分析ルールにおいて、`UserName` フィールドの値を「アカウント」エンティティとしてマッピングしていることを示しています。

2. The watchlist cannot be updated after it is created. (**いいえ**)
Microsoft Sentinel のウォッチリスト（このクエリでは `_GetWatchlist('Bad_IPs')` で呼び出されているもの）は、作成後も内容を更新、削除、または新しいデータの追加が可能です。クエリ内で呼び出されているからといって、そのデータが固定（イミュータブル）されるわけではありません。

3. The `IPList` variable is set as the IP address entity. (**いいえ**)
`IPList` は、クエリの冒頭で `let IPList = _GetWatchlist('Bad_IPs');` と定義されており、ウォッチリスト内の**IPアドレスのリスト全体**を保持する変数です。 一方で、IPアドレスエンティティとしてマッピングされているのは、クエリ末尾の `IPCustomEntity = case(...)` の部分であり、そこでは個別の `SourceIP` または `DestinationIP` が代入されています。`IPList` 変数そのものがエンティティとして設定されているわけではありません。

質問#55 トピック3
  
Microsoft Sentinelワークスペースがあります。Parser1  というカスタムAdvanced Security Information Model (ASIM)パーサーを開発し、Schema1というスキーマを生成します。Schema1 を検証する必要があります。  
  
コマンドをどのように完了すればよいですか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image142.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   9](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image143.png)

**解説:**
- **getschema**: この演算子は、`Parser1` が出力するデータの「列名」と「データ型」の一覧をテーブル形式で出力します。
- **invoke**: `getschema` で作成された「スキーマ情報テーブル」を、次の `ASimSchemaTester` 関数に引数として渡すために使用します。
- **ASimSchemaTester('Schema1')**: この関数は、データそのものではなく、**「データの構造（getschemaの出力）」**を受け取って、それが `Schema1` の定義と一致しているかをチェックします。

質問#56 トピック3
  
ユーザーおよびエンティティ行動分析 (UEBA) が有効になっている Microsoft Sentinel ワークスペースがあります。Server1  というサーバー上で実行された、セキュリティ上重要なユーザー操作に関連するすべてのログエントリを特定する必要があります。ソリューションは以下の要件を満たす必要があります。  
  
• IT 部門のメンバーではないユーザーによる、セキュリティ上重要な操作のみを含める。  
• 誤検知の数を最小限に抑える。  
  
クエリをどのように完了すればよいですか？回答するには、回答エリアで適切なオプションを選択してください。  

注: 正しい選択ごとに 1 ポイントが加算されます。  
  
![](https://img.examtopics.com/sc-200/image144.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   10](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image145.png)

**解説:**
1. `join kind=inner (` を選択する理由

「IT部門ではないユーザー」という条件でフィルタリングを行うためには、左側のテーブル（SecurityEvent）と右側のテーブル（ユーザー情報）の両方に存在するレコードのみを抽出する必要があります。`inner` ジョインを使用することで、右側のテーブルに情報がない（マッチしない）レコードを除外でき、**誤検知の数を最小限に抑える**という要件を満たすことができます。

2. `IdentityInfo` を選択する理由

「部署（Department）」などのユーザー属性情報は、UEBAが有効なワークスペースでは **`IdentityInfo`** テーブルに格納されます。

- **BehaviorAnalytics**: ユーザーの異常行動やスコアを格納するテーブルです。
    
- **SecurityEvent**: すでにメインのクエリ（左側）で使用されており、自己結合は今回の目的（属性によるフィルタ）には適しません。
    
 3. `summarize arg_max` の役割

`IdentityInfo` テーブルには時間の経過とともに同じユーザーのデータが複数記録されます。`summarize arg_max(TimeGenerated, *) by AccountObjectId` を使用することで、各ユーザーの**最新のプロファイル情報**（最新の部署情報など）のみを取得し、正確なフィルタリングを可能にします。

質問#57 トピック3
  
Microsoft Sentinelワークスペースをお持ちです。  
  
過去3時間に複数の国から成功したサインインを識別するKQLクエリを作成する必要があります。  
クエリはどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image146.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   7](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image147.png)

**解説:**
1. `imAuthentication` を選択する理由

「サインイン（ログオン）」に関する情報を取得するためには、ASIMの**認証スキーマ**を使用する必要があります。

- **imAuthentication**: ログオン、ログアウト、パスワード変更などの認証イベントを正規化するスキーマです。
    
- クエリの4行目に `EventType == 'Logon'` とあることからも、認証イベントを扱うこのテーブルが適切です。
    
- 他の `imNetworkSession`（ネットワーク通信）や `imWebSession`（HTTPリクエスト）などは、サインインの成功/失敗を判定するスキーマではありません。
    

 2. `SrcGeoCountry` を選択する理由

「複数の国から」という条件を判定するためには、接続元（ソース）の国情報をカウントする必要があります。

- **SrcGeoCountry**: サインインを試みた場所（ソース）の国名を表すASIM標準フィールドです。
    
- 直前の行で `isnotempty(SrcGeoCountry)` とフィルタリングされていることからも、このフィールドをカウント対象にするのが論理的です。
    
- **DstGeoCountry** は「宛先」の国を指すため、ユーザーがどこからアクセスしたかを判定するこのケースには適しません。
    

 完成したクエリのロジック
このクエリは、過去3時間に成功したログオンイベントを集計し、異なる送信元の国（`SrcGeoCountry`）の数（`dcount`）が5（`threshold`）以上のユーザーを抽出する、典型的な「あり得ない移動（Impossible Travel）」や「広範囲からのアクセス」を検知するためのものです。

質問#58 トピック3

HOTSPOT  
\-  
  
Azureサブスクリプションを所有しています。Microsoft  
  
Sentinelワークスペースを実装する予定です。1日あたり20GBのセキュリティログデータを取り込む予定です。  
  
ワークスペースのストレージを構成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 毎日取り込むデータのコストを最小限に抑える。  
• 追加コストをかけずにデータ保持期間を最大化する。  
  
各要件に対して、どのような対策を講じるべきでしょうか？回答するには、回答エリアから適切なオプションを選択してください。  
  
注：正解は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image148.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   18](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image149.png)

**解説:**
1. 取り込みコストの最小化について

Microsoft Sentinelの「コミットメントティア（予約容量）」は、最低でも **1日あたり100GB** の取り込みを約束することで割引が適用される仕組みです。

- 今回のケースでは、取り込み予定量が **1日あたり20GB** です。
    
- 100GBティアを選択すると、実際には20GBしか使っていなくても100GB分の固定料金（1日約296ドル〜）を支払うことになります。
    
- **Pay-As-You-Go (従量課金)** モデルであれば、実際に取り込んだ20GB分のみ（1GBあたり約4.3ドル × 20GB = 1日約86ドル）の支払いで済むため、こちらのほうが低コストになります。
    

 2. データ保持期間の最大化について

Microsoft Sentinelが有効なワークスペースでは、**最初の90日間** のデータ保持が追加コストなし（無料）で提供されます。

- **31日間**: デフォルトのLog Analytics設定に近いですが、Sentinelの特典である90日間をフルに活用できていません。
    
- **90日間**: Sentinelの「無料保持期間」を最大限に活用できる設定です。
    
- **365日間**: 90日を超えた分（残りの275日分）に対して追加の保持コストが発生するため、要件の「追加コストをかけずに」に反します。

質問#59 トピック3

sws1 という Microsoft Sentinel ワークスペースがあります。sws1  
  
でインシデントが発生した際に、オンプレミスの IT サービス管理システムでインシデントを通知する Azure ロジック アプリを作成する予定です。  
  
このロジック アプリ用に Microsoft Sentinel コネクタの資格情報を構成する必要があります。ソリューションは、以下の要件を満たす必要があります。  
  
• 管理作業を最小限に抑える。  
• 最小権限の原則を適用する。  
  
資格情報はどのように構成すればよいでしょうか？ 回答するには、回答領域から適切なオプションを選択してください。  
  
注: 正解は 1 点です。  
  
![](https://img.examtopics.com/sc-200/image150.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   18](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image430.png)

**解説:**
Logic AppのSentinelコネクタ用資格情報を、最小権限かつ管理負荷最小で構成する方法です。

1. マネージド ID を選択する理由 (管理作業の最小化)

マネージド ID は Azure によって自動的に管理される ID であり、パスワードやシークレットの管理（作成、保存、ローテーションなど）が不要です。

- **A service principal (サービス プリンシパル)** は、シークレットの管理や有効期限の監視が必要になるため、管理作業が増加します。
    
- **An Azure AD user account (Azure AD ユーザー アカウント)** は、個人のパスワード管理や多要素認証 (MFA) の影響を受けるため、自動化には適しません。
    

	 1. Microsoft Sentinel Reader を選択する理由 (最小権限の原則)

今回の要件は、インシデントが発生した際に「通知」を行うことです。

- **Microsoft Sentinel Reader**: インシデントのデータを受け取り、その内容を読み取って通知を送るために必要な最小限の権限（表示権限）を持っています。
    
- **Microsoft Sentinel Responder**: インシデントの割り当てや状態変更、ウォッチリストの更新などが可能ですが、通知を送るだけであれば過剰な権限となります。
    
- **Microsoft Sentinel Automation Contributor**: 自動化ルールを管理するための権限であり、ロジックアプリがインシデント情報を読み取るための権限ではありません。

質問#60 トピック3

Microsoft Sentinelワークスペースを使用しています。  
  
組み込みのAdvanced Security Information Model（ASIM）パーサーが自動更新されないようにする必要があります。  
  
この目標を達成するための2つの方法は何ですか？ 正解はそれぞれ完全な解決策を示しています。  
  
注：正解は1つにつき1ポイントです。

- A. 組み込みパーサーを参照するハンティング クエリを作成します。
- B. カスタムの統合パーサーを構築し、組み込みパーサー バージョンを含めます。
- C. 組み込みパーサーを再デプロイし、CallerContext パラメータに Any を指定し、SourceSpecificParser パラメータに Any を指定します。
- D. 組み込みパーサーを再デプロイし、Built-in の CallerContext パラメータを指定します。
- E. 組み込みパーサーを含む分析ルールを作成します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   20](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** BC [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)  

**解説:**
組み込みのASIMパーサーが自動更新されないように制御する方法です。
**「B. カスタムの統合パーサーを構築し、特定のバージョンを含める」**: デフォルトの統合パーサー（Unifying parser）は常に最新のパーサーを呼び出します。これを防ぐには、独自のカスタム統合パーサーを作成し、その中で使用するソース特定パーサーのバージョン（例: `vimNetworkSessionMicrosoftWindowsEventFirewallV02`）を明示的に指定します。
**「C. (またはWatchlistを使用)」**: もう一つの方法は、`ASim Disabled Parsers` ウォッチリストを使用して、特定の組み込みパーサーを統合パーサーの対象から除外（無効化）することです。

*コミュニティ投票の配分*

紀元前（53％）

BE（44％）

4%

質問#61 トピック3

Workbook1 というカスタム Microsoft Sentinel ワークブックがあります。Workbook1  
  
にグリッドを追加する必要があります。ソリューションでは、グリッドに最大 100 行が含まれるようにする必要があります。  
  
どうすればよいでしょうか？

- A. グリッド クエリに take 演算子を含めます。
- B. グリッド クエリにプロジェクト演算子を含めます。
- C. クエリ エディター インターフェイスで、設定を構成します。
- D. クエリ エディター インターフェイスで、\[詳細エディター\] を選択します。

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   13](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解：** A [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)  

**解説:**
Workbookのグリッド表示を最大100行に制限する方法です。
**「グリッド クエリに take 演算子を含めます」**: KQLクエリの末尾に `| take 100` （または `limit 100`）を追加することで、クエリ結果自体を100行に制限するのが最も確実かつ一般的な方法です。
※UI上の「Advanced Settings」でも表示行数を設定できますが、クエリレベルでの制御（A）が正解とされることが多いです。

*コミュニティ投票の配分*

A（86％）

14%

質問#62 トピック3

HOTSPOT  
\-  
  
SW1というMicrosoft Sentinelワークスペースがあります。  
  
タイムチャートを含むカスタムブックを作成する予定です。  
  
プロバイダーごとに1日あたりのセキュリティアラート数を特定するクエリを作成する必要があります。  
  
クエリはどのように完成させるべきですか？回答するには、回答エリアで適切なオプションを選択してください。  
  
注：正しい選択肢は1つにつき1ポイントです。  
  
![](https://img.examtopics.com/sc-200/image152.png)

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   3](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解:** ![](https://img.examtopics.com/sc-200/image153.png)

**解説:**
1. `bin` を選択する理由

「1日あたり」の統計を取得するためには、連続的な時間データ（`TimeGenerated`）を特定の時間枠（この場合は `1d`）にグループ化する必要があります。

- **bin**: 数値を指定されたサイズの倍数に切り捨てる関数で、時間のバケット化（グルーピング）に標準的に使用されます。
    
- **summarize count() by ProviderName, bin(TimeGenerated, 1d)** とすることで、プロバイダーごと・日ごとのカウントが可能になります。
    
- その他の `series_add` などの関数は、集計後の動的配列（シリーズ）を操作するためのものであり、ここでのグルーピングには適しません。
    

 2. `render` を選択する理由

クエリの結果を「タイムチャート」として視覚化するためには、結果セットをどのように表示するかを指定する演算子が必要です。

- **render**: グラフやチャートを描画するための演算子です。末尾に `timechart` が指定されているため、これと組み合わせて使用します。
    
- **materialize** は中間結果のキャッシュ、**project** は列の選択、**take** は行数の制限を行うためのもので、描画には関与しません。

質問#63 トピック3

Workspace1 という Microsoft Sentinel ワークスペースがあります。  
  
組み込みの統合型 ASIM パーサーから、組み込みのソース固有の Advanced Security Information Model (ASIM) パーサーを除外する必要があります。Workspace1  
  
には何を作成すればよいでしょうか？

- A. 解析規則
- B. ウォッチリスト
- C. ワークブック
- D. 狩猟に関する質問

[解決策を明らかにする](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#) [ソリューションを非表示](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)   [議論   12](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)

**正解：** B [🗳️](https://www.examtopics.com/exams/microsoft/sc-200/view/19/#)  

**解説:**
組み込みの統合ASIMパーサーから、特定のソース固有パーサーを除外するために作成するものです。
**「ウォッチリスト (Watchlist)」**: ASIMフレームワークでは、`ASim Disabled Parsers` という名前のウォッチリストを使用して、統合パーサーから除外したいパーサーを管理します。このリストに除外したいパーサー名とCallerContextを追加することで、クエリ変更なしに動作を制御できます。

*コミュニティ投票の配分*

B（94％）

6%

[以前の質問](https://www.examtopics.com/exams/microsoft/sc-200/view/18/)

![ファイル](https://www.examtopics.com/assets/images/file.svg) 41 ページ中 19 ページを表示しています。

410問中**181 - 190**問 を表示
