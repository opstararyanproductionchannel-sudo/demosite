
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<meta name="description" content="Aurum Lane: hand-finished 18K solitaires, made to order in Mumbai.">
<title>Aurum Lane</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Bodoni+Moda:ital,opsz,wght@0,6..96,400;0,6..96,500;1,6..96,400;1,6..96,500&family=Jost:wght@300;400;500&display=swap">
<style>
/* Concept: a dark bottle-green atelier. One 3D solitaire stays fixed behind the page; scroll directs the camera, the explode, and the metal. */
:root{
  --ink:#0a110e; --ink-rgb:10,17,14; --ink2:#111c17;
  --ivory:#f2ecdd; --mute:#aeb3a6; --gold:#d9b16a; --gold-soft:#b8914f;
  --line:rgba(242,236,221,.16);
  --display:'Bodoni Moda','Didot','Bodoni 72','Times New Roman',serif;
  --text:'Jost','Helvetica Neue',Arial,sans-serif;
  --h:160;
  color-scheme:dark;
}
*{box-sizing:border-box}
html{background:var(--ink)}
body{margin:0;position:relative;z-index:0;background:var(--ink);color:var(--ivory);font-family:var(--text);font-weight:300;font-size:17px;line-height:1.6;-webkit-font-smoothing:antialiased;overflow-x:hidden}
html.lenis,html.lenis body{height:auto}
.lenis.lenis-smooth{scroll-behavior:auto!important}
.lenis.lenis-stopped{overflow:hidden}
a{color:inherit;text-decoration:none}
button{font:inherit;color:inherit;cursor:pointer}
:focus-visible{outline:2px solid var(--gold);outline-offset:3px}

#bg{position:fixed;inset:0;z-index:-3;background:
  radial-gradient(70% 60% at 68% 42%,hsl(var(--h) 38% 15%) 0,transparent 70%),
  radial-gradient(60% 50% at 10% 100%,hsl(var(--h) 30% 9%) 0,transparent 70%),var(--ink)}
#gl{position:fixed;inset:0;width:100%;height:100%;z-index:-2;display:block}
.nogl #gl{display:none}

/* header */
.top{position:fixed;left:0;right:0;top:0;z-index:20;display:flex;justify-content:space-between;align-items:center;
  padding:calc(18px + env(safe-area-inset-top,0px)) max(16px,env(safe-area-inset-right,0px)) 18px max(16px,env(safe-area-inset-left,0px));pointer-events:none}
.top>*{pointer-events:auto}
.top::before{content:"";position:absolute;inset:0 0 -34px;background:linear-gradient(rgba(var(--ink-rgb),.82),rgba(var(--ink-rgb),0));z-index:-1;pointer-events:none}
.logo{font-family:var(--display);font-size:21px;letter-spacing:.22em;text-transform:uppercase;font-weight:500}
.top .mini{font-size:12px;letter-spacing:.2em;text-transform:uppercase;color:var(--mute);display:flex;gap:10px;align-items:center}
.top .mini i{width:6px;height:6px;border-radius:50%;background:var(--gold);display:inline-block}
.rail{position:fixed;right:max(10px,env(safe-area-inset-right,0px));top:50%;height:120px;width:2px;margin-top:-60px;background:var(--line);z-index:20;border-radius:2px;overflow:hidden}
.rail b{display:block;width:100%;height:100%;background:var(--gold);transform-origin:top;transform:scaleY(0)}
.wa{position:fixed;z-index:30;right:max(16px,env(safe-area-inset-right,0px));bottom:calc(16px + env(safe-area-inset-bottom,0px));
  display:flex;gap:10px;align-items:center;padding:13px 20px;border-radius:999px;background:var(--gold);color:#1a130a;font-weight:500;font-size:14px;letter-spacing:.06em;box-shadow:0 10px 34px rgba(0,0,0,.45)}
.wa svg{width:18px;height:18px}

/* layout */
.wrap{width:100%;max-width:1280px;margin:0 auto;padding-left:max(16px,env(safe-area-inset-left,0px));padding-right:max(16px,env(safe-area-inset-right,0px))}
.sec{position:relative}
.full{min-height:100vh;min-height:100svh;display:flex;align-items:center}
.stick{position:sticky;top:0;height:100vh;height:100svh;display:flex;align-items:center}
.col{max-width:520px;min-width:0}
.col.r{margin-left:auto}
.eyebrow{font-size:12px;letter-spacing:.28em;text-transform:uppercase;color:var(--gold);margin:0 0 22px;display:flex;align-items:center;gap:14px}
.eyebrow::before{content:"";width:36px;height:1px;background:var(--gold)}
h1,h2{font-family:var(--display);font-weight:400;line-height:1.02;letter-spacing:-.015em;margin:0 0 26px;text-wrap:balance}
h1{font-size:clamp(46px,8vw,116px)}
h2{font-size:clamp(36px,5.4vw,76px)}
h1 em,h2 em{font-style:italic;color:var(--gold)}
.lead{color:var(--mute);font-size:clamp(16px,1.5vw,19px);max-width:46ch;margin:0 0 34px}
.w{display:inline-block;overflow:hidden;vertical-align:top;padding-bottom:.14em;margin-bottom:-.14em}
.wi{display:inline-block}

.btns{display:flex;flex-wrap:wrap;gap:14px;align-items:center}
.btn{display:inline-flex;align-items:center;gap:12px;padding:16px 28px;border-radius:999px;border:1px solid var(--gold);background:var(--gold);color:#1a130a;font-size:14px;letter-spacing:.12em;text-transform:uppercase;font-weight:500;transition:background .3s,color .3s,transform .3s}
.btn.ghost{background:transparent;color:var(--ivory);border-color:var(--line)}
.btn:hover{background:var(--ivory);border-color:var(--ivory);color:#1a130a}
.btn.ghost:hover{background:transparent;border-color:var(--gold);color:var(--gold)}
.ticks{display:flex;gap:28px;flex-wrap:wrap;margin-top:56px;font-size:12px;letter-spacing:.2em;text-transform:uppercase;color:var(--mute)}
.ticks span{display:flex;gap:10px;align-items:center}
.ticks span::before{content:"";width:5px;height:5px;transform:rotate(45deg);background:var(--gold)}

.hero .mark{position:absolute;left:0;right:0;bottom:6vh;text-align:center;font-family:var(--display);font-size:clamp(80px,22vw,340px);letter-spacing:.06em;color:transparent;-webkit-text-stroke:1px rgba(242,236,221,.07);line-height:1;pointer-events:none;white-space:nowrap;overflow:hidden}
.cue{position:absolute;left:max(16px,env(safe-area-inset-left,0px));bottom:calc(28px + env(safe-area-inset-bottom,0px));font-size:11px;letter-spacing:.3em;text-transform:uppercase;color:var(--mute);display:flex;align-items:center;gap:14px}
.cue i{width:1px;height:46px;background:linear-gradient(var(--gold),transparent);display:block;animation:cue 2.2s ease-in-out infinite;transform-origin:top}
@keyframes cue{0%{transform:scaleY(0)}50%{transform:scaleY(1)}100%{transform:scaleY(1);opacity:0}}

dl.spec{display:grid;grid-template-columns:auto 1fr;gap:0;margin:34px 0 0;border-top:1px solid var(--line)}
dl.spec dt,dl.spec dd{margin:0;padding:15px 0;border-bottom:1px solid var(--line)}
dl.spec dt{font-size:12px;letter-spacing:.22em;text-transform:uppercase;color:var(--mute);padding-right:28px}
dl.spec dd{font-family:var(--display);font-size:20px}

.story{height:190vh;height:190svh}
.anat{height:260vh;height:260svh}
.parts{list-style:none;margin:34px 0 0;padding:0}
.parts li{display:grid;grid-template-columns:22px 1fr;gap:6px 14px;padding:16px 0;border-top:1px solid var(--line);opacity:.4;transition:opacity .5s}
.parts li.on{opacity:1}
.parts li:last-child{border-bottom:1px solid var(--line)}
.parts li::before{content:"";width:9px;height:9px;transform:rotate(45deg);border:1px solid var(--gold);margin-top:9px;transition:background .4s}
.parts li.on::before{background:var(--gold)}
.parts b{font-family:var(--display);font-weight:400;font-size:22px}
.parts span{grid-column:2;color:var(--mute);font-size:15px;line-height:1.5}

.coll{height:420vh;height:420svh}
.coll .stick{flex-direction:column;align-items:stretch;justify-content:space-between;padding-top:calc(96px + env(safe-area-inset-top,0px));padding-bottom:calc(7vh + env(safe-area-inset-bottom,0px))}
.coll .head{display:flex;justify-content:space-between;align-items:flex-end;gap:20px;flex-wrap:wrap}
.coll h2{font-size:clamp(30px,4vw,56px);margin:0}
.coll .hint{font-size:12px;letter-spacing:.24em;text-transform:uppercase;color:var(--mute)}
.track{display:flex;gap:22px;will-change:transform;width:max-content}
.card{flex:0 0 auto;width:min(80vw,380px);padding:26px 28px;border:1px solid var(--line);background:rgba(var(--ink-rgb),.62);backdrop-filter:blur(10px);-webkit-backdrop-filter:blur(10px);border-radius:4px;opacity:.45;transform:scale(.94);transition:opacity .5s,transform .5s,border-color .5s;will-change:transform}
.card.on{opacity:1;transform:scale(1);border-color:var(--gold-soft)}
.card .m{font-size:11px;letter-spacing:.26em;text-transform:uppercase;color:var(--gold)}
.card h3{font-family:var(--display);font-weight:400;font-size:34px;margin:8px 0 4px;line-height:1.1}
.card p{margin:0 0 18px;color:var(--mute);font-size:14.5px}
.card .row{display:flex;justify-content:space-between;align-items:center;gap:14px;border-top:1px solid var(--line);padding-top:16px}
.card .pr{font-family:var(--display);font-size:24px;font-variant-numeric:tabular-nums}
.card a{font-size:12px;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);border-bottom:1px solid var(--gold-soft);padding-bottom:2px}

.promise{padding:18vh 0}
.grid4{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:0;margin-top:34px;max-width:660px;border-top:1px solid var(--line);border-left:1px solid var(--line)}
.grid4>div{padding:28px 26px;border-right:1px solid var(--line);border-bottom:1px solid var(--line);min-width:0}
.grid4 .n{font-family:var(--display);font-size:clamp(34px,4vw,52px);color:var(--gold);line-height:1;font-variant-numeric:tabular-nums}
.grid4 h4{margin:12px 0 4px;font-weight:500;font-size:13px;letter-spacing:.18em;text-transform:uppercase}
.grid4 p{margin:0;color:var(--mute);font-size:14.5px;line-height:1.5}

.cta .inner{padding-top:calc(48vh);padding-bottom:40px}
.chips{display:flex;flex-wrap:wrap;gap:10px;margin:0 0 14px}
.chips .lab{flex:0 0 100%;font-size:11px;letter-spacing:.26em;text-transform:uppercase;color:var(--mute);margin-top:12px}
.chip{padding:11px 20px;border-radius:999px;border:1px solid var(--line);background:rgba(var(--ink-rgb),.5);font-size:14px;transition:all .3s}
.chip[aria-pressed="true"]{background:var(--gold);color:#1a130a;border-color:var(--gold)}
.chip .sw{display:inline-block;width:10px;height:10px;border-radius:50%;margin-right:9px;vertical-align:-1px}
.sum{font-family:var(--display);font-size:clamp(22px,2.6vw,32px);margin:26px 0 28px;font-variant-numeric:tabular-nums}
.sum small{display:block;font-family:var(--text);font-size:12px;letter-spacing:.2em;text-transform:uppercase;color:var(--mute);margin-bottom:6px}
.num{color:var(--mute);font-size:14px;margin-top:18px}
.num b{color:var(--ivory);font-weight:400;user-select:all}
footer{margin-top:90px;padding-top:26px;border-top:1px solid var(--line);display:flex;flex-wrap:wrap;gap:12px 40px;justify-content:space-between;color:var(--mute);font-size:13px;letter-spacing:.04em}
footer .logo{font-size:16px;color:var(--ivory)}

.cur{position:fixed;left:0;top:0;width:36px;height:36px;margin:-18px 0 0 -18px;border:1px solid var(--gold);border-radius:50%;z-index:50;pointer-events:none;opacity:0;transition:width .3s,height .3s,margin .3s,background .3s,opacity .3s}
.cur.big{width:70px;height:70px;margin:-35px 0 0 -35px;background:rgba(217,177,106,.12)}
@media (pointer:fine){.cur.show{opacity:.9}}
#loader{position:fixed;inset:0;z-index:100;background:var(--ink);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:22px}
#loader .logo{font-size:26px}
#loader .bar{width:160px;height:1px;background:var(--line);position:relative;overflow:hidden}
#loader .bar b{position:absolute;inset:0;background:var(--gold);transform:scaleX(0);transform-origin:left}
#loader small{font-size:11px;letter-spacing:.3em;color:var(--mute);font-variant-numeric:tabular-nums}

@media (max-aspect-ratio:9/10){
  body{font-size:16px}
  .full,.promise{align-items:flex-end}
  .col,.col.r{max-width:none;margin-left:0}
  .sec .scrim{background:linear-gradient(to top,rgba(var(--ink-rgb),.94) 0,rgba(var(--ink-rgb),.82) 55%,rgba(var(--ink-rgb),0) 100%);padding:70px 0 8vh}
  .stick{align-items:flex-end}
  .stick .scrim{padding-bottom:calc(5vh + env(safe-area-inset-bottom,0px))}
  .top .mini{display:none}
  .ticks{margin-top:34px;gap:10px 22px}
  .cue{display:none}
  .hero .mark{bottom:auto;top:14vh}
  .cta .inner{padding-top:34vh}
  .coll .stick{padding-top:calc(78px + env(safe-area-inset-top,0px))}
  .grid4>div{padding:20px 16px}
  .wa span{display:none}
  .wa{padding:14px}
  .pa
