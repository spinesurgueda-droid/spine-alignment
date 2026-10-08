# Spine Align 脊椎アライメント計測

X線画像をタップして脊椎アライメントパラメータ（約90項目）を計測し、患者ごとに術前・術後の推移を記録するWebアプリです。
患者データはそれぞれの端末内にだけ保存され、このサイト（GitHub）には送信されません。

## ファイル構成

| ファイル | 役割 |
|---|---|
| index.html | アプリ本体 |
| manifest.webmanifest | ホーム画面に追加したときの名前・アイコンの設定 |
| sw.js | オフラインでも起動できるようにする仕組み |
| icon-180.png / icon-192.png / icon-512.png | ホーム画面のアイコン |

## 公開手順（初回のみ・約30分）

PCのブラウザで行うのが簡単です（iPhoneのSafariでも可能）。

1. **アカウント作成**：https://github.com で「Sign up」。メールアドレス・パスワード・ユーザー名を登録します（ユーザー名はURLの一部になります）。
2. **保管場所（リポジトリ）を作る**：右上の「＋」→「New repository」
   - Repository name：`spine-align`
   - 「Public」を選択（無料プランで公開するには Public が必要。公開されるのはプログラムだけで、患者データは含まれません）
   - 「Create repository」を押す
3. **ファイルをアップロード**：作成直後の画面の「uploading an existing file」をクリック
   - このフォルダの7ファイル（index.html, manifest.webmanifest, sw.js, icon-180.png, icon-192.png, icon-512.png, README.md）をまとめてドラッグ＆ドロップ
   - iPhoneの場合は「choose your files」から「ファイル」アプリ内の保存場所を開き、全ファイルを選択
   - 下の「Commit changes」を押す
4. **公開をオンにする**：リポジトリ上部の「Settings」→ 左メニュー「Pages」
   - 「Build and deployment」の Source：「Deploy from a branch」
   - Branch：「main」と「/(root)」を選び「Save」
   - 1〜3分待ってページを再読み込みすると、上部に `https://spinesurgueda-droid.github.io/spine-alignment/` と表示されます
5. **iPhoneに入れる**：iPhoneの **Safari** でhttps://spinesurgueda-droid.github.io/spine-alignment/を開く →「共有」ボタン →「ホーム画面に追加」→「追加」
6. 以後は**必ずホーム画面のアイコンから**起動してください（Safariのタブで開いた場合とはデータの保存場所が別になります）。

## Claude 上の旧版からデータを移す

1. 旧版（Claude のリンク）で「患者・測定日」→「画像を含めて保存」→ iPhone の「ファイル」に保存
2. 新しいアプリ（ホーム画面のアイコン）で「患者・測定日」→「バックアップから復元」→ 保存したファイルを選択

## アプリを更新するとき

1. 新しい `index.html` を受け取る
2. GitHub のリポジトリ画面で「Add file」→「Upload files」→ 新しい `index.html` をアップロード →「Commit changes」（同じ名前のファイルは上書きされます）
3. 1〜3分後、iPhoneでアプリを開き直すと新しい版になります（反映されないときは一度アプリを完全に閉じて再起動）

患者データは端末に残るため、更新しても消えません。

## データ管理の注意

- 患者IDは実名ではなく、院内IDや匿名化コードの使用を推奨します。
- データはこの iPhone の中だけにあります。iPhone の紛失・初期化・アプリの削除（ホーム画面から削除）で失われます。**定期的に「画像を含めて保存」でバックアップを iCloud Drive などに保存してください。**
- iPhone には Face ID／パスコードを設定してください。
- 研究・教育用の計測補助ツールです。診断は画像と臨床所見に基づき医師が行ってください。
