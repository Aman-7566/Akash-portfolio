<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>Akash Kourav — BI Analyst & Power BI Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&family=Space+Grotesk:wght@400;500;700&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
:root{
  --navy:#0f1629;--navy2:#141c35;--navy3:#1a2340;
  --orange:#f05a28;--orange2:#ff7043;
  --text:#ffffff;--muted:#a0aec0;
  --card:rgba(255,255,255,0.05);--border:rgba(255,255,255,0.09);
}
html{scroll-behavior:smooth;}
body{background:var(--navy);color:var(--text);font-family:'Poppins',sans-serif;overflow-x:hidden;}

/* NAV */
nav{display:flex;align-items:center;justify-content:space-between;padding:0 2.5rem;height:64px;position:fixed;top:0;left:0;right:0;z-index:300;background:rgba(15,22,41,0.98);backdrop-filter:blur(20px);border-bottom:1px solid rgba(255,255,255,0.06);}
.nav-logo{width:38px;height:38px;border-radius:50%;background:var(--orange);display:flex;align-items:center;justify-content:center;font-weight:800;font-size:.85rem;color:#fff;flex-shrink:0;}
.nav-name{font-weight:700;font-size:.95rem;flex-shrink:0;margin-left:.6rem;}
.nav-tabs{display:flex;align-items:center;gap:.15rem;background:rgba(255,255,255,0.05);border:1px solid var(--border);border-radius:100px;padding:.2rem;margin:0 1.5rem;overflow-x:auto;scrollbar-width:none;flex:1;}
.nav-tabs::-webkit-scrollbar{display:none;}
.nav-tab{padding:.38rem .85rem;border-radius:100px;color:var(--muted);font-size:.72rem;font-weight:600;cursor:pointer;border:none;background:transparent;transition:all .22s;white-space:nowrap;font-family:'Poppins',sans-serif;}
.nav-tab:hover{color:#fff;}
.nav-tab.active{background:var(--orange);color:#fff;}
.nav-actions{display:flex;align-items:center;gap:.5rem;flex-shrink:0;}
.btn-edit{display:inline-flex;align-items:center;gap:.3rem;padding:.38rem .85rem;border-radius:100px;border:none;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;font-size:.72rem;transition:all .2s;}
.btn-edit.locked{background:rgba(255,255,255,.08);color:var(--muted);border:1px solid rgba(255,255,255,.12);}
.btn-edit.locked:hover{background:rgba(255,255,255,.13);color:#fff;}
.btn-edit.unlocked{background:linear-gradient(135deg,#16a34a,#15803d);color:#fff;border:1px solid rgba(34,197,94,.3);}
.btn-resume{background:var(--orange);color:#fff;padding:.38rem 1rem;border-radius:100px;font-weight:700;font-size:.72rem;display:inline-flex;align-items:center;gap:.3rem;transition:all .2s;border:none;cursor:pointer;}
.btn-resume:hover{background:var(--orange2);transform:translateY(-1px);}

/* PAGES */
.page{display:none;animation:fade .3s ease;}
.page.active{display:block;}
@keyframes fade{from{opacity:0;transform:translateY(10px);}to{opacity:1;}}

/* ======================== HERO — WIDE SPACED ======================== */
.hero{
  min-height:100vh;
  display:grid;
  grid-template-columns:minmax(300px,420px) 1fr minmax(300px,420px);
  align-items:center;
  gap:4rem;
  padding:88px 5rem 3rem;
  position:relative;
  overflow:hidden;
}
.deco{position:absolute;border-radius:50%;border:1px dashed rgba(255,255,255,.04);pointer-events:none;}
.deco-1{width:620px;height:620px;right:-140px;top:-100px;}
.deco-2{width:380px;height:380px;left:-90px;bottom:-80px;}

/* LEFT: Info panel */
.hero-left{z-index:2;display:flex;flex-direction:column;gap:1.4rem;}
.hero-eyebrow{color:var(--muted);font-size:.9rem;font-weight:400;}
.hero-name{color:var(--orange);font-size:clamp(1.8rem,3vw,3rem);font-weight:900;line-height:1.05;}
.hero-role{font-size:clamp(1rem,1.6vw,1.3rem);font-weight:700;margin-top:.15rem;white-space:nowrap;}
.hero-desc{color:var(--muted);font-size:.84rem;line-height:1.85;max-width:400px;}

.info-panel{background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.08);border-radius:20px;padding:1.4rem;display:flex;flex-direction:column;gap:.7rem;}
.info-title{font-size:.63rem;letter-spacing:.13em;text-transform:uppercase;color:var(--orange);font-weight:700;margin-bottom:.2rem;}
.info-item{display:flex;align-items:center;gap:.9rem;padding:.6rem .8rem;border-radius:10px;background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.05);transition:all .2s;cursor:pointer;text-decoration:none;}
.info-item:hover{border-color:rgba(240,90,40,.35);background:rgba(240,90,40,.06);}
.info-icon{font-size:1.1rem;flex-shrink:0;width:28px;text-align:center;}
.info-text{flex:1;}
.info-label{font-size:.57rem;color:var(--muted);line-height:1;margin-bottom:3px;}
.info-value{font-size:.78rem;font-weight:600;color:#fff;}
.avail{display:inline-flex;align-items:center;gap:.4rem;background:rgba(34,197,94,.11);border:1px solid rgba(34,197,94,.3);color:#4ade80;padding:.32rem .85rem;border-radius:100px;font-size:.67rem;font-weight:700;width:fit-content;margin-top:.2rem;}
.avail::before{content:'';width:6px;height:6px;border-radius:50%;background:#4ade80;flex-shrink:0;animation:pulse 1.5s infinite;}
@keyframes pulse{0%,100%{opacity:1;}50%{opacity:.35;}}

.hero-ctas{display:flex;align-items:center;gap:.8rem;flex-wrap:wrap;}
.btn-primary{background:var(--orange);color:#fff;padding:.65rem 1.6rem;border-radius:100px;font-weight:700;font-size:.84rem;border:none;cursor:pointer;font-family:'Poppins',sans-serif;transition:all .2s;}
.btn-primary:hover{background:var(--orange2);transform:translateY(-2px);box-shadow:0 6px 20px rgba(240,90,40,.28);}
.btn-circle{width:42px;height:42px;border-radius:50%;border:2px solid var(--orange);display:flex;align-items:center;justify-content:center;color:var(--orange);font-size:1rem;transition:all .2s;background:transparent;cursor:pointer;}
.btn-circle:hover{background:var(--orange);color:#fff;}
.follow{display:flex;align-items:center;gap:.7rem;font-size:.76rem;color:var(--muted);}
.socials{display:flex;gap:.35rem;}
.soc{width:33px;height:33px;border-radius:50%;display:flex;align-items:center;justify-content:center;text-decoration:none;font-weight:700;font-size:.65rem;transition:all .2s;color:#fff;}
.soc:hover{transform:scale(1.15);}
.soc-li{background:#0077b5;}
.soc-gh{background:#24292e;}
.soc-em{background:var(--orange);}

/* CENTER: Profile */
.hero-center{display:flex;justify-content:center;align-items:center;position:relative;z-index:2;}
.profile-wrap{position:relative;width:320px;height:320px;}
.ring{position:absolute;inset:0;border-radius:50%;border:2px solid var(--orange);animation:spinRing 20s linear infinite;opacity:.75;}
.profile-circle{position:absolute;top:28px;left:28px;width:264px;height:264px;border-radius:50%;background:linear-gradient(145deg,#7a2d12,var(--orange));overflow:hidden;cursor:pointer;transition:all .3s;box-shadow:0 0 40px rgba(240,90,40,.28);}
.profile-circle:hover{box-shadow:0 0 60px rgba(240,90,40,.45);}
.profile-img{width:100%;height:100%;object-fit:cover;display:block;}
.cam-btn{position:absolute;bottom:18px;right:18px;width:44px;height:44px;border-radius:50%;background:var(--orange);display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:1.1rem;z-index:3;box-shadow:0 4px 16px rgba(240,90,40,.45);transition:all .2s;}
.cam-btn:hover{background:var(--orange2);transform:scale(1.1);}
.metric{position:absolute;background:rgba(10,15,35,.92);backdrop-filter:blur(14px);border:1px solid rgba(255,255,255,.13);border-radius:12px;padding:.6rem .9rem;text-align:center;white-space:nowrap;box-shadow:0 8px 28px rgba(0,0,0,.35);}
.metric-val{font-size:1.4rem;font-weight:900;line-height:1;}
.metric-lbl{font-size:.58rem;color:var(--muted);margin-top:2px;}
.m1{top:5px;right:-55px;animation:mf1 3.2s ease-in-out infinite;}
.m2{top:50%;left:-65px;transform:translateY(-50%);animation:mf2 3.6s ease-in-out .5s infinite;}
.m3{bottom:10px;right:-45px;animation:mf3 3.2s ease-in-out 1s infinite;}
@keyframes spinRing{to{transform:rotate(360deg);}}
@keyframes mf1{0%,100%{transform:translateY(0);}50%{transform:translateY(-8px);}}
@keyframes mf2{0%,100%{transform:translateY(-50%);}50%{transform:translateY(calc(-50% - 8px));}}
@keyframes mf3{0%,100%{transform:translateY(0);}50%{transform:translateY(-7px);}}

/* RIGHT: text content */
.hero-right{z-index:2;display:flex;flex-direction:column;justify-content:center;gap:1.2rem;}

/* ======================== STATS ======================== */
.stats-sec{padding:2.5rem 3rem;background:linear-gradient(135deg,rgba(240,90,40,.032),rgba(240,90,40,.008));border-top:1px solid rgba(240,90,40,.1);border-bottom:1px solid rgba(240,90,40,.1);overflow:hidden;}
.stats-title{text-align:center;margin-bottom:2rem;}
.stats-title h3{font-size:1.3rem;font-weight:800;margin-bottom:.3rem;}
.stats-title p{color:var(--muted);font-size:.84rem;}
.stats-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:1.1rem;max-width:1100px;margin:0 auto;}
@media(max-width:900px){.stats-grid{grid-template-columns:repeat(3,1fr);}}
@media(max-width:550px){.stats-grid{grid-template-columns:repeat(2,1fr);}}
.scard{background:linear-gradient(145deg,rgba(20,28,53,.97),rgba(26,35,64,.93));border:1px solid rgba(240,90,40,.16);border-radius:18px;padding:1.5rem 1rem;text-align:center;position:relative;overflow:hidden;transition:all .4s ease;box-shadow:0 16px 40px rgba(0,0,0,.4),inset 0 1px 0 rgba(255,255,255,.06);}
.scard::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--orange),transparent);opacity:.6;}
.scard:hover{transform:translateY(-10px) scale(1.04);border-color:rgba(240,90,40,.55);box-shadow:0 28px 60px rgba(240,90,40,.18);}
.sglow{position:absolute;width:80px;height:80px;border-radius:50%;background:var(--orange);filter:blur(38px);opacity:.1;top:50%;left:50%;transform:translate(-50%,-50%);transition:opacity .4s;}
.scard:hover .sglow{opacity:.25;}
.scard-icon{font-size:2rem;margin-bottom:.65rem;display:block;filter:drop-shadow(0 4px 10px rgba(240,90,40,.3));}
.scard-val{font-size:2.1rem;font-weight:900;color:var(--orange);line-height:1;margin-bottom:.3rem;text-shadow:0 0 20px rgba(240,90,40,.35);}
.sline{width:28px;height:2px;background:linear-gradient(90deg,var(--orange),transparent);border-radius:2px;margin:.6rem auto .5rem;}
.scard-label{font-size:.8rem;color:#fff;font-weight:700;margin-bottom:.3rem;}
.scard-desc{font-size:.68rem;color:var(--muted);line-height:1.5;}

/* ======================== HERO VISUAL — Radar/Donut ======================== */
.hero-visual-wrap{max-width:700px;margin:2.5rem auto 0;background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.08);border-radius:20px;padding:1.8rem;display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;align-items:center;}
.hero-visual-title{font-size:.72rem;color:var(--muted);margin-bottom:1rem;font-weight:600;text-transform:uppercase;letter-spacing:.08em;text-align:center;grid-column:1/-1;}
.radar-wrap{display:flex;flex-direction:column;align-items:center;}
.radar-wrap canvas{max-width:260px;max-height:260px;}
.skill-bars{display:flex;flex-direction:column;gap:.7rem;justify-content:center;}
.skill-bar-item{}
.skill-bar-label{display:flex;justify-content:space-between;font-size:.7rem;font-weight:600;margin-bottom:.25rem;}
.skill-bar-label span:last-child{color:var(--orange);}
.skill-bar-track{height:6px;background:rgba(255,255,255,.07);border-radius:6px;overflow:hidden;}
.skill-bar-fill{height:100%;border-radius:6px;background:linear-gradient(90deg,var(--orange),var(--orange2));transition:width 1.4s cubic-bezier(.4,0,.2,1);}

/* ======================== LANDING MARKET SECTION ======================== */
.home-market-sec{padding:2.5rem 3rem 3rem;background:linear-gradient(135deg,rgba(15,22,41,1),rgba(20,28,53,1));}
.home-market-inner{max-width:1100px;margin:0 auto;}
.home-market-hdr{display:flex;align-items:center;justify-content:space-between;margin-bottom:1.5rem;flex-wrap:wrap;gap:1rem;}
.home-market-hdr h3{font-size:1.1rem;font-weight:800;}
.home-market-hdr p{color:var(--muted);font-size:.8rem;margin-top:.2rem;}
.refresh-small{background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.25);color:var(--orange);padding:.35rem 1rem;border-radius:100px;font-family:'Poppins',sans-serif;font-size:.7rem;font-weight:700;cursor:pointer;transition:all .2s;display:inline-flex;align-items:center;gap:.35rem;}
.refresh-small:hover{background:rgba(240,90,40,.2);}

/* ======================== MARKET CARDS ======================== */
.market-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(270px,1fr));gap:1.2rem;}
.market-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:1.3rem;transition:all .3s;cursor:pointer;text-decoration:none;display:block;position:relative;overflow:hidden;}
.market-card:hover{border-color:rgba(240,90,40,.45);transform:translateY(-4px);box-shadow:0 12px 30px rgba(0,0,0,.3);}
.market-card::after{content:'↗';position:absolute;top:.9rem;right:.9rem;color:var(--orange);font-size:.9rem;opacity:0;transition:opacity .25s;}
.market-card:hover::after{opacity:1;}
.market-tag{font-size:.65rem;letter-spacing:.1em;text-transform:uppercase;color:var(--orange);font-weight:700;margin-bottom:.4rem;}
.market-title{font-weight:700;font-size:.88rem;margin-bottom:.4rem;color:#fff;padding-right:1.2rem;}
.market-desc{color:var(--muted);font-size:.79rem;line-height:1.65;}
.market-date{font-size:.63rem;color:rgba(160,174,192,.5);margin-top:.6rem;}
.market-loading{text-align:center;padding:3rem;color:var(--muted);}
.market-spinner{width:36px;height:36px;border:3px solid rgba(240,90,40,.2);border-top-color:var(--orange);border-radius:50%;animation:spin .8s linear infinite;margin:0 auto .8rem;}
@keyframes spin{to{transform:rotate(360deg);}}

/* ======================== CONTACT ======================== */
.contact-section{padding:3rem;background:linear-gradient(135deg,rgba(15,22,41,1),rgba(20,28,53,1));}
.contact-wrap{max-width:780px;margin:0 auto;}
.contact-header{text-align:center;margin-bottom:2rem;}
.contact-header .sec-label-sm{color:var(--orange);font-size:.7rem;letter-spacing:.14em;text-transform:uppercase;font-weight:700;display:block;margin-bottom:.4rem;}
.contact-header h2{font-size:clamp(1.5rem,3vw,2.1rem);font-weight:850;margin-bottom:.5rem;}
.contact-header p{color:var(--muted);font-size:.84rem;}
.contact-form{background:linear-gradient(145deg,rgba(20,28,53,.98),rgba(15,22,41,.98));border:1px solid rgba(240,90,40,.2);border-radius:28px;padding:2.5rem;position:relative;overflow:hidden;box-shadow:0 30px 80px rgba(0,0,0,.5);}
.contact-form::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,transparent,var(--orange),var(--orange2),transparent);}
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.2rem;}
.form-grid .full{grid-column:1/-1;}
.fg-contact{position:relative;margin:0;}
.fg-contact label{display:block;font-size:.66rem;color:var(--muted);margin-bottom:.4rem;font-weight:700;text-transform:uppercase;letter-spacing:.07em;}
.fg-contact .fi{position:absolute;left:.9rem;top:50%;transform:translateY(-50%);font-size:.9rem;pointer-events:none;z-index:2;}
.fg-contact input,.fg-contact select,.fg-contact textarea{width:100%;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.09);border-radius:13px;padding:.72rem .9rem .72rem 2.6rem;color:#fff;font-family:'Poppins',sans-serif;font-size:.83rem;outline:none;transition:all .25s;appearance:none;}
.fg-contact textarea{padding:.72rem .9rem;height:100px;resize:none;}
.fg-contact.no-icon input,.fg-contact.no-icon select,.fg-contact.no-icon textarea{padding-left:.9rem;}
.fg-contact input:focus,.fg-contact textarea:focus{border-color:var(--orange);background:rgba(240,90,40,.06);box-shadow:0 0 0 3px rgba(240,90,40,.12);}
.fg-contact select option{background:#1a2340;color:#fff;}
.form-submit{width:100%;padding:.9rem;background:linear-gradient(135deg,var(--orange),var(--orange2));color:#fff;border:none;border-radius:14px;font-family:'Poppins',sans-serif;font-weight:800;font-size:.92rem;cursor:pointer;transition:all .25s;box-shadow:0 8px 24px rgba(240,90,40,.4);margin-top:.5rem;}
.form-submit:hover{transform:translateY(-2px);box-shadow:0 12px 32px rgba(240,90,40,.55);}
.form-orbs{position:absolute;pointer-events:none;}
.form-orb{position:absolute;border-radius:50%;filter:blur(60px);opacity:.08;}
.form-orb-1{width:200px;height:200px;background:var(--orange);top:-50px;right:-50px;}
.form-orb-2{width:150px;height:150px;background:#4ade80;bottom:-40px;left:-40px;}

/* ======================== GROWTH KPI ======================== */
.growth-kpi-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1.1rem;margin-bottom:2rem;}
@media(max-width:800px){.growth-kpi-grid{grid-template-columns:repeat(2,1fr);}}
.gkpi{background:linear-gradient(145deg,rgba(20,28,53,.97),rgba(26,35,64,.93));border:1px solid rgba(240,90,40,.16);border-radius:18px;padding:1.4rem 1.2rem;position:relative;overflow:hidden;transition:all .3s;}
.gkpi:hover{transform:translateY(-6px);border-color:rgba(240,90,40,.4);box-shadow:0 16px 40px rgba(240,90,40,.12);}
.gkpi::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--orange),transparent);opacity:.5;}
.gkpi-icon{font-size:1.6rem;margin-bottom:.6rem;}
.gkpi-val{font-size:2rem;font-weight:900;color:var(--orange);line-height:1;}
.gkpi-label{font-size:.75rem;color:#cbd5e1;font-weight:600;margin:.3rem 0 .5rem;}
.gkpi-badge{display:inline-flex;align-items:center;gap:.25rem;padding:.18rem .6rem;border-radius:100px;font-size:.62rem;font-weight:700;}
.gkpi-badge.up{background:rgba(74,222,128,.12);border:1px solid rgba(74,222,128,.25);color:#4ade80;}
.gkpi-badge.down{background:rgba(239,68,68,.12);border:1px solid rgba(239,68,68,.25);color:#f87171;}
.gkpi-sub{font-size:.67rem;color:var(--muted);margin-top:.3rem;}

.growth-container{background:var(--card);border:1px solid var(--border);border-radius:18px;padding:1.8rem;position:relative;overflow:hidden;}
.growth-canvas{width:100%;height:380px;}

/* ======================== CERTS SUMMARY ======================== */
.cert-summary-bar{background:linear-gradient(135deg,rgba(240,90,40,.08),rgba(240,90,40,.02));border:1px solid rgba(240,90,40,.18);border-radius:18px;padding:1.4rem 1.8rem;margin-bottom:2rem;display:grid;grid-template-columns:1fr 1fr 1fr;gap:1.5rem;align-items:center;}
@media(max-width:700px){.cert-summary-bar{grid-template-columns:1fr;}}
.cs-stat{text-align:center;}
.cs-val{font-size:2.2rem;font-weight:900;color:var(--orange);}
.cs-lbl{font-size:.72rem;color:var(--muted);font-weight:600;margin-top:.2rem;}
.cs-divider{width:1px;height:60px;background:rgba(255,255,255,.08);margin:0 auto;}
.skills-learned-wrap{margin-bottom:2rem;}
.skills-learned-title{font-size:.68rem;color:var(--muted);text-transform:uppercase;letter-spacing:.1em;font-weight:700;margin-bottom:.75rem;}
.skills-learned-chips{display:flex;flex-wrap:wrap;gap:.4rem;}
.sl-chip{background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.09);color:#cbd5e1;padding:.24rem .7rem;border-radius:100px;font-size:.68rem;font-weight:500;transition:all .2s;}
.sl-chip.hot{background:rgba(240,90,40,.1);border-color:rgba(240,90,40,.3);color:var(--orange);}
.sl-chip:hover{border-color:rgba(240,90,40,.4);color:var(--orange);background:rgba(240,90,40,.08);}

/* ======================== GENERAL SECTIONS ======================== */
.sec{padding:5rem 3rem 3.5rem;position:relative;}
.sec-label{color:var(--orange);font-size:.68rem;letter-spacing:.14em;text-transform:uppercase;margin-bottom:.4rem;font-weight:700;}
.sec h2{font-size:clamp(1.5rem,2.6vw,2.1rem);font-weight:850;margin-bottom:.4rem;}
.sec-bar{height:3px;width:46px;background:var(--orange);border-radius:3px;margin-bottom:2rem;}
.sec-sub{color:var(--muted);font-size:.84rem;line-height:1.8;max-width:500px;margin-bottom:2rem;}

/* LIGHTBOX */
.lb{display:none;position:fixed;inset:0;z-index:999;background:rgba(0,0,0,.92);backdrop-filter:blur(8px);align-items:center;justify-content:center;}
.lb.open{display:flex;}
.lb-inner{position:relative;}
.lb-inner img{max-width:92vw;max-height:90vh;border-radius:12px;object-fit:contain;}
.lb-close{position:absolute;top:-14px;right:-14px;width:30px;height:30px;border-radius:50%;background:var(--orange);color:#fff;border:none;font-size:1rem;cursor:pointer;display:flex;align-items:center;justify-content:center;}

/* LOGIN */
.login-overlay{display:none;position:fixed;inset:0;z-index:800;background:rgba(0,0,0,.88);backdrop-filter:blur(10px);align-items:center;justify-content:center;}
.login-overlay.open{display:flex;}
.login-box{background:linear-gradient(145deg,var(--navy2),#0d1528);border:1px solid rgba(240,90,40,.3);border-radius:24px;padding:2.2rem;width:100%;max-width:380px;position:relative;box-shadow:0 30px 70px rgba(0,0,0,.6);}
.login-box::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,transparent,var(--orange),transparent);border-radius:24px 24px 0 0;}
.login-logo{width:52px;height:52px;border-radius:50%;background:linear-gradient(135deg,var(--orange),var(--orange2));display:flex;align-items:center;justify-content:center;font-weight:900;font-size:1rem;margin:0 auto 1.2rem;box-shadow:0 8px 24px rgba(240,90,40,.35);}
.login-title{text-align:center;font-size:1.1rem;font-weight:840;margin-bottom:.25rem;}
.login-sub{text-align:center;color:var(--muted);font-size:.77rem;margin-bottom:1.5rem;}
.login-err{background:rgba(239,68,68,.1);border:1px solid rgba(239,68,68,.3);color:#fca5a5;border-radius:10px;padding:.6rem .9rem;font-size:.75rem;margin-bottom:.9rem;display:none;text-align:center;}
.login-err.show{display:block;}
.lf{margin-bottom:.9rem;position:relative;}
.lf label{display:block;font-size:.68rem;color:var(--muted);margin-bottom:.35rem;font-weight:700;text-transform:uppercase;letter-spacing:.06em;}
.lf input{width:100%;background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.1);border-radius:11px;padding:.72rem 1rem .72rem 2.6rem;color:#fff;font-family:'Poppins',sans-serif;font-size:.85rem;outline:none;transition:all .2s;}
.lf input:focus{border-color:var(--orange);background:rgba(240,90,40,.06);}
.lf-icon{position:absolute;left:.9rem;bottom:.78rem;font-size:.9rem;pointer-events:none;}
.login-btn{width:100%;padding:.82rem;background:linear-gradient(135deg,var(--orange),var(--orange2));color:#fff;border:none;border-radius:11px;font-family:'Poppins',sans-serif;font-weight:800;font-size:.9rem;cursor:pointer;transition:all .2s;box-shadow:0 6px 18px rgba(240,90,40,.35);margin-top:.4rem;}
.login-btn:hover{transform:translateY(-2px);box-shadow:0 10px 28px rgba(240,90,40,.48);}
.login-xbtn{position:absolute;top:.9rem;right:.9rem;background:rgba(255,255,255,.08);border:1px solid rgba(255,255,255,.1);color:var(--muted);width:28px;height:28px;border-radius:50%;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:.78rem;transition:all .2s;}
.login-xbtn:hover{background:rgba(255,255,255,.15);color:#fff;}

/* EDIT */
.edit-banner{display:none;position:fixed;top:64px;left:0;right:0;z-index:250;background:linear-gradient(90deg,rgba(34,197,94,.13),rgba(34,197,94,.06));border-bottom:1px solid rgba(34,197,94,.22);padding:.45rem 2rem;text-align:center;font-size:.71rem;color:#4ade80;font-weight:500;align-items:center;justify-content:center;gap:.5rem;}
.edit-banner.show{display:flex;}
.edit-dot{width:6px;height:6px;border-radius:50%;background:#4ade80;animation:pulse 1.5s infinite;}
.editable{outline:none;border-radius:4px;transition:all .2s;cursor:default;}
body.edit-mode .editable{cursor:text;background:rgba(240,90,40,.1);box-shadow:0 0 0 2px rgba(240,90,40,.32);padding:2px 5px;}

/* TOAST */
.toast{position:fixed;bottom:2rem;left:50%;transform:translateX(-50%) translateY(120px);background:rgba(15,22,41,.97);border:1px solid rgba(240,90,40,.4);color:#fff;padding:.75rem 1.5rem;border-radius:100px;font-size:.78rem;font-weight:600;z-index:9999;transition:transform .3s;pointer-events:none;backdrop-filter:blur(12px);box-shadow:0 8px 24px rgba(0,0,0,.4);}
.toast.show{transform:translateX(-50%) translateY(0);}

/* ======================== CHATBOT ======================== */
.chat-fab{position:fixed;bottom:2rem;right:2rem;z-index:400;width:58px;height:58px;border-radius:50%;background:linear-gradient(135deg,var(--orange),var(--orange2));border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;box-shadow:0 8px 28px rgba(240,90,40,.4);transition:all .2s;animation:chatPulse 2.6s ease-in-out infinite;}
.chat-fab:hover{transform:scale(1.12);animation:none;}
.chat-fab-icon{font-size:1.4rem;}
.chat-badge{position:absolute;top:-4px;right:-4px;width:18px;height:18px;border-radius:50%;background:#4ade80;border:2px solid var(--navy);display:flex;align-items:center;justify-content:center;font-size:.48rem;font-weight:900;color:var(--navy);}
@keyframes chatPulse{0%,100%{box-shadow:0 8px 28px rgba(240,90,40,.4);}50%{box-shadow:0 8px 38px rgba(240,90,40,.7),0 0 0 8px rgba(240,90,40,.1);}}
.cwin{position:fixed;bottom:6.5rem;right:2rem;z-index:400;width:355px;height:520px;background:var(--navy2);border:1px solid rgba(240,90,40,.23);border-radius:22px;display:none;flex-direction:column;box-shadow:0 26px 65px rgba(0,0,0,.55);overflow:hidden;}
.cwin.open{display:flex;animation:chatSlide .3s ease;}
@keyframes chatSlide{from{opacity:0;transform:translateY(16px) scale(.95);}to{opacity:1;transform:none;}}
.chat-hdr{padding:.9rem 1.1rem;display:flex;align-items:center;gap:.7rem;background:linear-gradient(135deg,rgba(240,90,40,.14),rgba(240,90,40,.05));border-bottom:1px solid rgba(255,255,255,.06);flex-shrink:0;}
.chat-av{width:34px;height:34px;border-radius:50%;background:var(--orange);display:flex;align-items:center;justify-content:center;font-weight:840;font-size:.78rem;flex-shrink:0;color:#fff;}
.chat-av-name{font-weight:750;font-size:.86rem;}
.chat-av-status{font-size:.64rem;color:#4ade80;display:flex;align-items:center;gap:.28rem;}
.chat-av-status::before{content:'';width:5px;height:5px;border-radius:50%;background:#4ade80;flex-shrink:0;}
.cclose{background:none;border:none;color:var(--muted);cursor:pointer;font-size:1.1rem;padding:.1rem;transition:color .2s;margin-left:auto;}
.cclose:hover{color:#fff;}
.cmsgs{flex:1;overflow-y:auto;padding:.9rem;display:flex;flex-direction:column;gap:.7rem;}
.cmsg{display:flex;gap:.5rem;align-items:flex-end;}
.cmsg.user{flex-direction:row-reverse;}
.cbubble{padding:.6rem .88rem;border-radius:14px;font-size:.78rem;line-height:1.6;max-width:80%;word-break:break-word;}
.cmsg.bot .cbubble{background:rgba(255,255,255,.07);border:1px solid rgba(255,255,255,.08);color:#e2e8f0;border-radius:14px 14px 14px 3px;}
.cmsg.user .cbubble{background:var(--orange);color:#fff;border-radius:14px 14px 3px 14px;}
.cdot{width:26px;height:26px;border-radius:50%;background:var(--orange);display:flex;align-items:center;justify-content:center;font-size:.6rem;font-weight:840;flex-shrink:0;}
.cmsg.user .cdot{background:rgba(255,255,255,.1);}
.cquick{padding:.45rem .9rem;display:flex;gap:.3rem;flex-wrap:wrap;border-top:1px solid rgba(255,255,255,.05);}
.cqbtn{background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.23);color:var(--orange);padding:.28rem .68rem;border-radius:100px;font-size:.65rem;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;transition:all .2s;white-space:nowrap;}
.cqbtn:hover{background:rgba(240,90,40,.2);}
.cinput-row{padding:.8rem .9rem;display:flex;gap:.5rem;border-top:1px solid rgba(255,255,255,.07);flex-shrink:0;background:rgba(10,15,35,.5);}
.cinput{flex:1;background:rgba(255,255,255,.07);border:1px solid rgba(255,255,255,.09);border-radius:100px;padding:.55rem 1rem;color:#fff;font-family:'Poppins',sans-serif;font-size:.78rem;outline:none;transition:border-color .2s;}
.cinput:focus{border-color:rgba(240,90,40,.5);}
.csend{width:36px;height:36px;border-radius:50%;background:var(--orange);border:none;color:#fff;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:.9rem;flex-shrink:0;transition:background .2s;}
.csend:hover{background:var(--orange2);}
.typing-dots span{display:inline-block;width:6px;height:6px;border-radius:50%;background:#a0aec0;margin:0 1px;animation:dot 1.2s infinite;}
.typing-dots span:nth-child(2){animation-delay:.2s;}
.typing-dots span:nth-child(3){animation-delay:.4s;}
@keyframes dot{0%,80%,100%{opacity:.2;}40%{opacity:1;}}

/* ABOUT */
.about-grid{display:grid;grid-template-columns:240px 1fr;gap:3rem;align-items:center;max-width:1000px;}
.about-img{aspect-ratio:3/4;background:linear-gradient(145deg,var(--navy3),#1f0f3a);border-radius:20px;border:1px solid var(--border);display:flex;align-items:center;justify-content:center;font-size:5rem;}
.about-body p{color:var(--muted);font-size:.85rem;line-height:1.85;margin-bottom:.85rem;}
.chips{display:flex;flex-wrap:wrap;gap:.45rem;margin-top:1.2rem;}
.chip{background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.27);color:var(--orange);padding:.28rem .85rem;border-radius:100px;font-size:.72rem;font-weight:600;}

/* SKILLS */
.skills-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:1.2rem;}
.sk{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:1.2rem;transition:all .3s;position:relative;overflow:hidden;}
.sk:hover{border-color:rgba(240,90,40,.5);transform:translateY(-5px);box-shadow:0 8px 24px rgba(240,90,40,.12);}
.sk-icon{font-size:1.7rem;margin-bottom:.6rem;display:block;}
.sk-title{font-weight:750;font-size:.87rem;margin-bottom:.75rem;}
.tags{display:flex;flex-wrap:wrap;gap:.3rem;}
.tag{background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.09);border-radius:100px;padding:.16rem .55rem;font-size:.65rem;color:var(--muted);transition:all .2s;}
.tag:hover{background:rgba(240,90,40,.14);border-color:rgba(240,90,40,.4);color:var(--orange);}
.tag.h{background:rgba(240,90,40,.11);border-color:rgba(240,90,40,.32);color:var(--orange);}

/* PROJECTS */
.projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(255px,1fr));gap:1.2rem;}
.proj{background:var(--navy3);border:1px solid var(--border);border-radius:16px;padding:1.4rem;transition:all .3s;}
.proj:hover{border-color:rgba(240,90,40,.4);transform:translateY(-4px);}
.proj-type{font-size:.65rem;letter-spacing:.1em;text-transform:uppercase;color:var(--orange);margin-bottom:.45rem;font-weight:700;}
.proj-title{font-weight:750;font-size:.92rem;margin-bottom:.4rem;}
.proj-desc{color:var(--muted);font-size:.8rem;line-height:1.65;}

/* EXPERIENCE */
.exp-timeline{max-width:860px;position:relative;}
.exp-timeline::before{content:'';position:absolute;left:23px;top:0;bottom:0;width:2px;background:linear-gradient(180deg,var(--orange),rgba(240,90,40,.1));border-radius:2px;}
.exp-item{display:flex;gap:1.5rem;margin-bottom:2rem;position:relative;}
.exp-dot{width:46px;height:46px;border-radius:50%;flex-shrink:0;background:linear-gradient(135deg,var(--orange),var(--orange2));display:flex;align-items:center;justify-content:center;font-size:1.1rem;position:relative;z-index:2;box-shadow:0 0 0 4px rgba(240,90,40,.15);}
.exp-card{flex:1;background:var(--card);border:1px solid var(--border);border-radius:16px;padding:1.4rem 1.6rem;transition:all .3s;position:relative;overflow:hidden;}
.exp-card::before{content:'';position:absolute;top:0;left:0;bottom:0;width:3px;background:var(--orange);opacity:0;transition:opacity .3s;}
.exp-card:hover{border-color:rgba(240,90,40,.4);transform:translateX(3px);}
.exp-card:hover::before{opacity:1;}
.exp-header{display:flex;align-items:flex-start;justify-content:space-between;gap:1rem;margin-bottom:.5rem;flex-wrap:wrap;}
.exp-title{font-weight:800;font-size:.94rem;}
.exp-period{background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.25);color:var(--orange);padding:.22rem .7rem;border-radius:100px;font-size:.65rem;font-weight:700;white-space:nowrap;flex-shrink:0;}
.exp-company{font-size:.79rem;color:var(--orange);font-weight:700;margin-bottom:.65rem;display:flex;align-items:center;gap:.35rem;}
.exp-company::before{content:'🏢';font-size:.85rem;}
.exp-bullets{list-style:none;display:flex;flex-direction:column;gap:.4rem;}
.exp-bullets li{display:flex;align-items:flex-start;gap:.45rem;color:var(--muted);font-size:.78rem;line-height:1.65;}
.exp-bullets li::before{content:'▹';color:var(--orange);flex-shrink:0;margin-top:2px;font-weight:700;}

/* CERTS */
.certs-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));gap:1.4rem;}
.cert-card{background:var(--card);border:1px solid var(--border);border-radius:18px;overflow:hidden;transition:all .3s;}
.cert-card:hover{border-color:rgba(240,90,40,.45);transform:translateY(-4px);}
.cert-wrap{width:100%;height:170px;background:var(--navy3);display:flex;align-items:center;justify-content:center;cursor:pointer;overflow:hidden;}
.cert-placeholder{display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.4rem;color:var(--muted);font-size:.76rem;text-align:center;padding:1rem;width:100%;height:100%;}
.cert-body{padding:1rem 1.2rem 1.2rem;}
.cert-org{font-size:.68rem;color:var(--muted);margin-bottom:.12rem;}
.cert-name{font-weight:750;font-size:.88rem;margin-bottom:.25rem;}
.cert-year{font-size:.68rem;color:var(--orange);font-weight:700;}
.add-cert{background:rgba(255,255,255,.023);border:1.5px dashed rgba(255,255,255,.11);border-radius:18px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.5rem;cursor:pointer;min-height:260px;transition:all .3s;color:var(--muted);font-size:.82rem;}
.add-cert:hover{border-color:var(--orange);background:rgba(240,90,40,.05);color:var(--orange);}

/* AWARDS */
.awards-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));gap:1.4rem;}
.award-card{background:var(--card);border:1px solid var(--border);border-radius:18px;overflow:hidden;transition:all .3s;}
.award-card:hover{border-color:rgba(240,90,40,.45);transform:translateY(-4px);}
.award-wrap{width:100%;height:160px;background:var(--navy3);display:flex;align-items:center;justify-content:center;cursor:pointer;overflow:hidden;}
.award-placeholder{display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.35rem;color:var(--muted);font-size:.76rem;text-align:center;padding:1rem;width:100%;height:100%;}
.award-body{padding:.95rem 1.1rem 1.1rem;}
.award-badge{display:inline-flex;align-items:center;gap:.28rem;background:rgba(240,90,40,.12);border:1px solid rgba(240,90,40,.28);color:var(--orange);padding:.2rem .7rem;border-radius:100px;font-size:.6rem;font-weight:700;margin-bottom:.35rem;}
.award-title{font-weight:750;font-size:.88rem;margin-bottom:.25rem;}
.award-desc{color:var(--muted);font-size:.77rem;line-height:1.62;}
.add-award{background:rgba(255,255,255,.023);border:1.5px dashed rgba(255,255,255,.11);border-radius:18px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.5rem;cursor:pointer;min-height:260px;transition:all .3s;color:var(--muted);font-size:.82rem;}
.add-award:hover{border-color:var(--orange);background:rgba(240,90,40,.05);color:var(--orange);}

/* FOOTER */
footer{padding:1.3rem 3rem;border-top:1px solid rgba(255,255,255,.05);display:flex;justify-content:space-between;align-items:center;color:var(--muted);font-size:.73rem;}

/* RESPONSIVE */
@media(max-width:1200px){
  .hero{grid-template-columns:1fr;padding:88px 2rem 2rem;gap:2.5rem;}
  .hero-center{order:-1;}
  .hero-right{order:1;}
  .hero-left{order:2;}
  .hero-role{white-space:normal;}
}
@media(max-width:768px){
  nav{padding:0 .9rem;flex-wrap:wrap;height:auto;gap:.3rem;padding-bottom:.4rem;}
  .nav-tabs{order:3;width:100%;margin:0;}
  .nav-actions{order:2;}
  .about-grid{grid-template-columns:1fr;gap:1.5rem;}
  .sec{padding:3.5rem 1.2rem 2.5rem;}
  .stats-sec{padding:2rem 1rem;}
  .contact-section{padding:2rem 1rem;}
  .form-grid{grid-template-columns:1fr;}
  .form-grid .full{grid-column:1;}
  .profile-wrap{width:260px;height:260px;}
  .profile-circle{width:212px;height:212px;top:24px;left:24px;}
  .m1{right:-5px;}.m2{left:-5px;}.m3{right:5px;}
  .cwin{width:calc(100vw - 2rem);right:1rem;bottom:5rem;}
  footer{flex-direction:column;gap:.3rem;padding:1rem;text-align:center;}
  .hero-visual-wrap{grid-template-columns:1fr;}
  .home-market-sec{padding:2rem 1rem;}
  .growth-kpi-grid{grid-template-columns:repeat(2,1fr);}
  .cert-summary-bar{grid-template-columns:1fr;}
  .cs-divider{width:60px;height:1px;}
}
</style>
</head>
<body>

<!-- LOGIN MODAL -->
<div class="login-overlay" id="loginModal">
  <div class="login-box">
    <button class="login-xbtn" onclick="closeLogin()">✕</button>
    <div class="login-logo">AK</div>
    <div class="login-title">🔐 Admin Login</div>
    <div class="login-sub">Unlock editing</div>
    <div class="login-err" id="loginErr">❌ Incorrect ID or Password</div>
    <div class="lf"><label>User ID</label><span class="lf-icon">👤</span><input type="text" id="lid" placeholder="Akash7566" autocomplete="off" onkeydown="if(event.key==='Enter')doLogin()"></div>
    <div class="lf"><label>Password</label><span class="lf-icon">🔒</span><input type="password" id="lpwd" placeholder="••••••••" onkeydown="if(event.key==='Enter')doLogin()"></div>
    <button class="login-btn" onclick="doLogin()">🔓 Unlock Edit Mode</button>
  </div>
</div>

<div class="edit-banner" id="editBanner"><div class="edit-dot"></div><span>✏️ Edit Mode — Click highlighted text to edit</span></div>
<div class="lb" id="lightbox" onclick="if(event.target===this)closeLB()"><div class="lb-inner"><button class="lb-close" onclick="closeLB()">✕</button><img id="lb-img" src="" alt=""></div></div>
<div class="toast" id="toast"></div>

<!-- NAV -->
<nav>
  <div style="display:flex;align-items:center;flex-shrink:0;">
    <div class="nav-logo">AK</div>
    <span class="nav-name">Akash Kourav</span>
  </div>
  <div class="nav-tabs">
    <button class="nav-tab active" onclick="showPage('home',this)">Home</button>
    <button class="nav-tab" onclick="showPage('about',this)">About</button>
    <button class="nav-tab" onclick="showPage('skills',this)">Skills</button>
    <button class="nav-tab" onclick="showPage('projects',this)">Projects</button>
    <button class="nav-tab" onclick="showPage('experience',this)">Experience</button>
    <button class="nav-tab" onclick="showPage('growth',this)">Growth</button>
    <button class="nav-tab" onclick="showPage('market',this)">Market</button>
    <button class="nav-tab" onclick="showPage('certs',this)">Certs</button>
    <button class="nav-tab" onclick="showPage('awards',this)">Awards</button>
  </div>
  <div class="nav-actions">
    <button class="btn-edit locked" id="editBtn" onclick="handleEditBtn()">🔒 Edit</button>
    <button class="btn-resume" onclick="showToast('📄 Resume download coming soon!')">
      <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>Resume
    </button>
  </div>
</nav>

<!-- ===== HOME PAGE ===== -->
<div class="page active" id="page-home">

  <!-- HERO -->
  <div class="hero">
    <div class="deco deco-1"></div>
    <div class="deco deco-2"></div>

    <!-- LEFT: Quick Info panel -->
    <div class="hero-left">
      <div class="info-panel">
        <div class="info-title">Quick Info</div>
        <a class="info-item" href="mailto:akash.kourav@email.com">
          <div class="info-icon">📧</div>
          <div class="info-text"><div class="info-label">Email — click to open</div><div class="info-value"><span class="editable" id="info-email" contenteditable="false">akash.kourav@email.com</span></div></div>
        </a>
        <a class="info-item" href="tel:+919876543210">
          <div class="info-icon">📱</div>
          <div class="info-text"><div class="info-label">Mobile — click to call</div><div class="info-value"><span class="editable" id="info-mobile" contenteditable="false">+91 98765 43210</span></div></div>
        </a>
        <a class="info-item" href="https://linkedin.com/in/akashkourav" target="_blank" rel="noopener">
          <div class="info-icon">🔗</div>
          <div class="info-text"><div class="info-label">LinkedIn — click to open</div><div class="info-value"><span class="editable" id="info-li" contenteditable="false">linkedin.com/in/akashkourav</span></div></div>
        </a>
        <div class="info-item">
          <div class="info-icon">🎓</div>
          <div class="info-text"><div class="info-label">Education</div><div class="info-value"><span class="editable" id="info-edu" contenteditable="false">B.Tech — Computer Science</span></div></div>
        </div>
        <div class="info-item">
          <div class="info-icon">📍</div>
          <div class="info-text"><div class="info-label">Location</div><div class="info-value"><span class="editable" id="info-loc" contenteditable="false">Mumbai, India</span></div></div>
        </div>
        <div class="info-item">
          <div class="info-icon">💼</div>
          <div class="info-text"><div class="info-label">Experience</div><div class="info-value"><span class="editable" id="info-exp" contenteditable="false">2+ Years BI</span></div></div>
        </div>
        <div class="avail">Available for hire</div>
      </div>
      <div class="follow">
        <span>Follow:</span>
        <div class="socials">
          <a href="https://linkedin.com/in/akashkourav" target="_blank" class="soc soc-li">in</a>
          <a href="https://github.com/akashkourav" target="_blank" class="soc soc-gh">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="white"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0 1.5 3.78c.1.85.34 2.75-.5 6.23"/></svg>
          </a>
          <a href="mailto:akash.kourav@email.com" class="soc soc-em">✉</a>
        </div>
      </div>
    </div>

    <!-- CENTER: Profile photo -->
    <div class="hero-center">
      <div class="profile-wrap">
        <div class="ring"></div>
        <div class="profile-circle" onclick="guardedAction(openProfileUpload)">
          <img id="profileImg" src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect fill='%23f05a28' width='100' height='100'/%3E%3Ctext x='50' y='50' font-size='38' font-weight='bold' fill='white' text-anchor='middle' dy='0.35em'%3EAK%3C/text%3E%3C/svg%3E" alt="Akash Kourav">
        </div>
        <div class="cam-btn" onclick="guardedAction(openProfileUpload)">📷</div>
        <div class="metric m1"><div class="metric-val">50+</div><div class="metric-lbl">Dashboards</div></div>
        <div class="metric m2"><div class="metric-val">2+</div><div class="metric-lbl">Years Exp</div></div>
        <div class="metric m3"><div class="metric-val">⭐ 5.0</div><div class="metric-lbl">BI Pro Rating</div></div>
      </div>
    </div>

    <!-- RIGHT: Text + CTAs -->
    <div class="hero-right">
      <p class="hero-eyebrow">Hello, I'm</p>
      <h1 class="hero-name"><span class="editable" id="info-name" contenteditable="false">Akash Kourav</span></h1>
      <p class="hero-role"><span class="editable" id="info-role" contenteditable="false">Power BI Developer & BI Analyst</span></p>
      <p class="hero-desc"><span class="editable" id="info-desc" contenteditable="false">Transforming raw data into powerful insights that drive smarter business decisions. Specializing in interactive dashboards, ETL pipelines, and data storytelling.</span></p>
      <div class="hero-ctas">
        <button onclick="showPage('projects',document.querySelectorAll('.nav-tab')[3])" class="btn-primary">Discover My Work</button>
        <button onclick="scrollToContact()" class="btn-circle" title="Contact me">📩</button>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-sec">
    <div class="stats-title">
      <h3>What I Bring To The Table</h3>
      <p>Proven expertise delivering measurable business impact through data</p>
    </div>
    <div class="stats-grid">
      <div class="scard"><div class="sglow"></div><span class="scard-icon">📊</span><div class="scard-val">50+</div><div class="sline"></div><div class="scard-label">Dashboards</div><div class="scard-desc">Power BI & Tableau interactive reports</div></div>
      <div class="scard"><div class="sglow"></div><span class="scard-icon">⚡</span><div class="scard-val">40%</div><div class="sline"></div><div class="scard-label">Time Saved</div><div class="scard-desc">Automated data pipelines & ETL</div></div>
      <div class="scard"><div class="sglow"></div><span class="scard-icon">💰</span><div class="scard-val">30%</div><div class="sline"></div><div class="scard-label">Cost Savings</div><div class="scard-desc">Operational efficiency gains</div></div>
      <div class="scard"><div class="sglow"></div><span class="scard-icon">🎯</span><div class="scard-val">100%</div><div class="sline"></div><div class="scard-label">Accuracy</div><div class="scard-desc">SQL-optimized data integrity</div></div>
      <div class="scard"><div class="sglow"></div><span class="scard-icon">🏆</span><div class="scard-val">5+</div><div class="sline"></div><div class="scard-label">Certifications</div><div class="scard-desc">Microsoft, Google, Tableau</div></div>
    </div>

    <!-- REPLACED MINI CHART: Skill proficiency radar + bars -->
    <div class="hero-visual-wrap">
      <p class="hero-visual-title">Skills & Impact at a Glance</p>
      <div class="radar-wrap">
        <canvas id="radarChart"></canvas>
      </div>
      <div class="skill-bars">
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>Power BI / DAX</span><span>95%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:0" data-width="95%"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>SQL / MySQL</span><span>90%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:0" data-width="90%"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>Python / ETL</span><span>80%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:0" data-width="80%"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>Tableau</span><span>85%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:0" data-width="85%"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>Azure / Cloud</span><span>70%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:0" data-width="70%"></div></div>
        </div>
        <div class="skill-bar-item">
          <div class="skill-bar-label"><span>Data Modeling</span><span>88%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:0" data-width="88%"></div></div>
        </div>
      </div>
    </div>
  </div>

  <!-- MARKET UPDATES ON LANDING PAGE -->
  <div class="home-market-sec">
    <div class="home-market-inner">
      <div class="home-market-hdr">
        <div>
          <h3>📡 Latest Tech Updates</h3>
          <p>Power BI · Microsoft Fabric · Cloud · AI/ML — refreshed daily</p>
        </div>
        <button class="refresh-small" onclick="loadHomeMarket(true)">🔄 Refresh</button>
      </div>
      <div id="homeMarketFeed">
        <div class="market-loading"><div class="market-spinner"></div>Fetching latest updates...</div>
      </div>
    </div>
  </div>

  <!-- CONTACT FORM -->
  <div class="contact-section" id="contactSection">
    <div class="contact-wrap">
      <div class="contact-header">
        <span class="sec-label-sm">Let's Connect</span>
        <h2>Get In Touch</h2>
        <p>Have a project in mind? Want to collaborate or hire? Drop a message — I'll get back to you within 24 hours.</p>
      </div>
      <div class="contact-form">
        <div class="form-orbs">
          <div class="form-orb form-orb-1"></div>
          <div class="form-orb form-orb-2"></div>
        </div>
        <div class="form-grid" style="position:relative;z-index:1;">
          <div class="fg-contact"><label>Your Name</label><span class="fi">👤</span><input type="text" id="f-name" placeholder="John Doe"></div>
          <div class="fg-contact"><label>Mobile Number</label><span class="fi">📱</span><input type="tel" id="f-mobile" placeholder="+91 98765 43210"></div>
          <div class="fg-contact"><label>Email Address</label><span class="fi">📧</span><input type="email" id="f-email" placeholder="you@company.com"></div>
          <div class="fg-contact no-icon"><label>Purpose of Connect</label>
            <select id="f-purpose"><option value="" disabled selected>Select purpose...</option><option>Full-time Hire</option><option>Freelance / Project</option><option>Collaboration</option><option>Mentorship</option><option>Networking</option><option>Other</option></select>
          </div>
          <div class="fg-contact full no-icon"><label>Message / Description</label><textarea id="f-desc" placeholder="Tell me about your project..."></textarea></div>
          <div class="full"><button class="form-submit" onclick="handleFormSubmit()">🚀 Send Message</button></div>
        </div>
      </div>
    </div>
  </div>

</div><!-- end page-home -->

<!-- ABOUT -->
<div class="page" id="page-about">
  <section class="sec">
    <p class="sec-label">About</p><h2>Data-driven Analyst</h2><div class="sec-bar"></div>
    <div class="about-grid">
      <div class="about-img">🧑‍💻</div>
      <div class="about-body">
        <h3 style="font-size:1.05rem;margin-bottom:.75rem;">Hi, I'm Akash 👋</h3>
        <p>Power BI Developer & BI Analyst based in Mumbai. I specialize in designing interactive dashboards, building data pipelines, and translating complex datasets into actionable insights.</p>
        <p>My work sits at the intersection of analytics, visualization, and business strategy — helping organizations make smarter, faster decisions backed by real data.</p>
        <div class="chips"><span class="chip">📍 Mumbai</span><span class="chip">💼 BI Analyst</span><span class="chip">🎓 B.Tech CS</span><span class="chip">⚡ Freelance</span><span class="chip">📊 Power BI Expert</span></div>
      </div>
    </div>
  </section>
</div>

<!-- SKILLS -->
<div class="page" id="page-skills">
  <section class="sec">
    <p class="sec-label">Skills</p><h2>Technical Expertise</h2><div class="sec-bar"></div>
    <div class="skills-grid">
      <div class="sk"><div class="sk-icon">📊</div><div class="sk-title">BI & Visualization</div><div class="tags"><span class="tag h">Power BI</span><span class="tag h">Tableau</span><span class="tag">Looker</span></div></div>
      <div class="sk"><div class="sk-icon">🗄️</div><div class="sk-title">Database & SQL</div><div class="tags"><span class="tag h">SQL</span><span class="tag h">MySQL</span><span class="tag">BigQuery</span></div></div>
      <div class="sk"><div class="sk-icon">🐍</div><div class="sk-title">Programming</div><div class="tags"><span class="tag h">Python</span><span class="tag">Pandas</span><span class="tag">NumPy</span></div></div>
      <div class="sk"><div class="sk-icon">⚙️</div><div class="sk-title">Analytics</div><div class="tags"><span class="tag h">ETL</span><span class="tag">Data Modeling</span><span class="tag">KPI Design</span></div></div>
      <div class="sk"><div class="sk-icon">☁️</div><div class="sk-title">Cloud & Platforms</div><div class="tags"><span class="tag">Azure</span><span class="tag">Google Cloud</span><span class="tag">Fabric</span></div></div>
      <div class="sk"><div class="sk-icon">🤝</div><div class="sk-title">Soft Skills</div><div class="tags"><span class="tag h">Storytelling</span><span class="tag">Stakeholder Mgmt</span></div></div>
    </div>
  </section>
</div>

<!-- PROJECTS -->
<div class="page" id="page-projects">
  <section class="sec">
    <p class="sec-label">Work</p><h2>Featured Projects</h2><div class="sec-bar"></div>
    <div class="projects-grid">
      <div class="proj"><div class="proj-type">Power BI · DAX · SQL</div><div class="proj-title">Executive Sales Dashboard</div><p class="proj-desc">Multi-page Power BI dashboard for 3 regions. Drill-through from KPIs to rep-level performance.</p></div>
      <div class="proj"><div class="proj-type">Python · ETL</div><div class="proj-title">Automated Reporting Pipeline</div><p class="proj-desc">Python ETL replacing 8 hours weekly manual reporting with automated scheduled process.</p></div>
      <div class="proj"><div class="proj-type">Tableau · Data Modeling</div><div class="proj-title">Customer Churn Analysis</div><p class="proj-desc">Tableau story with predictive churn indicators. Reduced churn rate significantly.</p></div>
      <div class="proj"><div class="proj-type">BigQuery · Looker</div><div class="proj-title">Operations Performance Tracker</div><p class="proj-desc">Real-time ops tracker monitoring SLA compliance and team productivity metrics.</p></div>
    </div>
  </section>
</div>

<!-- EXPERIENCE -->
<div class="page" id="page-experience">
  <section class="sec">
    <p class="sec-label">Career</p><h2>Work Experience</h2><div class="sec-bar"></div>
    <div class="exp-timeline">
      <div class="exp-item">
        <div class="exp-dot">💼</div>
        <div class="exp-card">
          <div class="exp-header"><div class="exp-title">Associate Analyst – BI</div><div class="exp-period">2023 – Present</div></div>
          <div class="exp-company">XYZ Analytics, Mumbai</div>
          <ul class="exp-bullets"><li>Designed 15+ Power BI dashboards for C-suite stakeholders</li><li>Built Python ETL pipelines reducing manual effort by 40%</li><li>Optimized SQL queries improving load times by 60%</li><li>Delivered automated weekly MIS reports</li></ul>
        </div>
      </div>
      <div class="exp-item">
        <div class="exp-dot">📊</div>
        <div class="exp-card">
          <div class="exp-header"><div class="exp-title">Data Analyst Intern</div><div class="exp-period">2022 – 2023</div></div>
          <div class="exp-company">ABC Solutions, Mumbai</div>
          <ul class="exp-bullets"><li>Developed Tableau dashboards for sales tracking</li><li>Performed EDA on large customer datasets</li><li>Created Excel MIS reports for management</li></ul>
        </div>
      </div>
      <div class="exp-item">
        <div class="exp-dot">🎓</div>
        <div class="exp-card">
          <div class="exp-header"><div class="exp-title">B.Tech — Computer Science</div><div class="exp-period">2018 – 2022</div></div>
          <div class="exp-company">University of Mumbai</div>
          <ul class="exp-bullets"><li>Focused on databases, data structures & algorithms</li><li>Final year project on Power BI analytics platform</li></ul>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- GROWTH -->
<div class="page" id="page-growth">
  <section class="sec">
    <p class="sec-label">Growth</p>
    <h2>Skills & Certifications Growth</h2>
    <div class="sec-bar"></div>
    <p class="sec-sub">My learning journey 2021–2025: technologies mastered, certifications earned, impact delivered, and costs saved.</p>

    <!-- KPI CARDS -->
    <div class="growth-kpi-grid">
      <div class="gkpi">
        <div class="gkpi-icon">🛠️</div>
        <div class="gkpi-val">12</div>
        <div class="gkpi-label">Skills Mastered</div>
        <div class="gkpi-badge up">▲ +20% vs last year</div>
        <div class="gkpi-sub">10 skills in 2024 → 12 in 2025</div>
      </div>
      <div class="gkpi">
        <div class="gkpi-icon">🎓</div>
        <div class="gkpi-val">5</div>
        <div class="gkpi-label">Certifications Earned</div>
        <div class="gkpi-badge up">▲ +25% vs last year</div>
        <div class="gkpi-sub">4 certs in 2024 → 5 in 2025</div>
      </div>
      <div class="gkpi">
        <div class="gkpi-icon">⚡</div>
        <div class="gkpi-val">60%</div>
        <div class="gkpi-label">Time Saved</div>
        <div class="gkpi-badge up">▲ +50% vs last year</div>
        <div class="gkpi-sub">40% in 2024 → 60% in 2025</div>
      </div>
      <div class="gkpi">
        <div class="gkpi-icon">💰</div>
        <div class="gkpi-val">30%</div>
        <div class="gkpi-label">Cost Savings</div>
        <div class="gkpi-badge up">▲ +20% vs last year</div>
        <div class="gkpi-sub">25% in 2024 → 30% in 2025</div>
      </div>
    </div>

    <div class="growth-container">
      <canvas id="growthChart" class="growth-canvas"></canvas>
    </div>
  </section>
</div>

<!-- MARKET -->
<div class="page" id="page-market">
  <section class="sec">
    <p class="sec-label">Market</p><h2>Latest Tech Updates</h2><div class="sec-bar"></div>
    <p class="sec-sub">Daily-refreshed updates on Power BI, Microsoft Fabric, Cloud, and AI/ML. Click any card to read more.</p>
    <div id="marketFeed">
      <div class="market-loading"><div class="market-spinner"></div>Fetching latest updates...</div>
    </div>
  </section>
</div>

<!-- CERTS -->
<div class="page" id="page-certs">
  <section class="sec">
    <p class="sec-label">Credentials</p>
    <h2>Certifications</h2>
    <div class="sec-bar"></div>

    <!-- SUMMARY BAR -->
    <div class="cert-summary-bar">
      <div class="cs-stat"><div class="cs-val">5</div><div class="cs-lbl">Total Certifications Earned</div></div>
      <div class="cs-divider"></div>
      <div class="cs-stat"><div class="cs-val">12</div><div class="cs-lbl">Skills / Tools Learned</div></div>
      <div class="cs-divider"></div>
      <div class="cs-stat"><div class="cs-val">3</div><div class="cs-lbl">Platforms Certified On</div></div>
    </div>

    <!-- SKILLS LEARNED CHIPS -->
    <div class="skills-learned-wrap">
      <div class="skills-learned-title">Skills Learned via Certifications</div>
      <div class="skills-learned-chips">
        <span class="sl-chip hot">Power BI</span>
        <span class="sl-chip hot">DAX</span>
        <span class="sl-chip hot">Data Modeling</span>
        <span class="sl-chip">SQL</span>
        <span class="sl-chip">Python</span>
        <span class="sl-chip hot">Tableau</span>
        <span class="sl-chip">BigQuery</span>
        <span class="sl-chip">Google Analytics</span>
        <span class="sl-chip">ETL Pipelines</span>
        <span class="sl-chip">Azure Fundamentals</span>
        <span class="sl-chip">Data Storytelling</span>
        <span class="sl-chip">KPI Design</span>
      </div>
    </div>

    <div class="certs-grid">
      <div class="cert-card">
        <div class="cert-wrap"><div class="cert-placeholder"><div style="font-size:2rem">🪟</div><div>Microsoft Power BI</div></div></div>
        <div class="cert-body"><div class="cert-org">Microsoft</div><div class="cert-name">PL-300: Power BI Data Analyst</div><div class="cert-year">✦ 2024</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-wrap"><div class="cert-placeholder"><div style="font-size:2rem">🐍</div><div>Google Analytics</div></div></div>
        <div class="cert-body"><div class="cert-org">Google</div><div class="cert-name">Data Analytics Professional</div><div class="cert-year">✦ 2023</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-wrap"><div class="cert-placeholder"><div style="font-size:2rem">📊</div><div>Tableau Specialist</div></div></div>
        <div class="cert-body"><div class="cert-org">Tableau</div><div class="cert-name">Tableau Desktop Specialist</div><div class="cert-year">✦ 2023</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-wrap"><div class="cert-placeholder"><div style="font-size:2rem">☁️</div><div>Azure Fundamentals</div></div></div>
        <div class="cert-body"><div class="cert-org">Microsoft</div><div class="cert-name">AZ-900: Azure Fundamentals</div><div class="cert-year">✦ 2022</div></div>
      </div>
      <div class="cert-card">
        <div class="cert-wrap"><div class="cert-placeholder"><div style="font-size:2rem">🐍</div><div>Python Essentials</div></div></div>
        <div class="cert-body"><div class="cert-org">Cisco / NetAcad</div><div class="cert-name">Python Essentials 1 & 2</div><div class="cert-year">✦ 2022</div></div>
      </div>
      <div class="add-cert" onclick="guardedAction(()=>showToast('Use edit mode to add certifications'))">
        <span>＋</span><div>Add Certification</div>
      </div>
    </div>
  </section>
</div>

<!-- AWARDS -->
<div class="page" id="page-awards">
  <section class="sec">
    <p class="sec-label">Recognition</p><h2>Awards & Appreciation</h2><div class="sec-bar"></div>
    <div class="awards-grid">
      <div class="award-card">
        <div class="award-wrap"><div class="award-placeholder"><span style="font-size:2rem">🏆</span><div>Star Performer</div></div></div>
        <div class="award-body"><div class="award-badge">🏆 Recognition</div><div class="award-title">Star Performer Award</div><div class="award-desc">For outstanding contribution to the BI team in Q3 2024.</div></div>
      </div>
      <div class="award-card">
        <div class="award-wrap"><div class="award-placeholder"><span style="font-size:2rem">🌟</span><div>Client Appreciation</div></div></div>
        <div class="award-body"><div class="award-badge">🌟 Appreciation</div><div class="award-title">Client Appreciation Letter</div><div class="award-desc">For excellent delivery of executive dashboard project.</div></div>
      </div>
      <div class="add-award" onclick="guardedAction(()=>showToast('Use edit mode to add awards'))">
        <span>＋</span><div>Add Award</div>
      </div>
    </div>
  </section>
</div>

<footer>
  <span>© 2025 Akash Kourav — BI Analyst & Power BI Developer</span>
  <span style="color:rgba(255,255,255,.08)">Built with precision & purpose</span>
</footer>

<!-- CHATBOT -->
<button class="chat-fab" id="chatFab" onclick="toggleChat()">
  <span class="chat-fab-icon">💬</span>
  <div class="chat-badge">AI</div>
</button>
<div class="cwin" id="chatWin">
  <div class="chat-hdr">
    <div class="chat-av">AK</div>
    <div><div class="chat-av-name">Akash's AI Assistant</div><div class="chat-av-status">Online</div></div>
    <button class="cclose" onclick="toggleChat()">✕</button>
  </div>
  <div class="cmsgs" id="cmsgs">
    <div class="cmsg bot"><div class="cdot">AK</div><div class="cbubble">Hi there! 👋 I'm Akash's AI assistant. Ask me anything about his skills, projects, or how to hire him!</div></div>
  </div>
  <div class="cquick">
    <button class="cqbtn" onclick="quickAsk('What are Akash\'s main skills?')">🛠 Skills</button>
    <button class="cqbtn" onclick="quickAsk('Tell me about Akash\'s projects')">💼 Work</button>
    <button class="cqbtn" onclick="quickAsk('What certifications does Akash have?')">🎓 Certs</button>
    <button class="cqbtn" onclick="quickAsk('How can I hire Akash?')">📩 Hire</button>
  </div>
  <div class="cinput-row">
    <input class="cinput" id="chatIn" type="text" placeholder="Ask anything..." onkeydown="if(event.key==='Enter')sendChat()">
    <button class="csend" onclick="sendChat()">➤</button>
  </div>
</div>

<input type="file" id="profileFileInput" accept="image/*" style="display:none" onchange="handleProfileUpload(event)">

<script>
const ADMIN_ID='Akash7566', ADMIN_PWD='Aman7566';
let isEdit=false,chatOpen=false,chatHist=[],marketLoaded=false,homeMarketLoaded=false;

// CHATBOT KNOWLEDGE BASE (no API key needed — works offline)
const KB={
  skills:`Akash's core skills include Power BI (expert level), DAX, Tableau, SQL/MySQL, Python, ETL pipelines, Data Modeling, BigQuery, Azure, Google Cloud, and Microsoft Fabric. He's also strong in data storytelling and stakeholder management.`,
  projects:`Akash's key projects:
1. Executive Sales Dashboard — Multi-page Power BI with drill-through for 3 regions
2. Automated Reporting Pipeline — Python ETL that eliminated 8 hrs/week of manual work
3. Customer Churn Analysis — Tableau story with predictive churn indicators
4. Operations Performance Tracker — Real-time BigQuery/Looker SLA dashboard`,
  certs:`Akash holds 5 certifications:
• PL-300: Power BI Data Analyst (Microsoft, 2024)
• Google Data Analytics Professional (2023)
• Tableau Desktop Specialist (2023)
• AZ-900: Azure Fundamentals (Microsoft, 2022)
• Python Essentials 1 & 2 (Cisco, 2022)`,
  hire:`To hire Akash:
📧 akash.kourav@email.com
📱 +91 98765 43210
🔗 linkedin.com/in/akashkourav
He's open to full-time roles, freelance projects, and collaborations. Scroll down to use the contact form!`,
  experience:`Akash has 2+ years of BI experience:
• Associate Analyst – BI at XYZ Analytics, Mumbai (2023–Present) — 15+ dashboards, Python ETL, SQL optimization
• Data Analyst Intern at ABC Solutions (2022–2023) — Tableau, EDA, Excel MIS
• B.Tech Computer Science, University of Mumbai (2018–2022)`,
  impact:`Key achievements:
• 50+ dashboards built
• 40% time saved via automation
• 30% cost savings delivered
• 100% data accuracy maintained
• 5+ certifications earned`,
};

function getBotReply(msg){
  const m=msg.toLowerCase();
  if(m.includes('skill')||m.includes('tool')||m.includes('technolog'))return KB.skills;
  if(m.includes('project')||m.includes('work')||m.includes('dashboard')||m.includes('built'))return KB.projects;
  if(m.includes('cert')||m.includes('pl-300')||m.includes('tableau specialist'))return KB.certs;
  if(m.includes('hire')||m.includes('contact')||m.includes('email')||m.includes('reach')||m.includes('available'))return KB.hire;
  if(m.includes('experience')||m.includes('job')||m.includes('career')||m.includes('company'))return KB.experience;
  if(m.includes('impact')||m.includes('achiev')||m.includes('result')||m.includes('saving')||m.includes('stat'))return KB.impact;
  if(m.includes('hello')||m.includes('hi ')||m.includes('hey'))return `Hi! 👋 I'm Akash's AI assistant. I can tell you about his skills, projects, certifications, experience, or how to hire him. What would you like to know?`;
  if(m.includes('location')||m.includes('where')||m.includes('mumbai'))return `Akash is based in Mumbai, India. He's available for remote work globally as well as on-site roles in Mumbai.`;
  if(m.includes('education')||m.includes('degree')||m.includes('btech')||m.includes('b.tech'))return `Akash holds a B.Tech in Computer Science from the University of Mumbai (2018–2022), where he focused on databases, data structures, and algorithms.`;
  return `Great question! I can help you with Akash's skills, projects, certifications, work experience, or contact info. Try asking "What are his skills?" or "How can I hire Akash?"`;
}

// EDIT MODE
function handleEditBtn(){isEdit?logoutEdit():openLogin();}
function openLogin(){document.getElementById('loginModal').classList.add('open');document.getElementById('lid').focus();}
function closeLogin(){document.getElementById('loginModal').classList.remove('open');}
function doLogin(){
  const id=document.getElementById('lid').value.trim(),pw=document.getElementById('lpwd').value;
  if(id===ADMIN_ID&&pw===ADMIN_PWD){closeLogin();enableEdit();}
  else{document.getElementById('loginErr').classList.add('show');document.getElementById('lpwd').value='';document.getElementById('lpwd').focus();}
}
function enableEdit(){
  isEdit=true;document.body.classList.add('edit-mode');
  document.getElementById('editBanner').classList.add('show');
  document.getElementById('editBtn').className='btn-edit unlocked';
  document.getElementById('editBtn').innerHTML='✏️ Exit';
  document.querySelectorAll('.editable').forEach(e=>e.setAttribute('contenteditable','true'));
  showToast('✅ Edit Mode Active');
}
function logoutEdit(){
  isEdit=false;document.body.classList.remove('edit-mode');
  document.getElementById('editBanner').classList.remove('show');
  document.getElementById('editBtn').className='btn-edit locked';
  document.getElementById('editBtn').innerHTML='🔒 Edit';
  document.querySelectorAll('.editable').forEach(e=>e.setAttribute('contenteditable','false'));
  showToast('🔒 Edits Saved');
}
function guardedAction(fn){isEdit?fn():openLogin();}

// NAVIGATION
function showPage(id,tab){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.nav-tab').forEach(t=>t.classList.remove('active'));
  document.getElementById('page-'+id).classList.add('active');
  if(tab&&tab.classList)tab.classList.add('active');
  window.scrollTo({top:0,behavior:'smooth'});
  if(id==='growth')setTimeout(initGrowthChart,100);
  if(id==='market'&&!marketLoaded)loadMarket();
}

// TOAST
function showToast(msg,dur=3000){
  const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'),dur);
}

// LIGHTBOX
function openLB(src){document.getElementById('lb-img').src=src;document.getElementById('lightbox').classList.add('open');}
function closeLB(){document.getElementById('lightbox').classList.remove('open');}

// PROFILE UPLOAD
function openProfileUpload(){document.getElementById('profileFileInput').click();}
function handleProfileUpload(e){
  const f=e.target.files[0];if(!f)return;
  const r=new FileReader();r.onload=ev=>{document.getElementById('profileImg').src=ev.target.result;showToast('✅ Photo updated!');};r.readAsDataURL(f);
}

// SCROLL TO CONTACT
function scrollToContact(){
  showPage('home',document.querySelector('.nav-tab'));
  setTimeout(()=>{document.getElementById('contactSection').scrollIntoView({behavior:'smooth',block:'start'});},300);
}

// CONTACT FORM
function handleFormSubmit(){
  const name=document.getElementById('f-name').value.trim();
  const email=document.getElementById('f-email').value.trim();
  const purpose=document.getElementById('f-purpose').value;
  if(!name||!email||!purpose){showToast('⚠️ Please fill Name, Email & Purpose');return;}
  showToast('✅ Message sent! Akash will reach out soon 🚀',4000);
  ['f-name','f-mobile','f-email','f-desc'].forEach(id=>document.getElementById(id).value='');
  document.getElementById('f-purpose').selectedIndex=0;
}

// CHATBOT — uses local KB, no API key needed
function toggleChat(){
  chatOpen=!chatOpen;
  const w=document.getElementById('chatWin');
  chatOpen?w.classList.add('open'):w.classList.remove('open');
}
function quickAsk(q){document.getElementById('chatIn').value=q;sendChat();}

function sendChat(){
  const inp=document.getElementById('chatIn'),msg=inp.value.trim();
  if(!msg)return;
  inp.value='';
  appendMsg('user',msg);
  // Show typing for realism
  const typingId='typing-'+Date.now();
  appendTyping(typingId);
  setTimeout(()=>{
    removeTyping(typingId);
    const reply=getBotReply(msg);
    appendMsg('bot',reply);
  },600+Math.random()*400);
}

function appendMsg(role,text){
  const c=document.getElementById('cmsgs');
  const d=document.createElement('div');d.className='cmsg '+role;
  const dot=document.createElement('div');dot.className='cdot';dot.textContent=role==='bot'?'AK':'👤';
  const b=document.createElement('div');b.className='cbubble';b.textContent=text;
  d.appendChild(dot);d.appendChild(b);
  c.appendChild(d);c.scrollTop=c.scrollHeight;
}
function appendTyping(id){
  const c=document.getElementById('cmsgs');
  const d=document.createElement('div');d.className='cmsg bot';d.id=id;
  const dot=document.createElement('div');dot.className='cdot';dot.textContent='AK';
  const b=document.createElement('div');b.className='cbubble';
  b.innerHTML='<span class="typing-dots"><span></span><span></span><span></span></span>';
  d.appendChild(dot);d.appendChild(b);
  c.appendChild(d);c.scrollTop=c.scrollHeight;
}
function removeTyping(id){const el=document.getElementById(id);if(el)el.remove();}

// RADAR CHART (replaces mini bar chart)
function initRadarChart(){
  const ctx=document.getElementById('radarChart');
  if(!ctx)return;
  new Chart(ctx,{
    type:'radar',
    data:{
      labels:['Power BI','SQL','Python','Tableau','Azure','Data Modeling'],
      datasets:[{
        label:'Proficiency',
        data:[95,90,80,85,70,88],
        backgroundColor:'rgba(240,90,40,.15)',
        borderColor:'#f05a28',
        borderWidth:2.5,
        pointBackgroundColor:'#f05a28',
        pointBorderColor:'#fff',
        pointBorderWidth:2,
        pointRadius:5,
        pointHoverRadius:7,
      }]
    },
    options:{
      responsive:true,maintainAspectRatio:true,
      plugins:{legend:{display:false},tooltip:{callbacks:{label:c=>' '+c.raw+'%'}}},
      scales:{r:{
        min:0,max:100,
        ticks:{display:false,stepSize:20},
        grid:{color:'rgba(255,255,255,.08)'},
        angleLines:{color:'rgba(255,255,255,.08)'},
        pointLabels:{color:'#a0aec0',font:{size:11,family:'Poppins',weight:'600'}}
      }}
    }
  });
  // Animate skill bars
  setTimeout(()=>{
    document.querySelectorAll('.skill-bar-fill').forEach(bar=>{
      bar.style.width=bar.dataset.width;
    });
  },300);
}

// GROWTH CHART
let growthChartInstance=null;
function initGrowthChart(){
  const ctx=document.getElementById('growthChart');
  if(!ctx)return;
  if(growthChartInstance){growthChartInstance.destroy();}
  growthChartInstance=new Chart(ctx,{
    type:'line',
    data:{
      labels:['2021','2022','2023','2024','2025'],
      datasets:[
        {label:'Skills Mastered',data:[2,5,8,10,12],borderColor:'#f05a28',backgroundColor:'rgba(240,90,40,.12)',borderWidth:3,fill:true,tension:.4,pointBackgroundColor:'#f05a28',pointRadius:5,pointHoverRadius:8},
        {label:'Certifications',data:[0,1,2,4,5],borderColor:'#4ade80',backgroundColor:'rgba(74,222,128,.10)',borderWidth:3,fill:true,tension:.4,pointBackgroundColor:'#4ade80',pointRadius:5,pointHoverRadius:8},
        {label:'% Time Saved',data:[0,5,15,40,60],borderColor:'#60a5fa',backgroundColor:'rgba(96,165,250,.10)',borderWidth:3,fill:true,tension:.4,pointBackgroundColor:'#60a5fa',pointRadius:5,pointHoverRadius:8},
        {label:'% Cost Savings',data:[0,3,10,25,30],borderColor:'#facc15',backgroundColor:'rgba(250,204,21,.08)',borderWidth:3,fill:true,tension:.4,pointBackgroundColor:'#facc15',pointRadius:5,pointHoverRadius:8}
      ]
    },
    options:{
      responsive:true,maintainAspectRatio:false,
      interaction:{mode:'index',intersect:false},
      plugins:{
        legend:{labels:{color:'#a0aec0',usePointStyle:true,pointStyle:'circle',padding:18,font:{family:'Poppins',size:12}}},
        tooltip:{backgroundColor:'rgba(15,22,41,.95)',borderColor:'rgba(240,90,40,.3)',borderWidth:1,titleColor:'#fff',bodyColor:'#a0aec0',padding:12,titleFont:{weight:'bold'}}
      },
      scales:{
        y:{ticks:{color:'#a0aec0',font:{size:11}},grid:{color:'rgba(255,255,255,.04)'},beginAtZero:true},
        x:{ticks:{color:'#a0aec0',font:{size:12}},grid:{color:'rgba(255,255,255,.04)'}}
      }
    }
  });
}

// MARKET DATA — static fallback articles (AI fetch optional)
const FALLBACK_ARTICLES=[
  {category:'POWER BI',title:'Copilot in Power BI: AI-Powered Report Generation',summary:'Microsoft\'s Copilot reduces dashboard creation time by up to 50% with AI-generated insights and narratives.',url:'https://powerbi.microsoft.com/blog',date:'May 2025'},
  {category:'FABRIC',title:'Microsoft Fabric OneLake: Unified Data Lake Updates',summary:'New Fabric features simplify data engineering with a unified lakehouse architecture for all analytics workloads.',url:'https://learn.microsoft.com/en-us/fabric',date:'May 2025'},
  {category:'CLOUD',title:'Azure Synapse Analytics: Serverless SQL Pools Expansion',summary:'Enterprise adoption surges as serverless SQL pools become the new analytics standard in the cloud.',url:'https://azure.microsoft.com/blog',date:'May 2025'},
  {category:'AI & ML',title:'Azure AI Foundry: New Model APIs for Predictive Analytics',summary:'AI-skilled BI analysts increasingly in demand as Azure expands its ML and predictive modeling capabilities.',url:'https://azure.microsoft.com/en-us/products/ai-foundry',date:'May 2025'},
  {category:'POWER BI',title:'Power BI May 2025 Feature Update',summary:'New DAX improvements, incremental refresh enhancements and composite model updates shipped this month.',url:'https://powerbi.microsoft.com/blog',date:'May 2025'},
  {category:'AI & ML',title:'AI-Driven Data Storytelling Trends 2025',summary:'BI professionals integrating LLMs with dashboards for automated narrative generation — the next frontier.',url:'https://www.gartner.com/en/analytics',date:'May 2025'},
];
const catColors={'POWER BI':'#f05a28','FABRIC':'#8b5cf6','CLOUD':'#60a5fa','AI & ML':'#4ade80'};

function renderMarketInto(containerId, articles){
  const feed=document.getElementById(containerId);
  if(!articles||!articles.length){feed.innerHTML='<p style="color:var(--muted);text-align:center;padding:2rem;">No updates found. Try refreshing.</p>';return;}
  const grid=document.createElement('div');grid.className='market-grid';
  articles.forEach(a=>{
    const color=catColors[a.category]||'var(--orange)';
    const card=document.createElement('a');
    card.className='market-card';card.href=a.url||'#';card.target='_blank';card.rel='noopener noreferrer';
    card.innerHTML=`<div class="market-tag" style="color:${color}">● ${a.category}</div><div class="market-title">${a.title}</div><div class="market-desc">${a.summary}</div><div class="market-date">📅 ${a.date||'Latest'}</div>`;
    grid.appendChild(card);
  });
  feed.innerHTML='';feed.appendChild(grid);
}

async function loadMarketData(force){
  const today=new Date().toDateString();
  const cacheKey='market_cache_'+today;
  if(!force){
    const cached=sessionStorage.getItem(cacheKey);
    if(cached)return JSON.parse(cached);
  }
  // Try Claude API with web search
  try{
    const res=await fetch('https://api.anthropic.com/v1/messages',{
      method:'POST',
      headers:{'Content-Type':'application/json','anthropic-version':'2023-06-01','anthropic-dangerous-direct-browser-access':'true'},
      body:JSON.stringify({
        model:'claude-sonnet-4-20250514',max_tokens:1200,
        tools:[{type:'web_search_20250305',name:'web_search'}],
        system:'Return ONLY a valid JSON array, no markdown, no preamble. Format: [{"category":"POWER BI","title":"...","summary":"...","url":"https://...","date":"..."},...]',
        messages:[{role:'user',content:'Search for the 6 latest news articles this week about Power BI updates, Microsoft Fabric, Azure cloud, AI/ML for data analytics. Return ONLY a JSON array with fields: category (one of: POWER BI, FABRIC, CLOUD, AI & ML), title, summary (max 120 chars), url, date.'}]
      })
    });
    if(!res.ok)throw new Error('api');
    const data=await res.json();
    const text=data.content.map(b=>b.type==='text'?b.text:'').join('');
    const match=text.match(/\[[\s\S]*\]/);
    const articles=JSON.parse(match?match[0]:text);
    sessionStorage.setItem(cacheKey,JSON.stringify(articles));
    return articles;
  }catch{return FALLBACK_ARTICLES;}
}

async function loadHomeMarket(force=false){
  if(!force&&homeMarketLoaded)return;
  homeMarketLoaded=true;
  document.getElementById('homeMarketFeed').innerHTML='<div class="market-loading"><div class="market-spinner"></div>Fetching latest updates...</div>';
  const articles=await loadMarketData(force);
  renderMarketInto('homeMarketFeed',articles);
}

async function loadMarket(force=false){
  marketLoaded=true;
  document.getElementById('marketFeed').innerHTML='<div class="market-loading"><div class="market-spinner"></div>Fetching latest updates...</div>';
  const articles=await loadMarketData(force);
  const feed=document.getElementById('marketFeed');
  renderMarketInto('marketFeed',articles);
  // Add refresh button
  const refreshBtn=document.createElement('button');
  refreshBtn.style.cssText='display:block;margin:1.5rem auto 0;background:rgba(240,90,40,.12);border:1px solid rgba(240,90,40,.3);color:var(--orange);padding:.5rem 1.4rem;border-radius:100px;font-family:Poppins,sans-serif;font-size:.75rem;font-weight:700;cursor:pointer;transition:all .2s;';
  refreshBtn.textContent='🔄 Refresh Updates';
  refreshBtn.onclick=()=>{marketLoaded=false;loadMarket(true);};
  feed.appendChild(refreshBtn);
}

// INIT
window.addEventListener('load',()=>{
  initRadarChart();
  loadHomeMarket();
});
</script>
</body>
</html>
