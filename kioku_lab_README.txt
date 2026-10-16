記憶ラボ v12.0 — PWA / ホーム画面追加対応セット

同梱ファイル
- index.html                 公開サイト用の入口
- kioku_lab_prototype.html    アプリ本体の別名コピー
- manifest.json              アプリ名・起動画面・アイコン設定
- sw.js                      キャッシュとオフライン時の起動を補助
- icon-192.png / icon-512.png ホーム画面アイコン
- .nojekyll                  GitHub Pagesで静的ファイルをそのまま公開するための設定
- kioku_lab_v12_CHANGELOG.txt 主な変更点

v12.0の主な変更
- 出題形式を「英語→日本語」「日本語→英語」「四択」に整理。古文単語・独自単語帳では、古文→現代語訳などの表示に切り替わります。
- 出題順は出題形式と別設定です。「復習優先順」「ランダム」を選択でき、設定は保存されます。
- 混同単語の比較モードを追加。現在の単語に近い候補を表示し、登録語を検索・複数選択して、訳・例文・追加情報を横並びで確認できます。
- 接頭語・語幹・接尾語の単語マップを追加。登録語を検索し、形の共通性や意味・綴りの近さから関連語を表示します。
- 「主張する・論じる」「言及する・述べる」「表現する」「苦情・不満を述べる」など、意味が広すぎる候補が同じグループになりにくいよう、内蔵の意味カテゴリを細分化しました。

ホーム画面に追加するには
注意：ダウンロードしたHTMLを直接開くだけでは、ChromeのPWAインストール条件を満たしません。HTTPSで公開してそのURLをChromeで開いてください。

Android Chromeでの公開例（GitHub Pages）
1. GitHubで新しいリポジトリを作ります。GitHub Pagesを使う無料プランでは公開リポジトリが必要になる場合があります。
2. ZIPを展開して、上記ファイルをリポジトリの一番上の階層にすべてアップロードします。
   学習データのJSONバックアップは絶対にアップロードしないでください。
3. リポジトリの Settings → Pages を開きます。
4. Build and deployment の Source を「Deploy from a branch」にします。
5. Branch を main、Folder を /(root) にして Save します。
6. 公開された https://<ユーザー名>.github.io/<リポジトリ名>/ をChromeで開きます。
7. Chromeの「︙」メニューから「アプリをインストール」または「ホーム画面に追加」を選びます。メニューの名称はChromeのバージョンにより異なる場合があります。

学習データについて
- ブラウザ内に保存されます。通常、このv12更新では同じURL・同じブラウザの保存データを同じキーで引き継ぎます。
- 古いアプリからHTTPS公開版へ移す場合、古いアプリの「データ」画面でJSONを書き出し、新しいHTTPS版で復元してください。URLが変わるとデータは自動では引き継がれません。
- JSONバックアップを公開リポジトリに入れないでください。
- Excel読み込みはSheetJS CDNを利用するため、Excel/CSV取込にはインターネット接続が必要になる場合があります。
- 端末間の自動クラウド同期はありません。

アルゴリズム上の注意
- 語構造マップは登録された綴りのパターンから接頭語・接尾語・語幹候補を機械的に推定します。語源を確定するものではなく、false positive / 見落としがあります。
- 意味グループも登録された訳と内蔵ルールに基づく候補です。比較前に意味・例文を確認してください。

GitHub公式手順
https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
