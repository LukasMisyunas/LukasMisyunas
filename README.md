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
  box-shadow:0 4px 14px rgba(61,90,69,0.28);
  transition:transform .12s ease,box-shadow .15s ease;
}
.pd-add-btn:active{transform:scale(0.97);box-shadow:none;}
.pd-add-btn.in-cart{background:var(--amber);box-shadow:0 4px 14px rgba(200,149,75,0.30);}
.cart-list{padding:0 16px 8px;}
.cart-item{
  display:flex;gap:12px;align-items:center;
  background:var(--surface);border-radius:14px;padding:12px;
  margin-bottom:10px;box-shadow:var(--shadow);
  border:1px solid var(--line);
  animation:cardIn .3s ease;cursor:pointer;
  transition:transform .12s ease;
}
.cart-item:active{transform:scale(0.98);}
.cart-item img{
  width:56px;height:56px;border-radius:10px;object-fit:contain;
  background:linear-gradient(150deg,#F5F0E8,#EDE4D0);padding:6px;flex-shrink:0;
}
.cart-item-img-empty{
  width:56px;height:56px;border-radius:10px;flex-shrink:0;
  background:linear-gradient(150deg,#F5F0E8,#EDE4D0);
}
.cart-item-info{flex:1;min-width:0;}
.cart-item-info .t{font-size:13px;font-weight:600;color:var(--ink);margin:0 0 3px;line-height:1.3;}
.cart-item-info .p{font-size:12.5px;color:var(--bark);margin:0;}
.cart-summary{
  background:var(--surface);border-radius:16px;padding:16px;
  margin:6px 16px 12px;box-shadow:var(--shadow);border:1px solid var(--line);
}
.summary-row{display:flex;justify-content:space-between;font-size:13.5px;color:var(--ink-soft);margin-bottom:8px;}
.summary-row.total{font-size:16px;font-weight:700;color:var(--ink);margin-top:10px;padding-top:10px;border-top:1px solid var(--line);}
.checkout-cta{
  margin:0 16px 20px;
  height:50px;width:calc(100% - 32px);
  border:none;border-radius:14px;
  background:var(--pine);color:#fff;
  font-size:15px;font-weight:700;
  display:flex;align-items:center;justify-content:center;gap:8px;
  box-shadow:0 6px 18px rgba(61,90,69,0.28);
  transition:transform .12s ease,box-shadow .15s ease;
}
.checkout-cta:active{transform:scale(0.97);box-shadow:none;}
.checkout-cta:disabled{background:var(--line-strong);color:var(--hint);box-shadow:none;}
.form-section{
  margin:0 16px 14px;
  background:var(--surface);border-radius:16px;padding:16px;
  box-shadow:var(--shadow);border:1px solid var(--line);
}
.form-section-title{display:flex;align-items:center;gap:8px;font-size:13.5px;font-weight:700;color:var(--ink);margin:0 0 14px;}
.form-section-title svg{color:var(--pine);}
.field{margin-bottom:11px;}
.field:last-child{margin-bottom:0;}
.field label{display:block;font-size:11.5px;font-weight:600;color:var(--bark);margin-bottom:5px;}
.field label .hint{font-weight:400;color:var(--hint);font-size:10.5px;}
.field input{
  width:100%;height:42px;border-radius:10px;
  border:1.5px solid var(--line-strong);background:var(--bg);
  padding:0 12px;font-size:13.5px;color:var(--ink);
  outline:none;transition:border-color .15s ease,box-shadow .15s ease;
  font-family:'Inter',sans-serif;
}
.field input:focus{border-color:var(--pine);box-shadow:0 0 0 3px rgba(61,90,69,0.10);}
.field-row{display:flex;gap:10px;}
.field-row .field{flex:1;}
.option-card{
  display:flex;align-items:flex-start;gap:12px;
  padding:13px;border-radius:12px;
  border:1.5px solid var(--line);margin-bottom:8px;cursor:pointer;
  transition:border-color .15s ease,background .15s ease;
}
.option-card:last-child{margin-bottom:0;}
.option-card.selected{border-color:var(--pine);background:var(--pine-soft);}
.option-radio{
  width:18px;height:18px;border-radius:50%;
  border:2px solid var(--line-strong);
  flex-shrink:0;margin-top:2px;
  display:flex;align-items:center;justify-content:center;
  transition:border-color .15s ease;
}
.option-card.selected .option-radio{border-color:var(--pine);}
.option-radio .dot-fill{
  width:9px;height:9px;border-radius:50%;background:var(--pine);
  transform:scale(0);transition:transform .15s ease;
}
.option-card.selected .dot-fill{transform:scale(1);}
.option-body{flex:1;}
.option-title-row{display:flex;justify-content:space-between;align-items:baseline;gap:8px;}
.option-title{font-size:13px;font-weight:600;color:var(--ink);}
.option-price{font-size:13px;font-weight:700;color:var(--pine-deep);white-space:nowrap;}
.option-desc{font-size:11.5px;color:var(--hint);margin-top:3px;line-height:1.4;}
.option-icon{
  width:32px;height:32px;border-radius:9px;flex-shrink:0;
  background:var(--bg);display:flex;align-items:center;justify-content:center;color:var(--bark);
}
.success-screen{text-align:center;padding:56px 28px 28px;}
.success-icon{
  width:68px;height:68px;margin:0 auto 16px;border-radius:50%;background:var(--pine);
  display:flex;align-items:center;justify-content:center;color:#fff;
  animation:popIn .4s cubic-bezier(.34,1.56,.64,1);
  box-shadow:0 8px 24px rgba(61,90,69,0.30);
}
.success-screen h2{
  font-family:'Playfair Display',Georgia,serif;
  color:var(--ink);font-size:22px;margin:0 0 8px;font-weight:700;
}
.success-screen p{color:var(--ink-soft);font-size:13.5px;line-height:1.6;margin:0 0 24px;}
.profile-card{
  margin:0 16px 14px;
  background:var(--surface);border-radius:16px;padding:18px;
  box-shadow:var(--shadow);border:1px solid var(--line);
  display:flex;align-items:center;gap:14px;
}
.avatar{
  width:54px;height:54px;border-radius:50%;
  background:linear-gradient(145deg,var(--pine),var(--pine-deep));
  display:flex;align-items:center;justify-content:center;
  color:#fff;flex-shrink:0;overflow:hidden;
  border:2px solid rgba(255,255,255,0.2);
}
.avatar img{width:100%;height:100%;object-fit:cover;}
.profile-name{font-size:15px;font-weight:700;color:var(--ink);margin:0 0 3px;}
.profile-sub{font-size:12px;color:var(--hint);margin:0;}
.auth-tag{
  display:inline-flex;align-items:center;gap:4px;
  font-size:10px;font-weight:700;padding:3px 8px;border-radius:6px;margin-top:5px;
}
.auth-tag.tg{background:var(--pine-soft);color:var(--pine-deep);}
.auth-options{margin:0 16px;}
.auth-btn{
  width:100%;display:flex;align-items:center;gap:12px;
  background:var(--surface);border:none;border-radius:14px;
  padding:13px 15px;margin-bottom:8px;
  box-shadow:var(--shadow);border:1px solid var(--line);
  transition:transform .12s ease;
}
.auth-btn:active{transform:scale(0.97);}
.auth-btn .ic{
  width:38px;height:38px;border-radius:11px;
  background:var(--pine-soft);display:flex;align-items:center;
  justify-content:center;color:var(--pine);flex-shrink:0;
}
.auth-btn .tx{flex:1;text-align:left;}
.auth-btn .tx .t{font-size:14px;font-weight:600;color:var(--ink);margin:0 0 2px;}
.auth-btn .tx .d{font-size:11.5px;color:var(--hint);margin:0;}
.auth-btn .chev{color:var(--hint);}
.auth-note{
  margin:12px 16px 0;padding:11px 13px;
  background:var(--amber-bg);border-radius:12px;
  font-size:11.5px;line-height:1.5;color:var(--amber-deep);
  display:flex;gap:8px;border:1px solid rgba(200,149,75,0.2);
}
.auth-note svg{flex-shrink:0;margin-top:1px;}
.menu-list{margin:14px 16px 0;}
.menu-item{
  display:flex;align-items:center;gap:12px;
  background:var(--surface);border-radius:13px;padding:13px 14px;
  margin-bottom:7px;box-shadow:var(--shadow);border:1px solid var(--line);
  cursor:pointer;transition:transform .12s ease;
}
.menu-item:active{transform:scale(0.97);}
.menu-item .ic{color:var(--pine);flex-shrink:0;}
.menu-item .t{flex:1;font-size:13.5px;font-weight:600;color:var(--ink);}
.menu-item .chev{color:var(--hint);flex-shrink:0;}
.menu-item.danger .ic,.menu-item.danger .t{color:var(--danger);}
.footer{padding:30px 20px 16px;text-align:center;}
.footer-logo{
  font-family:'Playfair Display',Georgia,serif;
  font-size:20px;font-weight:700;color:var(--ink);margin:0 0 8px;
}
.footer-quote{font-size:12px;line-height:1.6;color:var(--ink-soft);max-width:280px;margin:0 auto 16px;font-style:italic;}
.footer-socials{display:flex;justify-content:center;gap:10px;margin-bottom:22px;}
.footer-socials a{
  width:40px;height:40px;border-radius:50%;
  background:var(--surface);
  border:2px solid var(--line-strong);
  box-shadow:var(--shadow);
  display:flex;align-items:center;justify-content:center;
  color:var(--pine-deep);
  transition:transform .2s cubic-bezier(.34,1.56,.64,1),box-shadow .15s ease,border-color .15s ease;
}
.footer-socials a:active{transform:scale(0.88);}
.footer-socials a:hover{box-shadow:0 6px 18px rgba(30,51,38,0.25);border-color:var(--pine);transform:translateY(-2px);}
.footer-cols{
  display:flex;flex-direction:row;gap:0;
  text-align:left;margin-bottom:22px;
  border:1px solid var(--line);border-radius:14px;overflow:hidden;
  background:var(--surface);box-shadow:var(--shadow);
}
.footer-col{
  flex:1;padding:14px 12px;
  border-right:1px solid var(--line);
}
.footer-col:last-child{border-right:none;}
.footer-col-title{font-size:10px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:var(--amber-deep);margin:0 0 9px;}
.footer-links{display:flex;flex-direction:column;gap:7px;}
.footer-links a{
  font-size:11.5px;color:var(--ink-soft);
  transition:color .15s ease,font-weight .15s ease;
  display:block;
}
.footer-links a:hover{color:var(--pine-deep);font-weight:700;}
.footer-bottom{border-top:1px solid var(--line);padding-top:14px;font-size:11px;color:var(--hint);line-height:1.6;}
.toast{
  position:fixed;top:16px;left:50%;
  transform:translate(-50%,-16px);
  background:var(--ink);color:#fff;
  padding:9px 18px;border-radius:100px;
  font-size:13px;font-weight:500;
  display:flex;align-items:center;gap:8px;
  opacity:0;transition:opacity .3s cubic-bezier(.22,1,.36,1),transform .3s cubic-bezier(.22,1,.36,1);z-index:90;
  box-shadow:0 8px 24px rgba(0,0,0,0.22);
  max-width:88%;pointer-events:none;
}
.toast.show{opacity:1;transform:translate(-50%,0);}
.toast svg{color:var(--amber);flex-shrink:0;}
.card[data-card-id]{transition:opacity .2s ease;}
@media(prefers-reduced-motion:reduce){*{transition:none !important;animation:none !important;}}
@media(min-width:600px){
  #app{max-width:430px;margin:0 auto;box-shadow:0 0 80px rgba(0,0,0,0.14);}
  .bottom-nav{max-width:430px;left:50%;transform:translateX(-50%);}
  .toast{max-width:380px;}
}
@media(min-width:900px){
  body{background-attachment:fixed;}
  #app{max-width:460px;}
  .bottom-nav{max-width:460px;}
}
@media(max-width:390px){
  .topbar{padding:8px 12px 6px;}
  .logo-mark{width:36px;height:36px;}
  .icon-btn{width:32px;height:32px;}
  .hdr{padding:14px 14px 8px;}
  .hdr h1{font-size:20px;}
  .hdr p{font-size:12px;}
  .search-box{margin:0 12px 8px;}
  .filter-row{padding:0 12px 10px;gap:6px;}
  .price-chip .mini-range{width:54px;}
  .price-chip{padding:5px 9px;}
  .chip-toggle,.volume-chip{padding:6px 10px;font-size:11.5px;}
  .tabs{padding:2px 12px 4px;gap:5px;}
  .tab-btn{padding:6px 11px;font-size:11.5px;}
  .content{padding:4px 12px 24px;}
  .grid{grid-template-columns:1fr 1fr;gap:8px;}
  .card-info{padding:8px 9px 3px;}
  .card-title{font-size:12px;min-height:28px;}
  .card-price{font-size:13.5px;}
  .card-vol{font-size:9.5px;}
  .card-cat{font-size:9px;}
  .card-actions{padding:6px 9px 9px;}
  .qty-row{gap:5px;}
  .add-btn{font-size:10.5px;height:32px;padding:0 6px;gap:3px;}
  .add-btn svg{width:11px;height:11px;}
  .qty-btn{width:26px;height:26px;}
  .qty-val{font-size:12px;min-width:18px;}
  .nav-item{font-size:9px;}
}
</style>
</head>
<body>
<div id="app">

  <!-- ==================== КАТАЛОГ ==================== -->
  <section class="screen active" id="screen-catalog">
    <div class="topbar">
      <div class="topbar-left">
        <div class="logo-mark" id="logoMark"></div>
      </div>
      <div class="topbar-right">
        <button class="icon-btn" id="adminEditBtn" style="display:none;" aria-label="Админ">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M11 4H4a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-7"></path><path d="M18.5 2.5a2.121 2.121 0 0 1 3 3L12 15l-4 1 1-4 9.5-9.5z"></path></svg>
        </button>
        <button class="icon-btn" id="topCartBtn" aria-label="Корзина">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="9" cy="21" r="1"></circle><circle cx="20" cy="21" r="1"></circle><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path></svg>
          <span class="dot" id="topCartDot" style="display:none;">0</span>
        </button>
      </div>
    </div>

    <!-- ===================== ВОЛНА СВЕРХУ ===================== -->
    <div class="wave-top wave-top--gradient">
      <svg viewBox="0 0 1440 60" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <linearGradient id="waveGradientTop" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stop-color="#1E3326" stop-opacity="0.35"/>
            <stop offset="100%" stop-color="#1E3326" stop-opacity="0"/>
          </linearGradient>
        </defs>
        <path d="M0,30 C240,60 480,0 720,30 C960,60 1200,0 1440,30 L1440,0 L0,0 Z"/>
      </svg>
    </div>

    <section class="hdr">
      <p class="eyebrow">MagicHerbs · Mini App</p>
      <h1 class="serif">Каталог продукции</h1>
      <p>Нативные нутрицевтики премиального качества из дикоросов Сибири</p>
    </section>

    <div class="search-wrap">
      <div class="search-box" id="searchBox">
        <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
        <input type="text" id="searchInput" placeholder="Найти товар..." autocomplete="off"/>
        <button class="search-clear" id="searchClear" style="display:none;" aria-label="Очистить">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
        </button>
      </div>
    </div>

    <div class="filter-row">
      <button class="chip-toggle" id="newOnlyChip">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"></polygon></svg>
        Новинки
      </button>
      <div class="price-chip">
        <span class="lbl">До</span>
        <span class="val" id="priceValueLabel">10 000 ₽</span>
        <div class="mini-range">
          <div class="mini-rail"></div>
          <div class="mini-fill" id="priceFill"></div>
          <input type="range" class="mini-input" id="priceRange" min="300" max="10000" step="100" value="10000"/>
        </div>
      </div>
      <div class="volume-select-wrap">
        <button class="volume-chip" id="volumeChip">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"></path><polyline points="3.27 6.96 12 12.01 20.73 6.96"></polyline><line x1="12" y1="22.08" x2="12" y2="12"></line></svg>
          <span id="volumeChipLabel">Объём</span>
          <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"></polyline></svg>
        </button>
        <div class="volume-menu" id="volumeMenu">
          <div class="volume-option selected" data-value="any">Любой объём</div>
          <div class="volume-option" data-value="small">Малый (до 150 мл/г)</div>
          <div class="volume-option" data-value="medium">Средний (150–500 мл/г)</div>
          <div class="volume-option" data-value="large">Большой (от 500 мл/г)</div>
        </div>
      </div>
    </div>

    <div class="tabs-wrap">
      <div class="tabs" id="tabs"></div>
    </div>

    <section class="content">
      <div class="grid" id="grid"></div>
      <div class="empty-state" id="catalogEmpty" style="display:none;">
        <svg width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
        <p class="t">Ничего не найдено</p>
        <p class="d">Попробуйте изменить запрос,<br>категорию или диапазон цены.</p>
      </div>
    </section>

    <footer class="footer" id="appFooter">
      <p class="footer-logo">MagicHerbs®</p>
      <p class="footer-quote">«Природа даёт нам всё необходимое для здоровья. Мы бережно собираем это и сохраняем для вас.»</p>
      <div class="footer-socials">
        <a href="https://vk.com/mherbs" target="_blank" rel="noopener noreferrer" aria-label="VK бренда">
          <svg width="17" height="17" viewBox="0 0 48 48" fill="currentColor"><path d="M27.55,35.19V28.55c4.46.68,5.87,4.19,8.71,6.64H43.5a29.36,29.36,0,0,0-7.9-10.47c2.6-3.58,5.36-6.95,6.71-12.06H35.73c-2.58,3.91-3.94,8.49-8.18,11.51V12.66H18l2.28,2.82,0,10.05c-3.7-.43-6.2-7.2-8.91-12.87H4.5C7,20.32,12.26,37.13,27.55,35.19Z"></path></svg>
        </a>
        <a href="https://vk.me/yegorogourtsov" target="_blank" rel="noopener noreferrer" aria-label="VK создателя">
          <svg width="17" height="17" viewBox="0 0 48 48" fill="currentColor"><path d="M27.55,35.19V28.55c4.46.68,5.87,4.19,8.71,6.64H43.5a29.36,29.36,0,0,0-7.9-10.47c2.6-3.58,5.36-6.95,6.71-12.06H35.73c-2.58,3.91-3.94,8.49-8.18,11.51V12.66H18l2.28,2.82,0,10.05c-3.7-.43-6.2-7.2-8.91-12.87H4.5C7,20.32,12.26,37.13,27.55,35.19Z"></path></svg>
        </a>
        <a href="https://t.me/yegorogurtsov" target="_blank" rel="noopener noreferrer" aria-label="Telegram">
          <svg width="17" height="17" viewBox="0 0 448 512" fill="currentColor"><path d="M446.7 98.6l-67.6 318.8c-5.1 22.5-18.5 28.1-37.4 17.5l-103-75.9-49.7 47.8c-5.5 5.5-10.1 10.1-20.7 10.1l7.4-104.9 190.9-172.5c8.3-7.4-1.8-11.5-12.9-4.1L117.8 284 16.2 252.2c-22.1-6.9-22.5-22.1 4.6-32.7L418.2 66.4c19.3-6.9 36.2 4.7 28.5 32.2z"></path></svg>
        </a>
        <a href="https://wa.me/79009224496" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp">
          <svg width="17" height="17" viewBox="0 0 448 512" fill="currentColor"><path d="M380.9 97.1C339 55.1 283.2 32 223.9 32c-122.4 0-222 99.6-222 222 0 39.1 10.2 77.3 29.6 111L0 480l117.7-30.9c32.4 17.7 68.9 27 106.1 27h.1c122.3 0 224.1-99.6 224.1-222 0-59.3-25.2-115-67.1-157zm-157 341.6c-33.2 0-65.7-8.9-94-25.7l-6.7-4-69.8 18.3 18.7-68.1-4.4-7c-18.5-29.4-28.2-63.3-28.2-98.2 0-101.7 82.8-184.5 184.6-184.5 49.3 0 95.6 19.2 130.4 54.1 34.8 34.9 56.2 81.2 56.1 130.5 0 101.8-84.9 184.6-186.6 184.6zm101.2-138.2c-5.5-2.8-32.8-16.2-37.9-18-5.1-1.9-8.8-2.8-12.5 2.8-3.7 5.6-14.3 18-17.6 21.8-3.2 3.7-6.5 4.2-12 1.4-32.6-16.3-54-29.1-75.5-66-5.7-9.8 5.7-9.1 16.3-30.3 1.8-3.7.9-6.9-.5-9.7-1.4-2.8-12.5-30.1-17.1-41.2-4.5-10.8-9.1-9.3-12.5-9.5-3.2-.2-6.9-.2-10.6-.2-3.7 0-9.7 1.4-14.8 6.9-5.1 5.6-19.4 19-19.4 46.3 0 27.3 19.9 53.7 22.6 57.4 2.8 3.7 39.1 59.7 94.8 83.8 35.2 15.2 49 16.5 66.6 13.9 10.7-1.6 32.8-13.4 37.4-26.4 4.6-13 4.6-24.1 3.2-26.4-1.3-2.5-5-3.9-10.5-6.6z"></path></svg>
        </a>
      </div>
      <div class="footer-cols">
        <div class="footer-col">
          <p class="footer-col-title">Навигация</p>
          <div class="footer-links">
            <a href="http://85.239.60.203/catalog">Каталог</a>
            <a href="http://85.239.60.203/#brand-story">О нас</a>
            <a href="http://85.239.60.203/missiya">Миссия</a>
            <a href="http://85.239.60.203/otziv">Отзывы</a>
            <a href="http://85.239.60.203/protokol">Сертификаты</a>
          </div>
        </div>
        <div class="footer-col">
          <p class="footer-col-title">Сотрудничество</p>
          <div class="footer-links">
            <a href="http://85.239.60.203/opt">Оптовым</a>
            <a href="http://85.239.60.203/zdorov">Специалистам</a>
            <a href="http://85.239.60.203/oplata-i-dostavka">Доставка</a>
            <a href="http://85.239.60.203/rekvizit">Реквизиты</a>
          </div>
        </div>
        <div class="footer-col">
          <p class="footer-col-title">Юр. инфо</p>
          <div class="footer-links">
            <a href="http://85.239.60.203/privacy">Конфиденц.</a>
            <a href="http://85.239.60.203/terms">Соглашение</a>
            <a href="http://85.239.60.203/kontakt">Контакты</a>
          </div>
        </div>
      </div>
      <div class="footer-bottom">
        MagicHerbs © 2026. Все права защищены<br>
        Создано с заботой о здоровье.
      </div>
    </footer>

    <!-- ===================== ВОЛНА СНИЗУ ===================== -->
    <div class="wave-bottom wave-bottom--gradient">
      <svg viewBox="0 0 1440 60" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <linearGradient id="waveGradientBottom" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stop-color="#1E3326" stop-opacity="0"/>
            <stop offset="100%" stop-color="#1E3326" stop-opacity="0.35"/>
          </linearGradient>
        </defs>
        <path d="M0,30 C240,0 480,60 720,30 C960,0 1200,60 1440,30 L1440,60 L0,60 Z"/>
      </svg>
    </div>
  </section>

  <!-- ==================== СТРАНИЦА ТОВАРА ==================== -->
  <section class="screen" id="screen-product">
    <div class="page-head" style="padding-bottom:0;">
      <button class="back-btn" id="pdBackBtn" aria-label="Назад">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polyline points="15 18 9 12 15 6"></polyline></svg>
      </button>
    </div>
    <div class="pd-hero" id="pdHero"></div>
    <div class="pd-body" id="pdBody"></div>
    <div class="pd-actions-bar" id="pdActionsBar"></div>
  </section>

  <!-- ==================== ИЗБРАННОЕ ==================== -->
  <section class="screen" id="screen-favorites">
    <div class="page-head">
      <button class="back-btn" id="favBackBtn" aria-label="Назад">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polyline points="15 18 9 12 15 6"></polyline></svg>
      </button>
      <h1 class="serif">Избранное</h1>
    </div>
    <section class="content">
      <div class="grid" id="favGrid"></div>
      <div class="empty-state" id="favEmpty" style="display:none;">
        <svg width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>
        <p class="t">Пока пусто</p>
        <p class="d">Отмечайте товары значком сердца —<br>они появятся здесь.</p>
      </div>
    </section>
  </section>

  <!-- ==================== КОРЗИНА ==================== -->
  <section class="screen" id="screen-cart">
    <div class="page-head">
      <button class="back-btn" id="cartBackBtn" aria-label="Назад">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polyline points="15 18 9 12 15 6"></polyline></svg>
      </button>
      <h1 class="serif">Корзина</h1>
      <button class="clear-cart-btn" id="clearCartBtn" style="display:none;" aria-label="Очистить корзину">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="3 6 5 6 21 6"></polyline><path d="M19 6l-1 14a2 2 0 0 1-2 2H8a2 2 0 0 1-2-2L5 6"></path><path d="M10 11v6M14 11v6"></path><path d="M9 6V4a1 1 0 0 1 1-1h4a1 1 0 0 1 1 1v2"></path></svg>
        Очистить
      </button>
    </div>

    <div id="cartView">
      <div class="cart-list" id="cartList"></div>
      <div class="empty-state" id="cartEmpty" style="display:none;">
        <svg width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="9" cy="21" r="1"></circle><circle cx="20" cy="21" r="1"></circle><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path></svg>
        <p class="t">Корзина пуста</p>
        <p class="d">Загляните в каталог за нутрицевтиками.</p>
      </div>
      <div class="cart-summary" id="cartSummaryBlock" style="display:none;">
        <div class="summary-row"><span>Товаров</span><span id="sumCount">0</span></div>
        <div class="summary-row total"><span>Итого</span><span id="sumTotal">0 ₽</span></div>
      </div>
      <button class="checkout-cta" id="goCheckoutBtn" style="display:none;">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
        Оформить заказ
      </button>
    </div>

    <div id="checkoutView" style="display:none;">
      <div class="form-section">
        <p class="form-section-title">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>
          Контакты
        </p>
        <div class="field"><label>Ваши имя и фамилия *</label><input type="text" id="f_name" placeholder="Иван Иванов"/></div>
        <div class="field"><label>Ваш телефон *</label><input type="tel" id="f_phone" placeholder="+7 ___ ___-__-__"/></div>
        <div class="field"><label>E-mail * <span class="hint">— сюда придёт чек об оплате и трек-номер посылки</span></label><input type="email" id="f_email" placeholder="you@example.com"/></div>
      </div>

      <div class="form-section">
        <p class="form-section-title">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path><circle cx="12" cy="10" r="3"></circle></svg>
          Адрес доставки
        </p>
        <div class="field-row">
          <div class="field"><label>Страна *</label><input type="text" id="f_country" placeholder="Россия"/></div>
          <div class="field"><label>Город *</label><input type="text" id="f_city" placeholder="Москва"/></div>
        </div>
        <div class="field"><label>Адрес (улица, дом, квартира) *</label><input type="text" id="f_address" placeholder="ул. Ленина, д. 1, кв. 1"/></div>
        <div class="field"><label>Индекс *</label><input type="text" id="f_zip" placeholder="123456" inputmode="numeric"/></div>
      </div>

      <div class="form-section">
        <p class="form-section-title">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="1" y="3" width="15" height="13" rx="2"></rect><path d="M16 8h3l3 3v5h-6"></path><circle cx="5.5" cy="18.5" r="2.2"></circle><circle cx="18.5" cy="18.5" r="2.2"></circle></svg>
          Способ доставки
        </p>
        <div class="option-card selected" data-group="delivery" data-value="cdek_pvz" data-price="350">
          <div class="option-radio"><div class="dot-fill"></div></div>
          <div class="option-icon"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="1" y="3" width="15" height="13" rx="2"></rect><path d="M16 8h3l3 3v5h-6"></path><circle cx="5.5" cy="18.5" r="2.2"></circle><circle cx="18.5" cy="18.5" r="2.2"></circle></svg></div>
          <div class="option-body">
            <div class="option-title-row"><span class="option-title">СДЭК: ПВЗ — ПВЗ</span><span class="option-price">350 ₽</span></div>
            <p class="option-desc">От нашего пункта выдачи до вашего. Сроки: 3–7 рабочих дней</p>
          </div>
        </div>
        <div class="option-card" data-group="delivery" data-value="courier_door" data-price="550">
          <div class="option-radio"><div class="dot-fill"></div></div>
          <div class="option-icon"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"></path></svg></div>
          <div class="option-body">
            <div class="option-title-row"><span class="option-title">Курьером: ПВЗ — дверь</span><span class="option-price">550 ₽</span></div>
            <p class="option-desc">От нашего пункта выдачи курьером до вашего адреса. Сроки: 2–5 рабочих дней</p>
          </div>
        </div>
      </div>

      <div class="form-section">
        <p class="form-section-title">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="5" width="20" height="14" rx="2"></rect><line x1="2" y1="10" x2="22" y2="10"></line></svg>
          Способ оплаты
        </p>
        <div class="option-card selected" data-group="payment" data-value="yookassa">
          <div class="option-radio"><div class="dot-fill"></div></div>
          <div class="option-icon"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="9"></circle><path d="M12 7v10M8 9.5h6.5a2 2 0 1 1 0 4H9"></path></svg></div>
          <div class="option-body"><span class="option-title">ЮKassa</span><p class="option-desc">Оплата по карте, через ЮMoney или SberPay</p></div>
        </div>
        <div class="option-card" data-group="payment" data-value="ozonpay">
          <div class="option-radio"><div class="dot-fill"></div></div>
          <div class="option-icon"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="9"></circle><path d="M9 12l2 2 4-4"></path></svg></div>
          <div class="option-body"><span class="option-title">OzonPay</span><p class="option-desc">Быстрая и безопасная оплата через ваш аккаунт Ozon</p></div>
        </div>
      </div>

      <button class="checkout-cta" id="submitOrderBtn"><span id="submitOrderLabel">Оформить заказ на 0 ₽</span></button>
      <p style="text-align:center; font-size:11px; color:var(--hint); margin:-6px 16px 20px;">
        После оформления заказа вы получите ссылку на оплату в Telegram
      </p>
    </div>

    <div class="success-screen" id="successView" style="display:none;">
      <div class="success-icon"><svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg></div>
      <h2>Заказ отправлен!</h2>
      <p>Ссылка на оплату пришла вам в Telegram.<br>Перейдите по ней, чтобы оплатить заказ.</p>
      <button class="checkout-cta" id="backToCatalogBtn" style="position:static; width:calc(100% - 32px);">Вернуться в каталог</button>
    </div>
  </section>

  <!-- ==================== ПРОФИЛЬ ==================== -->
  <section class="screen" id="screen-profile">
    <div class="page-head"><h1 class="serif">Личный кабинет</h1></div>
    <div id="authView">
      <div class="auth-options">
        <button class="auth-btn" id="authTelegramBtn">
          <span class="ic">
            <svg width="19" height="19" viewBox="0 0 24 24" fill="currentColor"><path d="M9.78 18.65l.28-4.23 7.68-6.92c.34-.31-.07-.46-.52-.19L7.74 13.3 3.64 12c-.88-.25-.89-.86.2-1.3l15.97-6.16c.73-.33 1.43.18 1.15 1.3l-2.72 12.81c-.19.91-.74 1.13-1.5.71L12.6 16.3l-1.99 1.93c-.23.23-.42.42-.83.42z"/></svg>
          </span>
          <span class="tx"><span class="t">Войти через Telegram</span><span class="d">Подтянутся ваше имя, юзернейм и фото</span></span>
          <svg class="chev" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"></polyline></svg>
        </button>
      </div>
      <div class="auth-note">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><line x1="12" y1="16" x2="12" y2="12"></line><line x1="12" y1="8" x2="12" y2="8"></line></svg>
        <span>Вход через Telegram работает по-настоящему — данные берутся из вашего профиля.</span>
      </div>
    </div>
    <div id="profileView" style="display:none;">
      <div class="profile-card">
        <div class="avatar" id="profileAvatar">
          <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>
        </div>
        <div>
          <p class="profile-name" id="profileName">—</p>
          <p class="profile-sub" id="profileSub">—</p>
          <span class="auth-tag" id="profileAuthTag"></span>
        </div>
      </div>
      <div class="menu-list">
        <div class="menu-item" id="menuOrders">
          <span class="ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 11l3 3L22 4"></path><path d="M21 12v7a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h11"></path></svg></span>
          <span class="t">Мои заказы</span>
          <svg class="chev" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"></polyline></svg>
        </div>
        <div class="menu-item" id="menuFav">
          <span class="ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg></span>
          <span class="t">Избранное</span>
          <svg class="chev" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"></polyline></svg>
        </div>
        <div class="menu-item danger" id="menuLogout">
          <span class="ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 21H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h4"></path><polyline points="16 17 21 12 16 7"></polyline><line x1="21" y1="12" x2="9" y2="12"></line></svg></span>
          <span class="t">Выйти</span>
        </div>
      </div>
    </div>
  </section>

</div>

<!-- ==================== НИЖНЯЯ НАВИГАЦИЯ ==================== -->
<nav class="bottom-nav" id="bottomNav" role="navigation">
  <button class="nav-item active" data-screen="catalog" aria-label="Каталог">
    <div class="nav-icon">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="7" height="7" rx="1.5"></rect><rect x="14" y="3" width="7" height="7" rx="1.5"></rect><rect x="3" y="14" width="7" height="7" rx="1.5"></rect><rect x="14" y="14" width="7" height="7" rx="1.5"></rect></svg>
    </div>
    <span>Каталог</span>
  </button>
  <button class="nav-item" data-screen="favorites" aria-label="Избранное">
    <div class="nav-icon">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>
    </div>
    <span>Избранное</span>
  </button>
  <button class="nav-item" data-screen="cart" aria-label="Корзина">
    <div class="nav-icon">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="9" cy="21" r="1"></circle><circle cx="20" cy="21" r="1"></circle><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path></svg>
      <span class="nav-badge" id="navCartBadge" style="display:none;">0</span>
    </div>
    <span>Корзина</span>
  </button>
  <button class="nav-item" data-screen="profile" aria-label="Профиль">
    <div class="nav-icon">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>
    </div>
    <span>Профиль</span>
  </button>
</nav>

<div class="toast" id="toast"></div>

<!-- МОДАЛЬНОЕ ОКНО: ВХОД АДМИНА -->
<div id="adminLoginModal" style="display:none;position:fixed;inset:0;background:rgba(0,0,0,0.75);z-index:9999;padding:20px;align-items:center;justify-content:center;">
  <div style="background:#fff;border-radius:16px;padding:24px;max-width:400px;width:100%;">
    <h3 style="margin:0 0 16px;font-family:'Playfair Display',serif;font-size:20px;">Вход для админа</h3>
    <input type="email" id="adminEmail" placeholder="Email" style="width:100%;padding:12px;border:1.5px solid #ddd;border-radius:10px;margin-bottom:10px;font-size:14px;font-family:'Inter',sans-serif;">
    <input type="password" id="adminPassword" placeholder="Пароль" style="width:100%;padding:12px;border:1.5px solid #ddd;border-radius:10px;margin-bottom:16px;font-size:14px;font-family:'Inter',sans-serif;">
    <button id="adminLoginSubmit" style="width:100%;padding:13px;border-radius:10px;background:#2E4A35;color:#fff;font-weight:700;border:none;cursor:pointer;font-size:14px;font-family:'Inter',sans-serif;">Войти</button>
    <button id="adminLoginCancel" style="width:100%;padding:11px;border-radius:10px;background:#f5f5f5;color:#666;font-weight:600;border:none;cursor:pointer;margin-top:8px;font-size:13px;font-family:'Inter',sans-serif;">Отмена</button>
  </div>
</div>

<!-- МОДАЛЬНОЕ ОКНО: УПРАВЛЕНИЕ ТОВАРАМИ -->
<div id="adminModal" style="display:none;position:fixed;inset:0;background:rgba(0,0,0,0.75);z-index:9999;padding:20px;overflow-y:auto;">
  <div style="background:#fff;border-radius:16px;padding:20px;max-width:500px;margin:0 auto;">
    <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:16px;">
      <h3 style="margin:0;font-family:'Playfair Display',serif;font-size:18px;">Управление товарами</h3>
      <button id="adminCloseBtn" style="border:none;background:#f0f0f0;border-radius:50%;width:36px;height:36px;font-size:16px;cursor:pointer;">✕</button>
    </div>
    <button id="adminAddBtn" style="width:100%;padding:12px;border-radius:10px;background:#2E4A35;color:#fff;font-weight:700;border:none;cursor:pointer;margin-bottom:16px;font-size:14px;font-family:'Inter',sans-serif;">Добавить товар</button>
    <div id="adminProductsList"></div>
    <button id="adminLogoutBtn" style="width:100%;padding:11px;border-radius:10px;background:#f5f5f5;color:#666;font-weight:600;border:none;cursor:pointer;margin-top:16px;font-size:13px;font-family:'Inter',sans-serif;">Выйти</button>
  </div>
</div>

<script>
(function(){
  "use strict";

  var SUPABASE_URL = "https://uwtssaifirbamqoybkuo.supabase.co";
  var SUPABASE_KEY = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InV3dHNzYWlmaXJiYW1xb3lia3VvIiwicm9sZSI6ImFub24iLCJpYXQiOjE3ODkzMzkxOTMsImV4cCI6MjEwNDkxNTE5M30.69B-KN2B1OClBjcKf_d2Yfs23v3XHTTS7e8tsNJB0oU";
  var db = window.supabase.createClient(SUPABASE_URL, SUPABASE_KEY);

  var CONFIG = {
    logoUrl: "https://i.postimg.cc/7Z1VJ4jx/22109625-d753-4c25-8ab6-c36ff9ab9cff-Photoroom.png"
  };

  var PRODUCTS = [];

  async function loadProductsFromDB() {
    var { data, error } = await db
      .from("products")
      .select("*")
      .order("created_at", { ascending: true });

    if (error) {
      console.error("Ошибка загрузки товаров:", error);
      return;
    }
    if (!data) return;

    PRODUCTS = data.map(function(p) {
      return {
        id: String(p.id),
        slug: p.slug,
        title: p.title,
        category: p.category,
        price: p.price,
        volume: p.volume || "",
        image: p.image || "",
        desc: p.descr || "",
        isNew: p.is_new,
        outOfStock: p.out_of_stock
      };
    });

    computeCategories();
    renderTabs();
    renderGrid();
  }

  var CATEGORIES = ["Все"];
  function computeCategories(){
    CATEGORIES = ["Все"].concat(
      PRODUCTS.map(function(p){return p.category;})
        .filter(function(c,i,arr){
          return c && arr.indexOf(c)===i && c !== "Сыродавленные масла и жмыхи";
        })
    );
  }

  var cart = {};
  var favorites = {};
  var auth = null;
  var state = {
    search: "", category: "Все", maxPrice: 10000,
    newOnly: false, volume: "any",
    screen: "catalog", currentProductId: null
  };
  var orderDraft = { delivery:"cdek_pvz", deliveryPrice:350, payment:"yookassa" };
  var MIN_PRICE = 300, MAX_PRICE = 10000;

  function loadState(){
    try{ cart = JSON.parse(localStorage.getItem('mh_cart_v3')) || {}; }catch(e){ cart = {}; }
    try{ favorites = JSON.parse(localStorage.getItem('mh_fav_v3')) || {}; }catch(e){ favorites = {}; }
    try{ auth = JSON.parse(localStorage.getItem('mh_auth_v3')) || null; }catch(e){ auth = null; }
  }
  function saveCart(){ try{ localStorage.setItem('mh_cart_v3', JSON.stringify(cart)); }catch(e){} }
  function saveFav(){ try{ localStorage.setItem('mh_fav_v3', JSON.stringify(favorites)); }catch(e){} }
  function saveAuth(){ try{ localStorage.setItem('mh_auth_v3', JSON.stringify(auth)); }catch(e){} }

  function formatPrice(n){ return n.toString().replace(/\B(?=(\d{3})+(?!\d))/g, " ") + " ₽"; }
  function haptic(style){
    try{
      if(window.Telegram && window.Telegram.WebApp && window.Telegram.WebApp.HapticFeedback){
        window.Telegram.WebApp.HapticFeedback.impactOccurred(style || "light");
      }
    }catch(e){}
  }
  var toastTimer = null;
  function showToast(text){
    var t = document.getElementById("toast");
    t.innerHTML = '<svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg><span>' + text + '</span>';
    t.classList.add("show");
    clearTimeout(toastTimer);
    toastTimer = setTimeout(function(){ t.classList.remove("show"); }, 1800);
  }

  function renderLogo(){
    var el = document.getElementById("logoMark");
    el.innerHTML = '<img src="' + CONFIG.logoUrl + '" alt="MagicHerbs" style="width:44px;height:44px;object-fit:contain;display:block;"/>';
  }

  function findProduct(id){ return PRODUCTS.filter(function(x){return x.id===id;})[0]; }
  function cartCount(){ var n=0; Object.keys(cart).forEach(function(id){ n += cart[id]; }); return n; }
  function cartTotal(){
    var sum = 0;
    Object.keys(cart).forEach(function(id){ var p = findProduct(id); if(p) sum += p.price * cart[id]; });
    return sum;
  }

  function goScreen(name){
    state.screen = name;
    document.querySelectorAll(".screen").forEach(function(s){ s.classList.remove("active"); });
    document.getElementById("screen-" + name).classList.add("active");
    document.querySelectorAll(".nav-item").forEach(function(b){
      var match = (name === "product") ? "catalog" : name;
      b.classList.toggle("active", b.getAttribute("data-screen") === match);
    });
    if(name === "favorites") renderFavorites();
    if(name === "cart") showCartView();
    if(name === "profile") renderProfile();
    window.scrollTo(0,0);
  }

  document.querySelectorAll(".nav-item").forEach(function(btn){
    btn.addEventListener("click", function(){ haptic("light"); goScreen(btn.getAttribute("data-screen")); });
  });
  document.getElementById("topCartBtn").addEventListener("click", function(){ goScreen("cart"); });

  function renderTabs(){
    var wrap = document.getElementById("tabs");
    wrap.innerHTML = "";
    CATEGORIES.forEach(function(cat){
      var btn = document.createElement("button");
      btn.className = "tab-btn" + (cat === state.category ? " active" : "");
      btn.textContent = cat;
      btn.addEventListener("click", function(){
        haptic("light");
        state.category = cat;
        renderTabs();
        renderGrid();
        setTimeout(function(){
          var activeBtn = wrap.querySelector(".tab-btn.active");
          if(activeBtn) activeBtn.scrollIntoView({behavior:"smooth", inline:"center", block:"nearest"});
        }, 10);
      });
      wrap.appendChild(btn);
    });
  }

  document.getElementById("newOnlyChip").addEventListener("click", function(){
    state.newOnly = !state.newOnly;
    this.classList.toggle("active", state.newOnly);
    haptic("light");
    renderGrid();
  });

  var priceRange = document.getElementById("priceRange");
  var priceFill = document.getElementById("priceFill");
  var priceValueLabel = document.getElementById("priceValueLabel");
  function updatePriceFill(){
    requestAnimationFrame(function(){
      var pct = (priceRange.value - priceRange.min) / (priceRange.max - priceRange.min) * 100;
      priceFill.style.width = pct + "%";
    });
  }
  priceRange.addEventListener("input", function(){
    state.maxPrice = parseInt(priceRange.value, 10);
    priceValueLabel.textContent = state.maxPrice >= MAX_PRICE ? formatPrice(MAX_PRICE) : formatPrice(state.maxPrice);
    updatePriceFill();
    renderGrid();
  });
  updatePriceFill();

  var volumeChip = document.getElementById("volumeChip");
  var volumeChipLabel = document.getElementById("volumeChipLabel");
  var volumeMenu = document.getElementById("volumeMenu");
  var VOLUME_LABELS = { any:"Объём", small:"Малый", medium:"Средний", large:"Большой" };
  volumeChip.addEventListener("click", function(e){
    e.stopPropagation();
    volumeMenu.classList.toggle("open");
  });
  document.addEventListener("click", function(e){
    if(!volumeMenu.contains(e.target) && e.target !== volumeChip && !volumeChip.contains(e.target)){
      volumeMenu.classList.remove("open");
    }
  });
  volumeMenu.querySelectorAll(".volume-option").forEach(function(opt){
    opt.addEventListener("click", function(){
      state.volume = opt.getAttribute("data-value");
      volumeMenu.querySelectorAll(".volume-option").forEach(function(o){ o.classList.remove("selected"); });
      opt.classList.add("selected");
      volumeChipLabel.textContent = VOLUME_LABELS[state.volume];
      volumeChip.classList.toggle("active", state.volume !== "any");
      volumeMenu.classList.remove("open");
      haptic("light");
      renderGrid();
    });
  });

  var searchInput = document.getElementById("searchInput");
  var searchBox = document.getElementById("searchBox");
  var searchClear = document.getElementById("searchClear");
  searchInput.addEventListener("input", function(){
    state.search = searchInput.value.trim().toLowerCase();
    searchClear.style.display = state.search ? "flex" : "none";
    renderGrid();
  });
  searchInput.addEventListener("focus", function(){ searchBox.classList.add("focused"); });
  searchInput.addEventListener("blur", function(){ searchBox.classList.remove("focused"); });
  searchClear.addEventListener("click", function(){
    searchInput.value = ""; state.search = ""; searchClear.style.display = "none";
    renderGrid(); searchInput.focus();
  });

  function parseVolumeNumber(volStr){
    if(!volStr) return null;
    var s = volStr.toLowerCase().replace(",", ".");
    var m = s.match(/([\d.]+)\s*(л|l)\b/);
    if(m) return parseFloat(m[1]) * 1000;
    m = s.match(/([\d.]+)\s*(кг|kg)\b/);
    if(m) return parseFloat(m[1]) * 1000;
    m = s.match(/([\d.]+)/);
    if(m) return parseFloat(m[1]);
    return null;
  }
  function volumeBucket(volStr){
    var n = parseVolumeNumber(volStr);
    if(n === null) return null;
    if(n < 150) return "small";
    if(n <= 500) return "medium";
    return "large";
  }

  function buildCard(p, idx){
    var qty = cart[p.id] || 0;
    var isFav = !!favorites[p.id];
    var card = document.createElement("div");
    card.className = "card";
    card.setAttribute("data-card-id", p.id);
    card.style.animationDelay = (Math.min(idx,12) * 0.045) + "s";

    var imgWrap = document.createElement("div");
    imgWrap.className = "card-img-wrap";

    var badgeRow = document.createElement("div");
    badgeRow.className = "badge-row";
    if(p.isNew){ var nb = document.createElement("span"); nb.className="badge new"; nb.textContent="Новинка"; badgeRow.appendChild(nb); }
    if(p.outOfStock){ var ob = document.createElement("span"); ob.className="badge oos"; ob.textContent="Нет в наличии"; badgeRow.appendChild(ob); }
    imgWrap.appendChild(badgeRow);

    var favBtn = document.createElement("button");
    favBtn.className = "fav-btn" + (isFav ? " active" : "");
    favBtn.setAttribute("aria-label", "Добавить в избранное");
    favBtn.innerHTML = '<svg width="15" height="15" viewBox="0 0 24 24" fill="' + (isFav ? "currentColor" : "none") + '" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>';
    favBtn.addEventListener("click", function(e){
      e.preventDefault(); e.stopPropagation();
      favorites[p.id] = !favorites[p.id];
      saveFav(); haptic("light");
      var isNowFav = !!favorites[p.id];
      favBtn.style.transform = "scale(1.3)";
      setTimeout(function(){
        favBtn.style.transform = "";
        favBtn.className = "fav-btn" + (isNowFav ? " active" : "");
        favBtn.innerHTML = '<svg width="15" height="15" viewBox="0 0 24 24" fill="' + (isNowFav ? "currentColor" : "none") + '" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>';
      }, 80);
      if(state.screen === "favorites" && !isNowFav){
        var parentCard = favBtn.closest(".card");
        if(parentCard){
          parentCard.style.transition = "opacity .25s ease, transform .25s ease";
          parentCard.style.opacity = "0";
          parentCard.style.transform = "scale(0.92)";
          setTimeout(function(){ renderFavorites(); }, 250);
        }
      }
    });
    imgWrap.appendChild(favBtn);

    if(p.image){
      var img = document.createElement("img");
      img.src = p.image; img.alt = p.title; img.loading = "lazy";
      imgWrap.appendChild(img);
    } else {
      var ni = document.createElement("div");
      ni.className = "no-image";
      ni.innerHTML = '<svg width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2"></rect><circle cx="9" cy="9" r="2"></circle><path d="M21 15l-5-5L5 21"></path></svg>';
      imgWrap.appendChild(ni);
    }

    var info = document.createElement("div");
    info.className = "card-info";
    info.innerHTML =
      '<p class="card-cat">' + (p.category || "") + '</p>' +
      '<h3 class="card-title">' + p.title + '</h3>' +
      (p.volume ? '<p class="card-vol">' + p.volume + '</p>' : '') +
      '<p class="card-price">' + formatPrice(p.price) + '</p>';

    var actions = document.createElement("div");
    actions.className = "card-actions";
    if(p.outOfStock){
      actions.innerHTML = '<button class="add-btn disabled" disabled>Нет в продаже</button>';
    } else if(qty > 0){
      actions.innerHTML =
        '<div class="qty-row">' +
          '<div class="qty-control">' +
            '<button class="qty-btn" data-action="dec" data-id="' + p.id + '"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><line x1="5" y1="12" x2="19" y2="12"></line></svg></button>' +
            '<span class="qty-val">' + qty + '</span>' +
            '<button class="qty-btn" data-action="inc" data-id="' + p.id + '"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg></button>' +
          '</div>' +
          '<button class="add-btn in-cart" data-action="open-cart"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>В корзине</button>' +
        '</div>';
    } else {
      actions.innerHTML =
        '<button class="add-btn" data-action="add" data-id="' + p.id + '"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><circle cx="9" cy="21" r="1"></circle><circle cx="20" cy="21" r="1"></circle><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path></svg>В корзину</button>';
    }

    card.appendChild(imgWrap);
    card.appendChild(info);
    card.appendChild(actions);

    card.addEventListener("click", function(e){
      if(e.target.closest('.fav-btn') || e.target.closest('.add-btn') || e.target.closest('.qty-control')) return;
      openProduct(p.id);
    });

    return card;
  }

  function attachCardActions(container, onChange){
    if(container._cardDelegate) container.removeEventListener("click", container._cardDelegate);
    container._cardDelegate = function(e){
      var btn = e.target.closest("[data-action]");
      if(!btn) return;
      e.stopPropagation();
      var action = btn.getAttribute("data-action");
      var id = btn.getAttribute("data-id");
      if(action === "add"){
        if(!cart[id]){ cart[id] = 1; saveCart(); haptic("light"); showToast("Добавлено в корзину"); updateCartBadges(); onChange(id, 1); }
      } else if(action === "inc"){ cart[id] = (cart[id] || 0) + 1; saveCart(); haptic("light"); onChange(id, 1); }
      else if(action === "dec"){ cart[id] = Math.max(0, (cart[id]||0) - 1); if(cart[id] === 0) delete cart[id]; saveCart(); haptic("light"); onChange(id, -1); }
      else if(action === "open-cart"){ goScreen("cart"); }
    };
    container.addEventListener("click", container._cardDelegate);
  }

  function filteredProducts(){
    return PRODUCTS.filter(function(p){
      if(!p.title || p.price <= 1) return false;
      if(p.category === "Сыродавленные масла и жмыхи") return false;
      if(state.category !== "Все" && p.category !== state.category) return false;
      if(p.price > state.maxPrice) return false;
      if(state.search && p.title.toLowerCase().indexOf(state.search) === -1) return false;
      if(state.newOnly && !p.isNew) return false;
      if(state.volume !== "any" && volumeBucket(p.volume) !== state.volume) return false;
      return true;
    });
  }

  function renderGrid(){
    var grid = document.getElementById("grid");
    var list = filteredProducts();
    grid.innerHTML = "";
    list.forEach(function(p, idx){ grid.appendChild(buildCard(p, idx)); });
    document.getElementById("catalogEmpty").style.display = list.length ? "none" : "block";
    attachCardActions(grid, function(id){ if(id) updateCardInGrid(grid, id); updateCartBadges(); });
  }

  function updateCardInGrid(grid, id){
    if(!id) return;
    var cardEl = grid.querySelector('[data-card-id="' + id + '"]');
    if(cardEl){ var newCard = buildCard(findProduct(id), 0); newCard.style.animation = "none"; cardEl.parentNode.replaceChild(newCard, cardEl); }
  }

  function renderFavorites(){
    var grid = document.getElementById("favGrid");
    var ids = Object.keys(favorites).filter(function(id){ return favorites[id]; });
    var list = PRODUCTS.filter(function(p){ return ids.indexOf(p.id) !== -1; });
    grid.innerHTML = "";
    list.forEach(function(p, idx){ grid.appendChild(buildCard(p, idx)); });
    document.getElementById("favEmpty").style.display = list.length ? "none" : "block";
    attachCardActions(grid, function(id){ if(id){ updateCardInGrid(grid, id); } updateCartBadges(); });
  }

  function openProduct(id){
    state.currentProductId = id;
    window._pdVI = 0;
    renderProductScreen();
    goScreen("product");
    haptic("light");
  }

  function renderProductScreen(){
    var p = findProduct(state.currentProductId);
    if(!p) return;
    var isFav = !!favorites[p.id];
    var qty = cart[p.id] || 0;

    var hero = document.getElementById("pdHero");
    hero.innerHTML =
      (p.image ? '<img src="'+p.image+'" alt="'+p.title+'"/>' :
        '<div class="no-image"><svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2"></rect><circle cx="9" cy="9" r="2"></circle><path d="M21 15l-5-5L5 21"></path></svg></div>') +
      '<button class="pd-fav' + (isFav ? ' active' : '') + '" id="pdFavBtn" aria-label="Избранное">' +
        '<svg width="18" height="18" viewBox="0 0 24 24" fill="' + (isFav?"currentColor":"none") + '" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>' +
      '</button>';

    document.getElementById("pdFavBtn").addEventListener("click", function(){
      favorites[p.id] = !favorites[p.id];
      saveFav(); haptic("light");
      renderProductScreen();
    });

    var body = document.getElementById("pdBody");
    body.innerHTML =
      '<p class="pd-cat">' + (p.category || "") + '</p>' +
      '<h1 class="pd-title">' + p.title + '</h1>' +
      '<div class="pd-meta">' +
        (p.volume ? '<span class="pd-vol-tag">' + p.volume + '</span>' : '') +
        (p.isNew ? '<span class="pd-vol-tag" style="color:var(--pine-deep);border-color:var(--pine-soft);background:var(--pine-soft);">Новинка</span>' : '') +
      '</div>' +
      '<p class="pd-price">' + formatPrice(p.price) + '</p>' +
      '<div class="pd-desc">' + (p.desc || 'Описание скоро появится.') + '</div>';

    var actionsBar = document.getElementById("pdActionsBar");
    if(p.outOfStock){
      actionsBar.innerHTML = '<button class="pd-add-btn" disabled style="background:var(--line-strong); color:var(--hint);">Нет в продаже</button>';
    } else if(qty > 0){
      actionsBar.innerHTML =
        '<div class="qty-control">' +
          '<button class="qty-btn" data-action="dec" data-id="' + p.id + '"><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><line x1="5" y1="12" x2="19" y2="12"></line></svg></button>' +
          '<span class="qty-val">' + qty + '</span>' +
          '<button class="qty-btn" data-action="inc" data-id="' + p.id + '"><svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg></button>' +
        '</div>' +
        '<button class="pd-add-btn in-cart" data-action="open-cart"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>Перейти в корзину</button>';
    } else {
      actionsBar.innerHTML =
        '<button class="pd-add-btn" data-action="add" data-id="' + p.id + '"><svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><circle cx="9" cy="21" r="1"></circle><circle cx="20" cy="21" r="1"></circle><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path></svg>В корзину</button>';
    }
    attachCardActions(actionsBar, function(){ renderProductScreen(); renderGrid(); updateCartBadges(); });
  }

  document.getElementById("pdBackBtn").addEventListener("click", function(){ goScreen("catalog"); });
  document.getElementById("favBackBtn").addEventListener("click", function(){ haptic("light"); goScreen("catalog"); });
  document.getElementById("cartBackBtn").addEventListener("click", function(){ haptic("light"); goScreen("catalog"); });

  function updateCartBadges(){
    var count = cartCount();
    var dot = document.getElementById("topCartDot");
    var navBadge = document.getElementById("navCartBadge");
    var cartBtn = document.getElementById("topCartBtn");
    if(count > 0){ dot.style.display="flex"; dot.textContent=count; navBadge.style.display="flex"; navBadge.textContent=count; }
    else { dot.style.display="none"; navBadge.style.display="none"; }
    if(cartBtn){ cartBtn.style.transform="scale(1.18)"; setTimeout(function(){cartBtn.style.transform="";}, 200); }
  }

  function renderCartList(){
    var listEl = document.getElementById("cartList");
    var ids = Object.keys(cart);
    listEl.innerHTML = "";
    ids.forEach(function(id){
      var p = findProduct(id);
      if(!p) return;
      var row = document.createElement("div");
      row.className = "cart-item";
      row.innerHTML =
        (p.image ? '<img src="'+p.image+'" alt="'+p.title+'"/>' : '<div class="cart-item-img-empty"></div>') +
        '<div class="cart-item-info"><p class="t">' + p.title + '</p><p class="p">' + formatPrice(p.price) + ' · ' + cart[id] + ' шт.</p></div>' +
        '<div class="qty-control">' +
          '<button class="qty-btn" data-action="dec" data-id="'+id+'"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><line x1="5" y1="12" x2="19" y2="12"></line></svg></button>' +
          '<span class="qty-val">' + cart[id] + '</span>' +
          '<button class="qty-btn" data-action="inc" data-id="'+id+'"><svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg></button>' +
        '</div>';
      row.addEventListener("click", function(e){ if(e.target.closest('.qty-control')) return; openProduct(id); });
      listEl.appendChild(row);
    });
    attachCardActions(listEl, function(){ renderCartList(); renderCartSummary(); renderGrid(); updateCartBadges(); });
    document.getElementById("cartEmpty").style.display = ids.length ? "none" : "block";
  }

  function renderCartSummary(){
    var count = cartCount(), total = cartTotal();
    document.getElementById("cartSummaryBlock").style.display = count ? "block" : "none";
    document.getElementById("goCheckoutBtn").style.display = count ? "flex" : "none";
    document.getElementById("sumCount").textContent = count;
    document.getElementById("sumTotal").textContent = formatPrice(total);
    document.getElementById("clearCartBtn").style.display = count ? "flex" : "none";
  }

  document.getElementById("clearCartBtn").addEventListener("click", function(){
    if(!Object.keys(cart).length) return;
    haptic("medium");
    var items = document.querySelectorAll(".cart-item");
    items.forEach(function(item, i){
      item.style.transition = "opacity .25s ease " + (i*0.04) + "s, transform .25s ease " + (i*0.04) + "s";
      item.style.opacity = "0";
      item.style.transform = "translateX(30px)";
    });
    setTimeout(function(){ cart = {}; saveCart(); renderCartList(); renderCartSummary(); updateCartBadges(); renderGrid(); showToast("Корзина очищена"); }, items.length * 40 + 260);
  });

  function showCartView(){
    document.getElementById("cartView").style.display = "block";
    document.getElementById("checkoutView").style.display = "none";
    document.getElementById("successView").style.display = "none";
    renderCartList(); renderCartSummary();
  }
  function showCheckoutView(){
    document.getElementById("cartView").style.display = "none";
    document.getElementById("checkoutView").style.display = "block";
    document.getElementById("successView").style.display = "none";
    loadCustomerData();
    updateSubmitLabel();
  }
  function showSuccessView(){
    document.getElementById("cartView").style.display = "none";
    document.getElementById("checkoutView").style.display = "none";
    document.getElementById("successView").style.display = "block";
  }

  document.getElementById("goCheckoutBtn").addEventListener("click", function(){ haptic("light"); showCheckoutView(); });
  document.getElementById("backToCatalogBtn").addEventListener("click", function(){ goScreen("catalog"); });

  function updateSubmitLabel(){
    var total = cartTotal() + orderDraft.deliveryPrice;
    document.getElementById("submitOrderLabel").textContent = "Оформить заказ на " + formatPrice(total);
  }

  document.querySelectorAll('.option-card[data-group="delivery"]').forEach(function(card){
    card.addEventListener("click", function(){
      document.querySelectorAll('.option-card[data-group="delivery"]').forEach(function(c){ c.classList.remove("selected"); });
      card.classList.add("selected");
      orderDraft.delivery = card.getAttribute("data-value");
      orderDraft.deliveryPrice = parseInt(card.getAttribute("data-price"), 10) || 0;
      haptic("light"); updateSubmitLabel();
    });
  });
  document.querySelectorAll('.option-card[data-group="payment"]').forEach(function(card){
    card.addEventListener("click", function(){
      document.querySelectorAll('.option-card[data-group="payment"]').forEach(function(c){ c.classList.remove("selected"); });
      card.classList.add("selected");
      orderDraft.payment = card.getAttribute("data-value");
      haptic("light");
    });
  });

  var EMAIL_RE = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  var PHONE_RE = /^[\d\s\-\+\(\)]{10,18}$/;
  var ZIP_RE = /^\d{6}$/;

  function validateField(id){
    var el = document.getElementById(id);
    var val = el.value.trim();
    if(!val) return "empty";
    if(id === "f_email" && !EMAIL_RE.test(val)) return "format";
    if(id === "f_phone" && !PHONE_RE.test(val)) return "format";
    if(id === "f_zip" && !ZIP_RE.test(val)) return "format";
    return null;
  }
  function markFieldError(id){
    var fm = document.getElementById(id);
    fm.style.borderColor = "var(--danger)";
    fm.focus();
    setTimeout(function(){ fm.style.borderColor = ""; }, 1500);
  }
  ["f_email","f_phone","f_zip"].forEach(function(id){
    var el = document.getElementById(id);
    if(!el) return;
    el.addEventListener("blur", function(){
      if(el.value.trim() && validateField(id) === "format"){
        el.style.borderColor = "var(--danger)";
      } else {
        el.style.borderColor = "";
      }
    });
  });

  var CUSTOMER_FIELDS = ["f_name","f_phone","f_email","f_country","f_city","f_address","f_zip"];
  function saveCustomerData(){
    try{
      var data = {};
      CUSTOMER_FIELDS.forEach(function(id){ data[id] = document.getElementById(id).value; });
      localStorage.setItem('mh_customer_v1', JSON.stringify(data));
    }catch(e){}
  }
  function loadCustomerData(){
    try{
      var raw = localStorage.getItem('mh_customer_v1');
      if(!raw) return;
      var data = JSON.parse(raw);
      CUSTOMER_FIELDS.forEach(function(id){
        if(data[id] && document.getElementById(id)) document.getElementById(id).value = data[id];
      });
    }catch(e){}
  }

  document.getElementById("submitOrderBtn").addEventListener("click", function(){
    var required = ["f_name","f_phone","f_email","f_country","f_city","f_address","f_zip"];
    for(var i=0; i<required.length; i++){
      var problem = validateField(required[i]);
      if(problem === "empty"){
        haptic("medium");
        showToast("Заполните все обязательные поля");
        markFieldError(required[i]);
        return;
      }
      if(problem === "format"){
        haptic("medium");
        var messages = {
          f_email: "Проверьте формат e-mail (например, you@example.com)",
          f_phone: "Проверьте формат телефона (например, +7 900 123-45-67)",
          f_zip: "Индекс должен состоять из 6 цифр"
        };
        showToast(messages[required[i]] || "Проверьте правильность заполнения поля");
        markFieldError(required[i]);
        return;
      }
    }
    haptic("medium");
    saveCustomerData();

    var total = cartTotal() + orderDraft.deliveryPrice;
    var orderId = "ORD_" + Date.now() + "_" + Math.random().toString(36).substr(2, 4);
    var orderItems = Object.keys(cart).map(function(id){
      var p = findProduct(id);
      return { id: id, title: p ? p.title : id, qty: cart[id], price: p ? p.price : null };
    });

    var orderData = {
      action: 'create_payment',
      order_id: orderId,
      amount: total,
      items: orderItems,
      delivery: orderDraft.delivery,
      payment: orderDraft.payment,
      customer: {
        name: document.getElementById("f_name").value,
        phone: document.getElementById("f_phone").value,
        email: document.getElementById("f_email").value,
        country: document.getElementById("f_country").value,
        city: document.getElementById("f_city").value,
        address: document.getElementById("f_address").value,
        zip: document.getElementById("f_zip").value
      }
    };

    if (window.Telegram && window.Telegram.WebApp && window.Telegram.WebApp.initData) {
      submitOrderToBot(orderData);
    } else {
      showToast("Откройте приложение через Telegram");
    }
  });

  var BOT_ORDER_URL = "https://bot-1784478518-9917-fretix.bothost.tech/webhook/order";
  var ORDER_SECRET = "MpfdrZaIIVAN14xJTNQ4Imvx_a6S4rGooddccGdJCat";
  var submitBtnEl = document.getElementById("submitOrderBtn");

  function setSubmitLoading(isLoading){
    if(!submitBtnEl) return;
    submitBtnEl.disabled = isLoading;
    submitBtnEl.style.opacity = isLoading ? "0.6" : "";
    submitBtnEl.style.pointerEvents = isLoading ? "none" : "";
  }

  function submitOrderToBot(orderData){
    var tg = window.Telegram.WebApp;
    setSubmitLoading(true);
    var payload = {
      order_id: orderData.order_id,
      amount: orderData.amount,
      customer: orderData.customer,
      items: orderData.items,
      delivery: orderData.delivery,
      payment: orderData.payment,
      init_data: tg.initData
    };
    fetch(BOT_ORDER_URL, {
      method: "POST",
      headers: { "Content-Type": "application/json", "X-Order-Secret": ORDER_SECRET },
      body: JSON.stringify(payload)
    })
      .then(function(resp){ return resp.json(); })
      .then(function(result){
        setSubmitLoading(false);
        if(result && result.ok){
          showToast("Заказ создан! Ссылка на оплату отправлена вам в Telegram.");
          cart = {};
          saveCart();
          updateCartBadges();
          showSuccessView();
          setTimeout(function(){
            if (window.Telegram && window.Telegram.WebApp) {
              window.Telegram.WebApp.close();
            }
          }, 2000);
        } else {
          haptic("medium");
          showToast("Ошибка оформления заказа: " + ((result && result.error) || "попробуйте позже"));
        }
      })
      .catch(function(err){
        setSubmitLoading(false);
        haptic("medium");
        console.error("Ошибка отправки заказа:", err);
        showToast("Не удалось связаться с сервером. Попробуйте позже.");
      });
  }

  function renderProfile(){
    if(auth){
      document.getElementById("authView").style.display = "none";
      document.getElementById("profileView").style.display = "block";
      document.getElementById("profileName").textContent = auth.name || "Без имени";
      document.getElementById("profileSub").textContent = auth.sub || "";
      var tag = document.getElementById("profileAuthTag");
      tag.className = "auth-tag tg"; tag.textContent = "Вход через Telegram";
      var av = document.getElementById("profileAvatar");
      av.innerHTML = auth.photo ? ('<img src="'+auth.photo+'" alt=""/>') :
        '<svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>';
    } else {
      document.getElementById("authView").style.display = "block";
      document.getElementById("profileView").style.display = "none";
    }
  }

  document.getElementById("authTelegramBtn").addEventListener("click", function(){
    if (window.Telegram && window.Telegram.WebApp) {
      var user = window.Telegram.WebApp.initDataUnsafe && window.Telegram.WebApp.initDataUnsafe.user;
      if(user){
        auth = { type:"telegram", name: user.first_name || "Пользователь", sub: user.username ? "@" + user.username : "Telegram", photo: user.photo_url || null };
        saveAuth(); renderProfile(); showToast("Вход выполнен"); haptic("light");
      } else {
        showToast("Откройте приложение через Telegram");
      }
    } else {
      showToast("Откройте приложение через Telegram");
    }
  });

  document.getElementById("menuFav").addEventListener("click", function(){ goScreen("favorites"); });
  document.getElementById("menuOrders").addEventListener("click", function(){ showToast("Раздел в разработке"); });
  document.getElementById("menuLogout").addEventListener("click", function(){
    auth = null; saveAuth(); renderProfile(); showToast("Вы вышли из аккаунта");
  });

  function init(){
    try{
      if(window.Telegram && window.Telegram.WebApp){
        window.Telegram.WebApp.ready();
        window.Telegram.WebApp.expand();
      }
    }catch(e){}

    loadState();
    renderLogo();
    checkAdmin();

    loadProductsFromDB().then(function() {
      updateCartBadges();
    });

    renderProfile();
    if(window.Telegram && window.Telegram.WebApp){
      var user = window.Telegram.WebApp.initDataUnsafe && window.Telegram.WebApp.initDataUnsafe.user;
      if(user && !auth){
        auth = { type:"telegram", name: user.first_name || "Пользователь", sub: user.username ? "@" + user.username : "Telegram", photo: user.photo_url || null };
        saveAuth(); renderProfile();
      }
    }
    setupSecretAdminEntry();
  }

  // ==================== СЕКРЕТНЫЙ ВХОД В АДМИНКУ ====================
  var logoTapCount = 0;
  var logoTapTimer = null;
  function setupSecretAdminEntry(){
    var logo = document.getElementById("logoMark");
    if(!logo) return;
    logo.addEventListener("click", function(){
      logoTapCount++;
      clearTimeout(logoTapTimer);
      logoTapTimer = setTimeout(function(){ logoTapCount = 0; }, 2000);
      if(logoTapCount >= 5){
        logoTapCount = 0;
        haptic("medium");
        document.getElementById("adminLoginModal").style.display = "flex";
      }
    });
  }

  // ==================== АДМИН-ПАНЕЛЬ ====================
  var ADMIN_EMAIL = "Yegoro@mail.ru";

  function openAdminLogin(){
    document.getElementById("adminLoginModal").style.display = "flex";
  }
  function closeAdminLogin(){
    document.getElementById("adminLoginModal").style.display = "none";
    document.getElementById("adminEmail").value = "";
    document.getElementById("adminPassword").value = "";
  }

  async function loginAdmin(){
    var email = document.getElementById("adminEmail").value.trim();
    var password = document.getElementById("adminPassword").value;
    if(!email || !password){ showToast("Заполните email и пароль"); return; }
    var { data, error } = await db.auth.signInWithPassword({ email: email, password: password });
    if(error){ showToast("Ошибка: " + error.message); return; }
    if((data.user.email || "").toLowerCase() !== ADMIN_EMAIL.toLowerCase()){
      showToast("Нет доступа");
      await db.auth.signOut();
      return;
    }
    showToast("Вход выполнен");
    closeAdminLogin();
    document.getElementById("adminEditBtn").style.display = "flex";
    openAdminPanel();
  }

  async function logoutAdmin(){
    await db.auth.signOut();
    document.getElementById("adminEditBtn").style.display = "none";
    closeAdminPanel();
    showToast("Вы вышли");
  }

  function openAdminPanel(){
    renderAdminProducts();
    document.getElementById("adminModal").style.display = "block";
  }
  function closeAdminPanel(){
    document.getElementById("adminModal").style.display = "none";
  }

  function renderAdminProducts(){
    var list = document.getElementById("adminProductsList");
    list.innerHTML = "";
    if(PRODUCTS.length === 0){
      list.innerHTML = '<p style="text-align:center;color:#888;font-size:13px;">Товаров нет</p>';
      return;
    }
    PRODUCTS.forEach(function(p){
      var row = document.createElement("div");
      row.style.cssText = "border:1px solid #eee;border-radius:12px;padding:12px;margin-bottom:10px;";
      row.innerHTML =
        '<div style="display:flex;gap:10px;align-items:center;margin-bottom:10px;">' +
          '<img src="' + (p.image || '') + '" style="width:50px;height:50px;object-fit:contain;border-radius:8px;background:#f5f5f5;padding:4px;">' +
          '<div style="flex:1;min-width:0;">' +
            '<div style="font-weight:600;font-size:13px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;">' + p.title + '</div>' +
            '<div style="font-size:11px;color:#888;">' + p.category + ' • ' + p.price + ' ₽</div>' +
          '</div>' +
        '</div>' +
        '<div style="display:flex;gap:6px;flex-wrap:wrap;">' +
          '<button onclick="editProduct(\'' + p.id + '\')" style="flex:1;padding:8px;border-radius:8px;background:#C8954B;color:#fff;border:none;font-size:12px;cursor:pointer;font-weight:600;">Изменить</button>' +
          '<button onclick="changePrice(\'' + p.id + '\')" style="flex:1;padding:8px;border-radius:8px;background:#2E4A35;color:#fff;border:none;font-size:12px;cursor:pointer;font-weight:600;">Цена</button>' +
          '<button onclick="uploadProductImage(\'' + p.id + '\')" style="flex:1;padding:8px;border-radius:8px;background:#4A6FA5;color:#fff;border:none;font-size:12px;cursor:pointer;font-weight:600;">Фото</button>' +
          '<button onclick="deleteProduct(\'' + p.id + '\')" style="flex:1;padding:8px;border-radius:8px;background:#C0473B;color:#fff;border:none;font-size:12px;cursor:pointer;font-weight:600;">Удалить</button>' +
        '</div>';
      list.appendChild(row);
    });
  }

  async function changePrice(id){
    var p = PRODUCTS.find(function(x){ return String(x.id) === String(id); });
    if(!p) return;
    var newPrice = prompt("Новая цена (₽):", p.price);
    if(!newPrice) return;
    var priceNum = parseInt(newPrice, 10);
    if(isNaN(priceNum) || priceNum <= 0){ showToast("Введите число"); return; }
    var { error } = await db.from("products").update({ price: priceNum }).eq("id", id);
    if(error){ showToast("Ошибка: " + error.message); }
    else { showToast("Цена обновлена"); await loadProductsFromDB(); renderAdminProducts(); }
  }

  async function editProduct(id){
    var p = PRODUCTS.find(function(x){ return String(x.id) === String(id); });
    if(!p) return;
    var newTitle = prompt("Название:", p.title);
    if(newTitle === null) return;
    var newDescr = prompt("Описание:", p.desc);
    if(newDescr === null) return;
    var newVolume = prompt("Объём:", p.volume);
    if(newVolume === null) return;
    var { error } = await db.from("products").update({ title: newTitle, descr: newDescr, volume: newVolume }).eq("id", id);
    if(error){ showToast("Ошибка: " + error.message); }
    else { showToast("Товар обновлён"); await loadProductsFromDB(); renderAdminProducts(); }
  }

  async function deleteProduct(id){
    if(!confirm("Удалить товар?")) return;
    var { error } = await db.from("products").delete().eq("id", id);
    if(error){ showToast("Ошибка: " + error.message); }
    else { showToast("Товар удалён"); await loadProductsFromDB(); renderAdminProducts(); }
  }

  async function addNewProduct(){
    var title = prompt("Название товара:");
    if(!title) return;
    var category = prompt("Категория:");
    if(!category) return;
    var price = prompt("Цена (₽):");
    if(!price) return;
    var volume = prompt("Объём (например, 250 мл):") || "";
    var descr = prompt("Описание:") || "";
    var slug = title.toLowerCase().replace(/\s+/g, "-").replace(/[^a-z0-9\-]/g, "") + "-" + Date.now();
    var { error } = await db.from("products").insert({ slug: slug, title: title, category: category, price: parseInt(price, 10), volume: volume, descr: descr, image: "" });
    if(error){ showToast("Ошибка: " + error.message); }
    else { showToast("Товар добавлен"); await loadProductsFromDB(); renderAdminProducts(); }
  }

  function uploadProductImage(id){
    var input = document.createElement("input");
    input.type = "file";
    input.accept = "image/*";
    input.onchange = async function(e){
      var file = e.target.files[0];
      if(!file) return;
      showToast("Загрузка...");
      var fileName = "product_" + id + "_" + Date.now() + ".jpg";
      var { data, error } = await db.storage.from("product-images").upload(fileName, file, { upsert: true });
      if(error){ showToast("Ошибка: " + error.message); return; }
      var { data: urlData } = db.storage.from("product-images").getPublicUrl(fileName);
      var { error: updateError } = await db.from("products").update({ image: urlData.publicUrl }).eq("id", id);
      if(updateError){ showToast("Ошибка: " + updateError.message); }
      else { showToast("Картинка обновлена"); await loadProductsFromDB(); renderAdminProducts(); }
    };
    input.click();
  }

  async function checkAdmin(){
    var { data: { session } } = await db.auth.getSession();
    if(session && session.user.email && session.user.email.toLowerCase() === ADMIN_EMAIL.toLowerCase()){
      var btn = document.getElementById("adminEditBtn");
      if(btn) btn.style.display = "flex";
    }
  }

  // Экспорт функций
  window.editProduct = editProduct;
  window.changePrice = changePrice;
  window.deleteProduct = deleteProduct;
  window.uploadProductImage = uploadProductImage;
  window.addNewProduct = addNewProduct;
  window.loginAdmin = loginAdmin;
  window.logoutAdmin = logoutAdmin;

  // Обработчики
  document.addEventListener("DOMContentLoaded", function(){
    var adminEditBtn = document.getElementById("adminEditBtn");
    if(adminEditBtn){
      adminEditBtn.addEventListener("click", function(){
        db.auth.getSession().then(function(res){
          if(res.data.session && res.data.session.user.email &&
             res.data.session.user.email.toLowerCase() === ADMIN_EMAIL.toLowerCase()){
            openAdminPanel();
          } else {
            openAdminLogin();
          }
        });
      });
    }
    var loginSubmitBtn = document.getElementById("adminLoginSubmit");
    var loginCancelBtn = document.getElementById("adminLoginCancel");
    var adminCloseBtnEl = document.getElementById("adminCloseBtn");
    var adminLogoutBtnEl = document.getElementById("adminLogoutBtn");
    var adminAddBtnEl = document.getElementById("adminAddBtn");

    if(loginSubmitBtn) loginSubmitBtn.addEventListener("click", loginAdmin);
    if(loginCancelBtn) loginCancelBtn.addEventListener("click", closeAdminLogin);
    if(adminCloseBtnEl) adminCloseBtnEl.addEventListener("click", closeAdminPanel);
    if(adminLogoutBtnEl) adminLogoutBtnEl.addEventListener("click", logoutAdmin);
    if(adminAddBtnEl) adminAddBtnEl.addEventListener("click", addNewProduct);

    init();
  });

})();
</script>
</body>
</html>
