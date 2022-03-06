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

