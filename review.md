# jQuery 10
## 修正内容

1. Inputが空白にボタンを押した時とボタンを連打した時の挙動ができていない。
    - if文を使用して、それぞれのエラー時のステータスコードを元に、作成しました。
    ```javascript
    function error(error) {
            if (error.status === 0) {
              $(".message").append(
                "<p>通信に失敗しました。インターネットの接続状態を確認してください。</p>"
              );
            } else if (error.status === 400) {
              $(".message").append("<p>検索文字が入力されていません。</p>");
            } else if (error.status === 429) {
              $(".message").append(
                "<p>リクエスト過多です。しばらく時間を置いてからお試しください。</p>"
              );
            }
    ```
2. `get（）`のメリットを教えてください。
    - URLにパラメーターをつけることで、保存と共有することができるようになる。