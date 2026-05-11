<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>TesterUp – Exclusive Rewards</title>
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@400;500;600;700;800;900&family=DM+Sans:ital,wght@0,400;0,500;0,600;1,400&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}

:root{
  --bg:#06090f;
  --card:#0c1220;
  --card2:#101828;
  --card3:#131d2e;
  --orange:#f97316;
  --orange2:#fb923c;
  --orange3:#fdba74;
  --og:rgba(249,115,22,0.32);
  --og2:rgba(249,115,22,0.15);
  --text:#f1f5f9;
  --muted:#8da0b8;
  --muted2:#64748b;
  --border:rgba(249,115,22,0.16);
  --border2:rgba(255,255,255,0.06);
  --r:20px;
  --rs:14px;
}

html,body{
  min-height:100vh;
  background:var(--bg);
  font-family:'DM Sans',sans-serif;
  color:var(--text);
  display:flex;
  flex-direction:column;
  align-items:center;
  overflow-x:hidden;
  -webkit-font-smoothing:antialiased;
}

body::before{
  content:'';
  position:fixed;inset:0;
  background:
    radial-gradient(ellipse 90% 45% at 50% -5%,rgba(249,115,22,0.14) 0%,transparent 65%),
    radial-gradient(ellipse 50% 35% at 15% 105%,rgba(249,115,22,0.06) 0%,transparent 60%),
    radial-gradient(ellipse 50% 35% at 85% 100%,rgba(249,115,22,0.05) 0%,transparent 60%);
  pointer-events:none;z-index:0;
}

/* ═══ ELIGIBILITY LOADING SCREEN ═══ */
#eligScreen{
  position:fixed;inset:0;
  background:var(--bg);
  z-index:9999;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  padding:32px;
}

#eligScreen::before{
  content:'';
  position:absolute;inset:0;
  background:
    radial-gradient(ellipse 80% 50% at 50% 0%,rgba(249,115,22,0.16) 0%,transparent 60%),
    radial-gradient(ellipse 60% 40% at 50% 100%,rgba(249,115,22,0.08) 0%,transparent 60%);
  pointer-events:none;
}

.elig-logo{
  width:80px;height:80px;
  border-radius:22px;
  overflow:hidden;
  margin-bottom:28px;
  box-shadow:0 0 32px rgba(249,115,22,0.3),0 8px 32px rgba(0,0,0,0.6);
  animation:logo-float 3s ease-in-out infinite;
  position:relative;z-index:1;
}

.elig-logo img{width:80px;height:80px;object-fit:cover;display:block;border-radius:22px;}

.elig-spinner{
  width:48px;height:48px;
  border:3px solid rgba(249,115,22,0.12);
  border-top:3px solid var(--orange);
  border-radius:50%;
  animation:spin 0.9s linear infinite;
  margin-bottom:24px;
  box-shadow:0 0 18px rgba(249,115,22,0.25);
  position:relative;z-index:1;
}

@keyframes spin{to{transform:rotate(360deg)}}

.elig-title{
  font-family:'Sora',sans-serif;
  font-size:20px;
  font-weight:800;
  color:#fff;
  margin-bottom:8px;
  position:relative;z-index:1;
  letter-spacing:-0.3px;
}

.elig-msg{
  font-size:14px;
  color:var(--orange2);
  font-weight:600;
  min-height:22px;
  text-align:center;
  position:relative;z-index:1;
  transition:opacity 0.3s ease;
  margin-bottom:28px;
}

.elig-bar-wrap{
  width:240px;
  height:5px;
  background:rgba(255,255,255,0.06);
  border-radius:99px;
  overflow:hidden;
  position:relative;z-index:1;
}

.elig-bar{
  height:100%;
  border-radius:99px;
  background:linear-gradient(90deg,#ea580c,#f97316,#fb923c);
  box-shadow:0 0 12px rgba(249,115,22,0.6);
  width:0%;
  transition:width 0.5s ease;
  position:relative;
  overflow:hidden;
}

.elig-bar::after{
  content:'';
  position:absolute;top:0;bottom:0;
  width:50px;
  background:linear-gradient(90deg,transparent,rgba(255,255,255,0.4),transparent);
  animation:shimmer 1.2s linear infinite;
}

@keyframes shimmer{0%{left:-50px}100%{left:110%}}

/* ═══ REDIRECT LOADING OVERLAY ═══ */
#redirectOverlay{
  position:fixed;inset:0;
  background:rgba(6,9,15,0.97);
  z-index:9998;
  display:none;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  padding:32px;
  backdrop-filter:blur(8px);
}

#redirectOverlay.show{display:flex;animation:fadeIn 0.3s ease;}

@keyframes fadeIn{from{opacity:0}to{opacity:1}}

.redir-spinner{
  width:52px;height:52px;
  border:3px solid rgba(249,115,22,0.1);
  border-top:3px solid var(--orange);
  border-right:3px solid var(--orange2);
  border-radius:50%;
  animation:spin 0.8s linear infinite;
  margin-bottom:22px;
  box-shadow:0 0 22px rgba(249,115,22,0.3);
}

.redir-msg{
  font-family:'Sora',sans-serif;
  font-size:17px;
  font-weight:700;
  color:#fff;
  text-align:center;
  margin-bottom:8px;
  transition:opacity 0.3s ease;
}

.redir-sub{
  font-size:13px;
  color:var(--muted);
  text-align:center;
}

/* ═══ PAGE WRAP ═══ */
.page-wrap{
  width:100%;max-width:430px;
  min-height:100vh;
  display:flex;flex-direction:column;align-items:center;
  padding:0 0 40px;
  position:relative;z-index:1;
}

/* ═══ HEADER ═══ */
.header{
  width:100%;
  display:flex;flex-direction:column;align-items:center;
  padding:36px 24px 18px;
}

.logo-wrap{
  width:84px;height:84px;
  border-radius:24px;
  background:linear-gradient(135deg,#1c2c48 0%,#0c1220 100%);
  border:1.5px solid rgba(249,115,22,0.25);
  display:flex;align-items:center;justify-content:center;
  box-shadow:0 0 0 1px rgba(249,115,22,0.08),0 0 32px rgba(249,115,22,0.22),0 8px 32px rgba(0,0,0,0.6);
  margin-bottom:14px;
  position:relative;overflow:hidden;padding:0;
  animation:logo-float 4s ease-in-out infinite;
}

@keyframes logo-float{
  0%,100%{transform:translateY(0);box-shadow:0 0 32px rgba(249,115,22,0.22),0 8px 32px rgba(0,0,0,0.6);}
  50%{transform:translateY(-4px);box-shadow:0 0 44px rgba(249,115,22,0.32),0 14px 40px rgba(0,0,0,0.5);}
}

.logo-wrap img{width:84px;height:84px;border-radius:24px;object-fit:cover;display:block;}

.app-name{
  font-family:'Sora',sans-serif;
  font-size:24px;font-weight:900;letter-spacing:-0.6px;
  background:linear-gradient(90deg,#ffffff 0%,#fb923c 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  margin-bottom:8px;
}

.stars-row{display:flex;align-items:center;gap:6px;margin-bottom:5px;}
.stars{color:var(--orange);font-size:16px;letter-spacing:2px;text-shadow:0 0 12px rgba(249,115,22,0.6);}
.rating-num{font-size:13px;font-weight:700;color:var(--orange2);}
.rating-sub{font-size:13px;color:var(--muted);font-weight:500;margin-bottom:9px;}

.spots-badge{
  display:inline-flex;align-items:center;gap:5px;
  font-size:11.5px;font-weight:700;color:var(--orange2);letter-spacing:0.2px;
  text-shadow:0 0 12px rgba(249,115,22,0.5);
  animation:spots-pulse 2.2s ease-in-out infinite;
}

.spots-dot{
  width:7px;height:7px;border-radius:50%;
  background:var(--orange);box-shadow:0 0 8px var(--orange);
  animation:dot-blink 1.4s ease-in-out infinite;flex-shrink:0;
}

@keyframes dot-blink{0%,100%{opacity:1}50%{opacity:0.3}}
@keyframes spots-pulse{0%,100%{text-shadow:0 0 12px rgba(249,115,22,0.5)}50%{text-shadow:0 0 22px rgba(249,115,22,0.8)}}

/* ═══ PROGRESS ═══ */
.progress-wrap{width:calc(100% - 40px);margin:0 20px 22px;}

.progress-labels{display:flex;justify-content:space-between;align-items:center;margin-bottom:9px;}
.progress-label{font-size:11px;font-weight:700;color:var(--muted2);text-transform:uppercase;letter-spacing:1px;}
.step-indicator{
  font-family:'Sora',sans-serif;font-size:12px;font-weight:800;color:var(--orange2);
  background:rgba(249,115,22,0.1);padding:2px 9px;border-radius:99px;border:1px solid rgba(249,115,22,0.2);
}

.progress-track{
  width:100%;height:7px;background:rgba(255,255,255,0.06);
  border-radius:99px;overflow:hidden;position:relative;
}

.progress-fill{
  height:100%;border-radius:99px;
  background:linear-gradient(90deg,#ea580c,#f97316,#fb923c);
  box-shadow:0 0 14px rgba(249,115,22,0.7);
  transition:width 0.6s cubic-bezier(.4,0,.2,1);
  width:33%;position:relative;overflow:hidden;
}

.progress-fill::after{
  content:'';position:absolute;top:0;bottom:0;width:60px;
  background:linear-gradient(90deg,transparent,rgba(255,255,255,0.35),transparent);
  animation:shimmer 2s linear infinite;
}

/* ═══ CARD ═══ */
.card{
  width:calc(100% - 28px);
  background:var(--card);border-radius:var(--r);
  border:1px solid rgba(255,255,255,0.07);
  padding:26px 20px 22px;
  box-shadow:0 0 0 1px rgba(249,115,22,0.04),0 4px 6px rgba(0,0,0,0.3),0 20px 60px rgba(0,0,0,0.5);
  position:relative;overflow:hidden;
}

.card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent 0%,rgba(249,115,22,0.5) 50%,transparent 100%);
}

/* ═══ SLIDES ═══ */
.slide{display:none;}
.slide.active{display:block;animation:fadeUp 0.38s cubic-bezier(.4,0,.2,1);}

@keyframes fadeUp{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}

.urgency-badge{
  display:inline-flex;align-items:center;gap:5px;
  background:rgba(249,115,22,0.1);border:1px solid rgba(249,115,22,0.25);
  border-radius:99px;padding:5px 13px;
  font-size:12px;font-weight:700;color:var(--orange2);
  margin-bottom:14px;letter-spacing:0.1px;
}

.slide-headline{
  font-family:'Sora',sans-serif;font-size:20px;font-weight:800;
  line-height:1.25;color:#fff;margin-bottom:8px;letter-spacing:-0.4px;
}

.slide-sub{font-size:13.5px;color:var(--muted);line-height:1.55;margin-bottom:20px;font-style:italic;}

.orange-note{
  font-size:12.5px;color:var(--orange2);font-weight:600;
  margin-bottom:16px;display:flex;align-items:center;gap:5px;
}

.orange-note::before{content:'→';font-size:11px;opacity:0.7;}

/* ═══ BUTTONS ═══ */
.btn-group{display:flex;flex-direction:column;gap:11px;margin-bottom:20px;}

.choice-btn{
  width:100%;padding:16px 18px;border-radius:15px;
  background:linear-gradient(135deg,#111d30 0%,var(--card2) 100%);
  border:1.5px solid rgba(255,255,255,0.07);
  color:var(--text);font-family:'DM Sans',sans-serif;
  font-size:15px;font-weight:600;text-align:left;cursor:pointer;
  transition:all 0.2s cubic-bezier(.4,0,.2,1);
  display:flex;align-items:center;gap:12px;
  position:relative;overflow:hidden;-webkit-tap-highlight-color:transparent;
}

.choice-btn::before{
  content:'';position:absolute;right:16px;top:50%;transform:translateY(-50%);
  width:20px;height:20px;border-radius:50%;
  border:1.5px solid rgba(255,255,255,0.12);transition:all 0.2s;
}

.choice-btn:hover,.choice-btn:focus{
  border-color:rgba(249,115,22,0.5);
  background:linear-gradient(135deg,#1a2d48 0%,#141f34 100%);
  box-shadow:0 0 20px rgba(249,115,22,0.15),0 4px 16px rgba(0,0,0,0.3);
  transform:translateY(-1px);outline:none;
}

.choice-btn:hover::before{border-color:var(--orange);}
.choice-btn:active{transform:scale(0.98) translateY(0);}

.choice-btn.selected{
  border-color:var(--orange);
  background:linear-gradient(135deg,rgba(249,115,22,0.15) 0%,#141f34 100%);
  box-shadow:0 0 24px rgba(249,115,22,0.25),0 4px 16px rgba(0,0,0,0.3);
  animation:select-pop 0.3s cubic-bezier(.4,0,.2,1);
}

.choice-btn.selected::before{
  background:var(--orange);border-color:var(--orange);box-shadow:0 0 10px var(--orange);
}

@keyframes select-pop{0%{transform:scale(1)}40%{transform:scale(1.025)}100%{transform:scale(1)}}

.btn-emoji{font-size:20px;flex-shrink:0;}

.trust-text{font-size:12.5px;color:var(--muted2);text-align:center;line-height:1.5;}
.trust-text strong{color:var(--muted);font-weight:600;}

.info-card{
  background:linear-gradient(135deg,rgba(249,115,22,0.1) 0%,rgba(249,115,22,0.04) 100%);
  border:1px solid rgba(249,115,22,0.28);border-radius:var(--rs);
  padding:12px 15px;margin-bottom:18px;
  font-size:13px;color:var(--orange3);font-weight:600;
  display:flex;align-items:center;gap:8px;
  box-shadow:0 0 20px rgba(249,115,22,0.08);line-height:1.45;
}

.trust-checks{display:flex;flex-direction:column;gap:7px;margin-top:18px;}

.trust-check{
  display:flex;align-items:flex-start;gap:9px;
  font-size:12.5px;color:var(--muted);line-height:1.45;
}

.check-icon{
  width:18px;height:18px;border-radius:50%;
  background:rgba(249,115,22,0.12);border:1px solid rgba(249,115,22,0.3);
  color:var(--orange);font-size:10px;font-weight:800;
  display:flex;align-items:center;justify-content:center;
  flex-shrink:0;margin-top:1px;
}

/* ═══ FINAL SECTION ═══ */
.final-section{display:none;width:calc(100% - 28px);}

.final-section.active{
  display:flex;flex-direction:column;align-items:center;
  animation:fadeUp 0.45s cubic-bezier(.4,0,.2,1);
}

.final-card{
  width:100%;background:var(--card);border-radius:var(--r);
  border:1px solid rgba(249,115,22,0.22);
  padding:32px 22px 28px;
  box-shadow:0 0 0 1px rgba(249,115,22,0.05),0 0 60px rgba(249,115,22,0.1),0 8px 40px rgba(0,0,0,0.5);
  text-align:center;position:relative;overflow:hidden;
}

.final-card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--orange),transparent);
  box-shadow:0 0 24px var(--orange);
}

.unlock-wrap{
  position:relative;display:inline-flex;
  align-items:center;justify-content:center;margin-bottom:18px;
}

.unlock-ring{
  position:absolute;width:88px;height:88px;border-radius:50%;
  border:2px solid rgba(249,115,22,0.2);
  animation:ring-expand 2s ease-out infinite;
}

.unlock-ring2{
  position:absolute;width:72px;height:72px;border-radius:50%;
  border:1.5px solid rgba(249,115,22,0.15);
  animation:ring-expand 2s ease-out 0.5s infinite;
}

@keyframes ring-expand{
  0%{transform:scale(0.85);opacity:0.8}
  100%{transform:scale(1.2);opacity:0}
}

.unlock-icon{
  font-size:52px;position:relative;z-index:1;
  filter:drop-shadow(0 0 18px rgba(249,115,22,0.65));
  animation:unlock-bob 3s ease-in-out infinite;
}

@keyframes unlock-bob{
  0%,100%{transform:scale(1);filter:drop-shadow(0 0 18px rgba(249,115,22,0.65));}
  50%{transform:scale(1.06);filter:drop-shadow(0 0 30px rgba(249,115,22,0.9));}
}

.final-headline{
  font-family:'Sora',sans-serif;font-size:23px;font-weight:900;
  color:#fff;letter-spacing:-0.5px;margin-bottom:9px;line-height:1.2;
}

.final-sub{font-size:13.5px;color:var(--muted);line-height:1.55;margin-bottom:18px;}


/* NEW: Complete-offer prompt card */
.offer-prompt-card{
  background:linear-gradient(135deg,rgba(249,115,22,0.14) 0%,rgba(234,88,12,0.07) 100%);
  border:1.5px solid rgba(249,115,22,0.38);
  border-radius:var(--rs);
  padding:14px 16px;margin-bottom:20px;
  font-size:13.5px;color:#fff;font-weight:600;
  display:flex;align-items:flex-start;gap:9px;text-align:left;line-height:1.5;
  box-shadow:0 0 28px rgba(249,115,22,0.14),0 2px 8px rgba(0,0,0,0.3);
  position:relative;overflow:hidden;
}

.offer-prompt-card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,rgba(249,115,22,0.6),transparent);
}

.offer-prompt-icon{font-size:18px;flex-shrink:0;margin-top:1px;}

.cta-btn{
  display:block;width:100%;padding:19px 24px;border-radius:16px;
  background:linear-gradient(135deg,#f97316 0%,#ea580c 100%);
  color:#fff;font-family:'Sora',sans-serif;font-size:16px;font-weight:800;
  text-align:center;text-decoration:none;border:none;cursor:pointer;
  box-shadow:0 0 0 1px rgba(249,115,22,0.3),0 0 30px rgba(249,115,22,0.5),0 4px 20px rgba(249,115,22,0.3),0 2px 6px rgba(0,0,0,0.4);
  transition:all 0.25s ease;letter-spacing:0.1px;
  animation:cta-pulse 2.8s ease-in-out infinite;
  position:relative;overflow:hidden;
}

.cta-btn::after{
  content:'';position:absolute;top:0;left:-100%;width:60%;height:100%;
  background:linear-gradient(90deg,transparent,rgba(255,255,255,0.15),transparent);
  animation:cta-shine 3s linear 1.5s infinite;
}

@keyframes cta-shine{0%{left:-60%}100%{left:160%}}

@keyframes cta-pulse{
  0%,100%{box-shadow:0 0 30px rgba(249,115,22,0.5),0 4px 20px rgba(249,115,22,0.3),0 2px 6px rgba(0,0,0,0.4);}
  50%{box-shadow:0 0 50px rgba(249,115,22,0.7),0 6px 28px rgba(249,115,22,0.45),0 2px 6px rgba(0,0,0,0.4);}
}

.cta-btn:hover{
  transform:translateY(-2px) scale(1.015);
  box-shadow:0 0 60px rgba(249,115,22,0.75),0 8px 32px rgba(249,115,22,0.5),0 2px 8px rgba(0,0,0,0.4);
  animation:none;
}

.cta-btn:active{transform:scale(0.98);animation:none;}

/* New: beginner line below CTA */
.beginner-line{
  font-size:12.5px;color:var(--muted2);font-style:italic;
  margin-top:12px;text-align:center;line-height:1.5;
}

.final-trust{margin-top:16px;display:flex;flex-direction:column;gap:7px;}

.final-trust-item{
  font-size:13px;color:var(--muted2);
  display:flex;align-items:center;justify-content:center;gap:6px;
}

.final-trust-item .chk{color:var(--orange);font-weight:800;font-size:14px;}

/* Live activity feed */
.live-activity{
  margin-top:20px;
  background:rgba(255,255,255,0.025);
  border:1px solid rgba(255,255,255,0.06);
  border-radius:var(--rs);
  padding:14px 16px;
  display:flex;flex-direction:column;gap:9px;
  width:100%;
}

.live-activity-title{
  font-size:11px;font-weight:700;color:var(--muted2);
  text-transform:uppercase;letter-spacing:0.9px;margin-bottom:2px;
}

.live-item{
  display:flex;align-items:center;gap:8px;
  font-size:12.5px;color:var(--muted);line-height:1.4;
}

.live-dot{
  width:8px;height:8px;border-radius:50%;
  background:#22c55e;box-shadow:0 0 8px #22c55e;
  flex-shrink:0;animation:live-blink 2s ease-in-out infinite;
}

.live-dot:nth-child(1){animation-delay:0s;}
.live-item:nth-child(3) .live-dot{animation-delay:0.6s;}
.live-item:nth-child(4) .live-dot{animation-delay:1.2s;}

@keyframes live-blink{
  0%,100%{opacity:1;box-shadow:0 0 8px #22c55e;}
  50%{opacity:0.4;box-shadow:0 0 4px #22c55e;}
}

.urgency-footer{
  margin-top:16px;padding:10px 14px;
  background:rgba(249,115,22,0.05);
  border:1px solid rgba(249,115,22,0.1);
  border-radius:10px;
  font-size:12px;color:var(--muted2);
  text-align:center;line-height:1.5;font-style:italic;
}

.urgency-line{
  margin-top:14px;font-size:11.5px;color:var(--muted2);
  font-style:italic;text-align:center;
}

/* ═══ FOOTER ═══ */
footer{margin-top:36px;text-align:center;padding:0 24px;}

.footer-links{font-size:12px;color:var(--muted2);margin-bottom:6px;}
.footer-links a{color:var(--muted2);text-decoration:none;transition:color 0.2s;}
.footer-links a:hover{color:var(--orange2);}
.sep{margin:0 7px;opacity:0.35;}
.footer-copy{font-size:11px;color:rgba(100,116,139,0.45);}

::-webkit-scrollbar{width:3px;}
::-webkit-scrollbar-track{background:transparent;}
::-webkit-scrollbar-thumb{background:rgba(249,115,22,0.25);border-radius:4px;}
</style>
</head>
<body>

<!-- ═══ ELIGIBILITY LOADING SCREEN ═══ -->
<div id="eligScreen" style="display:none">
  <div class="elig-logo">
    <img src="data:image/png;base64,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bxc5x4NaASTwAKtGyRy0smVmBabDdoaJZvwtdWFuj6qcgbTz0DgG8ABznUkPUy2wRh3L3CVLhnDNEKaigGrnHfJPIfXSSO/KcdOfvAaAADJERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBY3mTgjDuYWEqrDOJqIVNFONWuG6SCQetkjd+S4a8/fB1BIOSIgqlzzyuv2VGNZbDd2makk2pLdXNboyrh13OHQ4bg5vA9IIJwFWwZ3ZaWTNPAtThu7tEU34WhrA3V9LOAdl46RwLeIJ5joRVzjnC94wZiy44Yv1Mae4UExilbwdxa5p4tcCCDxBCDxUREBEW5uSDleMys1qcXCnEthswbW3IOGrZdD97hP7bhvHuWvQSi5DuT7cFYMGNb5S7OIb7CHRNeO2paQ6Oa3Tg5+5zurYG4gqSCAADQDQBEBERAREQEREBERAREQEREBEJA51xSTxRjtnAIOVF5lReqOHXalb8Kxq55nYOtxIrcSWimI5+zVkbPlKaajOEWrp878u4pCw4uspI4tq2OHwg6L49PPLvuttHlLfrVXDPQbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrX6zPLLtzg30XWcanTfVNH904Z6DaaLArfmtgiufsUmKLLO7ojronH+jlk1Jf6Cpa10c7HNdvBDtQVGmg9dFwxVUMg1a8HxrmBB5ioBERAREQEREBERAREQEREBERAUb+XFk+3GuDDjWx0u1iGxQl0rWDtqqkGrnN04uZvc3q2xvJCkghAI0I1BQUzotzcr3LAZa5rVAt9N2KwXnarbbsjRsep++Qj9hx3D3LmLTKArMeRxl8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FOpsR4hbqx0rXbVHSu47Tgfvjh7lp06XAjRBtjOPNLCeVmGzd8SVn36QEUdDCQaiqeODG9A4uO4d8gGt3OzNbE+a+KHXe/TmKliJbQ26J5MFIw8Gji46Daed56gABjeNcV4hxniCe/YnutRcrhOe2llPrRwa1o3NaODQAAvFQEREBERAREQEREBERAW5sleUdmDlqILeKrz+sEejfO2ueT2NvRFJvdH1De39VaZRBZjlRylssceiKlddfQ/dX6A0V0c2IOd0Ml12HdW8OPuVuZpDmhzSCCNQRxVNCz/LrOXMrAAZDhvFddDRs5qKcien06BG/UN77dD1oLWUUKcEcty4RhkONMGU9R7qptU5jP8AKk2gT++FuPDHKuyYvTWCovtbZZXc0dxoXt077o9tg8bkG80WI2XNDLe8sa6148w1Ul35DbnFtjvtLtocx5xwWT0lZSVjC+kqoKho01MUgcBrzcyDnREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERARcFXWUlGwPq6qCnaddDLIGg6c/OsYvWaGW9mY510x5hqmLfyHXOLbPeaHbR5xzDigy5FozE/KuyYsrXinvtbepW88duoXu17zpNhh8TlpvG3LcuEgkhwZgunph+RU3Wcykj/dR7IB/fKCaziGtLnEAAakngtM5r8pbLHAQlpW3X0QXVmoFFa3NlDXdD5ddhvXvLh7lQNzFzlzKx+Hw4kxXXTUb+eigIgp9Ogxs0Du+7U9awBBubOrlHZg5lCe3mq84bBJq3ztoXkdkb0SybnSdY3N/VWmURAREQEREBERB//9k=" alt="TesterUp">
  </div>
  <div class="elig-spinner"></div>
  <div class="elig-title">Verifying your eligibility…</div>
  <div class="elig-msg" id="eligMsg">Checking available reward tasks…</div>
  <div class="elig-bar-wrap">
    <div class="elig-bar" id="eligBar"></div>
  </div>
</div>

<!-- ═══ REDIRECT OVERLAY ═══ -->
<div id="redirectOverlay">
  <div class="redir-spinner"></div>
  <div class="redir-msg" id="redirMsg">Securing available offers…</div>
  <div class="redir-sub">Please wait a moment</div>
</div>

<!-- ═══ MAIN PAGE ═══ -->
<div class="page-wrap" id="mainPage">

  <div class="header">
    <div class="logo-wrap">
      <img src="data:image/png;base64,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bxc5x4NaASTwAKtGyRy0smVmBabDdoaJZvwtdWFuj6qcgbTz0DgG8ABznUkPUy2wRh3L3CVLhnDNEKaigGrnHfJPIfXSSO/KcdOfvAaAADJERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBY3mTgjDuYWEqrDOJqIVNFONWuG6SCQetkjd+S4a8/fB1BIOSIgqlzzyuv2VGNZbDd2makk2pLdXNboyrh13OHQ4bg5vA9IIJwFWwZ3ZaWTNPAtThu7tEU34WhrA3V9LOAdl46RwLeIJ5joRVzjnC94wZiy44Yv1Mae4UExilbwdxa5p4tcCCDxBCDxUREBEW5uSDleMys1qcXCnEthswbW3IOGrZdD97hP7bhvHuWvQSi5DuT7cFYMGNb5S7OIb7CHRNeO2paQ6Oa3Tg5+5zurYG4gqSCAADQDQBEBERAREQEREBERAREQEREBEJA51xSTxRjtnAIOVF5lReqOHXalb8Kxq55nYOtxIrcSWimI5+zVkbPlKaajOEWrp878u4pCw4uspI4tq2OHwg6L49PPLvuttHlLfrVXDPQbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrT088u+620eUt+tOG3QbURar9PPLvuttHlLfrX6zPLLtzg30XWcanTfVNH904Z6DaaLArfmtgiufsUmKLLO7ojronH+jlk1Jf6Cpa10c7HNdvBDtQVGmg9dFwxVUMg1a8HxrmBB5ioBERAREQEREBERAREQEREBERAUb+XFk+3GuDDjWx0u1iGxQl0rWDtqqkGrnN04uZvc3q2xvJCkghAI0I1BQUzotzcr3LAZa5rVAt9N2KwXnarbbsjRsep++Qj9hx3D3LmLTKArMeRxl8MBZLW51VB2O63vS5VpI7Zoe0dijP7LNndwc5ygbyeMFjH+ceHcNzR7dHLVCatBG7zPEDJID0bQbsjrcFaw0BrQ1oAAGgA4IP1ERAREQEREBERAREQERCQBqUBdarrIadhc94Gi8DHOMbPhazz3O7V0VLTQt1dI8/ABxJPADeVCzOblCYgxXPNbsNyz2m0klpla7ZqJx3x6wdQ39J4KumOb+Akrmlnzg/BhkpZq7zZcG7vMdJo+QH9bfo394g9AKjZjjlMY3vMj47HFT2WnJ7VwAmm+Fw2R/D41o5xLnFziSSdSTxX4symCtfHmnR7N/xViW/yOfeb7ca7a52zVDnMHebroPEF4yIrsRokREUgiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgL0LNfL1Zpey2i7V9vfrqTTVDo9e/skarz0UDcODOUVmFYZGNr6mC9UzdxZUsDJNOp7dN/WQ5SKyv5SGEcSvio7hM6zV7tB2KrcAxx6Gycx8ehPQoKIrVsNbIWvUFxp6uMOjkaQegrug68yrmyjzsxVgSohpZZ5LpZmkB1LM/V0bf8A7bjvHeO7vc6m3lZmTYMc2WO4WisbK3cJI3bpIne5e3gf6HhqFiZMU08UM+RfjHBw1BX6rYIiICIiAiIgIiICIiAiIg0xyx8vhj3Ja4upYOyXWya3KiIHbODGnssY/aZtbuLmtVZyuXcA5pa4AgjQg8VVPyh8FjAGceIsNwx7FHFVGaiAG7zPKBJGB07IdsnraUEg/ubOFxJdMU4zmj3QRR22mcRxeeyS/AGxfxFTWWjOQxYRZeTtaKgs2JbtU1FfINOfV/Y2nxsiYVvNAREQEREBERAREQEREAnQarDMzccWfBmHqm7XarbBBEO+57uDWji48AvdxLdqa1W2arqZmRRRML3ve7QNaBqSTwCrxz7zMrMxMVySRyyMs1I8tooSdA7gZHD3R/oN3TrcxY+OR0M38yb3mLf31ldI+C3xuPmSiD9WRj3R6XnifENywdEWwiIiNIVCIikEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAXv4DxffMFX+K82OqdDK0gSRneyZmu9jxxH9RwXgIomNeUixnI7NG05gYeZWUj+x1MejKqme7t4X9B6QeB498EDaLXBw1Cq9yyxrdcB4rp75bHuLWkNqYNrRs8eu9p6+IPAqfGX+a2FsS2+nkoLtTSSSsDuwukAlb1FvPqOZYGakY59JTFLW14Y10bLRdGmudLOAWyNPjXbZIx3M4FWlD7REQEREBERAREQEREBQo+6TYWEd2wtjOGPdPDJbal45gWHskXjIfL/AAhTXWjOXPYReuTtd6gM25bTU09fGNObR/Y3HxMleUGxclrW2y5Q4QtYaGup7LSNfpxf2JpcfG4k+NZcuC30zaOgp6Rh1bBE2MHTTUNAHN4lzoCIiAiIgIiICIiAvmV4YwuPBfS8LGl2p7PY6quqZRHDBE6WR55mtaCSfgCCMfLWzFkhghwTbZ9JKtvZq5zTvbFr2rP3iCT1N6Comr2sc4hqsVYtuWIKxzjJWTueGk+sZzMb4mgDxLxVscdOCuiRERXEiIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAvawvXGKfzK9xDXnVh6HLxV+sc5j2vadHNOoPQVj7Ts9doxTjnzZu7ttvsW0VzU8vH1jzhuTD+P8YWItFvvtWI280cruys06AHa6eLRbMwzyirzS7Ed6tUVS0bjJTPLD/C7UH4QtDUM4qaSOdv5bdT1HiuZcXXaM+G0118HqmbdW79vpGS2OJ156xynn6wmRhbPnB102GTXA0MrvyKtvY9P3vW/1WyrViS23CFstNVRSsd61zHgg+MKu1ejYrleLdVh9ouFXRyk6l0MrmfDpzjvrMpvW0e/DQ7R2Jx5J/8AmvMT0nn92n4rGIpmSjVpBXItUcnW+3W84Nimu9a+sqWyvYZXNAJAO7mAW11t8WSMtIvXwlwm3bHk2Lab7Pk96kzE6egiIrjFEREBERAWI51Wxt5ygxha3N2jUWWrazdro/sTi0+JwB8Sy5cFwpm1lBUUjzo2eJ0ZOmugcCObxoOdERAREQEREBERAREQDzKPvLQxK60ZYVNFFIWzXOZlI3Q79k6uf4i1pHjUgJDowlQu5d11dLfbBaQ7tY45qh415yS1rfkd8KuYo1vAjOiItiqEREBERAX61rnuDWtLnE6AAaklevgzDlzxZiSksNpiD6mpdoCddljRvLnHgAFO3JvJTDWDLdDIyjjqbkWjstbMwGRx037OvrG9Q8evOrWTLFEIMU+CsZVMQlp8JX6aN3M+O3TOB8YauX0B457jMR/Fc32VZvFZ6RjQBE34F9+ddL+bb8Cse0z0NVYvoDxz3GYj+K5vsp6A8c9xmI/iub7Ks6866X8234E866X8234E9pnoaqxfQHjnuMxH8VzfZT0B457jMR/Fc32VZ1510v5tvwJ510v5tvwJ7TPQ1Vi+gPHPcZiP4rm+ynoDxz3GYj+K5vsqzrzrpfzbfgTzrpfzbfgT2mehqrF9AeOe4zEfxXN9lPQHjnuMxH8VzfZVnXnXS/m2/AnnXS/m2/AntM9DVWL6A8c9xmI/iub7KegPHPcZiP4rm+yrOvOul/Nt+BPOul/Nt+BPaZ6GqsX0B457jMR/Fc32U9AeOe4zEfxXN9lWdeddL+bb8CeddL+bb8Ce0z0NVYvoDxz3GYj+K5vsp6A8c9xmI/iub7Ks6866X8234E866X8234E9pnoaqxfQHjnuMxH8VzfZT0B457jMR/Fc32VZ1510v5tvwJ510v5tvwJ7TPQ1Vi+gPHPcZiP4rm+ynoDxz3GYj+K5vsqzrzrpfzbfgTzrpfzbfgT2mehqrF9AeOe4zEfxXN9lfMmBsbRsL5MH4hY0DUl1smAH/lVnnnXS/m2/Avl9ppHDTsTfgT2mehqqoqIJqaZ0NRDJDK06OZI0tcO+CuNWQ5mZU4XxjbJKe6WyKR+yRHO0BssR6Wv5x3uY8QVA/NvANyy9xVJaK0maneDJSVIGglZrx6HDmI/sQr2PNF+XmMOREV5IiIgIiIMjwnNtU8sBPrHbQ7x//wA/qvbWLYXk2bkWcHsI/v8A2WWwRPmkEcY1J/ouM3vjjHtNp683rHZXNbaN30r4zEzX/HykgifNII4xqT/Re5SUzKePZbvcfXO6UpKZlPHst3uPrndK51z2bNx8o8Hpu7t3Rs8cd/e+5J3kvewse+JPlW6QtLcl72Fj3xJ8q3SF2mwfq1PhD527Uftjaf67feIiLLaEREQEREBERAREQEREBERAREQEREHHUHSF3eUCOWnUmfNyCLV2kNsjGh5tTJIdR4tPgU9qv8A7vKv/AJY3txO8HxfOer+z++mGmURFnJEREBERBKXkK4bp5/PjEksYdN2ZtHG4/ktDQ9wHf2mfwhTDiYGMAAUYeQYP/kK6H/8AMSfQwqUI5lrs0/TlTIiIrYIiICIiAiIgIiICIiAiIgIiICIiAiIgIiIPxwBBBUb+WxhqCuy6fd2xjzRbJ2Ssdpv2XODHDvdsD+6FJFaU5XftO33/AHcf0rFXjnS0Cv8AREWyVCIiAiLt2q31NyrG01MzVx3knmaOkqi9646za06RC5gwZM+SuLFXW08oiPN2MLwTT3qBsLC4jUuOm4DQ7ytl0lMynj2W73H1zuldWxWmmtNL2KEbT3b5JCN7j9XUvRXnu+N4RtmbWnuxy+L6G7H9nLbm2PTPOuS06z0jWIjSPs5z9giItS69J3kvewse+JPlW6QtLcl72Fj3xJ8q3SF3ewfq1PhD5i7Uftjaf67feIiLLaEREQEREBERAREQEREBERAREQEREHFV/gHd5V/8sb24neD4vnPVgFX+Ad3lX/yxvbid4Pi+c9X9n99MNMoiLOSIiICIiCZXIM9gN08MSfQwqUIUXuQZ7Abp4Yk+hhUoQtdl9+VMiIitgiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgLSnK79py+/7uP6Vi3WtKcrv2nL7/u4/pWKqnvQK/0RFs1QiLt2q31NyrG01MzVx3knmaOkqi9646za06RC5gwZM+SuLFXW08oiPMtVvqblWNpqZmrjvJPM0dJWy7Ja6a1UYggGrjvkkI3vP/XBLJa6a1UYggGrjvkkI3vP/XBd9cFvfe9tstwU5Uj5+svfuyPZHHubH3+fnmn+30j8Z+qOXiREWkduIiIJO8l72Fj3xJ8q3SFpbkvewse+JPlW6Qu72D9Wp8IfMXaj9sbT/Xb7xERZbQiIiAiIgIiICIiAiIgIiICIiAiIg4qv8A7vKv8A5Y3txO8HxfOerAKv8A7vKv8A5Y3txO8HxfOer+z++mGmURFnJEREBERBMrkGewG6eGJPoYVKEKL3IM9gN08MSfQwqUIWuy+/KmRERWwREQEREBERAREQEREBERAREQEREBERAREQFpTld+05ff8Adx/SsW61pTld+05ff93H9KxVU96BX+iLt2q31NyrG01MzVx3knmaOkrYXvXHWbWnSIXsGDJnyVxYq62nlER5lqt9TcqxtNTM1cd5J5mjpK2XZLXTWqjEEA1cd8khG95/64JZLXTWqjEEA1cd8khG95/64Lvrgt773ttluCnKkfP1l792R7I49zY+/wA/PNP9vpH4z9UcvEiItI7cREQEREEneS97Cx74k+VbpC0tyXvYWPfEnyrdIXd7B+rU+EPmLtR+2Np/rt94iIstoRERAREQEREBERAREQEREBERAREQcVX+Ad3lX/yxvbid4Pi+c9WAVf4B3eVf/LG9uJ3g+L5z1f2f30w0yiIs5IiIgIiIJlcgz2A3TwxJ9DCpQhRe5BnsBunhiT6GFShC12X35UyIiK2CIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAtKcrv2nL7/u4/pWLdTiANStIcq2eGry0udsZNG2eq7HHGHO01PZGk/0BPiTjrT6Vp0iF3BgyZ8lcWKutpnSIjzQPtVvqblWNpqZmrjvJPM0dJWy7Ja6a1UYggGrjvkkI3vP/XBLJa6a1UYggGrjvkkI3vP/AFwXfXKb33vbbLcFOVI+frL3/sj2Rx7mx9/n55p/t9I/Gfqjl4kRFpHbiIiAiIgIiIJO8l72Fj3xJ8q3SFpbku+wse+JPlW6Qu72D9Wp8IfMXaj9sbT/AF2+8REWW0IiIgIiICIiAiIgIiICIiAiIgIiIOKr/AO7yr/5Y3txO8HxfOerAKoawu7ygFyy4nx5wguGgfbonN6xtyD5QVf2f30w0siIs5IiIgIiIJlcgz2BXTwxJ9DCpQhRT5B1dCMKXeh2h2VlzMrh+q6KMD5hUq2nVoK12X35Uy/URCrY8HF+Jrbhq3Pr7pUtp6dpDS9wJGpOgG7rWEuzowhruuzP5b/qXicrFx9LmqGv+2h+kaor22t29IZj2/5LjxWn3jt+bZr6UiJjR3vZPsxsG98E22m9q210jSY08I6xPPmmF6dOEP0sz+W/6k9OnCH6WZ/Lf9Sici1n5ez/AMMfP/LtfzYbs/m3+2v+qWPp04Q/SzP5b/qT06cIfpZn8t/1KJyJ+Xs/8MfP/J+bDdn82/21/wBUsfTpwh+lmfy3/Unp04Q/SzP5b/qUTkT8vZ/4Y+f+T82G7P5t/tr/AKpY+nThD9LM/lv+pPTpwh+lmfy3/UonIn5ez/wx8/8AJ+bDdn82/wBtf9UsfTpwh+lmfy3/AFJ6dOEP0qz+W/6lE5E/L2f+GPn/AJPzYbs/m3+2v+qaWEsw8P4jmfDbbhFPJGAXN3ggHjoQNyzKN7XtBBUB7Nc62z3KG4W+d0FREdWuHHqPSD0KVGUGY9Hii3tilc2GuiAE0JPN+sOlpW13fvSu0/Qvyt97iO1nYvJuaIz7PM3xecz41n108p8p+qfLXaSL5je17QQdV9LbOEEREBfjiANSjiANSsMzFxpbsMWiWrq5gNNzGD1z3cGgcSqbWrSs2tOkQu4MGTPkrixV1tPKIjzkzFxpbsMWiWrq5gNNzGD1z3cGgcSolY1xRcsVXh9fXvIaCRDCDq2JvQOvpPFMa4ouWK7w+vr3kNBIhhB7WJvQOk9J4/AvCXIby3lbabcFOVY+b37sh2Qx7mx9/n55p/tjpH4z9UcvEiItU7gREQEREBERAXp4asdwxDdorbbYTJK89s4+tY3i5x4BMNWO4Yhu0VttsJklee2cfWsbxc48ApXZV4AoML2tkcbA+d+jppnDtpHf2HQOC2W7t3W2q2s8qx/7SHHdrO1mLcmLu8f0s1vCOnrPp0jzehlThOLCmHYLfE98hbq573c7nHnOnDvLNV8saGNAAX0uypStKxWvhD572jaMm05bZss62tOsz1mRERVLIiIgIiICIiAiIgIiICIiAiIgIiIPmYaxuHUoNcuWgMOP7RcNnQT0TogdOfYeT/zFOZw1BCi1y67A6owlb73GzV1BWbLz0RyDQn+IMHjV3DOl4EOkRFsFQiIgIiINk8njMIZf44bU1j3C11rRDWEanY0OrZNBz6EnxOKsIw5faK62+GppqiOaKVgex7HAtc0jUEEc4VVyzzLfNjGOBNmC1VwnoQdfMdSC+MdOzvBb4jp1FY+XDx84QstD2nmIX6XN6QoW0nK1uscLWz4QjkkA3ubcS0HxGM/Kub1XVw7i2/Gn/wDJY/cX6I0bc5WJBy6qtD/tovnhREWYZmcoOqxrYJbVLhkUokc1235v29NlwPN2MdC1X6KP/A/+r/7LTbw2HPkyxateWnWHd9mt87FsWyTjz30nimfCZ8o6RLOLbXbWkMx7b8lx49S9Ja19FH/gf/V/9l72HMXQ1dS2jrI+wOdujkL9QT0HcNFpNp3TtFIm8V5fU9H3P213bnvXZr5ec8omYmPqmZjRliIi1DuRERAREQEREBdyzXOts9yhuFvndDURHVrhx6j0g9C6aKa2ms6x4qMmOmWk0vGsTymJ8JS0ygzHo8UW9sUrmw10QAmhJ5v1h0tK2hG9r2gg6qA9mudbZ7lDcLfO6GoiOrXDj1HpB6FKjKDMejxRb2xSubDXRACaEnm/WHS0rrd2bzjaI7vJ733vBu2PY6+6rztWyxrhn7a+k+nSfqnymdpL8cQBqV8NlaWbQI0WF5j45tuF7XJU1c2h9axjd7nu6AFtr3rSs2tOkQ4XBgybRkrixVm1p5REeMuTMXGluwxaJaurmA03MYPXPdwaBxKiVjXFFyxXeH19e8hoJEMIPaxN6B0npPH4Exrii5YqvD6+vkIaCRDCD2sTegdfSePwLwlyG8t5W2m3BTlWPm9+7IdkMe5sff5+eaf7Y6R+M/VHLxIiLVO4EREBERAREQF6eGrHcMQ3aK222EySvPbOPrWN4uceAX3hTD9xxLd47dbYi57t73kdrG33RUrMrcv6DC1rZHGzbnfo6aZw7aR39h0Dgtlu/d1tqtxTyrH/ALk43tZ2tw7kxd3j+lmnwjp6z+EefwfmVeAKDC9rZHGwPnfo6aZw7aR39h0DgthsaGNAARjQxoAC+l2OPHXHWK1jSIfPu07Tl2rLbNmtxWtzmZERFWsCIiAiIgIiICIiAiIgIiICIiAiIgIiICwLOzC8eK8CXWzODdaqmc1jjzNfzsd4nAHxLPVwV0ImgcwjXUKYnTmKn6qCalqZaaojdHNC8xyMdztcDoQfGuNbt5XWA5MM49dfqWHZt94cXuLW7mTj1wP7Xrus7XQtJLZUtxRqkREVSRERAREQEREBfEjNd4519oomImNJHXRckjNd4XGsW1ZrOgzfB2KBoy3XOTf62KZx/o761my0ks1wZifZ2LbcpO19bDM4836rj8hXLb23R45sEfGPxh652L7be7sG8LelbT91vwn7WcIiLmHroiIgIiICIiAu5ZrnW2i5Q3C3zugqIjq1w+Q9IPQumimtprOseKjJjplpNLxrE8pifCUhbLnVRPwtJUVw7FWwt2XQNOpe7hs9IP8ATitJ4vxHccT3d9wuMhJOoiiB7WNvQP7nivGRZu07wzbTSKXnlHz+LndzdlN37oz3z4K/St4a8+GOkf8AtdOQiIsF0oiIgIiICIiAvWwph644lu8dttsRc9297yO1jb7ophTD1xxLd47bbYi57t73kdrG33RUs8sMCW/C1pZBBHtSu0dLK4dtI7pP9hwWz3du621W4rcqx8/SHGdre1uLcuLusX0s1vCOnrP4R5/AywwJb8LWlkEEe1K7R0srh20juk/2HBZ4xoaNAEY0NGgC/V2NKVpWK1jSIfPu0bRl2nLbNmtxWtzmZERFUsiIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAhREGvc68CUOOMH1lnq27JkbtRSgamKQeteO8fhGo4qujFFjuOG79V2S7QGGrpZCx7eB6HDpBGhB6CrV5WB7C0jXVR/5TWTEWNrb562hkcN9pWnsTzuE7Ofsbj8h4HqJV/Dl4Z0nwTCCyLsXGiq7dXz0FfTyU1VA8xyxSN0cxw5wQuus5IiIgIiICIiAiIgLjkZ+UPGuRFTasWjQddF9yM03jmXwsW1ZrOkjMsGYn7DsW64yfe/WxSuPrf1T1dfD5M7Wkll+DcTmncy33KQmE7opXH1nUer5O9zczvbdHFrmwxz84/GHq/Yvtt3fDsG325eFbT5elvTpPl58vDPkX4CCNRvC/Vyz2IREQEREBERAREQEREBERAREQF62FMPXHEt3jtttiLnu3veR2sbfdFMKYeuOJbvHbbbEXPdve8jtY2+6KlnlhgS34WtLIII9qV2jpZXDtpHdJ/sOC2e7t3W2q3FblWPn6Q4ztb2txblxd1i+lmt4R09Z/CPP4GWGBLfha0sggj2pXaOllcO2kd0n+w4LPGNDRoAjGho0AX6uxpStKxWsaRD592jaMu05bZs1uK1uczIiIqlkREQEREBERAREQEREBERAREQEREBERAREQEREBERAXHPE2Vha4a6rkRBoHlCZF27G8L7pbQyhvkbdGVAHaygczJAOcdDucdY3KFOLcNXvCt4ktV9oJaOpZzBw7V49008zh1hWpSMa8aOGqwrMPLrDuMrY+hvVthqozqWkjR0Z6WuG9p7yv48005T4JVlopBZn8mTENmklq8JT+etKDqKWYhk7R1O3Nf/5T1FaJvFqudmrXUV2t9VQ1LeeKoiLHd/Q8OtZdb1t4DpoiKtIiIgIiICIiAuKRmm8cy5UVNqxaB10X1I3Z3jmXysWYmJ0kZbg/FBpNi33B5NPzRyk74+o9Xyd7mz8EEAggg7wQtJrK8HYmNDs0FweTTc0ch3mPqPV8i5ve26OPXNhjn5x19Y9XqfYzttODh2Hb7fQ8K2ny9J9Ok+Xny8NhIvxrmvaHNcHNI1BB1BC/Vyj2aJ1EREBERAREQEREBERAXrYUw9ccS3eO222Iue7e95Haxt90Uwph644lu8dttsRc9297yO1jb7oqWeWGBLfha0sggj2pXaOllcO2kd0n+w4LZ7u3dbarcVuVY+fpDjO1va3FuXF3WL6Wa3hHT1n8I8/gZYYEt+FrSyCCPaldo6WVw7aR3Sf7Dgs8Y0NGgCMaGjQBfq7GlK0rFaxpEPn3aNoy7TltmzW4rW5zMiIiqWRERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREHFNBHKNHNBWO4kwVYb9SmmulspK2E7+xzwte3XvELJ0QR9xPyYMAXJ75KSkq7Y928mjqCB4mv2mjxBYFc+SPESfO/FVVEOHZqRsnyOapfr82R0BXIy3jzEKZuSZe2yERYrgezgXUJafg2yvj1J1+7qKbyN321NjYb0BOxs9yFPf36mqE/qTr93UU3kbvtp6k6/d1FN5G77amx2NnuQnY2e5Cnv79TVCf1J1+7qKbyN3209Sdfu6im8jd9tTY7Gz3ITsbPchO/v1NUJ/UnX7uopvI3fbT1J1+7qKbyN321NjsbPchOxs9yE7+/U1QmPJNvx/+qKXyN3218Hkk37Xdimm8id9tTc7Gz3ITsbPchUzltbxNUIvUk3/uppfInfbT1JN/7qaXyJ321N3sbPchOxs9yFTxynVDSDIPFmGLRN/8YhukcbdqKEQFjh0gEuPwLB5GPjkdHI1zHtJDmuGhBHOCFP2qpYpoy1zRvWh87srTWmW9WSENrWjWWIbhMPtdfFc/vTdnea5sUc/OOv8A3971DsV219l4dh2+30PCtp/d9J9Ok+Xw8I8ov2Rj45HRyNcx7SQ5rhoQRzghfi5d7VE684EREBERAREQF6+E8O3PE11Zb7bCXO3GSQ+tjb0k/wBuK+sIYcuOJ7uy32+MnXQyykdrG3pP9hxUsstMD2/DFpjpqaLtvXSSOHbSO6Stpu7d1tqtxW5Vj5uK7W9rsW5cfc4dLZp8I8qx1n8I8/g+csMCW/C1pZBBHtSu0dLK4dtI7pP9hwWeMaGjQBGNDRoAv1dhSlaVitY0iHz/ALRtGXacts2a3Fa3OZkREVSyIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgLgq6dk8ZY5oOq50QR/zuytNaZb1ZYQ2taNZYhuEw+118VHqRj45HRyNcx7SQ5rhoQRzghT+q6dk8ZY5oOq0Nndlaa0y3qywhta0ayxDcJh9rr4rQ703X3muXFHPzjr/29R7FdtfZeHYdut9Dwraf3fSfTpPl8PCPKL9kY+OR0cjXMe0kOa4aEEc4IX4uXe1ROvOBERAXs4Qw5ccT3dlvt8ZOuhllI7WNvSf7DimEMOXHE93Zb7fGTroZZSO1jb0n+w4qWWWmB7fhi0x01NF23rpJHDtpHdJW03du621W4rcqx83Fdru12PcuPucP0s1vCP4fWfwjz+Blpge34YtMdNTRdt66SRw7aR3SVnTGho0ARjQ0aAL9XYUpWlYrWNIh8/58+TaMlsuW3Fa3OZnzERFUsiIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgLgq6dk8ZY5oOq50QR/zuytNaZb1ZYQ2taNZYhuEw+118VHqRj45HRyNcx7SQ5rhoQRzghT+q6dk8ZY5oOq0NnblYa0y3qyQhtaBrJENwmH2uvitDvTdfea5cUc/OOv8A29R7FdtfZeHYdut9Dwraf3fSfTpPl8PCPK9nCGHLjie7st9vjJ10MspHaxt6T/YcV9YUwxdcR3sWuige17XaTve0gQjXQ7XX1KWGWmB7fhi0x01NF23rpJHDtpHdJWr3du22024rcqx8/R2na3tfi3Ni7rDMWzWjlHlWOs/hHn8DLTA9vwxaY6ami7b10kjh20jukrOmNDRoAjGho0AX6uwpStKxWsaRDwDPnybRktly24rW5zM+YiIqlkREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERB1rtWNt9qq7g9he2mgfM5oO9wa0nT+ijV6sbDHcdePKI1IjGXsPvXg+f6NyqqWRgx1vrqlM31Y2GO468eURp6sbDHcdePKI1DJFf7ihomb6sbDHcdePKI09WNhjuOvHlEahkidxQ0ThwjyrcO4ixXaMPwYUusEtzroaNkr54y1jpZGsDiBwG1qpFKsHJb248Ff4goP8wxWfLHz0ikxoSIiw3O3FzcD5W33EYeG1FPTFlL1zv7SP4HOBPUCrMRrOiGp8W8rDCthxPc7JHhy5V4oKqSmNRFMwMkLHFpLQd+moK8v1Y2GO468eURqGb3Oe4ve4uc46kk6klfizu4onRaLlfjO24/wRb8VWuOSGCsDgYZCC+J7XFrmu04gjxjQrJlEj7n/jDR99wLVTc+lyomk95koH/pnQdDipbrDyV4bTCBcVXMKelmqHNLhExzyBx0Gq5V1Lz+J633vJ80qgRs9WNhjuOvHlEaerGwx3HXjyiNQyRZ/cUTomb6sbDHcdePKI19RcsXCpkAkwhems4ls0RI8Wo+VQwRO4oaJ9YY5UuVV4kZFW1N0sj3bta6k1Zr+1EX6DrOniW37dW2nEFrjr7VX0lxophrHPTStkjd3nAkKqZZfldmNinLm+tumHK90bHEeaKSQl0FQ3oezX4CNCOBVFtmj900WSUGHrbRVM1RT0kMUk79uVzGAF7tNNT0nQBfeK7vDhvCd3v80D54rXQzVj4mEBz2xRueWgnidnReblbja05g4JocT2glsVQC2WFxBfBK3c+N3WD8IIPFcOdPtOY1/w/X/5d6xIrpOibWm062nVo71Y2GO468eURr6ZyxcLF7Q/CF4a0neRPGdB3lDBFndxRGi2CzXKivFopLtbahlTRVkLZ4JWHUPY4ag/AV21FXkKZkmqoqjLe61GstMHVNqLz66PXWSId4nbA6C7gFKpYd6cFtECjD6sbDHcdePKI1J5VKK5gx1vrqmEzfVjYY7jrx5RGpK2msbcLVSXBjCxtTAyZrSd7Q5oOn9VU6rVcG+w+y+D4Po2qc+OtNNCXrIiLHQIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIg8nGXsPvXg+f6NyqqVquMvYfevB8/wBG5VVLL2bwlMCsz9KDK7uAw55Az6lWYra02mZjTQlg/pQZXdwGHPIGfUnpQZXdwGHPIGfUs4RY3Fbqhh1vysy4t9fT19Dgiw01XTStmgmjomNfG9pBa4HTcQQCCsxRFEzM+IKJP3QDGHbWHAtNLza3KsAPfZEPpCQf1Spavc1jHPe4Na0akk6ADpVY2dOLXY4zQv2JA8ugqaotpQeEDO0j3cO1aCeslXtnrrbXomGHIu3Z7fU3a70dqomB9VWVDKeFp4ve4NaPhIW4eV7l9S4ExvaPOyDsdurbTBGxwGgMsDRE/wAey2NxPEvJWZNoiYhLAsmcWvwPmdYsS7bmwUtUG1QGvbQP7SQace1cSOsBWdxvZJG2SN7XscAWuadQQeYgqpVWJ8k7GHovyWtL55uyV1qBttVqdTrGBsE67zrGWEnidVj7TXwsiW2F1Lz+J633vJ80rtrqXn8T1vveT5pWJCFT6Ii2qpZVaso8sJLXSSPwFh1z3QMLiaFmpJaN/Mvy55J5UXCkfSzYEs0bHjQup4ewvHeczQj4Vm9m/E9F73j+aF21rOK3VSrr5TWVLcrcZwU9vmmqLJc43TUL5dC9haQHxOPEt1addOZw46rVCl190Nq6bzLg6h7I01O3VylnEM0iGp75+Q9CiKs/FabUiZSlZ9z4v87brifC73l1PJBHXxNJ3Mc13Y3kDrDma/shSSzp9pzGv+H6/wDy71FX7n5RPkzKv9xAdsQWcwE8NZJo3D6M/wBVKrOn2nMa/wCH6/8Ay71i5f0grBRF9wRSzzxwQxuklkcGMY0alzidAAOlZyXoYUvtxwxiS34gtExhrqCds8LuGoPMekEagjiCQrN8t8W27HOCbZii1nSCuhDnR66mGQbnxnra4EdemvFVakEHQjQhSP5D+ZXofxbLgS6VGzbb0/boy526KrA0A/4gAb+01g4lWM9OKuseSJTcVSitrVSit7N5kCtVwb7D7L4Pg+jaqqlarg32H2XwfB9G1TtPhBL1kRFiIEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQeTjL2H3rwfP8ARuVVStVxl7D714Pn+jcqqll7N4SmBEUq/Ua3Lu+pPix3+or9r1r4iKiKVfqNbl3fUnxY7/UT1Gty7vqT4sd/qKnvqdRtvkX/APd9svviq+netyrCckcDS5dZdUOFJriy4vpZJXmoZEYw7bkc/wBaSdNNdOdZssG862mYQ1VyrcYeg/Ja7ywy7Fbcx520u/Q6ygh5HWIw869ICrpUkeXnjDz0x/b8I00u1BZafstQ0Hd2eYA6HvMDP4io3LNwV0p8Uw3TyMsL+iLO6grJY9ulssL6+TUbtsaMjHf23tcP2SpDcuTC3n3lEy+Qw7dTYqts5cOcQyfe5B8Jjcepq8HkGWWitGArviWsnp4am7Vgii25Gg9hhBAI1O7V75B+6FvvF9PZMSYVuuH6yvozBcaSWmeTM3cHtLdefnGuviVjJf8A5NegqzUjeQfjDzpzFrsJ1MulPfKfbgBO7zRCC4fCwyfwhR6uVHPb7jU0FS0NnppXwygHUBzSQd/HeF3MI3yswzii2Ygt50qrdVR1MY10DixwOyeo6aHqJWVevFWYFq66l5/E9b73k+aV82C6Ul8sVBeaB+3SV9NHUwO6WPaHN/oV9Xn8T1vveT5pWu80Kn0RFtFSXlFyxLZT0UFOcC1jjFG1mvni3foNPza47nyyovMjxbcBPFQQQx1RchsNPSQ2PU97Ud9RHRWe4p0RoyPMfGt/x/imoxFiKpE1VKAxjGDZjhjHrY2N4NGp6ySSdSSVjiKZHJQyPwbNh60Zi3Ktbf6udolpqZ0ezBRyNJBDmnUve1wO86AaagHcVVe0Y6jM+Rvl3VYIy2kuV2pzBdr9I2pkjc3R8UDRpEx3Xvc7Tht6c4K2HnT7TmNf8P1/+XestWJZ0+05jX/D9f8A5d6weKbW1lCsFexgj2Z2PwjT/SNXjr2MEezOx+Eaf6Rq2M+Cpt/llZa+g7MA4jttPsWa/vdMA1vaw1PPIzoAdrtjvuA3NWjKaaamqI6inlfFNE8PjkYdHNcDqCDwIKs3zjwPRZiZe3LDNVsMlmZ2SjmcPwFQ3fG/va7j0tLhxVZ13t9ZabrV2u4076eso5nwTxP52PaSHA94hWcF+KukohY9ye8wocyMtaG9PezzzgHma5RjdsztA1dpwDgQ4d/TgVWutvclPMg5fZlQx19R2Ox3jZpa/aPaxnX73L+64kH9VzupahU46cFpBWq4N9h9l8HwfRtVVStVwb7D7L4Pg+jare0+EEvWREWIgREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERB5OMvYfevB8/0blVUrVcZew+9eD5/o3KqpZezeEpgVtaqUU2PVhYG7mcR/BD9tVbRS1tNCUk0UbPVhYG7mcR/BD9tPVhYG7mcR/BD9tY3c36I0STXUvdypLPZq273CURUlFTvqJ3+5Yxpc4/ACtFYV5VWDsRYotOH6XD1+inudbDRxSSCLYY6R4YC7R+ugLt+i5+W9i/0P5SCxU8pZWYgqBTjQ6EQM0fKfmNPU8pGO3FESISY0v1XinFt1xFXE+aLjVyVDhrrsbTiQ0dQGgHUAvIRZjk9l/csy8axYZtlTFSPdDJPLUStLmxMYOcgbzq4tb+8thMxWFTDkUoPUc4k7s7T5NJ9aeo5xJ3Z2nyaT61b76nVCL6LducnJ2v8Alvgx2KKi+UVzpo6iOGaOCF7DGH6gPJPDa2R+8FpJV1tFo1hKdfIaxh5+5Vy4dqJdqrsFQYmgnf2CTV8Z+Hsje80Let5/E9b73k+aVAXkdYw9Cuc9BSTy7FDfGm3TAndtuIMR06dsNb3nlT6vP4nrfe8nzSsLNXhuhU+iIs9KzS05Z5bvtVI9+X2E3OdAwkmzU5JOyN/rFEXlm5bUuDMdU18sdugorHeIu0hp4gyKCdgAewNA0aCNlwHSXdCnNZvxPRe94/mhYfn1gSLMTLK54fDGebg3zRb3u/IqGAlm/gHb2E9DitfjyTW3NSrPUm+QnmG62Ylqsv7jUaUd01qLftHcypa3tmj9tg177Bpvcoz1EMtPPJBPG+KWNxY9jxo5rgdCCOBBXPZ7jW2i7Ul1t1Q6nraOZk9PK3nY9pBaR3iAs29eKuiVsKxLOn2nMa/4fr/8u9feUuMqTH2X1pxRS7LXVUIFRE0/gpm7pGeJwOnSNDxXxnT7TmNf8P1/+XetfEaW0lCsFexgj2Z2PwjT/SNXjr2MEezOx+Eaf6Rq2U+Cpamoe8uvLXzLcKfMm0057DUltNdgwbmyAaRyn9oDYJ5tQ3i5TCXl4ssNuxRhq4Yeu8PZqGvgdBM3iAR64dDgdCDwIBWux34LaqVVCLIMxsJ3LA+NLnhe6t/7RQzFgeBo2Vh3skb1OaQfGsfWxideaoVquDfYfZfB8H0bVVUrVcG+w+y+D4Po2rG2nwhEvWREWIgREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERB5OMvYfevB8/0blVUrZ6mCKpppaaeMSQysLJGHmc0jQj4FgHpIZTdwln/ln61fxZYprqlWuiso9JDKbuEs/8s/WnpIZTdwln/ln61d9pr0NVa6Kyj0kMpu4Sz/yz9aekhlN3CWf+WfrT2mvQ1QEyW9uPBX+IKD/MMWf8s/F/omzlqrdBJtUVhiFBGAdxl12pT39o7P7gUxLZk9ljbLlS3KgwXaqespJmTwTMYdqORjg5rhv5wQCvisyZytrKuarqsE2qaonkdJLI9ji57nHUknXeSSqe/rxcWhqrSUv/ALn5hfsVtxFjKeMh08jLdTOI07VoD5NOkEmP+E+LdPpIZTdwln/ln61l+F8PWTC9oZaMP22nt1BG5z2wQt0aC46k+MqMmeLV0g1eoiIsZDGs08NMxhl1fsNOALq+ikjiJ5mygbUZ8Tw0+JVdyMfFI6ORjmPYS1zXDQgjnBCtpWBVuTWVtbWT1lVgi0y1E8jpZXujOrnOOpJ38SVfxZYprEpVq0s81LVRVVPI6KaF4kje06FrgdQR1gqzfA2KYMaZS0OJ4C3/ALfbS+UN5mShpbI3xPDh4l5npIZTdwln/ln61luG8NWLDdk85LHbIKC3auPmeIHYBd67celMuWt9NBVUiso9JDKbuEs/8s/WnpIZTdwln/ln61d9pr0NWcWb8T0XveP5oXbXzExkUbY42hrGANaBwAX0sNCCPLXy+9C+YzcUUEGxbMQbUr9kdrHVD8IP3tQ/rJd0LQStTxbhfD2LbY22YktFLdKNkombFO3UNeAQHDoOhI8axT0kMpu4Sz/yz9ayqbREV0lOqM/IazDNkxjPgW4T7NvvRMlJtHdHVtbzdW20ad9rRxUrs6facxr/AIfr/wDLvXQt+TmWFvr6evosFWqCqppWzQysYQ5j2kFrhv5wQCs0udDSXO21Vtr4GVFHVwvgnhf62SN7S1zT1EEhWr3i1uKEKnF7GCPZnY/CNP8ASNViHpIZTdwln/ln61yUuS+VlLUxVNPgi0xzQvEkb2xnVrgdQRv6Vfnaa9E6s/REWGhHDlv5a+f+E48d2un2rlZWbFaGjfLSa66/8Mkn9lzjwChGrZ6mGGpp5KeoiZLDKwskje3Vr2kaEEHnBCwD0kMpu4Sz/wAs/WsjFn4Y0lOqtdWq4N9h9l8HwfRtWJekhlN3CWf+WfrWf00EVNTRU0EYjhiYGRsHM1oGgHwKMuWL6aDkREVhAiIgIiICIiAiIgIiICIiAiIg4LfUtrKCnq2DRs8TZANddA4A8/jXOsRyWujb1lDhC6Bwc6ostI5+nB/Ymhw8TgR4llyAiIgIiICIiAiIgIiICIiAiIgIigJdOUxm7Bc6qCO+0YZHM9jR53QncHED8lXKY5v4CfaKvv1TucP6eo/i6H7Kmxk/ioY1yysGJi9jpqykaanZGgE7e0lAHAbbXJfFakayMsRFgmfuNJMA5U3nEVLIxleyMQ0O00O+/wAhDWnQ7js6l2h4NKoiNZ0Gdoq+/VO5w/p6j+Lofsr2cDco7Ne642sVrrb3SPpay5U9PM0UEIJY+RrXDUN1G4lXp2eydE60RYnmjmFhnLjDxvOJKwxteS2npowHTVLx+Sxuu/TUak6AajUjUKzETPKEMsRQWx5yrswLxUyR4Zio8OUeujC2JtROR+s94LfgaNOlYM3PfN1s/Zhjm5bWpOhbGW/w7Oni0V+NntKdFkSKE2XPK0xbbKmOnxtQU9+oidH1FPG2Cpb1gN0jd3tG99S8wLi2wY2w7BfsN3COtopdxI3OjfxY9vO1w15j3+Ygq1fHanih7qIoCXTlMZuwXOqgjvtGGRzPY0ed0J3BxA/JU0xzfwE+0UNMjOUvi2tzGt9qx5cqWez3A+ZuyNpo4fM8riNh5LQO117U67gHa8FMtRek0nSQRYfnVfblhnKrEV/s8zYa+ho3SwPcwPDXAjfodxUK/VO5w/p6j+LofsqaYrXjWBYIi1NyVcbYhx9lhJfcTVUdTXC4ywB7IWxjYa1hA0aAPyitTcqHOzMLAmas1gw3daemoG0cMoY+jjkO04HU6uBKRjmbcIlkir79U7nD+nqP4uh+ynqnc4f09R/F0P2VX7PdOiwRFX36p3OH9PUfxdD9lZ/kBnXmjj7MeHC9xxDTRx1dFVdjkbb4QY5WwuMb9zd4DgDpx00UTgtEamiYqKBF+5ROd1jvVbZrld6SCtop3088Zt0PavaSCPW9IW1OSnnxiXGmO6nC2Na+mqJKumMlueynZEeyR6l7O1A11Zq7f7jrS2C0RqjRKNEWqeVDmTVZbZcebrTLGy9V1Q2moS9geGflPeWncQGgjvuarVYm06QNrIq+/VO5w/p6j+LofsqXPJvuuN8QZa0uJMc1zKirubzPSRsp2RCOn5mEhoGpdvdr0FvWrl8U0jWRstERWgREQEREBERAREQEREBERAXBcKltHQVFW8atgidIRrpqGgnn8S51iOdVzbZsoMYXRztk09lq3M36av7E4NHjcQPGg11yGL8L1ydrRTl+3LaamooJDrzaP7I0eJkrAt5qFP3NnFIjuuKcFzSfh4Y7lTN62HscvjIfF/CVNZAREQEREBERAREQEREBERAREQFVBfPx3Xe+ZPnFWvqqC+fjuu98yfOKytm80w6amV9z/wAUiqwzfsHzykyUNQ2tp2uP+zkGy8DqDmg9+RRfpMNebcqq7FNNG90tru0VNVEc3YpozsOPefGR/wAQeLK+SjioYUzvsk00gZS3JxttQSdBpLoGb+gSCMnqCvZY4qTAsWUSfugeKjrh3BUEm7trlVN178cX/N/opbKtXlFYpOL85cRXZkpkpWVRpKU66jsUX3tpHU7ZLv3isbZ6621Ia+WR5X+2XhbwzSfTMXYxBhoWrLbC1/mBbU3uqr3NGnPTxGFjD/H2b4Auvlf7ZeFvDNJ9MxZkzrCVoVfV01BQ1FdWTMgpqaJ0s0jz2rGNBLnHqABKrQzqzBuWZGPK2/1skjaTbMdvpnHdTwA9q3Tm1PO48ST1KbvK4vMllyDxC+B5ZNWNiomkdEkjQ8eNm2PGq7Fj7NXlNkQ2HkVlRes1cSS0FDO2ht1I1r66uezaEIOuy1rdRtPOh0Go5iSVJSp5HuCXW0x02J8Qx12zumk7C+IHp7GGA6dW341kXIhskFsyLpLlG0dmu9bUVMjuJ2HmEDvDsWvjPSt5KjLmtxaQKwc2MA3vLfGE+HL21j3taJaaoj9ZUQkkNe3o5iCOBBHWsq5MOZlRl1mLTeaahzbDdHsprlGT2rQToyboBYTqT7kuHFb8+6A2KCowHYcRtjHmmiuJpS4c/Y5Y3OOvTo6JvwnrULFkUnvKcxbWqoL5+O673zJ84qyzI69SYhygwrdp37c01sibM/XXakY3YcfG5pVad8/Hdd75k+cVa2eNJmCHTVhPJOzK9H+W8VLcKjsl9sobS1u0dXSs0+9zH9oAg/rNceIUAKW31lVRVdbTwPkgo2tfUPaN0bXODQT1bRA75HSs1yCzBny3zIoL7tvNukPma5RN1O3TuI2jpxLSA4dbdOJV3LTjqJ08pT2iMX+DnfKFWurI+UTUQVfJ+xVV0szJ6ea1mSKRjtWva7ZIcCOcEHVVuK3s3uyQnfyEvaRl8MVHzI1oLlw+3vUeDqb5Ct+8hL2kZfDFR8yNaC5cPt71Hg6m+QqKfpZGrMusPsxXjuyYakqnUrLnWx0zpms2jGHO0101GqlH6jW193lZ8XN/1FGzJa5UNnzawtdLnUx0tFS3OGWeaQ6NjYHAknqU+fTvym7u7P8AzD9SqzWvExwjTPqNbX3eVnxc3/UWYZO8m+hy5x5SYrgxXU3F9NHKwQPo2xh22wt12g882uvMs29O/Kbu7s/8w/Usyw3fLTiOy096sdfDX2+o2uw1ER1a/ZcWu07zmkeJY9smTTmhEXl35fed9/oswbdBpTXLSluGyNzZ2t7R5/aYNO+zrUc8I32uwzie24htr9mrt9Syoi6CWnXQ9R5j1EqzXMrCVBjnA91wtcdGxV0BYyTZ1MUg3skA6WuAPXpoqxcRWivw/fq+yXSEw1tDUPp52dDmkg6dI3bjxCyMF+KvDKYWlYWvVFiPDduv1uft0lwpmVER4hrmg6HrGuh6woKcszG/oszbmtVLMH27D7DRRbJ1DptdZnd/a0Z/wws15OOdMOFchsVW2vqGmvsEZntMbzqZBO7ZawDiGzO2j1P6lGCpmlqaiSonkdLNK8vke46lzidST16qMWLhtMyM0yMwLNmJmXa8OBr/ADG5/Z6+Rv8As6dmhedeBO5oPS4Ky+mghpaaKmp4mRQxMDI42DRrGgaAAcAAtA8iPL70NZePxZXwbNyxBpJFtDfHSt/Bj986v6wWdCkErOe/FbToSIiKygREQEREBERAREQEREBERAWjOXPfhZeTtd6cP2JbtU09BGdefV/ZHDxsieFvNQp+6TYpEl1wtguGT8BDJcqlvW89ji8YDJf4ggj5yeMaDAGceHcSTSbFHFVCGtJO7zPKDHIT07IdtDraFaw0hzQ5pBBGoI4qmhWY8jjMEY9yWtzaqfsl1smltrQT2zgxo7FIf2mbO/i5rkG50REBERAREQEREBERAREQEREBVQXz8d13vmT5xVr6qgvn47rvfMnzisrZvNMJD8kPD7cZ5Z5qYQk2D5tpaTsGum6bScsd3g9kZ8Sjk01NDWhw7JBU08mo4Oje0/0IIUoPuekzW4hxdT6HafSUzweGjXvH/wCwWsuVnhIYTztu7IIux0d00uVOAN2kuu2B3pBJu6NFdrb/AJJqJd4lzOibyZpsxYJWx1NVZwYdndsVcg7FoOnZlJ8TSq9LTQVV0ulJbKKMy1VXOyCFg/Ke9wa0eMkLMKzMKtqMkqHLdwf2GlvEld2TXQdiLO1j6+3fI498LM+RfhT0R500lwmi26SxwurnkjUGT1kQ7+07aH7BUVr3VZkZBy07NBhimy8wrShhp7XZ3wtcBoXuBY1zj3y3XvkrS2V/tl4W8M0n0zFu77oDO12aNiphrtMsrXno0dPKB80rSOV/tl4W8M0n0zFVj/RiaHLoExyNJj12RdacyaH8nR/P49lQMVjPKssMuIMh8SU9OwvnpYmVrABwhe17/wDyB6rmVGzz9EhY3yUXMdyfMJmNzXDsEoJaeInkB/rqtoLQfIYxFBdcmjZBI3zTZa2WJ0eu8RyuMrXadBc6Qfulb8WLkjS0oaD5dvtIxeGKf5kiggpk/dA8RwQ4Ww9hSOb/ALTVVjq+VjTvEcbHMbr1F0h0/YPQobLL2eNKJhY7yVf+79hP3tJ9NIq7r5+O673zJ84qzTJ6xS4ayswzY6hhZUUlthbO3T1spaHPH8RKrLvn47rvfMnziqcE62sQ3vyI7JbsSYnxfYbtAJ6GvsDoJmcdl0rBqOgjnB4EArUGZuELjgTHFzwvcgTLRSkRy6aCaI72SDqc0g9R1HBbw+5+e2RiDwP/AM6NbN5beWvojwfHja10+1c7IwiqDBvlpNdSf3CS7vF6nj4cuk+Y1llhmV598mHGuAbrUF1ws9rdJQF53yUpc0FvfjcQP2XNA9aVGtclPUT073PglfE5zHRuLTpq1wIcO8QSFxq9WsV10SnfyEvaRl8MVHzI1oLlw+3vUeDqb5Ct+8hL2kZfDFR8yNaC5cPt71Hg6m+QrHp+llDSNPDNUzsgp4pJppHBrI42lznE8ABvJXqehbE/c5ePIpPqWRcn727sG+GKf54VmKry5eCdNBVZ6FsT9zl48ik+pT+5JVLVUXJ8wzTVlNNTTs817UUrCxzdauYjUHeNxBW1UWPkzccaaAoc8vLL7zHeKHMS3QaQ12zR3LZHNM1v3uQ/tNBaT+o3pUxlg+ftuo7nkpjKnroGzRx2apqGNdwkijdJG7vhzGnxKnFbhtEoVmLOci8CT5i5lWzDzWP8xbfZ7hI3/Z0zCC868CdzQelwWDKYn3PahpBh/FNz7A3zY6qhgMvHsYYXbI6BqSevd0BZuW3DWZhKUdNBDS00VNTxMihiYGRxsGjWNA0AA4ABciItcgREQEREBERAREQEREBERAREQfjiGtLnEAAakngqp+UPjQY/zjxFiSGTbo5aow0RB3eZ4gI4yOjaDdo9bip5csfMEYCyWuLaWfsd1vettogD2zQ9p7LIP2WbW/g5zVWcgLc3JCzPGWua1ObhU9isF52aK5bR0bHqfvcx/Ycd59y560yiC5gEEag6goo38h3OBuNcGDBV8qtrENihDYnPPbVVINGtdrxczc13VsHeSVJBAREQEREBERAREQEREBERAVUF8/Hdd75k+cVa+oSXLkj5kVNxqahl7wmGSyve0OqqjXQknf8AeFkbPaK66ph6H3Pf2YYp8HxfSFZpy+cJG4YJtOMKeMGW01Bp6kgb+wzaAE954aB+2V7HJayVxVlZfrzX4gr7NVRV1KyGIUM0r3AtdqdduNu7varcGY2GoMYYEvWGJyxrbjRvhY941DJCNWP/AHXBrvEoteIy8UCrNTp5C2ExZcqp8RzxbNVfaova4t0PYItWMH8XZD3nBafHJBzK133zCWnvqo/0FM7CVkpcN4XteH6IaU1upI6aM6c4Y0N1PWdNT31cz5ImukEoYcv3247T/h+H/MVC01lf7ZeFvDNJ9MxS65T2RGLs0MfUN/sFxsdNS09rjo3srp5WPL2yyvJAZG4aaSDj07lgGDeSnmHZsX2a8VV5ws+Chr4KmVsdVOXlrJGuIAMIGug3akKqmSsU01Eyp4op4JIJ42yRSNLHscNQ5pGhBHEKuDlCZZXDLTHdTRGnkNlq5HTWup0Ja+InXsZPu2agEd48xCsiXh43wnh/GmH5rFiW2xV9DKdrZdqHMcOZ7HDe1w1O8dJ4ErHxZOCUK38qMxMRZa4mF8w9NGXPZ2OpppgXRVEeuuy4AjjzEbx4yDIWfllONr0gwEG3At01fctYQ7p0EYJHVqO/xXn485IF6gqZJ8FYipKylJ1bTXLWKVo6A9rS156yGrBm8l7N4z9jNot7W6kdkNwi2e/z6/0WTM4r85S1nmBi++46xTVYjxDVCetqDoA0aRxMHrY2N4NHAd8kkklbK5JuVtXjvHlNeq6meMPWaZs9RI5vazyt0cyEHjv0Luhv7QWycu+SDUCrjq8e4ggMDTqaK17RMnU6V4Gz1gNPUQpUYasdow3ZKay2K3wW+30zdmGCFujWjiekkneSdSTvKoyZoiNKj0VVBfPx3Xe+ZPnFWvqEly5I+ZFTcamoZe8Jhksr3tDqqo10JJ3/AHhUbPaK66kOT7n57ZGIPA//ADo1NSeKKeCSCeNskUjSx7HDUOaRoQRxCj5yXcj8WZXYtul3xBcLJUwVdB5mjbQzSvcHdka7Uh8bRpo08VIZUZrRN9YQrc5ReXUuW+ZNZa4Y3edNXrVWyQ79YXH1mvSw6tPeB4rW6sd5R2VjM08Ett9JJS016opRNb6mfUMaToHscWgkNcOgHe1p4KNXqQcyv05hLyuo/wBBZOPNWa85S3PyEvaRl8MVHzI1oLlw+3vUeDqb5CpWcmvL685aZdPw7fam31NW6vlqQ+ike+PZc1gA1e1p17U8FrHlG8n3GeY+ZUuJbHc7BT0b6SKEMrJ5mybTAddzYnDTf0q1S9YyTOoiRga/zYVxhacSU9OyplttUypZE8kNeWnXQkKQ/qxsSdxlp8pk+peP6kHMr9OYS8rqP9BPUg5lfpzCXldR/oK7a2K3iPY9WNiTuMtPlMn1LYGQPKIvGZWYUWGK3DlBQQvppZjNDM9ztWAbtDu4rU/qQcyv05hLyuo/0Fsjk5cn3GeXGZUWJb5c7BUUbKSWEso55nSbTwNNzomjTd0q3eMXDOgk2sSzp9pzGv8Ah+v/AMu9ZavDzCs9TiHAOIbBRPhjqrna6mjhfMSGNfJE5jS4gEgauGugPeWNXxQqwUzfufHsMxP4Ri+jWuvUg5lfpzCXldR/oKQHJaysxBlZh+82/EFZa6qWuq2TRGhlke0NDNDrtsbv72qy82Ss00iUtxoiLDQIiICIiAiIgIiICIiAiIgISANSdAEUbuXHnAMFYNOCbHVBuIL7C5szmO7akpDq1zupz97W9W2dxAQRe5XuZ4zKzWqDb6nstgs21RW3ZOrZND98mH7bhuPuWsWmURAREQe1gbFF4wZiy3YnsNSae4UEwlidwdwc1w4tcCQRxBKtGyRzLsmaeBabElocIpvwVdRl2r6WcAbTD0jiHcQRzHUCp9Z9kZmjfsqMaxX60OM1JJsx3Ghc7RlXDrvaehw3lruB6QSCFrSLG8tsb4dzCwlS4mwzWipopxo5p3SQSD10cjfyXDXm7xGoIJyRAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBEWN5k43w7l7hKqxNiatFNRQDRrRvknkPrY42/lOOnN3ydACQHl53Zl2TKzAtTiS7uEs34Khow7R9VOQdlg6BxLuAB5zoDVzjnFF4xniy44nv1Sai4V8xlldwbwa1o4NaAABwACyTPPNG/Zr41lv13cYaSPajt1C12rKSHXc0dLjuLncT0AADAUBERAREQEREGfZJ5r4oyoxQ272GfstJKQK63SvIhq2Dg4cHDU7LhvHWCQbIsnM0sJ5p4bF3w3WffowBWUMxAqKV54Pb0Hg4bj3wQKn17WCsV4hwZiCC/YYutRbbhAe1liPrhxa5p3OaeLSCCgt+RRv5P/KqwzjVlPY8aupsOYhdoxsrnbNHVO4bLifvbj7lx06HEnRSQBBGoOoKAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiEgDUnQBRv5QHKqwzgplRY8FOpsR4hbqx0rXbVHSu47Tgfvjh7lp06XAjRBtjOPNLCeVmGzd8SVn36QEUdDCQaiqeODG9A4uO4d8gGt3OzNbE+a+KHXe/TmKliJbQ26J5MFIw8Gji46Daed56gABjeNcV4hxniCe/YnutRcrhOe2llPrRwa1o3NaODQAAvFQEREBERAREQEREBERAW5sleUdmDlqILeKrz+sEejfO2ueT2NvRFJvdH1De39VaZRBZjlRylssceiKlddfQ/dX6A0V0c2IOd0Ml12HdW8OPuVuZpDmhzSCCNQRxVNCz/LrOXMrAAZDhvFddDRs5qKcien06BG/UN77dD1oLWUUKcEcty4RhkONMGU9R7qptU5jP8AKk2gT++FuPDHKuyYvTWCovtbZZXc0dxoXt077o9tg8bkG80WI2XNDLe8sa6148w1Ul35DbnFtjvtLtocx5xwWT0lZSVjC+kqoKho01MUgcBrzcyDnREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREBERARcFXWUlGwPq6qCnaddDLIGg6c/OsYvWaGW9mY510x5hqmLfyHXOLbPeaHbR5xzDigy5FozE/KuyYsrXinvtbepW88duoXu17zpNhh8TlpvG3LcuEgkhwZgunph+RU3Wcykj/dR7IB/fKCaziGtLnEAAakngtM5r8pbLHAQlpW3X0QXVmoFFa3NlDXdD5ddhvXvLh7lQNzFzlzKx+Hw4kxXXTUb+eigIgp9Ogxs0Du+7U9awBBubOrlHZg5lCe3mq84bBJq3ztoXkdkb0SybnSdY3N/VWmURAREQEREBERB//9k=" alt="TesterUp Logo">
    </div>
    <div class="app-name">TesterUp</div>
    <div class="stars-row">
      <span class="stars">★★★★★</span>
      <span class="rating-num">4.8/5</span>
    </div>
    <div class="rating-sub">Exclusive Rewards</div>
    <div class="spots-badge">
      <div class="spots-dot"></div>
      Limited reward spots currently available
    </div>
  </div>

  <div class="progress-wrap" id="progressWrap">
    <div class="progress-labels">
      <span class="progress-label">Progress</span>
      <span class="step-indicator" id="stepIndicator">1 / 3</span>
    </div>
    <div class="progress-track">
      <div class="progress-fill" id="progressFill"></div>
    </div>
  </div>

  <div class="card" id="quizCard">

    <!-- SLIDE 1 -->
    <div class="slide active" id="slide1">
      <div class="urgency-badge">🔥 High-paying offers are filling quickly</div>
      <div class="slide-headline">What type of rewards interests you the most?</div>
      <div class="slide-sub">Users are currently unlocking reward offers in just a few minutes.</div>
      <div class="btn-group">
        <button class="choice-btn" onclick="nextSlide(2)"><span class="btn-emoji">🎮</span> Testing games</button>
        <button class="choice-btn" onclick="nextSlide(2)"><span class="btn-emoji">📱</span> Trying new apps</button>
        <button class="choice-btn" onclick="nextSlide(2)"><span class="btn-emoji">📝</span> Completing surveys</button>
        <button class="choice-btn" onclick="nextSlide(2)"><span class="btn-emoji">🎥</span> Watching videos</button>
      </div>
      <div class="trust-text"><strong>Thousands of users</strong> are already earning rewards daily.</div>
    </div>

    <!-- SLIDE 2 -->
    <div class="slide" id="slide2">
      <div class="slide-headline">How old are you?</div>
      <div class="slide-sub">This helps match you with the highest-value reward opportunities available in your region.</div>
      <div class="btn-group">
        <button class="choice-btn" onclick="nextSlide(3)"><span class="btn-emoji">🧑</span> Under 21</button>
        <button class="choice-btn" onclick="nextSlide(3)"><span class="btn-emoji">🙋</span> 21 or older</button>
      </div>
      <div class="orange-note">Some exclusive offers are only available to eligible users.</div>
    </div>

    <!-- SLIDE 3 -->
    <div class="slide" id="slide3">
      <div class="slide-headline">How much would you like to earn monthly?</div>
      <div class="slide-sub">The more tasks you complete, the more reward opportunities you may unlock.</div>
      <div class="info-card">📊 Most active users choose offers between $500–$1,000 monthly.</div>
      <div class="btn-group" id="earningBtns">
        <button class="choice-btn" onclick="selectEarning(this)"><span class="btn-emoji">💵</span> $50 – $100</button>
        <button class="choice-btn" onclick="selectEarning(this)"><span class="btn-emoji">💰</span> $100 – $500</button>
        <button class="choice-btn" onclick="selectEarning(this)"><span class="btn-emoji">🏆</span> $500 – $1,000</button>
        <button class="choice-btn" onclick="selectEarning(this)"><span class="btn-emoji">🚀</span> $1,000+</button>
      </div>
      <div class="trust-checks">
        <div class="trust-check"><span class="check-icon">✔</span> Many users complete simple tasks daily</div>
        <div class="trust-check"><span class="check-icon">✔</span> New reward opportunities are added regularly</div>
        <div class="trust-check"><span class="check-icon">✔</span> Popular offers can disappear quickly</div>
        <div class="trust-check"><span class="check-icon">✔</span> Some users unlock premium offers within minutes</div>
      </div>
    </div>

  </div>

  <!-- FINAL SECTION -->
  <div class="final-section" id="finalSection">
    <div class="final-card">

      <div class="unlock-wrap">
        <div class="unlock-ring"></div>
        <div class="unlock-ring2"></div>
        <div class="unlock-icon">🔓</div>
      </div>

      <div class="final-headline">Your reward access is almost ready</div>
      <div class="final-sub">You are one step away from unlocking currently available reward offers.</div>


      <!-- Complete at least 1 offer prompt -->
      <div class="offer-prompt-card">
        <span class="offer-prompt-icon">⚠</span>
        <span>Complete at least <strong>1 reward offer</strong> to activate full access and unlock additional opportunities.</span>
      </div>

      <button class="cta-btn" onclick="handleCTA()">Continue to Available Offers →</button>

      <div class="beginner-line">Most users start with a simple beginner offer that takes only a few minutes.</div>

      <div class="final-trust">
        <div class="final-trust-item"><span class="chk">✓</span> Thousands of users already use TesterUp daily</div>
        <div class="final-trust-item"><span class="chk">✓</span> 100% free to start</div>
        <div class="final-trust-item"><span class="chk">✓</span> No subscription required</div>
      </div>

      <!-- Live activity feed -->
      <div class="live-activity">
        <div class="live-activity-title">Live Activity</div>
        <div class="live-item"><div class="live-dot"></div> New reward offers added recently</div>
        <div class="live-item"><div class="live-dot"></div> Beginner-friendly tasks currently available</div>
        <div class="live-item"><div class="live-dot"></div> Some offers may close once spots are filled</div>
      </div>

      <div class="urgency-footer">
        Users who complete their first offer often unlock additional reward opportunities.
      </div>

      <div class="urgency-line">Available reward opportunities may update throughout the day.</div>

    </div>
  </div>

  <footer>
    <div class="footer-links">
      <a href="#">Privacy Policy</a><span class="sep">·</span>
      <a href="#">Terms</a><span class="sep">·</span>
      <a href="#">Contact</a>
    </div>
    <div class="footer-copy">© 2025 TesterUp. All rights reserved.</div>
  </footer>

</div><!-- end page-wrap -->

<script>
const OFFER_URL = "https://raintrkr.com/r/eyJ0IjoidGVzdGVydXAtYSIsInRpZCI6IjhiZmEzMDJjMmQ5YmQ5OGZjY2IxIiwidHMiOjE3NzgwOTAzMjkxNzZ9?feb=1";

/* ─── ELIGIBILITY LOADING SCREEN ─── */
const eligMsgs = [
  "Checking available reward tasks…",
  "Matching beginner-friendly offers…",
  "Unlocking first-time user rewards…",
  "Activating available offers…",
  "Preparing your reward dashboard…"
];

function runEligScreen(onDone) {
  var bar = document.getElementById('eligBar');
  var msg = document.getElementById('eligMsg');
  var screen = document.getElementById('eligScreen');
  var totalDur = 3200;
  var msgInterval = totalDur / eligMsgs.length;
  var idx = 0;
  var startTime = null;

  // Reset bar and first message
  bar.style.width = '0%';
  msg.textContent = eligMsgs[0];
  msg.style.opacity = '1';

  function step(ts) {
    if (!startTime) startTime = ts;
    var elapsed = ts - startTime;
    var pct = Math.min((elapsed / totalDur) * 100, 100);
    bar.style.width = pct + '%';

    var newIdx = Math.min(Math.floor(elapsed / msgInterval), eligMsgs.length - 1);
    if (newIdx !== idx) {
      idx = newIdx;
      msg.style.opacity = '0';
      setTimeout(function() {
        msg.textContent = eligMsgs[idx];
        msg.style.opacity = '1';
      }, 180);
    }

    if (elapsed < totalDur) {
      requestAnimationFrame(step);
    } else {
      setTimeout(function() {
        if (typeof onDone === 'function') onDone();
      }, 200);
    }
  }
  requestAnimationFrame(step);
}

/* ─── QUIZ LOGIC ─── */
var currentSlide = 1;

function nextSlide(target) {
  var current = document.getElementById('slide' + currentSlide);
  current.style.transition = 'opacity 0.2s ease, transform 0.2s ease';
  current.style.opacity = '0';
  current.style.transform = 'translateY(-16px)';
  setTimeout(function() {
    current.classList.remove('active');
    current.style.cssText = '';
    var next = document.getElementById('slide' + target);
    next.classList.add('active');
    currentSlide = target;
    document.getElementById('stepIndicator').textContent = target + ' / 3';
    document.getElementById('progressFill').style.width = target === 1 ? '33%' : target === 2 ? '66%' : '100%';
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }, 210);
}

function selectEarning(btn) {
  var btns = document.querySelectorAll('#earningBtns .choice-btn');
  for (var i = 0; i < btns.length; i++) btns[i].classList.remove('selected');
  btn.classList.add('selected');

  setTimeout(function() {
    var progressFill = document.getElementById('progressFill');
    var progressWrap = document.getElementById('progressWrap');
    var quizCard = document.getElementById('quizCard');
    progressFill.style.width = '100%';
    document.getElementById('stepIndicator').textContent = '3 / 3';
    quizCard.style.transition = 'opacity 0.32s ease, transform 0.32s ease';
    quizCard.style.opacity = '0';
    quizCard.style.transform = 'translateY(-18px)';
    progressWrap.style.transition = 'opacity 0.32s ease';
    progressWrap.style.opacity = '0';

    setTimeout(function() {
      quizCard.style.display = 'none';
      progressWrap.style.display = 'none';
      window.scrollTo({ top: 0, behavior: 'smooth' });

      var eligScreen = document.getElementById('eligScreen');
      eligScreen.style.opacity = '1';
      eligScreen.style.display = 'flex';

      runEligScreen(function() {
        eligScreen.style.transition = 'opacity 0.45s ease';
        eligScreen.style.opacity = '0';
        setTimeout(function() {
          eligScreen.style.display = 'none';
          document.getElementById('finalSection').classList.add('active');
          window.scrollTo({ top: 0, behavior: 'smooth' });
        }, 460);
      });
    }, 330);
  }, 500);
}

/* ─── CTA REDIRECT OVERLAY ─── */
function handleCTA() {
  var overlay = document.getElementById('redirectOverlay');
  var redirMsg = document.getElementById('redirMsg');
  overlay.classList.add('show');

  setTimeout(function() {
    redirMsg.style.opacity = '0';
    setTimeout(function() {
      redirMsg.textContent = 'Redirecting to reward dashboard…';
      redirMsg.style.opacity = '1';
    }, 200);
  }, 700);

  setTimeout(function() {
    window.location.href = OFFER_URL;
  }, 1500);
}
</script>

</body>
</html>
