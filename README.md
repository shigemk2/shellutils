# shellutils

 * shell で作った便利ツール置き場

## インストール方法
 `sudo sh install.sh`
 上記を実行すると、bin ディレクトリ配下のスクリプトのシンボリックリンクが /usr/local/bin に作成されます。

## 使い方
### bkup
ファイルのバックアップを取る

 * `bkup [filename]` は `cp [filename] [filename].\`date '+%Y%m%d%H'\`` と同様の挙動。
 * 既に同名のバックアップファイルがある場合、[filename].\`date '+%Y%m%d%H'\`.[番号] でバックアップする。
 * -m で cp が mv になる。
 * -r で一番最後に取ったバックアップファイルを元に戻す。

### checkexec
外部ファイルにまとめたコマンドを1行ずつ確認しながら実行するスクリプト。

商用サーバで危険なコマンド群を実行するときに使えばいいと思う。

 * `checkexec [commandsFileName]`
 * 外部ファイルに定義した1行を1コマンドとして処理していく。
 * `#` で始まる行はコメントとして標準出力する。
 * コマンド確認時のyesに相当するキーは毎回ランダムで変更される。

### lockfile
ロックファイル制御スクリプト。

他のスクリプトから呼び出すことで、呼び出し元スクリプトのロックファイルを制御する。

 * `lockfile -c` でロックファイルの存在確認・ロックファイル作成。ロックファイルがあった場合にはexit.
 * `lockfile -r` でロックファイルを消去。

### ./src/shellUtils.sh
シェルスクリプトでバッチを書くときに使いそうな関数をまとめた。

利用したいシェルスクリプトの最初でこのファイルを読み込むこと。

詳細はソース参照。

 * ロギング関数
 * エラーハンドリング関数
 * ロックファイル制御関数


