# :custard:Cloud9でよく使うコマンド:custard:

* `Tab`インデント後ろに下げる。
* `Sift+Tab`で選択した行をまとめてインデントつける
* `ctl+@` インデント字上げ
* `save!`でsaveできなかった時の挙動の確認をする。エラー画面にヒントがあるかも
* `command+z`ひとつ前に戻る &emsp; ターミナル上で使うと処理を一時停止する
* `command+Y`一つ進む
* `command+F`検索（主に全角スペースの検索）
* `command+R`リロード
* `command+?`選択した部分をコメントアウト
* `command+A`全選択
* `command+F`検索（主に全角スペースの検索）
---

# :crown:ER図について:doughnut:
* FKがつくのは1対多の多のほう。
* ER図は日本語で記載

---
# :hearts:GitHubに関して:spades:
* `git add -A`→`git commit -m "[hoge]"`→`git push origin ブランチ名`
* 　ローカルとリモートが違うよって言われたら
  `git fetch`→`git rebase origin/ブランチ名`
---
# :violin:Bootstrapについて:musical_keyboard:
### メディアクエリって…？
* 画面サイズによって色を変えることができる。


---
# AWSについて
* EC2で仮想サーバーを作ることができる
### 仮想サーバーって？？
* ハードウェアに複数のサーバーを構築できる環境のこと。物理サーバーはハードウェア1個に対して1個のサーバー
### EC2について　2022/03/02
* 質問したこと　　undle exec rails db:migrate RAILS_ENV=production実行後にエラー　→原因：マスターユーザー名が間違っていた。
　直し方<br>前提：envファイルは機密情報なのでgithub上にはpushされないのでcloneし直そうとしても無駄。<br>このためアプリのディレクトリに移動して、直接直す。<br>`sudo vi .env`→aで直接入力モード→escで閲覧モードに。
---
# クラスメソッドインスタンスメソッド
* そもそもクラスとは？→設計図のようなもの　　インスタンスとは？→設計図から作成される物
* ex)1-1クラスには生徒がたくさんいる。User.all.nameとしたところで誰に呼びかけているかわからない。
---
## 20220308 質問したこと
* created_at カラムの検索ができない。　→原因：　date_select タグを使うと"date(1i)"=>"2013", "date(2i)"=>"1", "date(3i)"=>"1",のようにデータが取り出される。だから、ひとつずつ変数に入れてあげなければならない。そして、今回は日付順で並び替えたいので、さらにTimeオブジェクトにしてインスタンス変数に代入。
* また、その月中のデータを取りたいので、「インスタンス変数.beginning_of_month..インスタンス変数.end_of_month」とすると解決
## 20220309 質問したこと
* nilと””の違いは？？　nilは空のデータという意味ではない。nilはnilclassというデータ型。classはポケ○ンでいうタイプのこと。ちなむと、ターミナルで.classって調べると、データ型調べられるから見てみるといいかも。
* railsに生のSQL文を書くときは**どのテーブルのどのカラム**からデータを取ってくるのかきちんと書いてあげる。
* ダメな例.order('count(:user_id) desc')カラムしか指定してないからNG
## 20220310
* お気に入りした記事を簡単に一覧にする方法
モデルにアソシエーションを追加する　has_many :thanks_projects, through: :thanks,source: :project

## 20220320
#### デプロイ環境のfullcalendarで苦労した。
* 開発環境でyarnでフルカレンダーを導入したが、デプロイ環境でレイアウトが崩れた→linkタグでフルカレンダーのスタイルシートを導入して解決。
* フォントオーサムはwebパッカーに入れない
* ターボリンクスが悪さをしてカレンダーが表示されなかった→ターボリンクを無効にした。そして現場でも消してる場合が多いらしい

## 20220321
* fullcalendarで定期処理をしたかった。→フルカレンダーのrrleライブラリを使ってみるも、バージョン違いで使えず。他の方法を模索。ライブラリを使用する時はそのライブラリをgithub上で調べて、どれくらいの人が使っているかを確認してから使う。
* デプロイ環境でseedファイルを反映させるためには bundle exec rails db:seed RAILS_ENV=production
* テスト仕様書に関して。検索項目に関しては、全部を場合分けする必要はない。
* デプロイ環境の差分自動化ができなかった原因はブランチ名にアプリケーション名を入れていたから。
## 20220403
* APIが動かない原因の特定の仕方→①本番環境にpullできているか②再起動してみるkill プロセスID　　pumaを切る
* ちなみにviですぐ下に行きたい時は「o」押すとすぐ入力できる
* logファイルに移動→ps_aux プロセスごとに一覧が見られる
* kill プロセスID
* rails s -e production で再起動する
* 現場ではクレデンシャルズ？のほうが主流。調べること



配列を確認する時はincludes？を使う。アクティブレコードではexsist?

## 20220421ポートフォリオのレビューが返ってくる。以下指摘された改善点
1. （解決済み）URLを直接打つと編集者以外もアクセスできる<br>
→コントローラーに`before_action :ensure_correct_member, only: [:edit, :update]　`を定義して解決
2. (解決済み)ja.ymlファイルにmemberモデルのカラムの日本語名が記載されておらず、英語で表示される。
→ja.ymlファイルに追記して解決。
3. （解決済み）ラジオボタンをラベルでもクリックできるようにする
→labelにvalue: :oneを設定して解決　　
4.　（解決済み）プロフィール画像の縦横比を保って表示する
→imgにクラスを指定してcssで大きさとobject-fit: cover;を指定して解決　　

5.　コメントに日時を入れる

6.　管理者側でイベント登録をできるようにする
　


