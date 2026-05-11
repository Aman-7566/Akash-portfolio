<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>Akash Kourav — BI Analyst & Power BI Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800;900&family=Syne:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
:root{
  --navy:#080e1f;--navy2:#0d1428;--navy3:#111a33;--navy4:#162040;
  --orange:#f05a28;--orange2:#ff7a4a;--orange3:#ff9566;
  --green:#22c55e;--blue:#3b82f6;--purple:#a855f7;
  --text:#f1f5f9;--muted:#94a3b8;--muted2:#64748b;
  --card:rgba(255,255,255,0.04);--border:rgba(255,255,255,0.07);
  --glass:rgba(255,255,255,0.03);
}
html{scroll-behavior:smooth;}
body{background:var(--navy);color:var(--text);font-family:'Outfit',sans-serif;overflow-x:hidden;}

/* ============ NAV ============ */
nav{display:flex;align-items:center;justify-content:space-between;padding:0 2rem;height:60px;position:fixed;top:0;left:0;right:0;z-index:300;background:rgba(8,14,31,0.96);backdrop-filter:blur(20px);border-bottom:1px solid rgba(255,255,255,0.06);}
.nav-brand{display:flex;align-items:center;gap:.6rem;flex-shrink:0;}
.nav-logo{width:34px;height:34px;border-radius:10px;background:linear-gradient(135deg,var(--orange),var(--orange2));display:flex;align-items:center;justify-content:center;font-weight:900;font-size:.78rem;color:#fff;font-family:'Syne',sans-serif;}
.nav-name{font-weight:700;font-size:.88rem;font-family:'Syne',sans-serif;}
.nav-tabs{display:flex;align-items:center;gap:.1rem;background:rgba(255,255,255,0.04);border:1px solid var(--border);border-radius:12px;padding:.25rem;flex:1;max-width:680px;margin:0 1.5rem;overflow-x:auto;scrollbar-width:none;}
.nav-tabs::-webkit-scrollbar{display:none;}
.nav-tab{padding:.32rem .72rem;border-radius:8px;color:var(--muted);font-size:.7rem;font-weight:600;cursor:pointer;border:none;background:transparent;transition:all .2s;white-space:nowrap;font-family:'Outfit',sans-serif;letter-spacing:.01em;}
.nav-tab:hover{color:#fff;}
.nav-tab.active{background:var(--orange);color:#fff;}
.nav-actions{display:flex;align-items:center;gap:.5rem;flex-shrink:0;}
.btn-edit{display:inline-flex;align-items:center;gap:.3rem;padding:.32rem .75rem;border-radius:8px;border:1px solid rgba(255,255,255,.1);cursor:pointer;font-family:'Outfit',sans-serif;font-weight:600;font-size:.7rem;background:rgba(255,255,255,.05);color:var(--muted);transition:all .2s;}
.btn-edit:hover{color:#fff;background:rgba(255,255,255,.09);}
.btn-edit.unlocked{background:rgba(34,197,94,.12);color:#4ade80;border-color:rgba(34,197,94,.3);}
.btn-resume{background:var(--orange);color:#fff;padding:.32rem .9rem;border-radius:8px;font-weight:700;font-size:.7rem;display:inline-flex;align-items:center;gap:.3rem;transition:all .2s;border:none;cursor:pointer;font-family:'Outfit',sans-serif;}
.btn-resume:hover{background:var(--orange2);transform:translateY(-1px);}

/* ============ PAGES ============ */
.page{display:none;animation:fade .28s ease;}
.page.active{display:block;}
@keyframes fade{from{opacity:0;transform:translateY(8px);}to{opacity:1;transform:none;}}

/* ============ HERO — 3 COLUMN GRID ============ */
.hero{
  min-height:100vh;
  display:grid;
  grid-template-columns:360px 1fr 340px;
  gap:2.5rem;
  padding:80px 2.5rem 2.5rem;
  align-items:center;
  position:relative;
  overflow:hidden;
}
.hero::before{content:'';position:absolute;width:700px;height:700px;border-radius:50%;background:radial-gradient(circle,rgba(240,90,40,.08) 0%,transparent 70%);top:-200px;right:-150px;pointer-events:none;}
.hero::after{content:'';position:absolute;width:400px;height:400px;border-radius:50%;background:radial-gradient(circle,rgba(59,130,246,.06) 0%,transparent 70%);bottom:-100px;left:-80px;pointer-events:none;}

/* LEFT — info + follow */
.hero-left{z-index:2;display:flex;flex-direction:column;gap:1.2rem;}

.info-panel{background:rgba(255,255,255,.035);border:1px solid rgba(255,255,255,.07);border-radius:18px;padding:1.3rem;backdrop-filter:blur(10px);}
.info-panel-title{font-size:.6rem;letter-spacing:.14em;text-transform:uppercase;color:var(--orange);font-weight:700;margin-bottom:.9rem;display:flex;align-items:center;gap:.4rem;}
.info-panel-title::before{content:'';width:16px;height:2px;background:var(--orange);border-radius:2px;}
.info-item{display:flex;align-items:center;gap:.75rem;padding:.52rem .65rem;border-radius:10px;background:rgba(255,255,255,.025);border:1px solid rgba(255,255,255,.04);transition:all .2s;cursor:pointer;text-decoration:none;margin-bottom:.4rem;}
.info-item:last-child{margin-bottom:0;}
.info-item:hover{border-color:rgba(240,90,40,.3);background:rgba(240,90,40,.05);}
.info-icon{width:30px;height:30px;border-radius:8px;background:rgba(240,90,40,.12);display:flex;align-items:center;justify-content:center;font-size:.9rem;flex-shrink:0;}
.info-text{flex:1;min-width:0;}
.info-label{font-size:.55rem;color:var(--muted2);line-height:1;margin-bottom:2px;text-transform:uppercase;letter-spacing:.07em;}
.info-value{font-size:.76rem;font-weight:600;color:#fff;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;}
.avail-badge{display:inline-flex;align-items:center;gap:.5rem;background:rgba(34,197,94,.08);border:1px solid rgba(34,197,94,.22);color:#4ade80;padding:.38rem 1rem;border-radius:10px;font-size:.68rem;font-weight:700;width:100%;justify-content:center;margin-top:.3rem;}
.avail-dot{width:7px;height:7px;border-radius:50%;background:#4ade80;animation:pulse 1.6s infinite;flex-shrink:0;}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1);}50%{opacity:.4;transform:scale(.8);}}

/* Follow row below info panel */
.follow-row{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.06);border-radius:14px;padding:.9rem 1rem;display:flex;align-items:center;gap:.7rem;}
.follow-label{font-size:.67rem;color:var(--muted);font-weight:600;white-space:nowrap;}
.socials{display:flex;gap:.4rem;flex:1;justify-content:flex-end;}
.soc{width:34px;height:34px;border-radius:9px;display:flex;align-items:center;justify-content:center;text-decoration:none;font-weight:800;font-size:.7rem;transition:all .2s;color:#fff;}
.soc:hover{transform:translateY(-2px) scale(1.08);}
.soc-li{background:#0077b5;}
.soc-gh{background:#24292e;}
.soc-em{background:var(--orange);}
.soc-wa{background:#25d366;}

/* CENTER */
.hero-center{display:flex;justify-content:center;align-items:center;z-index:2;flex-direction:column;gap:0;}
.profile-outer{position:relative;width:300px;height:300px;}
.ring-outer{position:absolute;inset:-12px;border-radius:50%;border:1.5px dashed rgba(240,90,40,.3);animation:spinRing 25s linear infinite;}
.ring-inner{position:absolute;inset:0;border-radius:50%;border:2px solid rgba(240,90,40,.18);}
.profile-circle{position:absolute;inset:0;border-radius:50%;background:linear-gradient(145deg,#5a1a08,var(--orange));overflow:hidden;cursor:pointer;transition:all .3s;box-shadow:0 0 50px rgba(240,90,40,.22),0 0 100px rgba(240,90,40,.08);}
.profile-circle:hover{box-shadow:0 0 70px rgba(240,90,40,.38);}
.profile-img{width:100%;height:100%;object-fit:cover;display:block;}
.cam-btn{position:absolute;bottom:12px;right:12px;width:40px;height:40px;border-radius:50%;background:var(--orange);display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:.95rem;z-index:3;box-shadow:0 4px 14px rgba(240,90,40,.4);transition:all .2s;}
.cam-btn:hover{background:var(--orange2);transform:scale(1.1);}
.metric{position:absolute;background:rgba(8,14,31,.95);backdrop-filter:blur(16px);border:1px solid rgba(255,255,255,.1);border-radius:12px;padding:.55rem .85rem;text-align:center;white-space:nowrap;box-shadow:0 8px 24px rgba(0,0,0,.4);}
.metric-val{font-size:1.25rem;font-weight:900;line-height:1;font-family:'Syne',sans-serif;color:var(--orange);}
.metric-lbl{font-size:.56rem;color:var(--muted);margin-top:2px;}
.m1{top:-8px;right:-50px;animation:mf1 3.5s ease-in-out infinite;}
.m2{top:50%;left:-60px;transform:translateY(-50%);animation:mf2 3.8s ease-in-out .6s infinite;}
.m3{bottom:0;right:-48px;animation:mf3 3.2s ease-in-out 1.1s infinite;}
@keyframes spinRing{to{transform:rotate(360deg);}}
@keyframes mf1{0%,100%{transform:translateY(0);}50%{transform:translateY(-7px);}}
@keyframes mf2{0%,100%{transform:translateY(-50%);}50%{transform:translateY(calc(-50% - 7px));}}
@keyframes mf3{0%,100%{transform:translateY(0);}50%{transform:translateY(-7px);}}

/* Follow below profile image */
.profile-follow{width:300px;margin-top:1.1rem;background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.07);border-radius:14px;padding:.8rem 1rem;display:flex;align-items:center;gap:.6rem;}
.profile-follow-label{font-size:.65rem;color:var(--muted);font-weight:600;}
.profile-follow-socials{display:flex;gap:.35rem;margin-left:auto;}
.pf-soc{width:32px;height:32px;border-radius:8px;display:flex;align-items:center;justify-content:center;text-decoration:none;font-weight:800;font-size:.68rem;transition:all .2s;color:#fff;}
.pf-soc:hover{transform:translateY(-2px);}

/* RIGHT */
.hero-right{z-index:2;display:flex;flex-direction:column;gap:1.1rem;}
.hero-eyebrow{color:var(--muted);font-size:.82rem;font-weight:400;display:flex;align-items:center;gap:.5rem;}
.hero-eyebrow::before{content:'';width:20px;height:1px;background:var(--orange);}
.hero-name{font-size:clamp(1.9rem,3vw,2.8rem);font-weight:900;line-height:1.05;font-family:'Syne',sans-serif;color:var(--orange);}
.hero-role{font-size:clamp(.9rem,1.3vw,1.1rem);font-weight:700;color:#cbd5e1;}
.hero-desc{color:var(--muted);font-size:.83rem;line-height:1.85;}

.hero-stats-mini{display:grid;grid-template-columns:1fr 1fr;gap:.7rem;}
.hstat{background:rgba(255,255,255,.035);border:1px solid rgba(255,255,255,.07);border-radius:12px;padding:.8rem .9rem;display:flex;align-items:center;gap:.65rem;}
.hstat-icon{font-size:1.2rem;}
.hstat-val{font-size:1.3rem;font-weight:900;color:var(--orange);line-height:1;font-family:'Syne',sans-serif;}
.hstat-lbl{font-size:.62rem;color:var(--muted);margin-top:1px;}

.hero-ctas{display:flex;gap:.7rem;flex-wrap:wrap;align-items:center;}
.btn-primary{background:linear-gradient(135deg,var(--orange),var(--orange2));color:#fff;padding:.65rem 1.4rem;border-radius:10px;font-weight:700;font-size:.83rem;border:none;cursor:pointer;font-family:'Outfit',sans-serif;transition:all .2s;}
.btn-primary:hover{transform:translateY(-2px);box-shadow:0 6px 20px rgba(240,90,40,.32);}
.btn-secondary{background:rgba(255,255,255,.06);color:#fff;padding:.65rem 1.4rem;border-radius:10px;font-weight:600;font-size:.83rem;border:1px solid rgba(255,255,255,.1);cursor:pointer;font-family:'Outfit',sans-serif;transition:all .2s;}
.btn-secondary:hover{background:rgba(255,255,255,.1);border-color:rgba(255,255,255,.18);}

/* ============ STATS SECTION ============ */
.stats-sec{padding:3rem 2.5rem;background:linear-gradient(180deg,rgba(22,32,64,.5),transparent);}
.stats-title{text-align:center;margin-bottom:2rem;}
.stats-title h3{font-size:1.2rem;font-weight:800;font-family:'Syne',sans-serif;margin-bottom:.3rem;}
.stats-title p{color:var(--muted);font-size:.82rem;}
.stats-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:1rem;max-width:1100px;margin:0 auto;}
.scard{background:linear-gradient(160deg,rgba(17,26,51,.98),rgba(13,20,40,.98));border:1px solid rgba(255,255,255,.07);border-radius:16px;padding:1.4rem 1rem;text-align:center;position:relative;overflow:hidden;transition:all .35s;cursor:default;}
.scard::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--orange),transparent);opacity:.5;}
.scard:hover{transform:translateY(-8px);border-color:rgba(240,90,40,.4);box-shadow:0 20px 50px rgba(240,90,40,.12);}
.scard-icon{font-size:1.8rem;margin-bottom:.6rem;display:block;}
.scard-val{font-size:2rem;font-weight:900;color:var(--orange);line-height:1;font-family:'Syne',sans-serif;}
.scard-label{font-size:.76rem;color:#fff;font-weight:700;margin:.45rem 0 .25rem;}
.scard-desc{font-size:.66rem;color:var(--muted);line-height:1.5;}

/* SKILL VISUAL WRAP */
.hero-visual-wrap{max-width:1100px;margin:2rem auto 0;background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.06);border-radius:18px;padding:1.8rem;display:grid;grid-template-columns:1fr 1fr;gap:2rem;align-items:center;}
.visual-section-title{font-size:.65rem;color:var(--muted);text-transform:uppercase;letter-spacing:.1em;font-weight:700;margin-bottom:1rem;text-align:center;grid-column:1/-1;}
.radar-wrap{display:flex;flex-direction:column;align-items:center;}
.skill-bars{display:flex;flex-direction:column;gap:.75rem;}
.skill-bar-item{}
.skill-bar-label{display:flex;justify-content:space-between;font-size:.7rem;font-weight:600;margin-bottom:.28rem;color:#cbd5e1;}
.skill-bar-label span:last-child{color:var(--orange);}
.skill-bar-track{height:6px;background:rgba(255,255,255,.06);border-radius:6px;overflow:hidden;}
.skill-bar-fill{height:100%;border-radius:6px;background:linear-gradient(90deg,var(--orange),var(--orange2));transition:width 1.5s cubic-bezier(.25,1,.5,1);}

/* ============ HOME MARKET ============ */
.home-market-sec{padding:2.5rem 2.5rem 3rem;background:rgba(13,20,40,.6);}
.home-market-inner{max-width:1100px;margin:0 auto;}
.home-market-hdr{display:flex;align-items:flex-start;justify-content:space-between;margin-bottom:1.5rem;flex-wrap:wrap;gap:1rem;}
.home-market-hdr h3{font-size:1.05rem;font-weight:800;font-family:'Syne',sans-serif;}
.home-market-hdr p{color:var(--muted);font-size:.78rem;margin-top:.2rem;}
.refresh-small{background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.22);color:var(--orange);padding:.32rem .9rem;border-radius:8px;font-family:'Outfit',sans-serif;font-size:.69rem;font-weight:700;cursor:pointer;transition:all .2s;display:inline-flex;align-items:center;gap:.35rem;flex-shrink:0;}
.refresh-small:hover{background:rgba(240,90,40,.18);}
.market-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:1.1rem;}
.market-card{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.06);border-radius:14px;padding:1.2rem;transition:all .28s;cursor:pointer;text-decoration:none;display:block;position:relative;overflow:hidden;}
.market-card:hover{border-color:rgba(240,90,40,.4);transform:translateY(-3px);box-shadow:0 10px 28px rgba(0,0,0,.25);}
.market-card::after{content:'↗';position:absolute;top:.85rem;right:.85rem;color:var(--orange);font-size:.85rem;opacity:0;transition:opacity .22s;}
.market-card:hover::after{opacity:1;}
.market-tag{font-size:.62rem;letter-spacing:.1em;text-transform:uppercase;font-weight:700;margin-bottom:.4rem;}
.market-title{font-weight:700;font-size:.85rem;margin-bottom:.35rem;color:#fff;padding-right:1.2rem;line-height:1.4;}
.market-desc{color:var(--muted);font-size:.77rem;line-height:1.6;}
.market-date{font-size:.62rem;color:var(--muted2);margin-top:.55rem;}
.market-loading{text-align:center;padding:2.5rem;color:var(--muted);}
.market-spinner{width:32px;height:32px;border:2.5px solid rgba(240,90,40,.18);border-top-color:var(--orange);border-radius:50%;animation:spin .75s linear infinite;margin:0 auto .7rem;}
@keyframes spin{to{transform:rotate(360deg);}}

/* ============ CONTACT ============ */
.contact-section{padding:3rem 2.5rem;background:linear-gradient(180deg,rgba(13,20,40,.8),rgba(8,14,31,1));}
.contact-wrap{max-width:780px;margin:0 auto;}
.contact-header{text-align:center;margin-bottom:2rem;}
.contact-header .sec-label-sm{color:var(--orange);font-size:.67rem;letter-spacing:.14em;text-transform:uppercase;font-weight:700;display:block;margin-bottom:.4rem;}
.contact-header h2{font-size:clamp(1.4rem,3vw,2rem);font-weight:900;font-family:'Syne',sans-serif;margin-bottom:.5rem;}
.contact-header p{color:var(--muted);font-size:.83rem;}
.contact-form{background:rgba(13,20,40,.97);border:1px solid rgba(240,90,40,.18);border-radius:22px;padding:2.2rem;position:relative;overflow:hidden;}
.contact-form::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--orange),var(--orange2),transparent);}
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.1rem;position:relative;z-index:1;}
.form-grid .full{grid-column:1/-1;}
.fg-contact{position:relative;}
.fg-contact label{display:block;font-size:.64rem;color:var(--muted);margin-bottom:.38rem;font-weight:700;text-transform:uppercase;letter-spacing:.07em;}
.fg-contact .fi{position:absolute;left:.85rem;top:50%;transform:translateY(-50%);font-size:.85rem;pointer-events:none;z-index:2;}
.fg-contact input,.fg-contact select,.fg-contact textarea{width:100%;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.08);border-radius:11px;padding:.68rem .85rem .68rem 2.5rem;color:#fff;font-family:'Outfit',sans-serif;font-size:.82rem;outline:none;transition:all .22s;appearance:none;}
.fg-contact textarea{padding:.68rem .85rem;height:95px;resize:none;}
.fg-contact.no-icon input,.fg-contact.no-icon select,.fg-contact.no-icon textarea{padding-left:.85rem;}
.fg-contact input:focus,.fg-contact textarea:focus,.fg-contact select:focus{border-color:var(--orange);background:rgba(240,90,40,.05);box-shadow:0 0 0 3px rgba(240,90,40,.1);}
.fg-contact select option{background:#111a33;}
.form-submit{width:100%;padding:.85rem;background:linear-gradient(135deg,var(--orange),var(--orange2));color:#fff;border:none;border-radius:11px;font-family:'Outfit',sans-serif;font-weight:800;font-size:.9rem;cursor:pointer;transition:all .22s;box-shadow:0 6px 20px rgba(240,90,40,.32);margin-top:.4rem;}
.form-submit:hover{transform:translateY(-2px);box-shadow:0 10px 28px rgba(240,90,40,.48);}
.form-submit:disabled{opacity:.6;cursor:not-allowed;transform:none;}

/* ============ GROWTH KPIs ============ */
.growth-kpi-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1rem;margin-bottom:2rem;}
.gkpi{background:linear-gradient(145deg,rgba(17,26,51,.98),rgba(13,20,40,.98));border:1px solid rgba(255,255,255,.08);border-radius:16px;padding:1.3rem 1.1rem;position:relative;overflow:hidden;transition:all .3s;}
.gkpi:hover{transform:translateY(-5px);border-color:rgba(240,90,40,.35);box-shadow:0 14px 36px rgba(240,90,40,.1);}
.gkpi::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--orange),transparent);opacity:.5;}
.gkpi-icon{font-size:1.5rem;margin-bottom:.55rem;}
.gkpi-val{font-size:1.9rem;font-weight:900;color:var(--orange);line-height:1;font-family:'Syne',sans-serif;}
.gkpi-label{font-size:.73rem;color:#cbd5e1;font-weight:600;margin:.28rem 0 .45rem;}
.gkpi-badge{display:inline-flex;align-items:center;gap:.22rem;padding:.15rem .55rem;border-radius:100px;font-size:.6rem;font-weight:700;}
.gkpi-badge.up{background:rgba(34,197,94,.1);border:1px solid rgba(34,197,94,.22);color:#4ade80;}
.gkpi-sub{font-size:.64rem;color:var(--muted);margin-top:.28rem;}
.growth-container{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.07);border-radius:16px;padding:1.6rem;position:relative;}
.growth-canvas{width:100%;height:360px;}

/* ============ CERTS SECTION — ENHANCED ============ */
.cert-hero-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:1.2rem;margin-bottom:2rem;}
.cert-hero-stat{background:linear-gradient(145deg,rgba(17,26,51,.98),rgba(22,32,64,.95));border:1px solid rgba(255,255,255,.07);border-radius:18px;padding:1.6rem 1.2rem;text-align:center;position:relative;overflow:hidden;transition:all .35s;}
.cert-hero-stat::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;border-radius:18px 18px 0 0;}
.cert-hero-stat:nth-child(1)::before{background:linear-gradient(90deg,var(--orange),var(--orange2));}
.cert-hero-stat:nth-child(2)::before{background:linear-gradient(90deg,var(--blue),#60a5fa);}
.cert-hero-stat:nth-child(3)::before{background:linear-gradient(90deg,var(--purple),#c084fc);}
.cert-hero-stat:hover{transform:translateY(-6px);border-color:rgba(240,90,40,.25);box-shadow:0 16px 40px rgba(0,0,0,.3);}
.cert-stat-icon{font-size:2rem;margin-bottom:.6rem;}
.cert-stat-val{font-size:2.8rem;font-weight:900;line-height:1;font-family:'Syne',sans-serif;}
.cert-hero-stat:nth-child(1) .cert-stat-val{color:var(--orange);}
.cert-hero-stat:nth-child(2) .cert-stat-val{color:var(--blue);}
.cert-hero-stat:nth-child(3) .cert-stat-val{color:var(--purple);}
.cert-stat-label{font-size:.78rem;color:#cbd5e1;font-weight:700;margin:.4rem 0 .3rem;}
.cert-stat-sub{font-size:.67rem;color:var(--muted);line-height:1.5;}
.cert-progress-ring{width:60px;height:60px;margin:0 auto .7rem;}

.skills-learned-wrap{background:rgba(255,255,255,.025);border:1px solid rgba(255,255,255,.06);border-radius:16px;padding:1.2rem 1.4rem;margin-bottom:2rem;}
.skills-learned-hdr{display:flex;align-items:center;justify-content:space-between;margin-bottom:.8rem;}
.skills-learned-title{font-size:.65rem;color:var(--muted);text-transform:uppercase;letter-spacing:.1em;font-weight:700;}
.skills-learned-count{font-size:.65rem;color:var(--orange);font-weight:700;}
.skills-learned-chips{display:flex;flex-wrap:wrap;gap:.4rem;}
.sl-chip{background:rgba(255,255,255,.045);border:1px solid rgba(255,255,255,.08);color:#cbd5e1;padding:.26rem .72rem;border-radius:8px;font-size:.68rem;font-weight:600;transition:all .2s;cursor:default;}
.sl-chip.hot{background:rgba(240,90,40,.1);border-color:rgba(240,90,40,.28);color:var(--orange);}
.sl-chip:hover{border-color:rgba(240,90,40,.35);color:var(--orange);background:rgba(240,90,40,.07);}

.certs-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:1.3rem;}
.cert-card{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.06);border-radius:16px;overflow:hidden;transition:all .3s;position:relative;}
.cert-card:hover{border-color:rgba(240,90,40,.4);transform:translateY(-4px);box-shadow:0 12px 30px rgba(0,0,0,.25);}
.cert-card-badge{position:absolute;top:.75rem;right:.75rem;background:rgba(240,90,40,.15);border:1px solid rgba(240,90,40,.3);color:var(--orange);padding:.15rem .55rem;border-radius:6px;font-size:.58rem;font-weight:800;text-transform:uppercase;letter-spacing:.06em;}
.cert-wrap{width:100%;height:150px;background:linear-gradient(145deg,rgba(17,26,51,.98),rgba(22,32,64,.95));display:flex;align-items:center;justify-content:center;cursor:pointer;overflow:hidden;position:relative;}
.cert-wrap::after{content:'';position:absolute;inset:0;background:linear-gradient(180deg,transparent 60%,rgba(8,14,31,.6));}
.cert-placeholder{display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.5rem;color:var(--muted);font-size:.74rem;text-align:center;padding:1rem;width:100%;height:100%;position:relative;z-index:1;}
.cert-placeholder .cert-emoji{font-size:2.5rem;filter:drop-shadow(0 4px 12px rgba(240,90,40,.3));}
.cert-body{padding:1rem 1.1rem 1.2rem;}
.cert-org{font-size:.65rem;color:var(--muted);margin-bottom:.1rem;display:flex;align-items:center;gap:.3rem;}
.cert-name{font-weight:750;font-size:.86rem;margin-bottom:.4rem;color:#fff;}
.cert-meta{display:flex;align-items:center;justify-content:space-between;}
.cert-year{font-size:.65rem;color:var(--orange);font-weight:700;}
.cert-level{font-size:.6rem;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.08);padding:.12rem .5rem;border-radius:6px;color:var(--muted);}
.add-cert{background:rgba(255,255,255,.02);border:1.5px dashed rgba(255,255,255,.1);border-radius:16px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.5rem;cursor:pointer;min-height:240px;transition:all .28s;color:var(--muted);font-size:.8rem;}
.add-cert:hover{border-color:var(--orange);background:rgba(240,90,40,.04);color:var(--orange);}

/* ============ GENERAL SECTIONS ============ */
.sec{padding:5rem 2.5rem 3.5rem;}
.sec-label{color:var(--orange);font-size:.65rem;letter-spacing:.14em;text-transform:uppercase;margin-bottom:.4rem;font-weight:700;display:flex;align-items:center;gap:.4rem;}
.sec-label::before{content:'';width:14px;height:2px;background:var(--orange);border-radius:2px;}
.sec h2{font-size:clamp(1.4rem,2.5vw,2rem);font-weight:900;font-family:'Syne',sans-serif;margin-bottom:.4rem;}
.sec-bar{height:3px;width:40px;background:var(--orange);border-radius:3px;margin-bottom:1.8rem;}
.sec-sub{color:var(--muted);font-size:.83rem;line-height:1.8;max-width:500px;margin-bottom:2rem;}

/* ============ SKILLS ============ */
.skills-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:1.1rem;}
.sk{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.07);border-radius:14px;padding:1.2rem;transition:all .28s;position:relative;overflow:hidden;}
.sk:hover{border-color:rgba(240,90,40,.45);transform:translateY(-4px);}
.sk-icon{font-size:1.6rem;margin-bottom:.55rem;display:block;}
.sk-title{font-weight:750;font-size:.85rem;margin-bottom:.7rem;}
.tags{display:flex;flex-wrap:wrap;gap:.28rem;}
.tag{background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.08);border-radius:7px;padding:.14rem .52rem;font-size:.63rem;color:var(--muted);transition:all .2s;}
.tag:hover,.tag.h{background:rgba(240,90,40,.1);border-color:rgba(240,90,40,.3);color:var(--orange);}

/* ============ PROJECTS ============ */
.projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1.2rem;}
.proj{background:rgba(17,26,51,.8);border:1px solid rgba(255,255,255,.07);border-radius:14px;padding:1.4rem;transition:all .28s;position:relative;overflow:hidden;}
.proj:hover{border-color:rgba(240,90,40,.38);transform:translateY(-4px);}
.proj-type{font-size:.62rem;letter-spacing:.1em;text-transform:uppercase;color:var(--orange);margin-bottom:.4rem;font-weight:700;}
.proj-title{font-weight:750;font-size:.9rem;margin-bottom:.4rem;}
.proj-desc{color:var(--muted);font-size:.79rem;line-height:1.65;}

/* ============ EXPERIENCE ============ */
.exp-timeline{max-width:860px;position:relative;}
.exp-timeline::before{content:'';position:absolute;left:22px;top:24px;bottom:24px;width:2px;background:linear-gradient(180deg,var(--orange),rgba(240,90,40,.05));border-radius:2px;}
.exp-item{display:flex;gap:1.4rem;margin-bottom:2rem;position:relative;}
.exp-dot{width:44px;height:44px;border-radius:12px;flex-shrink:0;background:linear-gradient(135deg,var(--orange),var(--orange2));display:flex;align-items:center;justify-content:center;font-size:1rem;position:relative;z-index:2;box-shadow:0 0 0 4px rgba(240,90,40,.12);}
.exp-card{flex:1;background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.07);border-radius:14px;padding:1.3rem 1.5rem;transition:all .28s;position:relative;overflow:hidden;}
.exp-card::before{content:'';position:absolute;top:0;left:0;bottom:0;width:3px;background:var(--orange);opacity:0;transition:opacity .28s;border-radius:3px 0 0 3px;}
.exp-card:hover{border-color:rgba(240,90,40,.35);transform:translateX(3px);}
.exp-card:hover::before{opacity:1;}
.exp-header{display:flex;align-items:flex-start;justify-content:space-between;gap:1rem;margin-bottom:.45rem;flex-wrap:wrap;}
.exp-title{font-weight:800;font-size:.92rem;}
.exp-period{background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.22);color:var(--orange);padding:.2rem .65rem;border-radius:8px;font-size:.62rem;font-weight:700;white-space:nowrap;flex-shrink:0;}
.exp-company{font-size:.77rem;color:var(--orange);font-weight:700;margin-bottom:.6rem;}
.exp-bullets{list-style:none;display:flex;flex-direction:column;gap:.38rem;}
.exp-bullets li{display:flex;align-items:flex-start;gap:.4rem;color:var(--muted);font-size:.77rem;line-height:1.65;}
.exp-bullets li::before{content:'▹';color:var(--orange);flex-shrink:0;margin-top:2px;}

/* ============ AWARDS ============ */
.awards-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1.3rem;}
.award-card{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.07);border-radius:16px;overflow:hidden;transition:all .3s;}
.award-card:hover{border-color:rgba(240,90,40,.4);transform:translateY(-4px);}
.award-wrap{width:100%;height:140px;background:linear-gradient(145deg,rgba(17,26,51,.98),rgba(22,32,64,.95));display:flex;align-items:center;justify-content:center;cursor:pointer;}
.award-placeholder{display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.4rem;color:var(--muted);font-size:.74rem;text-align:center;padding:1rem;}
.award-body{padding:.9rem 1.1rem 1.1rem;}
.award-badge{display:inline-flex;align-items:center;gap:.25rem;background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.25);color:var(--orange);padding:.18rem .65rem;border-radius:8px;font-size:.58rem;font-weight:700;margin-bottom:.35rem;}
.award-title{font-weight:750;font-size:.86rem;margin-bottom:.22rem;}
.award-desc{color:var(--muted);font-size:.76rem;line-height:1.6;}
.add-award{background:rgba(255,255,255,.02);border:1.5px dashed rgba(255,255,255,.1);border-radius:16px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.5rem;cursor:pointer;min-height:240px;transition:all .28s;color:var(--muted);font-size:.8rem;}
.add-award:hover{border-color:var(--orange);background:rgba(240,90,40,.04);color:var(--orange);}

/* ============ ABOUT ============ */
.about-grid{display:grid;grid-template-columns:240px 1fr;gap:2.5rem;align-items:start;max-width:1000px;}
.about-img{aspect-ratio:3/4;background:linear-gradient(145deg,rgba(22,32,64,.98),rgba(30,15,60,.9));border-radius:18px;border:1px solid rgba(255,255,255,.07);display:flex;align-items:center;justify-content:center;font-size:5rem;}
.about-body p{color:var(--muted);font-size:.84rem;line-height:1.85;margin-bottom:.85rem;}
.chips{display:flex;flex-wrap:wrap;gap:.4rem;margin-top:1.1rem;}
.chip{background:rgba(240,90,40,.09);border:1px solid rgba(240,90,40,.24);color:var(--orange);padding:.26rem .8rem;border-radius:8px;font-size:.7rem;font-weight:600;}

/* ============ LIGHTBOX ============ */
.lb{display:none;position:fixed;inset:0;z-index:999;background:rgba(0,0,0,.92);backdrop-filter:blur(8px);align-items:center;justify-content:center;}
.lb.open{display:flex;}
.lb-inner{position:relative;}
.lb-inner img{max-width:92vw;max-height:90vh;border-radius:12px;object-fit:contain;}
.lb-close{position:absolute;top:-14px;right:-14px;width:30px;height:30px;border-radius:50%;background:var(--orange);color:#fff;border:none;font-size:1rem;cursor:pointer;display:flex;align-items:center;justify-content:center;}

/* ============ LOGIN ============ */
.login-overlay{display:none;position:fixed;inset:0;z-index:800;background:rgba(0,0,0,.88);backdrop-filter:blur(10px);align-items:center;justify-content:center;}
.login-overlay.open{display:flex;}
.login-box{background:linear-gradient(145deg,var(--navy2),#0a1020);border:1px solid rgba(240,90,40,.25);border-radius:20px;padding:2rem;width:100%;max-width:360px;position:relative;box-shadow:0 28px 65px rgba(0,0,0,.6);}
.login-box::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--orange),transparent);border-radius:20px 20px 0 0;}
.login-logo{width:48px;height:48px;border-radius:12px;background:linear-gradient(135deg,var(--orange),var(--orange2));display:flex;align-items:center;justify-content:center;font-weight:900;font-size:.9rem;font-family:'Syne',sans-serif;margin:0 auto 1rem;}
.login-title{text-align:center;font-size:1.05rem;font-weight:800;font-family:'Syne',sans-serif;margin-bottom:.2rem;}
.login-sub{text-align:center;color:var(--muted);font-size:.75rem;margin-bottom:1.3rem;}
.login-err{background:rgba(239,68,68,.1);border:1px solid rgba(239,68,68,.28);color:#fca5a5;border-radius:9px;padding:.55rem .85rem;font-size:.73rem;margin-bottom:.85rem;display:none;text-align:center;}
.login-err.show{display:block;}
.lf{margin-bottom:.85rem;position:relative;}
.lf label{display:block;font-size:.65rem;color:var(--muted);margin-bottom:.32rem;font-weight:700;text-transform:uppercase;letter-spacing:.06em;}
.lf input{width:100%;background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.09);border-radius:10px;padding:.68rem 1rem .68rem 2.4rem;color:#fff;font-family:'Outfit',sans-serif;font-size:.83rem;outline:none;transition:all .2s;}
.lf input:focus{border-color:var(--orange);background:rgba(240,90,40,.05);}
.lf-icon{position:absolute;left:.85rem;bottom:.75rem;font-size:.85rem;pointer-events:none;}
.login-btn{width:100%;padding:.78rem;background:linear-gradient(135deg,var(--orange),var(--orange2));color:#fff;border:none;border-radius:10px;font-family:'Outfit',sans-serif;font-weight:800;font-size:.88rem;cursor:pointer;transition:all .2s;margin-top:.3rem;}
.login-btn:hover{transform:translateY(-2px);}
.login-xbtn{position:absolute;top:.85rem;right:.85rem;background:rgba(255,255,255,.07);border:1px solid rgba(255,255,255,.09);color:var(--muted);width:26px;height:26px;border-radius:50%;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:.75rem;transition:all .2s;}
.login-xbtn:hover{background:rgba(255,255,255,.14);color:#fff;}

/* ============ EDIT ============ */
.edit-banner{display:none;position:fixed;top:60px;left:0;right:0;z-index:250;background:linear-gradient(90deg,rgba(34,197,94,.12),rgba(34,197,94,.05));border-bottom:1px solid rgba(34,197,94,.2);padding:.42rem 2rem;text-align:center;font-size:.7rem;color:#4ade80;font-weight:500;align-items:center;justify-content:center;gap:.5rem;}
.edit-banner.show{display:flex;}
.edit-dot{width:6px;height:6px;border-radius:50%;background:#4ade80;animation:pulse 1.5s infinite;}
.editable{outline:none;border-radius:4px;transition:all .2s;cursor:default;}
body.edit-mode .editable{cursor:text;background:rgba(240,90,40,.1);box-shadow:0 0 0 2px rgba(240,90,40,.3);padding:2px 5px;}

/* ============ TOAST ============ */
.toast{position:fixed;bottom:2rem;left:50%;transform:translateX(-50%) translateY(120px);background:rgba(8,14,31,.97);border:1px solid rgba(240,90,40,.35);color:#fff;padding:.7rem 1.4rem;border-radius:10px;font-size:.76rem;font-weight:600;z-index:9999;transition:transform .3s;pointer-events:none;backdrop-filter:blur(12px);box-shadow:0 8px 24px rgba(0,0,0,.4);}
.toast.show{transform:translateX(-50%) translateY(0);}

/* ============ CHATBOT ============ */
.chat-fab{position:fixed;bottom:2rem;right:2rem;z-index:400;width:56px;height:56px;border-radius:50%;background:linear-gradient(135deg,var(--orange),var(--orange2));border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;box-shadow:0 8px 26px rgba(240,90,40,.4);transition:all .2s;animation:chatPulse 2.8s ease-in-out infinite;}
.chat-fab:hover{transform:scale(1.1);animation:none;}
.chat-fab-icon{font-size:1.3rem;}
.chat-badge{position:absolute;top:-4px;right:-4px;width:18px;height:18px;border-radius:50%;background:#4ade80;border:2px solid var(--navy);display:flex;align-items:center;justify-content:center;font-size:.46rem;font-weight:900;color:var(--navy);}
@keyframes chatPulse{0%,100%{box-shadow:0 8px 26px rgba(240,90,40,.4);}50%{box-shadow:0 8px 36px rgba(240,90,40,.65),0 0 0 7px rgba(240,90,40,.09);}}
.cwin{position:fixed;bottom:6.2rem;right:2rem;z-index:400;width:360px;height:530px;background:var(--navy2);border:1px solid rgba(240,90,40,.2);border-radius:20px;display:none;flex-direction:column;box-shadow:0 24px 60px rgba(0,0,0,.55);overflow:hidden;}
.cwin.open{display:flex;animation:chatSlide .28s ease;}
@keyframes chatSlide{from{opacity:0;transform:translateY(14px) scale(.96);}to{opacity:1;transform:none;}}
.chat-hdr{padding:.85rem 1rem;display:flex;align-items:center;gap:.65rem;background:linear-gradient(135deg,rgba(240,90,40,.12),rgba(240,90,40,.04));border-bottom:1px solid rgba(255,255,255,.05);flex-shrink:0;}
.chat-av{width:34px;height:34px;border-radius:10px;background:var(--orange);display:flex;align-items:center;justify-content:center;font-weight:900;font-size:.76rem;flex-shrink:0;color:#fff;font-family:'Syne',sans-serif;}
.chat-av-name{font-weight:750;font-size:.84rem;}
.chat-av-status{font-size:.62rem;color:#4ade80;display:flex;align-items:center;gap:.26rem;}
.chat-av-status::before{content:'';width:5px;height:5px;border-radius:50%;background:#4ade80;}
.cclose{background:none;border:none;color:var(--muted);cursor:pointer;font-size:1rem;padding:.1rem;transition:color .2s;margin-left:auto;}
.cclose:hover{color:#fff;}
.cmsgs{flex:1;overflow-y:auto;padding:.85rem;display:flex;flex-direction:column;gap:.65rem;}
.cmsgs::-webkit-scrollbar{width:3px;}
.cmsgs::-webkit-scrollbar-track{background:transparent;}
.cmsgs::-webkit-scrollbar-thumb{background:rgba(255,255,255,.1);border-radius:3px;}
.cmsg{display:flex;gap:.45rem;align-items:flex-end;}
.cmsg.user{flex-direction:row-reverse;}
.cbubble{padding:.58rem .84rem;border-radius:13px;font-size:.77rem;line-height:1.6;max-width:82%;word-break:break-word;}
.cmsg.bot .cbubble{background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.07);color:#e2e8f0;border-radius:13px 13px 13px 3px;}
.cmsg.user .cbubble{background:var(--orange);color:#fff;border-radius:13px 13px 3px 13px;}
.cdot{width:26px;height:26px;border-radius:8px;background:var(--orange);display:flex;align-items:center;justify-content:center;font-size:.58rem;font-weight:900;flex-shrink:0;font-family:'Syne',sans-serif;}
.cmsg.user .cdot{background:rgba(255,255,255,.08);}
.cquick{padding:.4rem .85rem;display:flex;gap:.28rem;flex-wrap:wrap;border-top:1px solid rgba(255,255,255,.05);}
.cqbtn{background:rgba(240,90,40,.09);border:1px solid rgba(240,90,40,.2);color:var(--orange);padding:.26rem .65rem;border-radius:8px;font-size:.63rem;cursor:pointer;font-family:'Outfit',sans-serif;font-weight:600;transition:all .2s;white-space:nowrap;}
.cqbtn:hover{background:rgba(240,90,40,.18);}
.cinput-row{padding:.75rem .85rem;display:flex;gap:.45rem;border-top:1px solid rgba(255,255,255,.06);flex-shrink:0;background:rgba(8,14,31,.5);}
.cinput{flex:1;background:rgba(255,255,255,.07);border:1px solid rgba(255,255,255,.08);border-radius:10px;padding:.52rem .9rem;color:#fff;font-family:'Outfit',sans-serif;font-size:.77rem;outline:none;transition:border-color .2s;}
.cinput:focus{border-color:rgba(240,90,40,.45);}
.csend{width:34px;height:34px;border-radius:9px;background:var(--orange);border:none;color:#fff;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:.85rem;flex-shrink:0;transition:background .2s;}
.csend:hover{background:var(--orange2);}
.typing-dots span{display:inline-block;width:5px;height:5px;border-radius:50%;background:#94a3b8;margin:0 1px;animation:dot 1.2s infinite;}
.typing-dots span:nth-child(2){animation-delay:.2s;}
.typing-dots span:nth-child(3){animation-delay:.4s;}
@keyframes dot{0%,80%,100%{opacity:.2;}40%{opacity:1;}}

/* ============ FOOTER ============ */
footer{padding:1.2rem 2.5rem;border-top:1px solid rgba(255,255,255,.05);display:flex;justify-content:space-between;align-items:center;color:var(--muted);font-size:.71rem;}

/* ============ RESPONSIVE ============ */
@media(max-width:1200px){
  .hero{grid-template-columns:1fr;padding:78px 1.5rem 2rem;gap:2rem;justify-items:center;}
  .hero-left{width:100%;max-width:500px;}
  .hero-right{width:100%;max-width:500px;text-align:left;}
  .hero-center{order:-1;}
  .profile-follow{width:300px;}
}
@media(max-width:900px){
  .stats-grid{grid-template-columns:repeat(3,1fr);}
  .growth-kpi-grid{grid-template-columns:repeat(2,1fr);}
  .cert-hero-stats{grid-template-columns:1fr;}
  .about-grid{grid-template-columns:1fr;gap:1.5rem;}
}
@media(max-width:600px){
  nav{padding:0 .85rem;flex-wrap:wrap;height:auto;gap:.25rem;padding-bottom:.35rem;}
  .nav-tabs{order:3;width:100%;margin:0;}
  .nav-actions{order:2;}
  .stats-grid{grid-template-columns:repeat(2,1fr);}
  .form-grid{grid-template-columns:1fr;}
  .form-grid .full{grid-column:1;}
  .cwin{width:calc(100vw - 1.5rem);right:.75rem;bottom:5rem;}
  .sec{padding:3.5rem 1.2rem 2.5rem;}
  .stats-sec,.home-market-sec,.contact-section{padding-left:1.2rem;padding-right:1.2rem;}
  footer{flex-direction:column;gap:.3rem;text-align:center;padding:1rem;}
}
</style>
</head>
<body>

<!-- LOGIN MODAL -->
<div class="login-overlay" id="loginModal">
  <div class="login-box">
    <button class="login-xbtn" onclick="closeLogin()">✕</button>
    <div class="login-logo">AK</div>
    <div class="login-title">Admin Login</div>
    <div class="login-sub">Enter credentials to unlock edit mode</div>
    <div class="login-err" id="loginErr">❌ Incorrect ID or Password</div>
    <div class="lf"><label>User ID</label><span class="lf-icon">👤</span><input type="text" id="lid" placeholder="Akash7566" autocomplete="off" onkeydown="if(event.key==='Enter')doLogin()"></div>
    <div class="lf"><label>Password</label><span class="lf-icon">🔒</span><input type="password" id="lpwd" placeholder="••••••••" onkeydown="if(event.key==='Enter')doLogin()"></div>
    <button class="login-btn" onclick="doLogin()">🔓 Unlock Edit Mode</button>
  </div>
</div>

<div class="edit-banner" id="editBanner"><div class="edit-dot"></div><span>✏️ Edit Mode Active — Click highlighted text to edit</span></div>
<div class="lb" id="lightbox" onclick="if(event.target===this)closeLB()"><div class="lb-inner"><button class="lb-close" onclick="closeLB()">✕</button><img id="lb-img" src="" alt=""></div></div>
<div class="toast" id="toast"></div>

<!-- NAV -->
<nav>
  <div class="nav-brand">
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
    <button class="btn-edit" id="editBtn" onclick="handleEditBtn()">🔒 Edit</button>
    <button class="btn-resume" onclick="showToast('📄 Resume download coming soon!')">⬇ Resume</button>
  </div>
</nav>

<!-- ========== HOME PAGE ========== -->
<div class="page active" id="page-home">

  <div class="hero">
    <!-- LEFT: Quick Info + Follow -->
    <div class="hero-left">
      <div class="info-panel">
        <div class="info-panel-title">Quick Info</div>
        <a class="info-item" href="mailto:akashkoyrav7566@gmail.com">
          <div class="info-icon">📧</div>
          <div class="info-text"><div class="info-label">Email</div><div class="info-value"><span class="editable" id="info-email" contenteditable="false">akashkoyrav7566@gmail.com</span></div></div>
        </a>
        <a class="info-item" href="tel:+917509762086">
          <div class="info-icon">📱</div>
          <div class="info-text"><div class="info-label">Mobile</div><div class="info-value"><span class="editable" id="info-mobile" contenteditable="false">+91 75097 62086</span></div></div>
        </a>
        <a class="info-item" href="https://wa.me/917509762086" target="_blank">
          <div class="info-icon">💬</div>
          <div class="info-text"><div class="info-label">WhatsApp</div><div class="info-value">+91 75097 62086</div></div>
        </a>
        <a class="info-item" href="https://linkedin.com/in/akashkourav" target="_blank">
          <div class="info-icon">🔗</div>
          <div class="info-text"><div class="info-label">LinkedIn</div><div class="info-value"><span class="editable" id="info-li" contenteditable="false">linkedin.com/in/akashkourav</span></div></div>
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
          <div class="info-text"><div class="info-label">Experience</div><div class="info-value"><span class="editable" id="info-exp" contenteditable="false">2+ Years BI Analytics</span></div></div>
        </div>
        <div class="avail-badge"><div class="avail-dot"></div>Available for Hire</div>
      </div>

      <div class="follow-row">
        <span class="follow-label">Follow me:</span>
        <div class="socials">
          <a href="https://linkedin.com/in/akashkourav" target="_blank" class="soc soc-li">in</a>
          <a href="https://github.com/akashkourav" target="_blank" class="soc soc-gh">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="white"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0 1.5 3.78c.1.85.34 2.75-.5 6.23"/></svg>
          </a>
          <a href="mailto:akashkoyrav7566@gmail.com" class="soc soc-em">✉</a>
          <a href="https://wa.me/917509762086" target="_blank" class="soc soc-wa">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="white"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 0 1-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 0 1-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 0 1 2.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0 0 12.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 0 0 5.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 0 0-3.48-8.413z"/></svg>
          </a>
        </div>
      </div>
    </div>

    <!-- CENTER: Profile + Follow -->
    <div class="hero-center">
      <div class="profile-outer">
        <div class="ring-outer"></div>
        <div class="ring-inner"></div>
        <div class="profile-circle" onclick="guardedAction(openProfileUpload)">
          <img id="profileImg" src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect fill='%23f05a28' width='100' height='100'/%3E%3Ctext x='50' y='50' font-size='38' font-weight='bold' fill='white' text-anchor='middle' dy='0.35em' font-family='sans-serif'%3EAK%3C/text%3E%3C/svg%3E" alt="Akash Kourav">
        </div>
        <div class="cam-btn" onclick="guardedAction(openProfileUpload)">📷</div>
        <div class="metric m1"><div class="metric-val">50+</div><div class="metric-lbl">Dashboards</div></div>
        <div class="metric m2"><div class="metric-val">2+</div><div class="metric-lbl">Years Exp</div></div>
        <div class="metric m3"><div class="metric-val">⭐5.0</div><div class="metric-lbl">Rating</div></div>
      </div>

      <!-- Follow Below Profile -->
      <div class="profile-follow">
        <span class="profile-follow-label">Connect:</span>
        <div class="profile-follow-socials">
          <a href="https://linkedin.com/in/akashkourav" target="_blank" class="pf-soc" style="background:#0077b5;">in</a>
          <a href="https://github.com/akashkourav" target="_blank" class="pf-soc" style="background:#24292e;">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="white"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0 1.5 3.78c.1.85.34 2.75-.5 6.23"/></svg>
          </a>
          <a href="mailto:akashkoyrav7566@gmail.com" class="pf-soc" style="background:var(--orange);">✉</a>
          <a href="https://wa.me/917509762086" target="_blank" class="pf-soc" style="background:#25d366;">
            <svg width="13" height="13" viewBox="0 0 24 24" fill="white"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 0 1-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 0 1-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 0 1 2.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0 0 12.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 0 0 5.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 0 0-3.48-8.413z"/></svg>
          </a>
        </div>
      </div>
    </div>

    <!-- RIGHT: Name, role, stats, CTAs -->
    <div class="hero-right">
      <p class="hero-eyebrow">Hello, I'm</p>
      <h1 class="hero-name"><span class="editable" id="info-name" contenteditable="false">Akash Kourav</span></h1>
      <p class="hero-role"><span class="editable" id="info-role" contenteditable="false">Power BI Developer & BI Analyst</span></p>
      <p class="hero-desc"><span class="editable" id="info-desc" contenteditable="false">Transforming raw data into powerful insights that drive smarter business decisions. Specializing in interactive dashboards, ETL pipelines, and data storytelling across industries.</span></p>

      <div class="hero-stats-mini">
        <div class="hstat"><span class="hstat-icon">📊</span><div><div class="hstat-val">50+</div><div class="hstat-lbl">Dashboards Built</div></div></div>
        <div class="hstat"><span class="hstat-icon">⚡</span><div><div class="hstat-val">40%</div><div class="hstat-lbl">Time Saved</div></div></div>
        <div class="hstat"><span class="hstat-icon">💰</span><div><div class="hstat-val">30%</div><div class="hstat-lbl">Cost Reduction</div></div></div>
        <div class="hstat"><span class="hstat-icon">🏆</span><div><div class="hstat-val">5+</div><div class="hstat-lbl">Certifications</div></div></div>
      </div>

      <div class="hero-ctas">
        <button onclick="showPage('projects',document.querySelectorAll('.nav-tab')[3])" class="btn-primary">Discover My Work →</button>
        <button onclick="scrollToContact()" class="btn-secondary">📩 Hire Me</button>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-sec">
    <div class="stats-title">
      <h3>What I Bring To The Table</h3>
      <p>Proven expertise delivering measurable business impact through data intelligence</p>
    </div>
    <div class="stats-grid">
      <div class="scard"><span class="scard-icon">📊</span><div class="scard-val">50+</div><div class="scard-label">Dashboards</div><div class="scard-desc">Power BI & Tableau interactive reports</div></div>
      <div class="scard"><span class="scard-icon">⚡</span><div class="scard-val">40%</div><div class="scard-label">Time Saved</div><div class="scard-desc">Automated data pipelines & ETL</div></div>
      <div class="scard"><span class="scard-icon">💰</span><div class="scard-val">30%</div><div class="scard-label">Cost Savings</div><div class="scard-desc">Operational efficiency gains</div></div>
      <div class="scard"><span class="scard-icon">🎯</span><div class="scard-val">100%</div><div class="scard-label">Accuracy</div><div class="scard-desc">SQL-optimized data integrity</div></div>
      <div class="scard"><span class="scard-icon">🏆</span><div class="scard-val">5+</div><div class="scard-label">Certifications</div><div class="scard-desc">Microsoft, Google, Tableau</div></div>
    </div>

    <div class="hero-visual-wrap">
      <p class="visual-section-title">Skills Proficiency Overview</p>
      <div class="radar-wrap"><canvas id="radarChart" style="max-width:260px;max-height:260px;"></canvas></div>
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

  <!-- MARKET UPDATES -->
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
        <div class="form-grid">
          <div class="fg-contact"><label>Your Name</label><span class="fi">👤</span><input type="text" id="f-name" placeholder="John Doe"></div>
          <div class="fg-contact"><label>Mobile Number</label><span class="fi">📱</span><input type="tel" id="f-mobile" placeholder="+91 98765 43210"></div>
          <div class="fg-contact"><label>Email Address</label><span class="fi">📧</span><input type="email" id="f-email" placeholder="you@company.com"></div>
          <div class="fg-contact no-icon"><label>Purpose of Connect</label>
            <select id="f-purpose"><option value="" disabled selected>Select purpose...</option><option>Full-time Hire</option><option>Freelance / Project</option><option>Collaboration</option><option>Mentorship</option><option>Networking</option><option>Other</option></select>
          </div>
          <div class="fg-contact full no-icon"><label>Message / Description</label><textarea id="f-desc" placeholder="Tell me about your project or requirement..."></textarea></div>
          <div class="full"><button class="form-submit" id="formSubmitBtn" onclick="handleFormSubmit()">🚀 Send Message</button></div>
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
        <h3 style="font-size:1.05rem;margin-bottom:.75rem;font-family:'Syne',sans-serif;">Hi, I'm Akash 👋</h3>
        <p>Power BI Developer & BI Analyst based in Mumbai, India. I specialize in designing interactive dashboards, building data pipelines, and translating complex datasets into clear, actionable insights that decision-makers can actually use.</p>
        <p>My work sits at the intersection of analytics, visualization, and business strategy — helping organizations make smarter, faster decisions backed by real data. I've delivered 50+ dashboards across sales, operations, and customer analytics domains.</p>
        <p>Currently open to full-time roles, freelance projects, and exciting collaborations in the BI & Analytics space.</p>
        <div class="chips">
          <span class="chip">📍 Mumbai, India</span>
          <span class="chip">💼 BI Analyst</span>
          <span class="chip">🎓 B.Tech CS</span>
          <span class="chip">⚡ Available Now</span>
          <span class="chip">📊 Power BI Expert</span>
          <span class="chip">🐍 Python</span>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- SKILLS -->
<div class="page" id="page-skills">
  <section class="sec">
    <p class="sec-label">Skills</p><h2>Technical Expertise</h2><div class="sec-bar"></div>
    <div class="skills-grid">
      <div class="sk"><div class="sk-icon">📊</div><div class="sk-title">BI & Visualization</div><div class="tags"><span class="tag h">Power BI</span><span class="tag h">Tableau</span><span class="tag">Looker Studio</span><span class="tag">DAX</span></div></div>
      <div class="sk"><div class="sk-icon">🗄️</div><div class="sk-title">Database & SQL</div><div class="tags"><span class="tag h">SQL</span><span class="tag h">MySQL</span><span class="tag">BigQuery</span><span class="tag">PostgreSQL</span></div></div>
      <div class="sk"><div class="sk-icon">🐍</div><div class="sk-title">Programming</div><div class="tags"><span class="tag h">Python</span><span class="tag">Pandas</span><span class="tag">NumPy</span><span class="tag">Matplotlib</span></div></div>
      <div class="sk"><div class="sk-icon">⚙️</div><div class="sk-title">Data Engineering</div><div class="tags"><span class="tag h">ETL Pipelines</span><span class="tag">Data Modeling</span><span class="tag">KPI Design</span></div></div>
      <div class="sk"><div class="sk-icon">☁️</div><div class="sk-title">Cloud & Platforms</div><div class="tags"><span class="tag">Azure</span><span class="tag">Google Cloud</span><span class="tag">MS Fabric</span></div></div>
      <div class="sk"><div class="sk-icon">🤝</div><div class="sk-title">Soft Skills</div><div class="tags"><span class="tag h">Data Storytelling</span><span class="tag">Stakeholder Mgmt</span><span class="tag">Agile</span></div></div>
    </div>
  </section>
</div>

<!-- PROJECTS -->
<div class="page" id="page-projects">
  <section class="sec">
    <p class="sec-label">Work</p><h2>Featured Projects</h2><div class="sec-bar"></div>
    <div class="projects-grid">
      <div class="proj"><div class="proj-type">Power BI · DAX · SQL</div><div class="proj-title">Executive Sales Dashboard</div><p class="proj-desc">Multi-page Power BI dashboard for 3 regions. Drill-through from KPIs to rep-level performance. Reduced reporting time by 6 hrs/week.</p></div>
      <div class="proj"><div class="proj-type">Python · ETL · Automation</div><div class="proj-title">Automated Reporting Pipeline</div><p class="proj-desc">Python ETL replacing 8 hours/week of manual reporting with a fully automated scheduled pipeline. Zero manual intervention needed.</p></div>
      <div class="proj"><div class="proj-type">Tableau · Data Modeling</div><div class="proj-title">Customer Churn Analysis</div><p class="proj-desc">Tableau story with predictive churn indicators helping identify at-risk customers. Reduced churn rate by 15% in 2 quarters.</p></div>
      <div class="proj"><div class="proj-type">BigQuery · Looker Studio</div><div class="proj-title">Operations Performance Tracker</div><p class="proj-desc">Real-time ops tracker monitoring SLA compliance, team productivity metrics, and escalation trends across 5 departments.</p></div>
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
          <div class="exp-company">🏢 XYZ Analytics, Mumbai</div>
          <ul class="exp-bullets">
            <li>Designed 15+ Power BI dashboards for C-suite stakeholders, replacing legacy Excel reports</li>
            <li>Built Python ETL pipelines reducing manual reporting effort by 40% across 3 departments</li>
            <li>Optimized SQL queries improving dashboard load times by 60% via indexing & query restructuring</li>
            <li>Delivered automated weekly MIS reports saving 8+ hours of analyst time per week</li>
          </ul>
        </div>
      </div>
      <div class="exp-item">
        <div class="exp-dot">📊</div>
        <div class="exp-card">
          <div class="exp-header"><div class="exp-title">Data Analyst Intern</div><div class="exp-period">2022 – 2023</div></div>
          <div class="exp-company">🏢 ABC Solutions, Mumbai</div>
          <ul class="exp-bullets">
            <li>Developed Tableau dashboards for real-time sales tracking across 4 product lines</li>
            <li>Performed EDA on large customer datasets (500K+ rows) using Python & SQL</li>
            <li>Created automated Excel MIS reports streamlining monthly reporting for management</li>
          </ul>
        </div>
      </div>
      <div class="exp-item">
        <div class="exp-dot">🎓</div>
        <div class="exp-card">
          <div class="exp-header"><div class="exp-title">B.Tech — Computer Science</div><div class="exp-period">2018 – 2022</div></div>
          <div class="exp-company">🏛️ University of Mumbai</div>
          <ul class="exp-bullets">
            <li>Focused on databases, data structures, algorithms & software engineering principles</li>
            <li>Final year project: Power BI analytics platform for academic performance tracking</li>
          </ul>
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
    <div class="growth-kpi-grid">
      <div class="gkpi"><div class="gkpi-icon">🛠️</div><div class="gkpi-val">12</div><div class="gkpi-label">Skills Mastered</div><div class="gkpi-badge up">▲ +20% vs last year</div><div class="gkpi-sub">10 skills (2024) → 12 (2025)</div></div>
      <div class="gkpi"><div class="gkpi-icon">🎓</div><div class="gkpi-val">5</div><div class="gkpi-label">Certifications Earned</div><div class="gkpi-badge up">▲ +25% vs last year</div><div class="gkpi-sub">4 certs (2024) → 5 (2025)</div></div>
      <div class="gkpi"><div class="gkpi-icon">⚡</div><div class="gkpi-val">60%</div><div class="gkpi-label">Time Saved</div><div class="gkpi-badge up">▲ +50% vs last year</div><div class="gkpi-sub">40% (2024) → 60% (2025)</div></div>
      <div class="gkpi"><div class="gkpi-icon">💰</div><div class="gkpi-val">30%</div><div class="gkpi-label">Cost Savings</div><div class="gkpi-badge up">▲ +20% vs last year</div><div class="gkpi-sub">25% (2024) → 30% (2025)</div></div>
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

<!-- CERTS — ENHANCED -->
<div class="page" id="page-certs">
  <section class="sec">
    <p class="sec-label">Credentials</p>
    <h2>Certifications</h2>
    <div class="sec-bar"></div>

    <!-- HERO STATS -->
    <div class="cert-hero-stats">
      <div class="cert-hero-stat">
        <div class="cert-stat-icon">🏆</div>
        <div class="cert-stat-val">5</div>
        <div class="cert-stat-label">Total Certifications</div>
        <div class="cert-stat-sub">Verified credentials from Microsoft, Google & Tableau</div>
      </div>
      <div class="cert-hero-stat">
        <div class="cert-stat-icon">🛠️</div>
        <div class="cert-stat-val">12</div>
        <div class="cert-stat-label">Skills Acquired</div>
        <div class="cert-stat-sub">From Power BI to Cloud to Python via structured learning</div>
      </div>
      <div class="cert-hero-stat">
        <div class="cert-stat-icon">🌐</div>
        <div class="cert-stat-val">3</div>
        <div class="cert-stat-label">Platforms Certified</div>
        <div class="cert-stat-sub">Microsoft · Google · Tableau / Cisco</div>
      </div>
    </div>

    <!-- SKILLS CHIPS -->
    <div class="skills-learned-wrap">
      <div class="skills-learned-hdr">
        <div class="skills-learned-title">Skills Learned via Certifications</div>
        <div class="skills-learned-count">12 skills</div>
      </div>
      <div class="skills-learned-chips">
        <span class="sl-chip hot">Power BI</span><span class="sl-chip hot">DAX</span><span class="sl-chip hot">Data Modeling</span>
        <span class="sl-chip">SQL</span><span class="sl-chip">Python</span><span class="sl-chip hot">Tableau</span>
        <span class="sl-chip">BigQuery</span><span class="sl-chip">Google Analytics</span><span class="sl-chip">ETL Pipelines</span>
        <span class="sl-chip">Azure Fundamentals</span><span class="sl-chip">Data Storytelling</span><span class="sl-chip">KPI Design</span>
      </div>
    </div>

    <div class="certs-grid">
      <div class="cert-card">
        <div class="cert-card-badge">2024</div>
        <div class="cert-wrap"><div class="cert-placeholder"><div class="cert-emoji">🪟</div><div>Microsoft Certified</div></div></div>
        <div class="cert-body"><div class="cert-org">🏢 Microsoft</div><div class="cert-name">PL-300: Power BI Data Analyst</div><div class="cert-meta"><span class="cert-year">✦ Jan 2024</span><span class="cert-level">Expert</span></div></div>
      </div>
      <div class="cert-card">
        <div class="cert-card-badge">2023</div>
        <div class="cert-wrap"><div class="cert-placeholder"><div class="cert-emoji">🔍</div><div>Google Certified</div></div></div>
        <div class="cert-body"><div class="cert-org">🏢 Google</div><div class="cert-name">Data Analytics Professional Certificate</div><div class="cert-meta"><span class="cert-year">✦ Jun 2023</span><span class="cert-level">Professional</span></div></div>
      </div>
      <div class="cert-card">
        <div class="cert-card-badge">2023</div>
        <div class="cert-wrap"><div class="cert-placeholder"><div class="cert-emoji">📊</div><div>Tableau Certified</div></div></div>
        <div class="cert-body"><div class="cert-org">🏢 Tableau / Salesforce</div><div class="cert-name">Tableau Desktop Specialist</div><div class="cert-meta"><span class="cert-year">✦ Mar 2023</span><span class="cert-level">Specialist</span></div></div>
      </div>
      <div class="cert-card">
        <div class="cert-card-badge">2022</div>
        <div class="cert-wrap"><div class="cert-placeholder"><div class="cert-emoji">☁️</div><div>Azure Certified</div></div></div>
        <div class="cert-body"><div class="cert-org">🏢 Microsoft</div><div class="cert-name">AZ-900: Azure Fundamentals</div><div class="cert-meta"><span class="cert-year">✦ Sep 2022</span><span class="cert-level">Foundational</span></div></div>
      </div>
      <div class="cert-card">
        <div class="cert-card-badge">2022</div>
        <div class="cert-wrap"><div class="cert-placeholder"><div class="cert-emoji">🐍</div><div>Cisco NetAcad</div></div></div>
        <div class="cert-body"><div class="cert-org">🏢 Cisco / NetAcad</div><div class="cert-name">Python Essentials 1 & 2</div><div class="cert-meta"><span class="cert-year">✦ Apr 2022</span><span class="cert-level">Intermediate</span></div></div>
      </div>
      <div class="add-cert" onclick="guardedAction(()=>showToast('Enter edit mode to add certifications'))">
        <span style="font-size:1.5rem;">＋</span><div>Add Certification</div>
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
        <div class="award-body"><div class="award-badge">🏆 Recognition</div><div class="award-title">Star Performer Award</div><div class="award-desc">Outstanding contribution to the BI team in Q3 2024. Delivered 5 dashboards ahead of schedule.</div></div>
      </div>
      <div class="award-card">
        <div class="award-wrap"><div class="award-placeholder"><span style="font-size:2rem">🌟</span><div>Client Appreciation</div></div></div>
        <div class="award-body"><div class="award-badge">🌟 Appreciation</div><div class="award-title">Client Appreciation Letter</div><div class="award-desc">Excellent delivery of executive dashboard project with zero revisions requested by the client.</div></div>
      </div>
      <div class="add-award" onclick="guardedAction(()=>showToast('Enter edit mode to add awards'))">
        <span style="font-size:1.5rem;">＋</span><div>Add Award</div>
      </div>
    </div>
  </section>
</div>

<footer>
  <span>© 2025 Akash Kourav — BI Analyst & Power BI Developer · Mumbai, India</span>
  <span style="color:rgba(255,255,255,.07)">Built with precision & purpose</span>
</footer>

<!-- CHATBOT -->
<button class="chat-fab" id="chatFab" onclick="toggleChat()">
  <span class="chat-fab-icon">💬</span>
  <div class="chat-badge">AI</div>
</button>
<div class="cwin" id="chatWin">
  <div class="chat-hdr">
    <div class="chat-av">AK</div>
    <div><div class="chat-av-name">Akash's AI Assistant</div><div class="chat-av-status">Online now</div></div>
    <button class="cclose" onclick="toggleChat()">✕</button>
  </div>
  <div class="cmsgs" id="cmsgs">
    <div class="cmsg bot"><div class="cdot">AK</div><div class="cbubble">Hi there! 👋 I'm Akash's AI assistant. Ask me anything about his skills, projects, experience, certifications, or how to hire him!</div></div>
  </div>
  <div class="cquick">
    <button class="cqbtn" onclick="quickAsk('What are Akash\'s main skills?')">🛠 Skills</button>
    <button class="cqbtn" onclick="quickAsk('Tell me about Akash\'s projects')">💼 Work</button>
    <button class="cqbtn" onclick="quickAsk('What certifications does Akash have?')">🎓 Certs</button>
    <button class="cqbtn" onclick="quickAsk('How can I connect with Akash?')">🔗 Connect</button>
    <button class="cqbtn" onclick="quickAsk('I want to hire Akash')">📩 Hire</button>
  </div>
  <div class="cinput-row">
    <input class="cinput" id="chatIn" type="text" placeholder="Ask anything about Akash..." onkeydown="if(event.key==='Enter')sendChat()">
    <button class="csend" onclick="sendChat()">➤</button>
  </div>
</div>

<input type="file" id="profileFileInput" accept="image/*" style="display:none" onchange="handleProfileUpload(event)">

<script>
const ADMIN_ID='Akash7566', ADMIN_PWD='Aman7566';
const OWNER_EMAIL='akashkoyrav7566@gmail.com';
const OWNER_WHATSAPP='+917509762086';
let isEdit=false,chatOpen=false,marketLoaded=false,homeMarketLoaded=false;

// ============ COMPREHENSIVE KB ============
const KB={
  name:`Akash Kourav`,
  role:`Power BI Developer & BI Analyst based in Mumbai, India`,
  email:`akashkoyrav7566@gmail.com`,
  phone:`+91 75097 62086`,
  whatsapp:`+91 75097 62086`,
  linkedin:`linkedin.com/in/akashkourav`,
  location:`Mumbai, India`,
  education:`B.Tech in Computer Science from University of Mumbai (2018–2022)`,
  experience_years:`2+`,

  about:`Akash Kourav is a Power BI Developer & BI Analyst based in Mumbai, India with 2+ years of experience. He specializes in designing interactive dashboards, building data pipelines, and translating complex datasets into clear, actionable insights for decision-makers. He is currently available for full-time roles, freelance projects, and collaborations.`,

  skills:`Akash's core skills:
• Power BI & DAX — Expert (95%)
• SQL / MySQL — Advanced (90%)
• Tableau — Advanced (85%)
• Data Modeling — Advanced (88%)
• Python (Pandas, NumPy) — Intermediate (80%)
• ETL Pipelines — Advanced
• BigQuery & Looker Studio — Intermediate
• Azure / Google Cloud / Microsoft Fabric — Intermediate (70%)
• Data Storytelling & Stakeholder Management`,

  projects:`Akash's key projects:
1. 📊 Executive Sales Dashboard — Multi-page Power BI with drill-through for 3 regions; reduced reporting time by 6 hrs/week
2. ⚡ Automated Reporting Pipeline — Python ETL eliminating 8 hrs/week of manual reporting
3. 📉 Customer Churn Analysis — Tableau story with predictive churn indicators; reduced churn 15% in 2 quarters
4. 🏭 Operations Performance Tracker — Real-time BigQuery/Looker SLA dashboard across 5 departments`,

  certs:`Akash holds 5 certifications:
• 🪟 PL-300: Power BI Data Analyst (Microsoft, 2024) — Expert level
• 🔍 Google Data Analytics Professional Certificate (Google, 2023)
• 📊 Tableau Desktop Specialist (Tableau/Salesforce, 2023)
• ☁️ AZ-900: Azure Fundamentals (Microsoft, 2022)
• 🐍 Python Essentials 1 & 2 (Cisco/NetAcad, 2022)`,

  experience:`Work experience:
• 💼 Associate Analyst – BI at XYZ Analytics, Mumbai (2023–Present)
  - 15+ Power BI dashboards for C-suite stakeholders
  - Python ETL pipelines reducing manual effort by 40%
  - SQL optimization improving load times by 60%
  - Automated weekly MIS reports saving 8+ hrs/week

• 📊 Data Analyst Intern at ABC Solutions, Mumbai (2022–2023)
  - Tableau dashboards for sales tracking (4 product lines)
  - EDA on 500K+ row customer datasets
  - Automated Excel MIS reports for management

• 🎓 B.Tech Computer Science, University of Mumbai (2018–2022)`,

  impact:`Key achievements & impact:
• 50+ dashboards built (Power BI & Tableau)
• 40% time saved via automation & ETL pipelines
• 30% cost savings delivered to clients
• 60% improvement in dashboard load times via SQL optimization
• 8+ hours/week saved through automated reporting
• 100% data accuracy maintained
• 5+ professional certifications earned`,

  awards:`Awards & Recognition:
• 🏆 Star Performer Award — Q3 2024 at XYZ Analytics for delivering 5 dashboards ahead of schedule
• 🌟 Client Appreciation Letter — For excellent delivery of executive dashboard with zero revisions`,

  hire:`To connect with or hire Akash:
📧 Email: akashkoyrav7566@gmail.com
📱 Phone / WhatsApp: +91 75097 62086
🔗 LinkedIn: linkedin.com/in/akashkourav
📍 Location: Mumbai, India

He's open to:
✅ Full-time BI / Data Analyst roles
✅ Freelance / contract projects
✅ Collaborations & partnerships
✅ Mentorship & networking

Would you like to open the contact form? Just say "yes" or "open contact form"!`,

  contact_form:`I'll open the "Get In Touch" form for you right now! You can fill in your details and Akash will respond within 24 hours. 📩`,
};

function getBotReply(msg){
  const m=msg.toLowerCase();

  // Contact form triggers
  if(m==='yes'||m.includes('open contact')||m.includes('get in touch')||m.includes('contact form')||m.includes('open form')){
    setTimeout(()=>{toggleChat();scrollToContact();},500);
    return KB.contact_form;
  }

  if(m.includes('skill')||m.includes('tool')||m.includes('technolog')||m.includes('proficien'))return KB.skills;
  if(m.includes('project')||m.includes('work')||m.includes('dashboard')||m.includes('built')||m.includes('portfolio'))return KB.projects;
  if(m.includes('cert')||m.includes('pl-300')||m.includes('credential')||m.includes('qualification'))return KB.certs;
  if(m.includes('award')||m.includes('recognition')||m.includes('appreciation')||m.includes('achiev'))return KB.awards;
  if(m.includes('hire')||m.includes('recruit')||m.includes('available')||m.includes('open to'))return KB.hire;
  if(m.includes('connect')||m.includes('contact')||m.includes('email')||m.includes('reach')||m.includes('whatsapp')||m.includes('phone')||m.includes('number'))return KB.hire;
  if(m.includes('experience')||m.includes('job')||m.includes('career')||m.includes('company')||m.includes('work at'))return KB.experience;
  if(m.includes('impact')||m.includes('result')||m.includes('saving')||m.includes('stat')||m.includes('number')||m.includes('metric'))return KB.impact;
  if(m.includes('hello')||m.includes('hi ')||m.includes('hey')||m===('hi')||m==='hello')return `Hi! 👋 I'm Akash's AI assistant. I can tell you about his skills, projects, certifications, experience, or how to hire him. What would you like to know?`;
  if(m.includes('location')||m.includes('where')||m.includes('mumbai')||m.includes('city'))return `Akash is based in Mumbai, India. He's available for remote work globally as well as on-site opportunities in Mumbai.`;
  if(m.includes('education')||m.includes('degree')||m.includes('btech')||m.includes('college')||m.includes('university'))return `${KB.education}. He focused on databases, data structures, and algorithms, with a final year project on a Power BI analytics platform.`;
  if(m.includes('about')||m.includes('who is')||m.includes('tell me about'))return KB.about;
  if(m.includes('name')||m.includes('role')||m.includes('position')||m.includes('designation'))return `${KB.name} is a ${KB.role}.`;

  return `Great question! I can help you with:\n• 🛠 Skills & technologies\n• 💼 Projects & portfolio\n• 🎓 Certifications\n• 📋 Work experience\n• 🏆 Awards\n• 📩 How to hire Akash\n\nWhat would you like to know?`;
}

// ============ EDIT MODE ============
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
  const btn=document.getElementById('editBtn');
  btn.className='btn-edit unlocked';btn.innerHTML='✏️ Exit Edit';
  document.querySelectorAll('.editable').forEach(e=>e.setAttribute('contenteditable','true'));
  showToast('✅ Edit Mode Active — click text to edit');
}
function logoutEdit(){
  isEdit=false;document.body.classList.remove('edit-mode');
  document.getElementById('editBanner').classList.remove('show');
  const btn=document.getElementById('editBtn');
  btn.className='btn-edit';btn.innerHTML='🔒 Edit';
  document.querySelectorAll('.editable').forEach(e=>e.setAttribute('contenteditable','false'));
  showToast('🔒 Edits Saved');
}
function guardedAction(fn){isEdit?fn():openLogin();}

// ============ NAVIGATION ============
function showPage(id,tab){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.nav-tab').forEach(t=>t.classList.remove('active'));
  document.getElementById('page-'+id).classList.add('active');
  if(tab&&tab.classList)tab.classList.add('active');
  window.scrollTo({top:0,behavior:'smooth'});
  if(id==='growth')setTimeout(initGrowthChart,120);
  if(id==='market'&&!marketLoaded)loadMarket();
}

// ============ TOAST ============
function showToast(msg,dur=3000){
  const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'),dur);
}

// ============ LIGHTBOX ============
function openLB(src){document.getElementById('lb-img').src=src;document.getElementById('lightbox').classList.add('open');}
function closeLB(){document.getElementById('lightbox').classList.remove('open');}

// ============ PROFILE UPLOAD ============
function openProfileUpload(){document.getElementById('profileFileInput').click();}
function handleProfileUpload(e){
  const f=e.target.files[0];if(!f)return;
  const r=new FileReader();r.onload=ev=>{document.getElementById('profileImg').src=ev.target.result;showToast('✅ Profile photo updated!');};r.readAsDataURL(f);
}

// ============ SCROLL TO CONTACT ============
function scrollToContact(){
  showPage('home',document.querySelector('.nav-tab'));
  setTimeout(()=>document.getElementById('contactSection').scrollIntoView({behavior:'smooth',block:'start'}),300);
}

// ============ CONTACT FORM ============
async function handleFormSubmit(){
  const name=document.getElementById('f-name').value.trim();
  const mobile=document.getElementById('f-mobile').value.trim();
  const email=document.getElementById('f-email').value.trim();
  const purpose=document.getElementById('f-purpose').value;
  const desc=document.getElementById('f-desc').value.trim();

  if(!name||!email||!purpose){showToast('⚠️ Please fill Name, Email & Purpose');return;}

  const btn=document.getElementById('formSubmitBtn');
  btn.disabled=true;btn.textContent='⏳ Sending...';

  // Prepare message content
  const msgBody=`New Contact Request from Portfolio:

Name: ${name}
Mobile: ${mobile||'Not provided'}
Email: ${email}
Purpose: ${purpose}
Message: ${desc||'No message'}

Sent from: Akash Kourav Portfolio`;

  // Send via EmailJS (free) or mailto fallback
  try{
    // Try mailto as primary method (opens email client)
    const mailtoLink=`mailto:${OWNER_EMAIL}?subject=Portfolio Contact: ${encodeURIComponent(purpose)} from ${encodeURIComponent(name)}&body=${encodeURIComponent(msgBody)}`;
    
    // Also prepare WhatsApp message
    const waMsg=`🔔 *New Portfolio Contact*\n\n*Name:* ${name}\n*Mobile:* ${mobile||'N/A'}\n*Email:* ${email}\n*Purpose:* ${purpose}\n*Message:* ${desc||'N/A'}`;
    const waLink=`https://wa.me/${OWNER_WHATSAPP.replace(/\D/g,'')}?text=${encodeURIComponent(waMsg)}`;

    // Open in background
    window.open(mailtoLink,'_blank');

    showToast('✅ Message sent! Akash will respond within 24 hours 🚀',4500);

    // Ask if they want WhatsApp too
    setTimeout(()=>{
      const confirmWa=confirm('Message sent via Email! 📧\n\nWould you also like to send via WhatsApp for faster response?');
      if(confirmWa)window.open(waLink,'_blank');
    },1000);

  }catch(err){
    showToast('⚠️ Please email akashkoyrav7566@gmail.com directly',5000);
  }

  // Clear form
  ['f-name','f-mobile','f-email','f-desc'].forEach(id=>{document.getElementById(id).value='';});
  document.getElementById('f-purpose').selectedIndex=0;
  btn.disabled=false;btn.textContent='🚀 Send Message';
}

// ============ CHATBOT ============
function toggleChat(){
  chatOpen=!chatOpen;
  const w=document.getElementById('chatWin');
  chatOpen?w.classList.add('open'):w.classList.remove('open');
}
function quickAsk(q){
  if(!chatOpen){chatOpen=true;document.getElementById('chatWin').classList.add('open');}
  document.getElementById('chatIn').value=q;sendChat();
}
function sendChat(){
  const inp=document.getElementById('chatIn'),msg=inp.value.trim();
  if(!msg)return;inp.value='';
  appendMsg('user',msg);
  const typingId='t'+Date.now();
  appendTyping(typingId);
  setTimeout(()=>{
    removeTyping(typingId);
    appendMsg('bot',getBotReply(msg));
  },500+Math.random()*350);
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
  d.appendChild(dot);d.appendChild(b);c.appendChild(d);c.scrollTop=c.scrollHeight;
}
function removeTyping(id){const el=document.getElementById(id);if(el)el.remove();}

// ============ RADAR CHART ============
function initRadarChart(){
  const ctx=document.getElementById('radarChart');if(!ctx)return;
  if(ctx._chartInstance){ctx._chartInstance.destroy();}
  ctx._chartInstance=new Chart(ctx,{
    type:'radar',
    data:{
      labels:['Power BI','SQL','Python','Tableau','Azure','Data Modeling'],
      datasets:[{
        label:'Proficiency',data:[95,90,80,85,70,88],
        backgroundColor:'rgba(240,90,40,.13)',borderColor:'#f05a28',borderWidth:2.5,
        pointBackgroundColor:'#f05a28',pointBorderColor:'#fff',pointBorderWidth:2,pointRadius:4,pointHoverRadius:6
      }]
    },
    options:{
      responsive:true,maintainAspectRatio:true,
      plugins:{legend:{display:false},tooltip:{callbacks:{label:c=>' '+c.raw+'%'}}},
      scales:{r:{min:0,max:100,ticks:{display:false,stepSize:20},
        grid:{color:'rgba(255,255,255,.06)'},angleLines:{color:'rgba(255,255,255,.06)'},
        pointLabels:{color:'#94a3b8',font:{size:10,family:'Outfit',weight:'600'}}
      }}
    }
  });
  setTimeout(()=>{document.querySelectorAll('.skill-bar-fill').forEach(bar=>{bar.style.width=bar.dataset.width;});},350);
}

// ============ GROWTH CHART ============
let growthChartInst=null;
function initGrowthChart(){
  const ctx=document.getElementById('growthChart');if(!ctx)return;
  if(growthChartInst){growthChartInst.destroy();}
  growthChartInst=new Chart(ctx,{
    type:'line',
    data:{
      labels:['2021','2022','2023','2024','2025'],
      datasets:[
        {label:'Skills Mastered',data:[2,5,8,10,12],borderColor:'#f05a28',backgroundColor:'rgba(240,90,40,.1)',borderWidth:2.5,fill:true,tension:.4,pointBackgroundColor:'#f05a28',pointRadius:4,pointHoverRadius:7},
        {label:'Certifications',data:[0,1,2,4,5],borderColor:'#22c55e',backgroundColor:'rgba(34,197,94,.08)',borderWidth:2.5,fill:true,tension:.4,pointBackgroundColor:'#22c55e',pointRadius:4,pointHoverRadius:7},
        {label:'% Time Saved',data:[0,5,15,40,60],borderColor:'#3b82f6',backgroundColor:'rgba(59,130,246,.08)',borderWidth:2.5,fill:true,tension:.4,pointBackgroundColor:'#3b82f6',pointRadius:4,pointHoverRadius:7},
        {label:'% Cost Savings',data:[0,3,10,25,30],borderColor:'#f59e0b',backgroundColor:'rgba(245,158,11,.07)',borderWidth:2.5,fill:true,tension:.4,pointBackgroundColor:'#f59e0b',pointRadius:4,pointHoverRadius:7}
      ]
    },
    options:{
      responsive:true,maintainAspectRatio:false,
      interaction:{mode:'index',intersect:false},
      plugins:{
        legend:{labels:{color:'#94a3b8',usePointStyle:true,pointStyle:'circle',padding:16,font:{family:'Outfit',size:11}}},
        tooltip:{backgroundColor:'rgba(8,14,31,.95)',borderColor:'rgba(240,90,40,.25)',borderWidth:1,titleColor:'#fff',bodyColor:'#94a3b8',padding:11,titleFont:{weight:'bold',family:'Outfit'}}
      },
      scales:{
        y:{ticks:{color:'#64748b',font:{size:10}},grid:{color:'rgba(255,255,255,.03)'},beginAtZero:true},
        x:{ticks:{color:'#64748b',font:{size:11}},grid:{color:'rgba(255,255,255,.03)'}}
      }
    }
  });
}

// ============ MARKET DATA ============
const FALLBACK_ARTICLES=[
  {category:'POWER BI',title:'Copilot in Power BI: AI-Powered Report Generation',summary:'Microsoft\'s Copilot reduces dashboard creation time by up to 50% with AI-generated insights and narratives.',url:'https://powerbi.microsoft.com/blog',date:'May 2025'},
  {category:'FABRIC',title:'Microsoft Fabric OneLake: Unified Data Lake Updates',summary:'New Fabric features simplify data engineering with a unified lakehouse architecture for all analytics workloads.',url:'https://learn.microsoft.com/en-us/fabric',date:'May 2025'},
  {category:'CLOUD',title:'Azure Synapse: Serverless SQL Pools Expansion',summary:'Enterprise adoption surges as serverless SQL pools become the new analytics standard in the cloud.',url:'https://azure.microsoft.com/blog',date:'May 2025'},
  {category:'AI & ML',title:'Azure AI Foundry: New Model APIs for Predictive Analytics',summary:'AI-skilled BI analysts increasingly in demand as Azure expands its ML and predictive modeling capabilities.',url:'https://azure.microsoft.com/en-us/products/ai-foundry',date:'May 2025'},
  {category:'POWER BI',title:'Power BI May 2025 Feature Update',summary:'New DAX improvements, incremental refresh enhancements and composite model updates shipped this month.',url:'https://powerbi.microsoft.com/blog',date:'May 2025'},
  {category:'AI & ML',title:'AI-Driven Data Storytelling Trends 2025',summary:'BI professionals integrating LLMs with dashboards for automated narrative generation — the next frontier.',url:'https://www.gartner.com/en/analytics',date:'May 2025'},
];
const catColors={'POWER BI':'#f05a28','FABRIC':'#a855f7','CLOUD':'#3b82f6','AI & ML':'#22c55e'};

function renderMarketInto(containerId,articles){
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
  const today=new Date().toDateString(),cacheKey='mkt_'+today;
  if(!force){const c=sessionStorage.getItem(cacheKey);if(c)return JSON.parse(c);}
  try{
    const res=await fetch('https://api.anthropic.com/v1/messages',{
      method:'POST',
      headers:{'Content-Type':'application/json','anthropic-version':'2023-06-01','anthropic-dangerous-direct-browser-access':'true'},
      body:JSON.stringify({
        model:'claude-sonnet-4-20250514',max_tokens:1200,
        tools:[{type:'web_search_20250305',name:'web_search'}],
        system:'Return ONLY a valid JSON array, no markdown, no preamble.',
        messages:[{role:'user',content:'Search for 6 latest news articles this week about Power BI updates, Microsoft Fabric, Azure cloud, AI/ML for data analytics. Return ONLY JSON array: [{"category":"POWER BI","title":"...","summary":"...","url":"https://...","date":"..."},...] Categories must be one of: POWER BI, FABRIC, CLOUD, AI & ML'}]
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
  renderMarketInto('marketFeed',articles);
  const feed=document.getElementById('marketFeed');
  const rb=document.createElement('button');
  rb.style.cssText='display:block;margin:1.5rem auto 0;background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.25);color:var(--orange);padding:.48rem 1.3rem;border-radius:8px;font-family:Outfit,sans-serif;font-size:.73rem;font-weight:700;cursor:pointer;';
  rb.textContent='🔄 Refresh Updates';
  rb.onclick=()=>{marketLoaded=false;loadMarket(true);};
  feed.appendChild(rb);
}

// ============ INIT ============
window.addEventListener('load',()=>{
  initRadarChart();
  loadHomeMarket();
});
</script>
</body>
</html>
