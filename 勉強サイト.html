<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>勉強サイト</title>
<style>
:root{
  box-sizing:border-box;
  padding-top:env(safe-area-inset-top,0px);
  padding-bottom:env(safe-area-inset-bottom,0px);
  --bg:#ffffff; --text:#1a1a1a; --muted:#6b6b6b; --line:#dcdcdc;
  --btn:#1a1a1a; --btn-text:#ffffff; --err:#b3261e; --stage:#f3f3f3;
  color-scheme:light;
}
@media (prefers-color-scheme:dark){
  :root:not([data-theme="light"]){
    --bg:#141414; --text:#f0f0f0; --muted:#9a9a9a; --line:#333333;
    --btn:#f0f0f0; --btn-text:#141414; --err:#ff8a80; --stage:#1e1e1e;
    color-scheme:dark;
  }
}
:root[data-theme="dark"]{
  --bg:#141414; --text:#f0f0f0; --muted:#9a9a9a; --line:#333333;
  --btn:#f0f0f0; --btn-text:#141414; --err:#ff8a80; --stage:#1e1e1e;
  color-scheme:dark;
}
html{height:100%;scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box}
body{
  margin:0;min-height:100%;background:var(--bg);color:var(--text);
  font-family:"Hiragino Sans","Yu Gothic","Noto Sans JP",system-ui,sans-serif;
  line-height:1.7;
}
[hidden]{display:none!important}

/* パスワード画面 */
#gate{min-height:100vh;display:grid;place-items:center;padding:24px}
.gate-box{width:100%;max-width:340px;text-align:center}
h1{font-size:22px;margin:0 0 24px}
input{
  width:100%;padding:12px 14px;font-size:16px;border-radius:8px;
  border:1px solid var(--line);background:var(--bg);color:var(--text);
}
input:focus{outline:2px solid var(--text);outline-offset:1px}
button{
  width:100%;margin-top:12px;padding:12px;font-size:16px;
  border:0;border-radius:8px;background:var(--btn);color:var(--btn-text);cursor:pointer;
}
button:hover{opacity:.85}
.msg{min-height:1.5em;margin:12px 0 0;font-size:14px;color:var(--err)}
.shake{animation:shake .35s}
@keyframes shake{25%{transform:translateX(-8px)}75%{transform:translateX(8px)}}

/* ゲーム画面 */
#site{max-width:960px;margin:0 auto;padding:20px 16px 40px}
header{display:flex;justify-content:space-between;align-items:center;margin-bottom:16px}
header h2{margin:0;font-size:20px}
.link{background:none;color:var(--muted);width:auto;margin:0;padding:6px 12px;font-size:13px;border:1px solid var(--line)}
.stage{
  position:relative;width:100%;aspect-ratio:16/9;border-radius:8px;overflow:hidden;
  background:var(--stage);border:1px solid var(--line);
  display:grid;place-items:center;color:var(--muted);font-size:14px;text-align:center;
}
.stage iframe{position:absolute;inset:0;width:100%;height:100%;border:0}
</style>
</head>
<body>

<main id="gate">
  <div class="gate-box" id="box">
    <h1>パスワードを入力</h1>
    <input id="pass" type="password" placeholder="パスワード" autocomplete="off" aria-label="パスワード">
    <button id="enter" type="button">入る</button>
    <p class="msg" id="msg" role="alert"></p>
  </div>
</main>

<div id="site" hidden>
  <header>
    <h2>勉強サイト</h2>
    <button class="link" id="out" type="button">ログアウト</button>
  </header>

  <div class="stage" id="stage">
    <!-- Unity の WebGL ビルドを入れたら、下の p を消して、この行のコメントを外す:
    <iframe src="game/index.html" allowfullscreen></iframe>
    -->
    <p>ここに Unity のゲームが表示されます</p>
  </div>
</div>

<script>
// パスワードの「ハッシュ値」です(パスワードそのものは書いていません)。
// 今のパスワードは「cardgame」です。変えるときは、ブラウザの開発者ツール(コンソール)で
// 次の1行を実行し、出てきた文字列を下の PASS_HASH に貼り付けてください:
// crypto.subtle.digest("SHA-256", new TextEncoder().encode("新しいパスワード")).then(b=>console.log([...new Uint8Array(b)].map(x=>x.toString(16).padStart(2,"0")).join("")))
const PASS_HASH = "7d224b2268ac6f251abf62c4c263b0ed44b6cc6f4e6cb3425af60430e0408d18";
const KEY = "unlocked-v1";

const $ = id => document.getElementById(id);

async function sha256(text){
  const buf = await crypto.subtle.digest("SHA-256", new TextEncoder().encode(text));
  return [...new Uint8Array(buf)].map(b => b.toString(16).padStart(2, "0")).join("");
}

function show(unlocked){
  $("gate").hidden = unlocked;
  $("site").hidden = !unlocked;
}

async function tryEnter(){
  const value = $("pass").value.trim();
  if(!value) return;
  let ok = false;
  try { ok = (await sha256(value)) === PASS_HASH; } catch(e) { ok = false; }
  if(ok){
    try { sessionStorage.setItem(KEY, "1"); } catch(e) {}
    $("pass").value = "";
    show(true);
  } else {
    $("msg").textContent = "パスワードが違います。";
    const box = $("box");
    box.classList.remove("shake"); void box.offsetWidth; box.classList.add("shake");
    $("pass").select();
  }
}

$("enter").addEventListener("click", tryEnter);
$("pass").addEventListener("keydown", e => { if(e.key === "Enter") tryEnter(); });
$("out").addEventListener("click", () => {
  try { sessionStorage.removeItem(KEY); } catch(e) {}
  $("msg").textContent = "";
  show(false);
});

let saved = null;
try { saved = sessionStorage.getItem(KEY); } catch(e) {}
show(saved === "1");
</script>
</body>
</html>
