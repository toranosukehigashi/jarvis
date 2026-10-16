JARVIS ランチャー（ホーム画面アイコン用）
==========================================
Apps Script のWebアプリは、iPhoneのホーム画面アイコンを自由に設定できません。
このフォルダを公開すると、アークリアクターのアイコンで全画面起動できます。

■ 手順（GitHub Pages・無料）
1. GitHub にログイン →「New repository」→ 名前を jarvis などにして作成（Public）
2. 「Add file → Upload files」で、このフォルダの中身をすべてアップロード
   （index.html / manifest.json / icon.svg / favicon-32.png / apple-touch-icon.png / icon-192.png / icon-512.png）
3. index.html を開いて鉛筆アイコンで編集し、
   var APP_URL = '…'; の部分に Apps Script のウェブアプリURL（…/exec）を貼り付けて保存
4. Settings → Pages → Branch を「main」「/(root)」にして Save
5. 数分後に https://<ユーザー名>.github.io/jarvis/ が開けるようになります
6. iPhoneのSafariでそのURLを開く → 共有 →「ホーム画面に追加」

■ ブラウザのタブのファビコンも変える場合
GAS_JARVIS_v6.js の先頭付近
  var FAVICON_URL = '';
を
  var FAVICON_URL = 'https://<ユーザー名>.github.io/jarvis/favicon-32.png';
に変更 → 保存 →「新バージョン」で再デプロイ。

■ 注意
・Webアプリのデプロイ設定「アクセスできるユーザー」は「全員」にしてください（ランチャー内に表示するため）。
・ランチャーから開いた場合と、URLを直接開いた場合とでは、テーマ設定や途中の解答（端末保存分）が別々に保存されます。成績はどちらも同じスプレッドシートに記録されます。
