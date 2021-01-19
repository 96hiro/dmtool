### ランサーズの営業DM自動化ツール

実行ファイル：Send_dm.py<br>
送信設定ファイル:Send_Config.csv<br>
送信履歴管理ファイル：Send_History.csv<br>

【仕様】
・送信するメッセージ文言はCSVで設定できる
・下記の様なURLをCSVなどで複数指定できる
  (https://www.lancers.jp/client_directory/all/industry/2147)
・１つのURL毎にDMを送信できる件数を設定できる
・クライアントのプロフィールの文言に所定の文字が含まれている場合のみ
　DMが送れるようにもできる（ただし、未指定で全てに対して送信も可能とする）
・重複してDMが送信されないように一度送信したクライアント名はCSVに控えておき
　次回以降は送信除外する。また投稿日時も、このCSVに出力する
・各ポイントでログを取り、ログファイルを作成する

【送信設定ファイルの設定方法】
・各カラム(指定URL,指定送信件数,指定文章,所定文言,)に対する値を1行ずつ設定してください。
　※このファイルのカラム行は固定です。順番の入れ替え等を行わないでください。
・上記カラムの【所定文言】以外は全て必須項目です。なお【所定文言】がBlankの場合は【所定文言】の設定無しと見なし、処理を行います。
【例】
 指定URL,指定送信件数,指定文章,所定文言,
 https://www.lancers.jp/client_dctory/all/industry/2138,21,はじめまして、〇〇と申します。突然のDM失礼いたします。,,
 https://www.lancers.jp/client_directory/all/industry/2138,21,はじめまして。はじめまして、〇〇と申します。突然のDM失礼いたします。,プログラミング,

 上記の例では、一行目の【所定文言】はBlankで、二行目の【所定文言】では、プログラミングと指定しています。

【実行方法】
・上記送信設定ファイルルに情報を入力後する
・Send_dm.pyから実行してください
・コンソール画面から,ランサーズへのログイン情報を入力してください
・Send_History.csvは初回実行時に自動的に生成されます。
