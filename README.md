<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no"/>
<title>MagicHerbs — Каталог</title>
<script src="https://telegram.org/js/telegram-web-app.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Playfair+Display:ital,wght@0,600;0,700;1,600&family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<link rel="icon" type="image/png" href="https://i.postimg.cc/7Z1VJ4jx/22109625-d753-4c25-8ab6-c36ff9ab9cff-Photoroom.png">
<style>
:root {
  --bg:#F5F7F3;
  --surface:#FFFFFF;
  --ink:#1A2420;
  --ink-soft:#46524C;
  --hint:#8B958F;
  --line:rgba(26,36,32,0.09);
  --line-strong:rgba(26,36,32,0.15);
  --pine:#2E4A35;
  --pine-deep:#1E3326;
  --pine-soft:rgba(46,74,53,0.10);
  --amber:#C8954B;
  --amber-deep:#A97A36;
  --amber-bg:rgba(200,149,75,0.11);
  --bark:#8B5E3C;
  --danger:#C0473B;
  --danger-bg:rgba(192,71,59,0.08);
  --shadow:0 4px 16px rgba(26,36,32,0.07);
  --shadow-lg:0 12px 32px rgba(26,36,32,0.13);
  --radius:18px;
}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent;margin:0;padding:0;}
html,body{min-height:100vh;}
body{
  background-color:var(--bg);
  background-image:url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="300" height="300" viewBox="0 0 300 300"><g fill="none" stroke="%232E4A35" stroke-width="1.1" opacity="0.08"><ellipse cx="30" cy="54" rx="10" ry="16"/><path d="M21 42 Q30 47 39 42"/><path d="M20 48 Q30 53 40 48"/><path d="M20 54 Q30 59 40 54"/><path d="M21 60 Q30 65 39 60"/><path d="M23 66 Q30 70 37 66"/><path d="M27 70 Q30 72 33 70"/><line x1="30" y1="36" x2="30" y2="38"/></g><g fill="none" stroke="%232E4A35" stroke-width="1.1" opacity="0.065"><path d="M148 65 Q146 42 148 28"/><path d="M148 55 Q138 48 132 42"/><path d="M148 50 Q158 43 164 38"/><path d="M148 45 Q140 36 136 28"/><path d="M148 42 Q156 35 162 28"/></g><g fill="none" stroke="%232E4A35" stroke-width="1" opacity="0.07"><ellipse cx="225" cy="45" rx="5" ry="7"/><path d="M225 38 L225 30"/><ellipse cx="240" cy="55" rx="4" ry="6"/><path d="M240 49 L240 42"/><ellipse cx="212" cy="58" rx="4" ry="5.5"/><path d="M212 53 L212 46"/></g><g fill="none" stroke="%232E4A35" stroke-width="1.1" opacity="0.08"><ellipse cx="78" cy="200" rx="7" ry="11"/><path d="M71 191 Q78 195 85 191"/><path d="M70 196 Q78 200 86 196"/><path d="M71 201 Q78 205 85 201"/><path d="M72 206 Q78 209 84 206"/><path d="M74 210 Q78 212 82 210"/><line x1="78" y1="186" x2="78" y2="189"/></g><g fill="none" stroke="%232E4A35" stroke-width="1" opacity="0.065"><path d="M60 150 L92 154"/><path d="M64 150 L60 142 M64 150 L70 140 M70 151 L68 143 M70 151 L76 142 M76 152 L74 144 M76 152 L82 143 M82 153 L84 146"/></g><g fill="none" stroke="%232E4A35" stroke-width="1.1" opacity="0.07"><ellipse cx="200" cy="195" rx="9" ry="13"/><path d="M192 184 Q200 188 208 184"/><path d="M191 190 Q200 194 209 190"/><path d="M192 196 Q200 200 208 196"/><path d="M193 202 Q200 205 207 202"/><path d="M195 207 Q200 209 205 207"/><line x1="200" y1="180" x2="200" y2="182"/></g><g fill="none" stroke="%232E4A35" stroke-width="1" opacity="0.065"><ellipse cx="270" cy="170" rx="5" ry="7"/><path d="M270 163 L270 155"/><ellipse cx="255" cy="185" rx="4" ry="6"/><path d="M255 179 L255 172"/></g><g fill="none" stroke="%232E4A35" stroke-width="1" opacity="0.06"><path d="M140 220 Q138 200 140 185"/><path d="M140 210 Q130 203 125 196"/><path d="M140 205 Q150 198 156 192"/></g></svg>');
  background-repeat:repeat;
  background-size:300px 300px;
  font-family:'Inter',system-ui,sans-serif;
  color:var(--ink);
  -webkit-font-smoothing:antialiased;
  position:relative;
}
.serif{font-family:'Playfair Display',Georgia,serif;}
.bebas{font-family:'Bebas Neue',sans-serif;letter-spacing:.05em;}
button{font-family:'Inter',system-ui,sans-serif;cursor:pointer;border:none;background:none;}
svg{display:block;flex-shrink:0;}
::selection{background:rgba(46,74,53,0.15);color:var(--ink);}
a{color:inherit;text-decoration:none;}
img{display:block;}
#app{padding-bottom:72px;position:relative;}

/* ===================== ВОЛНЫ СВЕРХУ И СНИЗУ ===================== */
.wave-top,
.wave-bottom {
  position: relative;
  width: 100%;
  height: 40px;
  overflow: hidden;
  pointer-events: none;
  color: var(--pine-deep);
}
.wave-top {
  margin-top: -1px;
}
.wave-bottom {
  margin-bottom: 72px;
}
.wave-top svg,
.wave-bottom svg {
  width: 100%;
  height: 100%;
  display: block;
}
.wave-top svg path,
.wave-bottom svg path {
  fill: currentColor;
  opacity: 0.92;
}
.wave-top--gradient svg path,
.wave-bottom--gradient svg path {
  fill: url(#waveGradientTop);
  opacity: 1;
}

/* ===================== ОСНОВНЫЕ СТИЛИ ===================== */
.screen{display:none;}
.screen.active{display:block;animation:screenIn .4s cubic-bezier(.22,1,.36,1);}
@keyframes screenIn{from{opacity:0;transform:translateY(6px);}to{opacity:1;transform:translateY(0);}}
@keyframes popIn{from{transform:scale(0.5);opacity:0;}70%{transform:scale(1.04);}to{transform:scale(1);opacity:1;}}
@keyframes cardIn{from{opacity:0;transform:translateY(14px);}to{opacity:1;transform:translateY(0);}}
@keyframes navCircle{from{opacity:0;transform:translate(-50%,-50%) scale(0.4);}to{opacity:1;transform:translate(-50%,-50%) scale(1);}}
.topbar{
  display:flex;align-items:center;justify-content:space-between;
  padding:10px 16px 8px;
  background:var(--pine-deep);
  position:sticky;top:0;z-index:30;
  backdrop-filter:blur(12px);
  -webkit-backdrop-filter:blur(12px);
  box-shadow:0 4px 18px rgba(30,51,38,0.30);
}
.topbar-left{display:flex;align-items:center;gap:10px;}
.logo-mark{
  width:44px;height:44px;
  display:flex;align-items:center;justify-content:center;
  flex-shrink:0;
  background:transparent !important;
  border:none !important;
  box-shadow:none !important;
  border-radius:0 !important;
}
.logo-mark img{width:44px;height:44px;object-fit:contain;border-radius:0;background:transparent;}
.topbar-right{display:flex;align-items:center;gap:8px;}
.icon-btn{
  width:36px;height:36px;border-radius:50%;
  border:1.5px solid rgba(255,255,255,0.20);
  background:rgba(255,255,255,0.10);
  box-shadow:0 2px 8px rgba(0,0,0,0.15);
  display:flex;align-items:center;justify-content:center;
  color:#fff;
  position:relative;
  transition:transform .25s cubic-bezier(.34,1.56,.64,1),box-shadow .2s ease,background .2s ease;
}
.icon-btn:active{transform:scale(0.85);}
.icon-btn:hover{box-shadow:0 6px 18px rgba(0,0,0,0.25);background:rgba(255,255,255,0.22);}
.icon-btn .dot{
  position:absolute;top:-4px;right:-4px;
  min-width:17px;height:17px;padding:0 4px;
  border-radius:9px;
  background:var(--amber);
  color:#fff;font-size:9.5px;font-weight:700;
  display:flex;align-items:center;justify-content:center;
  border:2px solid var(--pine-deep);
}
.hdr{padding:20px 20px 12px;text-align:center;}
.eyebrow{
  font-size:10px;letter-spacing:.2em;text-transform:uppercase;
  color:var(--amber-deep);margin:0 0 8px;font-weight:600;
  font-family:'Inter',sans-serif;
}
.hdr h1{
  font-family:'Bebas Neue','Playfair Display',Georgia,serif;
  margin:0 0 6px;font-size:28px;font-weight:700;color:var(--pine-deep);line-height:1.12;
  letter-spacing:-.02em;
}
.hdr p{
  font-size:13px;color:var(--ink-soft);line-height:1.55;margin:0;
  font-family:'Inter',sans-serif;font-weight:400;
}
.search-wrap{padding:4px 16px 10px;}
.search-box{
  display:flex;align-items:center;gap:10px;
  background:var(--surface);
  border:1.5px solid var(--line);
  border-radius:14px;
  padding:10px 14px;
  box-shadow:var(--shadow);
  transition:border-color .18s ease,box-shadow .18s ease;
}
.search-box.focused{border-color:var(--pine);box-shadow:0 0 0 3px rgba(61,90,69,0.10);}
.search-box svg{color:var(--hint);}
.search-box input{
  flex:1;border:none;background:transparent;outline:none;
  font-family:'Inter',sans-serif;
  font-size:14px;color:var(--ink);
}
.search-box input::placeholder{color:var(--hint);}
.search-clear{border:none;background:transparent;color:var(--hint);cursor:pointer;display:flex;padding:0;}
.filter-row{
  display:flex;align-items:center;gap:8px;
  padding:0 16px 10px;
  overflow-x:auto;scrollbar-width:none;
  overflow-y:visible;
  padding-bottom:14px;
  position:relative;
  z-index:20;
}
.filter-row::-webkit-scrollbar{display:none;}
.volume-select-wrap{
  position:relative;flex:0 0 auto;
  isolation:isolate;
}
.chip-toggle{
  flex:0 0 auto;display:flex;align-items:center;gap:5px;
  font-size:12px;font-weight:600;
  padding:7px 13px;
  border-radius:100px;
  border:1.5px solid var(--line);
  background:var(--surface);
  color:var(--ink-soft);
  white-space:nowrap;
  box-shadow:var(--shadow);
  transition:.2s cubic-bezier(.34,1.56,.64,1);
  position:relative;overflow:hidden;
}
.chip-toggle::after{
  content:'';position:absolute;inset:0;
  background:radial-gradient(circle at center, rgba(255,255,255,0.5) 0%, transparent 70%);
  opacity:0;transition:opacity .3s ease;
}
.chip-toggle:active::after{opacity:1;}
.chip-toggle svg{flex-shrink:0;transition:transform .3s cubic-bezier(.34,1.56,.64,1);}
.chip-toggle.active{
  background:var(--amber-bg);
  border-color:var(--amber);
  color:var(--amber-deep);
}
.chip-toggle.active svg{transform:rotate(20deg) scale(1.2);}
.price-chip{
  flex:0 0 auto;
  display:flex;align-items:center;gap:8px;
  padding:6px 12px;
  border-radius:100px;
  border:1.5px solid var(--line);
  background:var(--surface);
  box-shadow:var(--shadow);
}
.price-chip .lbl{font-size:11px;font-weight:600;color:var(--ink-soft);white-space:nowrap;}
.price-chip .val{font-size:11px;font-weight:700;color:var(--pine-deep);white-space:nowrap;}
.price-chip .mini-range{width:74px;position:relative;height:18px;display:flex;align-items:center;}
.price-chip .mini-rail{position:absolute;left:0;right:0;height:3px;border-radius:3px;background:var(--line-strong);}
.price-chip .mini-fill{position:absolute;left:0;height:3px;border-radius:3px;background:var(--pine);transition:none;}
input[type="range"].mini-input{
  position:absolute;width:100%;margin:0;
  -webkit-appearance:none;background:transparent;pointer-events:none;
}
input[type="range"].mini-input::-webkit-slider-thumb{
  pointer-events:auto;-webkit-appearance:none;
  width:16px;height:16px;border-radius:50%;
  background:var(--pine);border:2.5px solid var(--surface);
  box-shadow:0 2px 6px rgba(30,51,38,0.35);cursor:pointer;
  transition:transform .15s ease;
}
input[type="range"].mini-input::-webkit-slider-thumb:active{transform:scale(1.2);}
input[type="range"].mini-input::-moz-range-thumb{
  pointer-events:auto;width:16px;height:16px;border-radius:50%;
  background:var(--pine);border:2.5px solid var(--surface);cursor:pointer;
}
.volume-select-wrap{position:relative;flex:0 0 auto;}
.volume-chip{
  display:flex;align-items:center;gap:5px;
  font-size:12px;font-weight:600;
  padding:7px 10px 7px 13px;
  border-radius:100px;
  border:1.5px solid var(--line);
  background:var(--surface);
  color:var(--ink-soft);
  white-space:nowrap;
  box-shadow:var(--shadow);
  transition:.15s ease;
}
.volume-chip.active{background:var(--amber-bg);border-color:var(--amber);color:var(--amber-deep);}
.volume-menu{
  position:fixed;
  background:var(--surface);
  border:1.5px solid var(--line);
  border-radius:14px;
  box-shadow:var(--shadow-lg);
  padding:6px;min-width:200px;z-index:9999;
  display:none;
}
.volume-menu.open{display:block;animation:fadeIn .15s ease;}
.volume-option{
  display:flex;align-items:center;justify-content:space-between;
  padding:9px 11px;border-radius:10px;cursor:pointer;
  font-size:13px;color:var(--ink);transition:background .12s ease;
}
.volume-option:hover{background:var(--pine-soft);}
.volume-option.selected{color:var(--pine-deep);font-weight:700;background:var(--pine-soft);}
.tabs-wrap{
  padding:0 0 10px;
  position:relative;
}
.tabs-wrap::after{
  content:'';
  position:absolute;right:0;top:0;bottom:10px;
  width:32px;
  background:linear-gradient(to left, var(--bg), transparent);
  pointer-events:none;z-index:2;
}
.tabs{
  display:flex;gap:7px;
  overflow-x:auto;
  padding:4px 16px 4px;
  scrollbar-width:thin;
  scrollbar-color:var(--pine-soft) transparent;
  -webkit-overflow-scrolling:touch;
  scroll-snap-type:x proximity;
}
.tabs::-webkit-scrollbar{height:3px;}
.tabs::-webkit-scrollbar-thumb{background:var(--pine-soft);border-radius:3px;}
.tabs::-webkit-scrollbar-track{background:transparent;}
.tab-btn{
  flex:0 0 auto;
  font-size:12.5px;font-weight:600;
  padding:7px 15px;
  border-radius:100px;
  border:1.5px solid var(--line);
  background:var(--surface);
  color:var(--ink-soft);
  white-space:nowrap;
  box-shadow:var(--shadow);
  transition:background .28s cubic-bezier(.22,1,.36,1),color .2s ease,border-color .2s ease,box-shadow .25s ease,transform .2s cubic-bezier(.22,1,.36,1);
  font-family:'Inter',sans-serif;
  scroll-snap-align:start;
  will-change:transform;
}
.tab-btn:active{transform:scale(0.93);transition:transform .1s ease;}
.tab-btn:hover{border-color:var(--pine);color:var(--pine-deep);}
.tab-btn.active{background:var(--pine);border-color:var(--pine);color:#fff;box-shadow:0 4px 14px rgba(46,74,53,0.32);}
.content{padding:4px 16px 28px;}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
.card{
  position:relative;
  background:var(--surface);
  border-radius:var(--radius);
  overflow:visible;
  box-shadow:var(--shadow);
  display:flex;flex-direction:column;
  animation:cardIn .5s cubic-bezier(.22,1,.36,1) backwards;
  cursor:pointer;
  border:1px solid var(--line);
  will-change:transform;
  transition:transform .35s cubic-bezier(.22,1,.36,1),box-shadow .3s ease;
}
.card:hover{transform:translateY(-3px);box-shadow:0 10px 28px rgba(30,51,38,0.14);}
.card:active{transform:scale(0.96);box-shadow:var(--shadow);transition:transform .12s cubic-bezier(.22,1,.36,1),box-shadow .12s ease;}
.card-img-wrap{
  position:relative;width:100%;aspect-ratio:1/1;
  background:linear-gradient(150deg,#F5F0E8,#EDE4D0);
  overflow:hidden;
  border-radius:var(--radius) var(--radius) 0 0;
}
.card-img-wrap img{
  width:100%;height:100%;object-fit:contain;padding:14px;
  transition:transform .3s ease;
}
.card:hover .card-img-wrap img{transform:scale(1.07);}
.card:active .card-img-wrap img{transform:scale(1.03);}
.no-image{
  width:100%;height:100%;display:flex;align-items:center;
  justify-content:center;color:rgba(26,36,32,0.2);
}
.badge-row{position:absolute;top:8px;left:8px;display:flex;gap:4px;z-index:2;}
.badge{
  font-size:9px;font-weight:700;letter-spacing:.04em;
  padding:3px 7px;border-radius:6px;color:#fff;
}
.badge.new{background:var(--pine);}
.badge.oos{background:rgba(26,36,32,0.72);}
.fav-btn{
  position:absolute;top:8px;right:8px;
  width:30px;height:30px;border-radius:50%;
  background:rgba(255,255,255,0.94);
  border:1px solid rgba(26,36,32,0.08);
  display:flex;align-items:center;justify-content:center;
  color:var(--hint);cursor:pointer;z-index:10;
  box-shadow:0 2px 8px rgba(0,0,0,0.10);
  transition:transform .25s cubic-bezier(.34,1.56,.64,1),color .15s ease,background .15s ease;
}
.fav-btn:active{transform:scale(0.78);}
.fav-btn.active{color:var(--danger);}
.fav-btn.active svg{fill:var(--danger);}
.card-info{padding:10px 11px 4px;flex:1;}
.card-cat{font-size:9px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--bark);margin:0 0 3px;opacity:.75;}
.card-title{margin:0 0 3px;font-size:13px;font-weight:600;line-height:1.3;color:var(--ink);min-height:32px;letter-spacing:-.01em;}
.card-vol{font-size:10px;color:var(--hint);margin:0 0 5px;font-weight:500;}
.card-price{margin:0;font-size:15px;font-weight:700;color:var(--pine-deep);letter-spacing:-.02em;}
.card-actions{
  padding:8px 11px 11px;
  border-radius:0 0 var(--radius) var(--radius);
  overflow:hidden;
}
.qty-row{display:flex;align-items:center;gap:8px;}
.qty-control{
  display:flex;align-items:center;
  background:var(--bg);border:1.5px solid var(--line-strong);
  border-radius:10px;overflow:hidden;flex:0 0 auto;
}
.qty-btn{
  width:30px;height:32px;border:none;background:transparent;
  display:flex;align-items:center;justify-content:center;color:var(--ink);
  transition:background .12s ease;
}
.qty-btn:active{background:var(--line);}
.qty-btn:disabled{opacity:.3;cursor:default;}
.qty-val{min-width:22px;text-align:center;font-size:13px;font-weight:700;color:var(--ink);}
.add-btn{
  flex:1;height:34px;border:none;border-radius:10px;
  background:var(--pine);color:#fff;
  font-size:11.5px;font-weight:600;letter-spacing:.01em;
  display:flex;align-items:center;justify-content:center;gap:4px;
  transition:transform .28s cubic-bezier(.22,1,.36,1),background .22s ease,box-shadow .22s ease;
  white-space:nowrap;overflow:hidden;min-width:0;padding:0 8px;
  box-shadow:0 3px 8px rgba(30,51,38,0.22);
  will-change:transform;
}
.add-btn:active{transform:scale(0.93);transition:transform .1s ease;}
.add-btn:hover{box-shadow:0 5px 14px rgba(30,51,38,0.32);}
.add-btn.in-cart{background:var(--amber);}
.add-btn.disabled{background:var(--line-strong);color:var(--hint);cursor:default;box-shadow:none;}
.empty-state{text-align:center;padding:56px 24px;color:var(--hint);}
.empty-state svg{margin:0 auto 14px;opacity:.45;color:var(--bark);}
.empty-state .t{font-size:15px;font-weight:600;color:var(--ink);margin:0 0 6px;}
.empty-state .d{font-size:13px;line-height:1.5;margin:0;}
.bottom-nav{
  position:fixed;left:0;right:0;bottom:0;
  background:var(--pine-deep);
  background-image:url('https://i.postimg.cc/zDtncrLb/c20d2333-07cb-46cd-9378-ec66adea63c9.png');
  background-size:cover;
  background-position:center top;
  border-top:1px solid rgba(255,255,255,0.10);
  display:flex;
  padding:4px 4px calc(4px + env(safe-area-inset-bottom));
  z-index:40;
  box-shadow:0 -4px 24px rgba(30,51,38,0.35);
}
.bottom-nav::before{
  content:'';position:absolute;inset:0;
  background:rgba(22,42,28,0.86);
  pointer-events:none;
}
.nav-item{
  flex:1;display:flex;flex-direction:column;align-items:center;gap:1px;
  background:none;border:none;cursor:pointer;
  color:rgba(255,255,255,0.48);
  font-size:9.5px;font-weight:600;letter-spacing:.01em;
  padding:4px 2px 3px;position:relative;z-index:1;
  transition:color .22s ease;
}
.nav-item:hover{color:rgba(255,255,255,0.82);}
.nav-item.active{color:#fff;}
.nav-item .nav-icon{
  width:24px;height:24px;
  display:flex;align-items:center;justify-content:center;
  position:relative;z-index:1;
  transition:transform .3s cubic-bezier(.34,1.56,.64,1);
}
.nav-item:active .nav-icon{transform:scale(0.80) !important;}
.nav-item:hover .nav-icon{transform:translateY(-2px);}
.nav-item.active .nav-icon{transform:translateY(-1px);}
.nav-item.active .nav-icon::before{
  content:'';
  position:absolute;
  width:30px;height:30px;
  top:50%;left:50%;
  transform:translate(-50%,-50%);
  border-radius:50%;
  background:rgba(255,255,255,0.15);
  z-index:-1;
  animation:navCircle .3s cubic-bezier(.22,1,.36,1);
}
.nav-badge{
  position:absolute;top:-5px;right:-7px;
  min-width:15px;height:15px;padding:0 3px;
  border-radius:8px;background:var(--amber);color:#fff;
  font-size:9px;font-weight:700;
  display:flex;align-items:center;justify-content:center;
}
.clear-cart-btn{
  margin-left:auto;
  display:flex;align-items:center;gap:5px;
  font-size:12px;font-weight:600;
  padding:6px 12px;
  border-radius:100px;
  border:1.5px solid var(--danger-bg);
  background:var(--danger-bg);
  color:var(--danger);
  cursor:pointer;
  transition:all .2s cubic-bezier(.34,1.56,.64,1);
  white-space:nowrap;
}
.clear-cart-btn:active{transform:scale(0.92);}
.clear-cart-btn:hover{background:var(--danger);color:#fff;border-color:var(--danger);}
.page-head{
  display:flex;align-items:center;gap:12px;
  padding:14px 16px 12px;
  border-bottom:1px solid var(--line);
}
.page-head h1{
  margin:0;font-size:20px;font-weight:700;color:var(--ink);
  font-family:'Playfair Display',Georgia,serif;
}
.back-btn{
  width:34px;height:34px;border-radius:50%;
  border:1.5px solid var(--line-strong);
  background:var(--surface);
  box-shadow:var(--shadow);
  display:flex;align-items:center;justify-content:center;
  color:var(--ink);flex-shrink:0;
  transition:transform .12s ease;
}
.back-btn:active{transform:scale(0.90);}
.pd-hero{
  width:100%;aspect-ratio:1/1;max-height:320px;
  background:linear-gradient(150deg,#F5F0E8,#EDE4D0);
  display:flex;align-items:center;justify-content:center;
  position:relative;overflow:hidden;
}
.pd-hero img{width:100%;height:100%;object-fit:contain;padding:28px;}
.pd-fav{
  position:absolute;top:14px;right:14px;
  width:38px;height:38px;border-radius:50%;
  background:rgba(255,255,255,0.92);
  border:1.5px solid rgba(26,36,32,0.08);
  display:flex;align-items:center;justify-content:center;
  color:var(--hint);box-shadow:var(--shadow);
  transition:transform .2s cubic-bezier(.34,1.56,.64,1),color .15s ease;
}
.pd-fav:active{transform:scale(0.84);}
.pd-fav.active{color:var(--danger);}
.pd-fav.active svg{fill:var(--danger);}
.pd-body{padding:18px 18px 22px;animation:slideInRight .28s ease;}
.pd-cat{font-size:10.5px;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--bark);margin:0 0 8px;}
.pd-title{
  font-family:'Bebas Neue','Playfair Display',Georgia,serif;
  font-size:28px;font-weight:400;letter-spacing:.04em;color:var(--ink);margin:0 0 10px;line-height:1.15;
}
.pd-meta{display:flex;align-items:center;gap:8px;margin-bottom:14px;flex-wrap:wrap;}
.pd-vol-tag{
  font-size:11.5px;font-weight:600;color:var(--ink-soft);
  background:var(--bg);border:1.5px solid var(--line);
  padding:4px 10px;border-radius:8px;
}
.pd-price{
  font-family:'Playfair Display',Georgia,serif;
  font-size:28px;font-weight:700;color:var(--pine-deep);margin:0 0 16px;
}
.pd-desc{font-size:13.5px;line-height:1.65;color:var(--ink-soft);margin:0 0 16px;}
.pd-desc ul{padding-left:20px;margin:8px 0;}
.pd-desc li{margin-bottom:5px;}
.pd-desc strong{color:var(--ink);}
.pd-actions-bar{
  position:sticky;bottom:0;
  background:var(--surface);
  border-top:1px solid var(--line);
  padding:11px 16px calc(11px + env(safe-area-inset-bottom));
  display:flex;gap:10px;align-items:center;
}
.pd-actions-bar .qty-control{height:46px;}
.pd-actions-bar .qty-btn{height:46px;width:38px;}
.pd-add-btn{
  flex:1;height:46px;border:none;border-radius:13px;
  background:var(--pine);color:#fff;
  font-family:'Playfair Display',Georgia,serif;
  font-size:15px;font-weight:700;
  display:flex;align-items:center;justify-content:center;gap:8px;
  box-shadow:0 4px 14px rgba
