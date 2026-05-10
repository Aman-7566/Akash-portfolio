<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Akash Kourav — BI Analyst</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
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
nav{
  display:flex;align-items:center;justify-content:space-between;
  padding:1rem 4rem;position:fixed;top:0;left:0;right:0;z-index:300;
  background:rgba(15,22,41,0.95);backdrop-filter:blur(20px);
  border-bottom:1px solid rgba(255,255,255,0.06);
}
.nav-brand{display:flex;align-items:center;gap:.7rem;}
.nav-logo{width:40px;height:40px;border-radius:50%;background:var(--orange);display:flex;align-items:center;justify-content:center;font-weight:800;font-size:.85rem;color:#fff;flex-shrink:0;}
.nav-name{font-weight:700;font-size:1rem;}
.nav-tabs{display:flex;align-items:center;gap:.3rem;background:rgba(255,255,255,0.05);border:1px solid var(--border);border-radius:100px;padding:.3rem;}
.nav-tab{
  padding:.5rem 1.3rem;border-radius:100px;
  color:var(--muted);font-size:.82rem;font-weight:500;
  cursor:pointer;border:none;background:transparent;
  transition:all .25s;white-space:nowrap;
}
.nav-tab:hover{color:#fff;}
.nav-tab.active{background:var(--orange);color:#fff;}
.nav-actions{display:flex;align-items:center;gap:.8rem;}
.btn-resume{
  background:var(--orange);color:#fff;padding:.55rem 1.5rem;border-radius:100px;
  text-decoration:none;font-weight:600;font-size:.82rem;
  display:inline-flex;align-items:center;gap:.4rem;transition:background .2s,transform .2s;
  border:none;cursor:pointer;
}
.btn-resume:hover{background:var(--orange2);transform:translateY(-1px);}

/* PAGES */
.page{display:none;animation:fadeIn .4s ease;}
.page.active{display:block;}
@keyframes fadeIn{from{opacity:0;transform:translateY(16px);}to{opacity:1;transform:none;}}

/* ═══ HERO ═══ */
.hero{
  min-height:100vh;display:flex;align-items:center;
  padding:7rem 4rem 2rem;position:relative;overflow:hidden;gap:2rem;
  flex-wrap:wrap;
}
.deco1,.deco2{position:absolute;border-radius:50%;border:1px dashed rgba(255,255,255,0.055);pointer-events:none;}
.deco1{width:520px;height:520px;right:-100px;top:-80px;}
.deco2{width:320px;height:320px;left:-100px;bottom:-80px;}

/* Left: Name/title/desc */
.hero-left{flex:1;min-width:260px;max-width:420px;}
.hero-eyebrow{color:var(--muted);font-size:1.05rem;font-weight:400;margin-bottom:.15rem;}
.hero-name{color:var(--orange);font-size:clamp(2rem,4vw,3.4rem);font-weight:800;line-height:1.05;margin-bottom:.15rem;}
.hero-role{font-size:clamp(1.1rem,2vw,1.7rem);font-weight:700;margin-bottom:.9rem;}
.hero-desc{color:var(--muted);font-size:.87rem;font-weight:300;line-height:1.85;margin-bottom:1.3rem;}
.hero-ctas{display:flex;align-items:center;gap:1rem;margin-bottom:1.3rem;flex-wrap:wrap;}
.btn-dis{background:var(--orange);color:#fff;padding:.78rem 2rem;border-radius:100px;text-decoration:none;font-weight:600;font-size:.87rem;transition:background .2s,transform .2s;display:inline-block;border:none;cursor:pointer;}
.btn-dis:hover{background:var(--orange2);transform:translateY(-2px);}
.btn-circ{width:44px;height:44px;border-radius:50%;border:2px solid var(--orange);display:flex;align-items:center;justify-content:center;color:var(--orange);text-decoration:none;font-size:1rem;transition:all .2s;background:transparent;cursor:pointer;}
.btn-circ:hover{background:var(--orange);color:#fff;transform:scale(1.1);}
.follow-row{display:flex;align-items:center;gap:.8rem;font-size:.82rem;color:var(--muted);}
.socials{display:flex;gap:.45rem;}
.soc{width:33px;height:33px;border-radius:50%;display:flex;align-items:center;justify-content:center;text-decoration:none;font-weight:700;font-size:.7rem;transition:transform .2s;}
.soc:hover{transform:scale(1.15);}
.soc-li{background:#0077b5;color:#fff;}
.soc-gh{background:#24292e;color:#fff;}
.soc-em{background:var(--orange);color:#fff;}

/* Center: Profile circle */
.hero-center{display:flex;justify-content:center;align-items:center;position:relative;}
.pwrap{position:relative;width:310px;height:310px;}
.ring{position:absolute;inset:0;border-radius:50%;border:2px solid var(--orange);animation:spin 22s linear infinite;}
.pcircle{position:absolute;top:20px;left:20px;width:270px;height:270px;border-radius:50%;background:linear-gradient(145deg,#7a2d12,var(--orange));display:flex;align-items:center;justify-content:center;overflow:hidden;cursor:pointer;transition:opacity .3s;}
.pcircle:hover{opacity:0.8;}
.pimg{width:100%;height:100%;object-fit:cover;}
.profile-upload{position:absolute;bottom:4px;right:4px;width:44px;height:44px;background:var(--orange);border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:all .2s;box-shadow:0 4px 12px rgba(240,90,40,.3);z-index:2;}
.profile-upload:hover{background:var(--orange2);transform:scale(1.1);}
.profile-upload span{font-size:1.2rem;pointer-events:none;}
.fcard{position:absolute;background:rgba(10,15,35,.88);backdrop-filter:blur(12px);border:1px solid rgba(255,255,255,.13);border-radius:13px;padding:.7rem 1rem;text-align:center;min-width:105px;}
.fcard-num{font-size:1.5rem;font-weight:800;line-height:1;}
.fcard-lbl{font-size:.65rem;color:var(--muted);margin-top:2px;}
.fcard-stars{color:#f5a623;font-size:11px;margin-bottom:3px;}
.fc1{top:10px;right:-45px;animation:float1 3s ease-in-out infinite;}
.fc2{top:50%;left:-55px;animation:float2 3.5s ease-in-out .5s infinite;}
.fc3{bottom:20px;right:-20px;animation:float3 3s ease-in-out 1s infinite;}
@keyframes spin{to{transform:rotate(360deg);}}
@keyframes float1{0%,100%{transform:translateY(0);}50%{transform:translateY(-8px);}}
@keyframes float2{0%,100%{transform:translateY(-50%);}50%{transform:translateY(calc(-50% - 8px));}}
@keyframes float3{0%,100%{transform:translateY(0);}50%{transform:translateY(-7px);}}

/* Right: Info Panel */
.hero-right{flex:1;min-width:240px;max-width:310px;}
.info-panel{background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.09);border-radius:20px;padding:1.5rem;display:flex;flex-direction:column;gap:.85rem;}
.info-panel h3{font-size:.78rem;letter-spacing:.12em;text-transform:uppercase;color:var(--orange);margin-bottom:.2rem;}
.info-row{display:flex;align-items:flex-start;gap:.7rem;padding:.6rem .7rem;border-radius:10px;background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.06);transition:border-color .2s;}
.info-row:hover{border-color:rgba(240,90,40,.3);}
.info-icon{font-size:1.1rem;flex-shrink:0;margin-top:1px;}
.info-label{font-size:.65rem;color:var(--muted);line-height:1;margin-bottom:2px;}
.info-value{font-size:.8rem;font-weight:600;color:#fff;word-break:break-all;}
.info-value a{color:var(--orange);text-decoration:none;}
.info-value a:hover{text-decoration:underline;}
.avail-badge{display:inline-flex;align-items:center;gap:.4rem;background:rgba(34,197,94,.1);border:1px solid rgba(34,197,94,.3);color:#4ade80;padding:.35rem .8rem;border-radius:100px;font-size:.72rem;font-weight:600;margin-top:.3rem;}
.avail-badge::before{content:'';width:7px;height:7px;border-radius:50%;background:#4ade80;animation:pulse-green 1.5s infinite;}
@keyframes pulse-green{0%,100%{opacity:1;}50%{opacity:.4;}}

/* ═══ 3D STATS ROW ═══ */
.stats-showcase{
  padding:3.5rem 4rem;
  background:linear-gradient(135deg,rgba(240,90,40,.04),rgba(240,90,40,.01));
  border-top:1px solid rgba(240,90,40,.15);
  border-bottom:1px solid rgba(240,90,40,.15);
  overflow:hidden;
  position:relative;
}
.stats-showcase::before{
  content:'';position:absolute;inset:0;
  background:radial-gradient(ellipse 60% 80% at 50% 50%, rgba(240,90,40,.06), transparent);
  pointer-events:none;
}
.stats-title{text-align:center;margin-bottom:2.5rem;position:relative;}
.stats-title h3{font-size:1.3rem;font-weight:700;margin-bottom:.4rem;}
.stats-title p{color:var(--muted);font-size:.88rem;}
.stats-row{
  display:flex;gap:1.5rem;max-width:1200px;margin:0 auto;
  perspective:1000px;
  justify-content:center;
  flex-wrap:nowrap;overflow-x:auto;padding-bottom:.5rem;
}
.stat-card-3d{
  flex:1;min-width:180px;max-width:240px;
  background:linear-gradient(145deg,rgba(20,28,53,.95),rgba(26,35,64,.9));
  border:1px solid rgba(240,90,40,.2);border-radius:20px;
  padding:1.8rem 1.3rem;text-align:center;
  position:relative;overflow:hidden;cursor:default;
  transform:perspective(600px) rotateX(8deg) rotateY(0deg);
  transform-style:preserve-3d;
  transition:transform .4s ease,box-shadow .4s ease,border-color .4s;
  box-shadow:
    0 20px 40px rgba(0,0,0,.4),
    0 8px 16px rgba(0,0,0,.2),
    inset 0 1px 0 rgba(255,255,255,.07);
}
.stat-card-3d::before{
  content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--orange),transparent);
  opacity:.6;
}
.stat-card-3d::after{
  content:'';position:absolute;bottom:0;left:0;right:0;top:0;
  background:linear-gradient(135deg,rgba(255,255,255,.04) 0%,transparent 50%,rgba(240,90,40,.04) 100%);
  border-radius:20px;pointer-events:none;
}
.stat-card-3d:hover{
  transform:perspective(600px) rotateX(0deg) rotateY(0deg) translateY(-10px) scale(1.04);
  border-color:rgba(240,90,40,.6);
  box-shadow:
    0 32px 64px rgba(240,90,40,.2),
    0 16px 32px rgba(0,0,0,.3),
    inset 0 1px 0 rgba(255,255,255,.12);
}
.stat-glow{
  position:absolute;width:80px;height:80px;border-radius:50%;
  background:var(--orange);filter:blur(40px);opacity:.12;
  top:50%;left:50%;transform:translate(-50%,-50%);
  transition:opacity .4s;
}
.stat-card-3d:hover .stat-glow{opacity:.25;}
.stat-icon-3d{font-size:2.2rem;margin-bottom:.7rem;display:block;position:relative;z-index:1;filter:drop-shadow(0 4px 8px rgba(240,90,40,.3));}
.stat-value-3d{font-size:2.4rem;font-weight:900;color:var(--orange);line-height:1;margin-bottom:.3rem;position:relative;z-index:1;text-shadow:0 0 20px rgba(240,90,40,.4);}
.stat-label-3d{font-size:.82rem;color:#fff;font-weight:600;margin-bottom:.4rem;position:relative;z-index:1;}
.stat-desc-3d{font-size:.72rem;color:var(--muted);line-height:1.5;position:relative;z-index:1;}
.stat-line{width:30px;height:2px;background:linear-gradient(90deg,var(--orange),transparent);border-radius:2px;margin:.6rem auto .5rem;position:relative;z-index:1;}

/* INNER SECTIONS */
.sec{padding:5.5rem 4rem 4rem;}
.sec-label{color:var(--orange);font-size:.73rem;letter-spacing:.12em;text-transform:uppercase;margin-bottom:.4rem;}
h2.sec-h{font-size:clamp(1.6rem,2.8vw,2.3rem);font-weight:800;margin-bottom:.6rem;}
.abar{height:3px;width:50px;background:var(--orange);border-radius:3px;margin-bottom:2.2rem;}
.sec-sub{color:var(--muted);font-size:.87rem;line-height:1.75;max-width:480px;margin-bottom:2.5rem;}

/* ABOUT */
.about-grid{display:grid;grid-template-columns:260px 1fr;gap:3.5rem;align-items:center;max-width:1000px;}
.about-img{aspect-ratio:3/4;background:linear-gradient(145deg,var(--navy3),#261540);border-radius:22px;border:1px solid var(--border);display:flex;align-items:center;justify-content:center;font-size:5rem;position:relative;}
.about-body p{color:var(--muted);font-size:.86rem;line-height:1.8;margin-bottom:.8rem;}
.chips{display:flex;flex-wrap:wrap;gap:.5rem;margin-top:1.2rem;}
.chip{background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.28);color:var(--orange);padding:.28rem .85rem;border-radius:100px;font-size:.74rem;font-weight:500;}

/* SKILLS */
.skills-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(210px,1fr));gap:1.3rem;}
.sk{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:1.3rem;transition:all .3s ease;position:relative;overflow:hidden;}
.sk::before{content:'';position:absolute;top:0;left:-100%;width:100%;height:100%;background:linear-gradient(90deg,transparent,rgba(240,90,40,.1),transparent);transition:left .5s;}
.sk:hover{border-color:rgba(240,90,40,.5);transform:translateY(-6px);box-shadow:0 8px 24px rgba(240,90,40,.15);}
.sk:hover::before{left:100%;}
.sk-icon{font-size:1.8rem;margin-bottom:.65rem;display:inline-block;}
.sk-title{font-weight:700;font-size:.88rem;margin-bottom:.8rem;color:#fff;}
.tags{display:flex;flex-wrap:wrap;gap:.33rem;}
.tag{background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.09);border-radius:100px;padding:.17rem .58rem;font-size:.69rem;color:var(--muted);transition:all .2s;}
.tag:hover{background:rgba(240,90,40,.15);border-color:rgba(240,90,40,.4);color:var(--orange);}
.tag.h{background:rgba(240,90,40,.11);border-color:rgba(240,90,40,.32);color:var(--orange);}

/* PROJECTS */
.proj-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(265px,1fr));gap:1.3rem;}
.pj{background:var(--navy3);border:1px solid var(--border);border-radius:16px;padding:1.5rem;transition:border-color .3s,transform .3s;position:relative;overflow:hidden;}
.pj::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--orange),var(--orange2));opacity:0;transition:opacity .3s;}
.pj:hover{border-color:rgba(240,90,40,.4);transform:translateY(-4px);}
.pj:hover::before{opacity:1;}
.pj-type{font-size:.69rem;letter-spacing:.1em;text-transform:uppercase;color:var(--orange);margin-bottom:.5rem;}
.pj-title{font-weight:700;font-size:.95rem;margin-bottom:.5rem;}
.pj-desc{color:var(--muted);font-size:.81rem;line-height:1.65;margin-bottom:1rem;}

/* CERTIFICATIONS */
.cert-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(290px,1fr));gap:1.5rem;}
.cert-card{background:var(--card);border:1px solid var(--border);border-radius:18px;overflow:hidden;transition:border-color .3s,transform .3s;}
.cert-card:hover{border-color:rgba(240,90,40,.45);transform:translateY(-4px);}
.cert-img-wrap{width:100%;height:180px;background:var(--navy3);position:relative;overflow:hidden;cursor:pointer;display:flex;align-items:center;justify-content:center;}
.cert-img-wrap img{width:100%;height:100%;object-fit:cover;display:block;}
.cert-img-placeholder{display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.5rem;color:var(--muted);font-size:.78rem;text-align:center;padding:1rem;width:100%;height:100%;}
.cert-img-placeholder .upload-icon{font-size:2rem;margin-bottom:.2rem;}
.cert-upload-btn{background:rgba(240,90,40,.15);border:1px dashed rgba(240,90,40,.4);color:var(--orange);padding:.35rem .9rem;border-radius:8px;font-size:.72rem;font-weight:600;cursor:pointer;transition:background .2s;margin-top:.3rem;}
.cert-upload-btn:hover{background:rgba(240,90,40,.25);}
.cert-body{padding:1.1rem 1.3rem 1.3rem;}
.cert-org{font-size:.7rem;color:var(--muted);margin-bottom:.2rem;}
.cert-name{font-weight:700;font-size:.9rem;margin-bottom:.3rem;}
.cert-yr{font-size:.72rem;color:var(--orange);}
.cert-view-btn{display:inline-flex;align-items:center;gap:.3rem;margin-top:.7rem;font-size:.72rem;color:var(--orange);background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.25);padding:.28rem .7rem;border-radius:6px;cursor:pointer;transition:background .2s;font-family:'Poppins',sans-serif;}
.cert-view-btn:hover{background:rgba(240,90,40,.22);}
.add-cert-card{background:rgba(255,255,255,.03);border:1.5px dashed rgba(255,255,255,.12);border-radius:18px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.6rem;cursor:pointer;min-height:280px;transition:border-color .3s,background .3s;color:var(--muted);font-size:.85rem;}
.add-cert-card:hover{border-color:var(--orange);background:rgba(240,90,40,.05);color:var(--orange);}
.add-cert-card span{font-size:2rem;}

/* AWARDS */
.awards-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(290px,1fr));gap:1.5rem;}
.award-card{background:var(--card);border:1px solid var(--border);border-radius:18px;overflow:hidden;transition:border-color .3s,transform .3s;}
.award-card:hover{border-color:rgba(240,90,40,.45);transform:translateY(-4px);}
.award-img-wrap{width:100%;height:170px;background:var(--navy3);position:relative;overflow:hidden;cursor:pointer;display:flex;align-items:center;justify-content:center;}
.award-img-wrap img{width:100%;height:100%;object-fit:cover;display:block;}
.award-img-placeholder{display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.5rem;color:var(--muted);font-size:.78rem;text-align:center;padding:1rem;width:100%;height:100%;}
.award-body{padding:1rem 1.2rem 1.2rem;}
.award-badge{display:inline-flex;align-items:center;gap:.3rem;background:rgba(240,90,40,.12);border:1px solid rgba(240,90,40,.28);color:var(--orange);padding:.22rem .7rem;border-radius:100px;font-size:.65rem;}
.award-title{font-weight:700;font-size:.9rem;margin-bottom:.3rem;}
.award-desc{color:var(--muted);font-size:.8rem;line-height:1.6;}
.add-award-card{background:rgba(255,255,255,.03);border:1.5px dashed rgba(255,255,255,.12);border-radius:18px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.6rem;cursor:pointer;min-height:280px;transition:border-color .3s,background .3s;color:var(--muted);font-size:.85rem;}
.add-award-card:hover{border-color:var(--orange);background:rgba(240,90,40,.05);color:var(--orange);}
.add-award-card span{font-size:2rem;}

/* LIGHTBOX */
.lightbox{display:none;position:fixed;inset:0;z-index:999;background:rgba(0,0,0,.88);backdrop-filter:blur(8px);align-items:center;justify-content:center;}
.lightbox.open{display:flex;}
.lb-inner{position:relative;max-width:90vw;max-height:90vh;}
.lb-inner img{max-width:90vw;max-height:85vh;border-radius:12px;object-fit:contain;box-shadow:0 20px 60px rgba(0,0,0,.5);}
.lb-close{position:absolute;top:-14px;right:-14px;width:32px;height:32px;border-radius:50%;background:var(--orange);color:#fff;border:none;font-size:1.1rem;cursor:pointer;display:flex;align-items:center;justify-content:center;}

/* MODALS */
.modal-overlay{display:none;position:fixed;inset:0;z-index:500;background:rgba(0,0,0,.75);backdrop-filter:blur(6px);align-items:center;justify-content:center;}
.modal-overlay.open{display:flex;}
.modal{background:var(--navy2);border:1px solid var(--border);border-radius:20px;padding:2rem;width:100%;max-width:480px;position:relative;}
.modal h3{font-size:1.1rem;font-weight:700;margin-bottom:1.2rem;}
.modal-close{position:absolute;top:1rem;right:1rem;background:none;border:none;color:var(--muted);font-size:1.3rem;cursor:pointer;}
.modal-close:hover{color:#fff;}
.form-group{margin-bottom:1rem;}
.form-group label{display:block;font-size:.78rem;color:var(--muted);margin-bottom:.4rem;font-weight:500;}
.form-group input,.form-group textarea{width:100%;background:rgba(255,255,255,.06);border:1px solid var(--border);border-radius:10px;padding:.65rem .9rem;color:#fff;font-family:'Poppins',sans-serif;font-size:.85rem;outline:none;transition:border-color .2s;}
.form-group input:focus,.form-group textarea:focus{border-color:var(--orange);}
.form-group textarea{resize:none;height:80px;}
.img-upload-area{width:100%;height:130px;border:1.5px dashed rgba(240,90,40,.4);border-radius:10px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.4rem;cursor:pointer;font-size:.8rem;color:var(--muted);transition:background .2s;position:relative;overflow:hidden;}
.img-upload-area:hover{background:rgba(240,90,40,.06);}
.img-upload-area img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;}
.img-upload-area input[type=file]{position:absolute;inset:0;opacity:0;cursor:pointer;width:100%;height:100%;}
.modal-save{width:100%;padding:.75rem;background:var(--orange);color:#fff;border:none;border-radius:100px;font-family:'Poppins',sans-serif;font-weight:700;font-size:.9rem;cursor:pointer;margin-top:.5rem;transition:background .2s;}
.modal-save:hover{background:var(--orange2);}

/* UPLOAD MODALS */
.upload-modal{display:none;position:fixed;inset:0;z-index:600;background:rgba(0,0,0,.8);align-items:center;justify-content:center;}
.upload-modal.open{display:flex;}
.upload-modal-content{background:var(--navy2);border-radius:20px;padding:2rem;max-width:500px;width:90%;position:relative;border:1px solid var(--border);}
.upload-modal-content h3{font-size:1.2rem;margin-bottom:1.5rem;font-weight:700;}
.upload-modal-content .close-btn{position:absolute;top:1rem;right:1rem;background:none;border:none;color:var(--muted);font-size:1.3rem;cursor:pointer;}
.file-drop-zone{border:2px dashed rgba(240,90,40,.4);border-radius:12px;padding:2rem;text-align:center;cursor:pointer;transition:all .2s;background:rgba(240,90,40,.05);position:relative;}
.file-drop-zone:hover,.file-drop-zone.drag-over{background:rgba(240,90,40,.1);border-color:rgba(240,90,40,.6);}
.file-drop-zone input[type="file"]{position:absolute;inset:0;opacity:0;cursor:pointer;width:100%;height:100%;}
.file-drop-icon{font-size:2.5rem;margin-bottom:.5rem;}
.file-drop-text{color:var(--muted);font-size:.85rem;}
.file-preview{margin:1.5rem 0;text-align:center;}
.file-preview img{max-width:100%;max-height:200px;border-radius:10px;border:1px solid rgba(240,90,40,.3);}
.file-preview .fname{color:var(--muted);font-size:.85rem;padding:.8rem;background:rgba(255,255,255,.04);border-radius:8px;display:flex;align-items:center;gap:.5rem;justify-content:center;}
.modal-actions{display:flex;gap:1rem;margin-top:1.5rem;}
.modal-actions button{flex:1;padding:.75rem;border-radius:100px;border:none;font-family:'Poppins',sans-serif;font-weight:600;cursor:pointer;transition:all .2s;}
.btn-save{background:var(--orange);color:#fff;}
.btn-save:hover{background:var(--orange2);}
.btn-cancel{background:rgba(255,255,255,.1);color:var(--muted);}
.btn-cancel:hover{background:rgba(255,255,255,.15);}

/* TOAST */
.toast{
  position:fixed;bottom:2rem;left:50%;transform:translateX(-50%) translateY(100px);
  background:rgba(15,22,41,.96);border:1px solid rgba(240,90,40,.4);
  color:#fff;padding:.8rem 1.5rem;border-radius:100px;
  font-size:.83rem;font-weight:500;z-index:9999;
  transition:transform .3s ease;pointer-events:none;
  backdrop-filter:blur(12px);
}
.toast.show{transform:translateX(-50%) translateY(0);}

/* ═══ CHATBOT ═══ */
.chat-fab{
  position:fixed;bottom:2rem;right:2rem;z-index:400;
  width:58px;height:58px;border-radius:50%;
  background:linear-gradient(135deg,var(--orange),var(--orange2));
  border:none;cursor:pointer;
  display:flex;align-items:center;justify-content:center;
  box-shadow:0 8px 24px rgba(240,90,40,.4);
  transition:transform .25s,box-shadow .25s;
  animation:fabPulse 2.5s ease-in-out infinite;
}
.chat-fab:hover{transform:scale(1.1);box-shadow:0 12px 32px rgba(240,90,40,.55);animation:none;}
@keyframes fabPulse{0%,100%{box-shadow:0 8px 24px rgba(240,90,40,.4);}50%{box-shadow:0 8px 32px rgba(240,90,40,.7),0 0 0 8px rgba(240,90,40,.1);}}
.chat-fab-icon{font-size:1.5rem;line-height:1;}
.chat-fab-badge{
  position:absolute;top:-4px;right:-4px;
  width:18px;height:18px;border-radius:50%;
  background:#4ade80;border:2px solid var(--navy);
  display:flex;align-items:center;justify-content:center;
  font-size:.55rem;font-weight:700;color:var(--navy);
}

.chatbot-window{
  position:fixed;bottom:6rem;right:2rem;z-index:400;
  width:360px;height:520px;
  background:var(--navy2);border:1px solid rgba(240,90,40,.25);
  border-radius:20px;display:none;flex-direction:column;
  box-shadow:0 24px 60px rgba(0,0,0,.5);
  overflow:hidden;
  animation:chatSlide .3s ease;
}
.chatbot-window.open{display:flex;}
@keyframes chatSlide{from{opacity:0;transform:translateY(20px) scale(.95);}to{opacity:1;transform:none;}}
.chat-header{
  padding:1rem 1.2rem;display:flex;align-items:center;gap:.8rem;
  background:linear-gradient(135deg,rgba(240,90,40,.15),rgba(240,90,40,.05));
  border-bottom:1px solid rgba(255,255,255,.07);flex-shrink:0;
}
.chat-av{width:36px;height:36px;border-radius:50%;background:var(--orange);display:flex;align-items:center;justify-content:center;font-weight:800;font-size:.8rem;flex-shrink:0;}
.chat-av-info{flex:1;}
.chat-av-name{font-weight:700;font-size:.88rem;}
.chat-av-status{font-size:.7rem;color:#4ade80;display:flex;align-items:center;gap:.3rem;}
.chat-av-status::before{content:'';width:6px;height:6px;border-radius:50%;background:#4ade80;}
.chat-close-btn{background:none;border:none;color:var(--muted);cursor:pointer;font-size:1.1rem;padding:.2rem;}
.chat-close-btn:hover{color:#fff;}
.chat-messages{flex:1;overflow-y:auto;padding:1rem;display:flex;flex-direction:column;gap:.8rem;}
.chat-messages::-webkit-scrollbar{width:3px;}
.chat-messages::-webkit-scrollbar-thumb{background:rgba(240,90,40,.3);border-radius:3px;}
.chat-msg{display:flex;gap:.6rem;align-items:flex-end;max-width:100%;}
.chat-msg.user{flex-direction:row-reverse;}
.chat-bubble{
  padding:.65rem .9rem;border-radius:14px;font-size:.8rem;line-height:1.55;
  max-width:78%;word-break:break-word;
}
.chat-msg.bot .chat-bubble{background:rgba(255,255,255,.07);border:1px solid rgba(255,255,255,.09);color:#e2e8f0;border-radius:14px 14px 14px 4px;}
.chat-msg.user .chat-bubble{background:var(--orange);color:#fff;border-radius:14px 14px 4px 14px;}
.chat-dot{width:28px;height:28px;border-radius:50%;background:var(--orange);display:flex;align-items:center;justify-content:center;font-size:.65rem;font-weight:800;flex-shrink:0;}
.chat-msg.user .chat-dot{background:rgba(255,255,255,.1);}
.chat-typing{display:flex;gap:4px;align-items:center;padding:.65rem .9rem;}
.chat-typing span{width:6px;height:6px;border-radius:50%;background:var(--muted);animation:typingDot 1.2s infinite;}
.chat-typing span:nth-child(2){animation-delay:.2s;}
.chat-typing span:nth-child(3){animation-delay:.4s;}
@keyframes typingDot{0%,60%,100%{transform:translateY(0);opacity:.4;}30%{transform:translateY(-5px);opacity:1;}}
.chat-quick{padding:.5rem 1rem;display:flex;gap:.4rem;flex-wrap:wrap;border-top:1px solid rgba(255,255,255,.05);}
.chat-quick-btn{background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.25);color:var(--orange);padding:.3rem .7rem;border-radius:100px;font-size:.68rem;cursor:pointer;font-family:'Poppins',sans-serif;transition:all .2s;white-space:nowrap;}
.chat-quick-btn:hover{background:rgba(240,90,40,.2);}
.chat-input-row{
  padding:.8rem 1rem;display:flex;gap:.6rem;
  border-top:1px solid rgba(255,255,255,.07);flex-shrink:0;
  background:rgba(10,15,35,.5);
}
.chat-input{
  flex:1;background:rgba(255,255,255,.07);border:1px solid rgba(255,255,255,.1);
  border-radius:100px;padding:.55rem 1rem;color:#fff;font-family:'Poppins',sans-serif;
  font-size:.8rem;outline:none;transition:border-color .2s;
}
.chat-input:focus{border-color:rgba(240,90,40,.5);}
.chat-send{
  width:36px;height:36px;border-radius:50%;background:var(--orange);border:none;
  color:#fff;cursor:pointer;display:flex;align-items:center;justify-content:center;
  font-size:.9rem;transition:background .2s;flex-shrink:0;
}
.chat-send:hover{background:var(--orange2);}

/* FOOTER */
footer{padding:1.5rem 4rem;border-top:1px solid rgba(255,255,255,.05);display:flex;justify-content:space-between;align-items:center;color:var(--muted);font-size:.77rem;}

@media(max-width:1050px){
  .hero{flex-direction:column;padding:6rem 1.5rem 2rem;align-items:center;}
  .hero-left,.hero-right{max-width:500px;width:100%;}
  .hero-right{order:-1;}
  .info-panel{flex-direction:row;flex-wrap:wrap;gap:.6rem;}
  .info-row{min-width:45%;}
}
@media(max-width:768px){
  nav{padding:.9rem 1rem;gap:.4rem;flex-wrap:wrap;}
  .nav-tabs{gap:.05rem;padding:.2rem;order:3;width:100%;overflow-x:auto;}
  .nav-tab{padding:.4rem .8rem;font-size:.75rem;}
  .nav-actions{order:2;}
  .hero{padding:5.5rem 1rem 1.5rem;}
  .pwrap{width:240px;height:240px;}
  .pcircle{width:210px;height:210px;top:15px;left:15px;}
  .fc1{right:-5px;}.fc2{left:-5px;}.fc3{right:5px;}
  .sec{padding:3.5rem 1.2rem 2.5rem;}
  .about-grid{grid-template-columns:1fr;}
  .stats-showcase{padding:2rem 1rem;}
  .stats-row{gap:1rem;}
  .stat-card-3d{min-width:150px;}
  footer{flex-direction:column;gap:.4rem;padding:1.2rem;text-align:center;}
  .chatbot-window{width:calc(100vw - 2rem);right:1rem;bottom:5.5rem;}
  .chat-fab{right:1rem;}
}
</style>
</head>
<body>

<!-- LIGHTBOX -->
<div class="lightbox" id="lightbox" onclick="closeLB(event)">
  <div class="lb-inner">
    <button class="lb-close" onclick="closeLightbox()">✕</button>
    <img id="lb-img" src="" alt="">
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<!-- PROFILE MODAL -->
<div class="upload-modal" id="profileModal">
  <div class="upload-modal-content">
    <button class="close-btn" onclick="closeProfileModal()">✕</button>
    <h3>📷 Update Profile Picture</h3>
    <div class="file-drop-zone" id="profileDropZone">
      <div class="file-drop-icon">🖼️</div>
      <div class="file-drop-text">Click to upload or drag &amp; drop<br><small style="opacity:.6;">PNG, JPG, WEBP supported</small></div>
      <input type="file" id="profileFileInput" accept="image/*">
    </div>
    <div class="file-preview" id="profilePreview" style="display:none;"></div>
    <div class="modal-actions">
      <button class="btn-save" onclick="saveProfilePicture()">✓ Save Picture</button>
      <button class="btn-cancel" onclick="closeProfileModal()">Cancel</button>
    </div>
  </div>
</div>

<!-- RESUME MODAL -->
<div class="upload-modal" id="resumeModal">
  <div class="upload-modal-content">
    <button class="close-btn" onclick="closeResumeModal()">✕</button>
    <h3>📄 Upload Resume</h3>
    <div class="file-drop-zone" id="resumeDropZone">
      <div class="file-drop-icon">📋</div>
      <div class="file-drop-text">Click to upload or drag &amp; drop<br><small style="opacity:.6;">PDF, DOC, DOCX supported</small></div>
      <input type="file" id="resumeFileInput" accept=".pdf,.doc,.docx">
    </div>
    <div class="file-preview" id="resumePreview" style="display:none;"></div>
    <div class="modal-actions">
      <button class="btn-save" onclick="saveResume()">✓ Save &amp; Download</button>
      <button class="btn-cancel" onclick="closeResumeModal()">Cancel</button>
    </div>
  </div>
</div>

<!-- CERT MODAL -->
<div class="modal-overlay" id="certModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('certModal')">✕</button>
    <h3>Add Certification</h3>
    <div class="form-group"><label>Issuing Organization</label><input type="text" id="c-org" placeholder="e.g. Microsoft"></div>
    <div class="form-group"><label>Certification Name</label><input type="text" id="c-name" placeholder="e.g. PL-300: Power BI Associate"></div>
    <div class="form-group"><label>Year</label><input type="text" id="c-year" placeholder="e.g. 2024"></div>
    <div class="form-group">
      <label>Certification Image</label>
      <div class="img-upload-area" id="cImgArea">
        <input type="file" accept="image/*" id="cImgFile">
        <span style="font-size:1.5rem">📷</span>
        <span>Click to upload image</span>
      </div>
    </div>
    <input type="hidden" id="cImgData">
    <button class="modal-save" onclick="saveCert()">Save Certification</button>
  </div>
</div>

<!-- AWARD MODAL -->
<div class="modal-overlay" id="awardModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal('awardModal')">✕</button>
    <h3>Add Award / Appreciation</h3>
    <div class="form-group"><label>Award Title</label><input type="text" id="a-title" placeholder="e.g. Best Analyst Q3 2024"></div>
    <div class="form-group"><label>Given By</label><input type="text" id="a-by" placeholder="e.g. Company Name / Team"></div>
    <div class="form-group"><label>Description</label><textarea id="a-desc" placeholder="Brief description of the award..."></textarea></div>
    <div class="form-group">
      <label>Award Image / Certificate</label>
      <div class="img-upload-area" id="aImgArea">
        <input type="file" accept="image/*" id="aImgFile">
        <span style="font-size:1.5rem">🏆</span>
        <span>Click to upload image</span>
      </div>
    </div>
    <input type="hidden" id="aImgData">
    <button class="modal-save" onclick="saveAward()">Save Award</button>
  </div>
</div>

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
    <button class="nav-tab" onclick="showPage('projects',this)">Work</button>
    <button class="nav-tab" onclick="showPage('certifications',this)">Certs</button>
    <button class="nav-tab" onclick="showPage('awards',this)">Awards</button>
  </div>
  <div class="nav-actions">
    <button class="btn-resume" onclick="openResumeModal()">
      <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>
      Resume
    </button>
  </div>
</nav>

<!-- ═══ PAGE: HOME ═══ -->
<div class="page active" id="page-home">
<div class="hero">
  <div class="deco1"></div><div class="deco2"></div>

  <!-- LEFT -->
  <div class="hero-left">
    <p class="hero-eyebrow">Hello,</p>
    <h1 class="hero-name">I'm Akash Kourav</h1>
    <p class="hero-role">A BI Analyst</p>
    <p class="hero-desc">Transforming raw data into powerful insights that drive smarter decisions. Every dashboard tells a story — I make sure it's the right one.</p>
    <div class="hero-ctas">
      <a href="#" onclick="showPage('projects',document.querySelectorAll('.nav-tab')[3]);return false;" class="btn-dis">Discover More</a>
      <button onclick="openResumeModal()" class="btn-circ" title="Download Resume">↓</button>
    </div>
    <div class="follow-row">
      <span>Follow me:</span>
      <div class="socials">
        <a href="https://linkedin.com/in/akashkourav" target="_blank" class="soc soc-li">in</a>
        <a href="https://github.com/akashkourav" target="_blank" class="soc soc-gh">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="white"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0 1.5 3.78c.1.85.34 2.75-.5 6.23"></path></svg>
        </a>
        <a href="mailto:akash.kourav@email.com" class="soc soc-em">✉</a>
      </div>
    </div>
  </div>

  <!-- CENTER: Profile -->
  <div class="hero-center">
    <div class="pwrap">
      <div class="ring"></div>
      <div class="pcircle" onclick="openProfileModal()" title="Click to update photo">
        <img id="profileImg" class="pimg" src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect fill='%23f05a28' width='100' height='100'/%3E%3Ctext x='50' y='50' font-size='40' font-weight='bold' fill='white' text-anchor='middle' dy='0.3em'%3EAK%3C/text%3E%3C/svg%3E" alt="Profile">
      </div>
      <div class="profile-upload" onclick="openProfileModal()" title="Update Profile Picture">
        <span>📷</span>
      </div>
      <div class="fcard fc1"><div class="fcard-num">10+</div><div class="fcard-lbl">Dashboards built</div></div>
      <div class="fcard fc2"><div class="fcard-num">2+</div><div class="fcard-lbl">Years exp.</div></div>
      <div class="fcard fc3"><div class="fcard-stars">★★★★★</div><div class="fcard-num" style="font-size:1rem;">BI Pro</div><div class="fcard-lbl">Specialist</div></div>
    </div>
  </div>

  <!-- RIGHT: Info Panel -->
  <div class="hero-right">
    <div class="info-panel">
      <h3>Quick Info</h3>

      <div class="info-row">
        <div class="info-icon">🎓</div>
        <div>
          <div class="info-label">Education</div>
          <div class="info-value">B.Tech — Computer Science<br><span style="color:var(--muted);font-size:.72rem;">University of Mumbai · 2022</span></div>
        </div>
      </div>

      <div class="info-row">
        <div class="info-icon">📧</div>
        <div>
          <div class="info-label">Email</div>
          <div class="info-value"><a href="mailto:akash.kourav@email.com">akash.kourav@email.com</a></div>
        </div>
      </div>

      <div class="info-row">
        <div class="info-icon">📱</div>
        <div>
          <div class="info-label">Mobile</div>
          <div class="info-value"><a href="tel:+919876543210">+91 98765 43210</a></div>
        </div>
      </div>

      <div class="info-row">
        <div class="info-icon">📍</div>
        <div>
          <div class="info-label">Location</div>
          <div class="info-value">Mumbai, Maharashtra 🇮🇳</div>
        </div>
      </div>

      <div class="info-row">
        <div class="info-icon">💼</div>
        <div>
          <div class="info-label">Experience</div>
          <div class="info-value">2+ Years · Associate Analyst – BI</div>
        </div>
      </div>

      <div class="info-row">
        <div class="info-icon">🌐</div>
        <div>
          <div class="info-label">LinkedIn</div>
          <div class="info-value"><a href="https://linkedin.com/in/akashkourav" target="_blank">linkedin.com/in/akashkourav</a></div>
        </div>
      </div>

      <div class="avail-badge">Available for opportunities</div>
    </div>
  </div>
</div>

<!-- ═══ 3D STATS ROW ═══ -->
<div class="stats-showcase">
  <div class="stats-title">
    <h3>What I Bring To The Table</h3>
    <p>Proven expertise in turning data chaos into actionable insights</p>
  </div>
  <div class="stats-row">
    <div class="stat-card-3d">
      <div class="stat-glow"></div>
      <span class="stat-icon-3d">📊</span>
      <div class="stat-value-3d">50+</div>
      <div class="stat-line"></div>
      <div class="stat-label-3d">Dashboards Created</div>
      <div class="stat-desc-3d">Production-ready Power BI &amp; Tableau solutions</div>
    </div>
    <div class="stat-card-3d">
      <div class="stat-glow"></div>
      <span class="stat-icon-3d">⚡</span>
      <div class="stat-value-3d">40%</div>
      <div class="stat-line"></div>
      <div class="stat-label-3d">Time Saved</div>
      <div class="stat-desc-3d">Automated reporting &amp; ETL pipelines</div>
    </div>
    <div class="stat-card-3d">
      <div class="stat-glow"></div>
      <span class="stat-icon-3d">🎯</span>
      <div class="stat-value-3d">100%</div>
      <div class="stat-line"></div>
      <div class="stat-label-3d">Data Accuracy</div>
      <div class="stat-desc-3d">SQL-optimized queries &amp; data validation</div>
    </div>
    <div class="stat-card-3d">
      <div class="stat-glow"></div>
      <span class="stat-icon-3d">🚀</span>
      <div class="stat-value-3d">8+</div>
      <div class="stat-line"></div>
      <div class="stat-label-3d">Tools Mastered</div>
      <div class="stat-desc-3d">Power BI, Tableau, SQL, Python &amp; more</div>
    </div>
    <div class="stat-card-3d">
      <div class="stat-glow"></div>
      <span class="stat-icon-3d">🏆</span>
      <div class="stat-value-3d">5+</div>
      <div class="stat-line"></div>
      <div class="stat-label-3d">Certifications</div>
      <div class="stat-desc-3d">Microsoft, Google, Tableau &amp; more</div>
    </div>
  </div>
</div>
</div>

<!-- ═══ PAGE: ABOUT ═══ -->
<div class="page" id="page-about">
<section class="sec">
  <p class="sec-label">About Me</p>
  <h2 class="sec-h">Data-driven &amp; insight-focused</h2>
  <div class="abar"></div>
  <div class="about-grid">
    <div class="about-img" style="font-size:5rem;display:flex;align-items:center;justify-content:center;">🧑‍💻</div>
    <div class="about-body">
      <h3>Hi, I'm Akash 👋</h3>
      <p>I'm an Associate Analyst in Business Intelligence based in Mumbai. I specialize in designing interactive dashboards, building data pipelines, and translating complex datasets into narratives that drive business decisions.</p>
      <p>My work sits at the intersection of analytics, visualization, and business strategy — helping teams move from gut-feel to evidence-based decision making with Power BI, SQL, Python, and Tableau.</p>
      <p>When I'm not wrangling data, I'm exploring new BI tools, sharpening my SQL skills, or mentoring others on data storytelling.</p>
      <div class="chips">
        <span class="chip">📍 Mumbai, India</span>
        <span class="chip">💼 Associate Analyst – BI</span>
        <span class="chip">🎓 B.Tech CS · 2022</span>
        <span class="chip">⚡ Available for freelance</span>
        <span class="chip">📊 Power BI Expert</span>
        <span class="chip">🐍 Python Enthusiast</span>
      </div>
    </div>
  </div>
</section>
</div>

<!-- ═══ PAGE: SKILLS ═══ -->
<div class="page" id="page-skills">
<section class="sec">
  <p class="sec-label">Technical Expertise</p>
  <h2 class="sec-h">Skills &amp; Tools</h2>
  <div class="abar"></div>
  <p class="sec-sub">A full stack of BI capabilities — from data wrangling to executive-ready dashboards.</p>
  <div class="skills-grid">
    <div class="sk"><div class="sk-icon">📊</div><div class="sk-title">BI &amp; Visualization</div><div class="tags"><span class="tag h">Power BI</span><span class="tag h">Tableau</span><span class="tag">Looker</span><span class="tag">Data Studio</span></div></div>
    <div class="sk"><div class="sk-icon">🗄️</div><div class="sk-title">Databases &amp; Query</div><div class="tags"><span class="tag h">SQL</span><span class="tag h">MySQL</span><span class="tag">PostgreSQL</span><span class="tag">BigQuery</span><span class="tag">Excel</span></div></div>
    <div class="sk"><div class="sk-icon">🐍</div><div class="sk-title">Programming</div><div class="tags"><span class="tag h">Python</span><span class="tag">Pandas</span><span class="tag">NumPy</span><span class="tag">DAX</span><span class="tag">M Query</span></div></div>
    <div class="sk"><div class="sk-icon">⚙️</div><div class="sk-title">Analytics</div><div class="tags"><span class="tag h">ETL</span><span class="tag">Data Modeling</span><span class="tag">KPI Design</span><span class="tag">Root Cause</span></div></div>
    <div class="sk"><div class="sk-icon">☁️</div><div class="sk-title">Cloud &amp; Platforms</div><div class="tags"><span class="tag">Azure</span><span class="tag">Google Cloud</span><span class="tag">SharePoint</span><span class="tag">Jira</span></div></div>
    <div class="sk"><div class="sk-icon">🤝</div><div class="sk-title">Soft Skills</div><div class="tags"><span class="tag h">Storytelling</span><span class="tag">Stakeholder Mgmt</span><span class="tag">Agile</span><span class="tag">Documentation</span></div></div>
  </div>
</section>
</div>

<!-- ═══ PAGE: PROJECTS ═══ -->
<div class="page" id="page-projects">
<section class="sec">
  <p class="sec-label">Featured Work</p>
  <h2 class="sec-h">Projects</h2>
  <div class="abar"></div>
  <p class="sec-sub">Real-world BI solutions delivering measurable impact.</p>
  <div class="proj-grid">
    <div class="pj"><div class="pj-type">Power BI · DAX · SQL</div><div class="pj-title">Executive Sales Dashboard</div><p class="pj-desc">Multi-page Power BI dashboard consolidating sales data from 3 regions. Leaders can drill from KPIs down to rep-level performance instantly.</p><div class="tags"><span class="tag h">Power BI</span><span class="tag">SQL</span><span class="tag">DAX</span></div></div>
    <div class="pj"><div class="pj-type">Python · ETL · Automation</div><div class="pj-title">Automated Reporting Pipeline</div><p class="pj-desc">Python ETL pipeline that replaced 8 hours of weekly manual reporting with a fully automated scheduled process feeding clean data to dashboards.</p><div class="tags"><span class="tag h">Python</span><span class="tag">Pandas</span><span class="tag">Excel</span></div></div>
    <div class="pj"><div class="pj-type">Tableau · Data Modeling</div><div class="pj-title">Customer Churn Analysis</div><p class="pj-desc">Tableau story with predictive churn indicators built on customer behavior data. Helped surface at-risk accounts and reduce churn rate.</p><div class="tags"><span class="tag h">Tableau</span><span class="tag">MySQL</span><span class="tag">Python</span></div></div>
    <div class="pj"><div class="pj-type">SQL · BigQuery · Looker</div><div class="pj-title">Operations Performance Tracker</div><p class="pj-desc">Real-time ops tracker using BigQuery and Looker, monitoring SLA compliance and team productivity metrics end-to-end.</p><div class="tags"><span class="tag h">BigQuery</span><span class="tag">Looker</span><span class="tag">SQL</span></div></div>
  </div>
</section>
</div>

<!-- ═══ PAGE: CERTIFICATIONS ═══ -->
<div class="page" id="page-certifications">
<section class="sec">
  <p class="sec-label">Credentials</p>
  <h2 class="sec-h">Certifications</h2>
  <div class="abar"></div>
  <p class="sec-sub">Click any certification image to view it full size.</p>
  <div class="cert-grid" id="certGrid">
    <div class="cert-card">
      <div class="cert-img-wrap" id="cimg-0"><div class="cert-img-placeholder"><div class="upload-icon">🪟</div><div>Microsoft Power BI</div><label class="cert-upload-btn">Upload Certificate<input type="file" accept="image/*" style="display:none" onchange="uploadCertImg(event,0)"></label></div></div>
      <div class="cert-body"><div class="cert-org">Microsoft</div><div class="cert-name">PL-300: Power BI Data Analyst Associate</div><div class="cert-yr">✦ Add your year</div><button class="cert-view-btn" onclick="viewCertImg(0)" style="display:none" id="cvbtn-0">🔍 View Full Size</button></div>
    </div>
    <div class="cert-card">
      <div class="cert-img-wrap" id="cimg-1"><div class="cert-img-placeholder"><div class="upload-icon">🐍</div><div>Google Analytics</div><label class="cert-upload-btn">Upload Certificate<input type="file" accept="image/*" style="display:none" onchange="uploadCertImg(event,1)"></label></div></div>
      <div class="cert-body"><div class="cert-org">Google / Coursera</div><div class="cert-name">Google Data Analytics Professional Certificate</div><div class="cert-yr">✦ Add your year</div><button class="cert-view-btn" onclick="viewCertImg(1)" style="display:none" id="cvbtn-1">🔍 View Full Size</button></div>
    </div>
    <div class="cert-card">
      <div class="cert-img-wrap" id="cimg-2"><div class="cert-img-placeholder"><div class="upload-icon">📊</div><div>Tableau Specialist</div><label class="cert-upload-btn">Upload Certificate<input type="file" accept="image/*" style="display:none" onchange="uploadCertImg(event,2)"></label></div></div>
      <div class="cert-body"><div class="cert-org">Tableau</div><div class="cert-name">Tableau Desktop Specialist</div><div class="cert-yr">✦ Add your year</div><button class="cert-view-btn" onclick="viewCertImg(2)" style="display:none" id="cvbtn-2">🔍 View Full Size</button></div>
    </div>
    <div class="add-cert-card" onclick="openModal('certModal')"><span>＋</span><div>Add Certification</div></div>
  </div>
</section>
</div>

<!-- ═══ PAGE: AWARDS ═══ -->
<div class="page" id="page-awards">
<section class="sec">
  <p class="sec-label">Recognition</p>
  <h2 class="sec-h">Awards &amp; Appreciation</h2>
  <div class="abar"></div>
  <p class="sec-sub">Achievements and recognition received throughout my career.</p>
  <div class="awards-grid" id="awardsGrid">
    <div class="award-card">
      <div class="award-img-wrap" id="aimg-0"><div class="award-img-placeholder"><span style="font-size:2rem">🏆</span><div>Star Performer Award</div><label class="cert-upload-btn">Upload Image<input type="file" accept="image/*" style="display:none" onchange="uploadAwardImg(event,0)"></label></div></div>
      <div class="award-body"><div class="award-badge">🏆 Recognition</div><div class="award-title">Star Performer Award</div><div class="award-desc">Add a description of this award and what you achieved.</div><button class="cert-view-btn" onclick="viewAwardImg(0)" style="display:none" id="avbtn-0">🔍 View Certificate</button></div>
    </div>
    <div class="award-card">
      <div class="award-img-wrap" id="aimg-1"><div class="award-img-placeholder"><span style="font-size:2rem">🌟</span><div>Appreciation Letter</div><label class="cert-upload-btn">Upload Image<input type="file" accept="image/*" style="display:none" onchange="uploadAwardImg(event,1)"></label></div></div>
      <div class="award-body"><div class="award-badge">🌟 Appreciation</div><div class="award-title">Client Appreciation Letter</div><div class="award-desc">Add a description of this appreciation and context.</div><button class="cert-view-btn" onclick="viewAwardImg(1)" style="display:none" id="avbtn-1">🔍 View Letter</button></div>
    </div>
    <div class="add-award-card" onclick="openModal('awardModal')"><span>＋</span><div>Add Award / Appreciation</div></div>
  </div>
</section>
</div>

<footer>
  <span>© 2025 Akash Kourav</span>
  <span style="color:rgba(255,255,255,.12)">Built with precision &amp; purpose</span>
</footer>

<!-- ═══ CHATBOT ═══ -->
<button class="chat-fab" id="chatFab" onclick="toggleChat()" title="Chat with AI about my portfolio">
  <span class="chat-fab-icon" id="chatFabIcon">💬</span>
  <div class="chat-fab-badge">AI</div>
</button>

<div class="chatbot-window" id="chatbotWindow">
  <div class="chat-header">
    <div class="chat-av">AK</div>
    <div class="chat-av-info">
      <div class="chat-av-name">Akash's AI Assistant</div>
      <div class="chat-av-status">Online · Ask me anything</div>
    </div>
    <button class="chat-close-btn" onclick="toggleChat()">✕</button>
  </div>
  <div class="chat-messages" id="chatMessages">
    <div class="chat-msg bot">
      <div class="chat-dot">AK</div>
      <div class="chat-bubble">Hi! 👋 I'm Akash's AI assistant. I can answer questions about his skills, experience, projects, education and more. What would you like to know?</div>
    </div>
  </div>
  <div class="chat-quick" id="chatQuick">
    <button class="chat-quick-btn" onclick="quickAsk('What skills does Akash have?')">🛠 Skills</button>
    <button class="chat-quick-btn" onclick="quickAsk('Tell me about his projects')">💼 Projects</button>
    <button class="chat-quick-btn" onclick="quickAsk('What are his certifications?')">🎓 Certs</button>
    <button class="chat-quick-btn" onclick="quickAsk('Is he available for hire?')">📩 Hire</button>
  </div>
  <div class="chat-input-row">
    <input class="chat-input" id="chatInput" type="text" placeholder="Ask about Akash's portfolio..." onkeydown="if(event.key==='Enter')sendChat()">
    <button class="chat-send" onclick="sendChat()">➤</button>
  </div>
</div>

<script>
// ══════════════════════════════════════
// PORTFOLIO DATA (feeds the chatbot)
// ══════════════════════════════════════
const PORTFOLIO_CONTEXT = `
You are an AI assistant for Akash Kourav's personal portfolio website. Answer questions about Akash based only on the information below. Be concise, friendly, and professional. Use bullet points when listing multiple items. If something isn't covered, say you don't have that detail but suggest contacting Akash directly.

ABOUT AKASH:
- Name: Akash Kourav
- Role: Associate Analyst – Business Intelligence (BI)
- Location: Mumbai, Maharashtra, India
- Experience: 2+ years in BI and data analytics
- Education: B.Tech in Computer Science, University of Mumbai (2022)
- Email: akash.kourav@email.com
- Mobile: +91 98765 43210
- LinkedIn: linkedin.com/in/akashkourav
- GitHub: github.com/akashkourav
- Available for: Full-time opportunities AND freelance projects

SKILLS:
- BI & Visualization: Power BI (Expert), Tableau, Looker, Google Data Studio
- Databases & Query: SQL, MySQL, PostgreSQL, BigQuery, Excel
- Programming: Python, Pandas, NumPy, DAX, M Query
- Analytics: ETL, Data Modeling, KPI Design, Root Cause Analysis
- Cloud & Platforms: Azure, Google Cloud, SharePoint, Jira
- Soft Skills: Data Storytelling, Stakeholder Management, Agile, Documentation

PROJECTS:
1. Executive Sales Dashboard (Power BI, DAX, SQL)
   - Multi-page Power BI dashboard for 3 regional sales teams
   - Enables drill-through from executive KPIs to rep-level performance

2. Automated Reporting Pipeline (Python, ETL, Automation)
   - Replaced 8 hours of weekly manual reporting with automated Python ETL
   - Feeds clean, scheduled data directly into dashboards

3. Customer Churn Analysis (Tableau, MySQL, Python)
   - Built Tableau story with predictive churn indicators
   - Surfaced at-risk accounts and helped reduce churn rate

4. Operations Performance Tracker (BigQuery, Looker, SQL)
   - Real-time tracker for SLA compliance and team productivity
   - End-to-end solution from raw data to Looker dashboards

CERTIFICATIONS:
- Microsoft PL-300: Power BI Data Analyst Associate
- Google Data Analytics Professional Certificate (Coursera)
- Tableau Desktop Specialist

STATS / ACHIEVEMENTS:
- 50+ dashboards created
- 40% time savings through automation
- 100% data accuracy in deliverables
- 8+ tools mastered
- 5+ certifications

HOW TO CONTACT:
- Email: akash.kourav@email.com
- Phone: +91 98765 43210
- LinkedIn: linkedin.com/in/akashkourav
- Available for freelance and full-time roles
`;

// ══════════════════════════════════════
// PAGE SWITCHING
// ══════════════════════════════════════
function showPage(id, tabEl) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
  document.getElementById('page-' + id).classList.add('active');
  if (tabEl) tabEl.classList.add('active');
  window.scrollTo({top:0,behavior:'smooth'});
}

// ══════════════════════════════════════
// TOAST
// ══════════════════════════════════════
function showToast(msg, duration=3000) {
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  setTimeout(() => t.classList.remove('show'), duration);
}

// ══════════════════════════════════════
// PROFILE PICTURE MODAL
// ══════════════════════════════════════
let pendingProfileData = null;

function openProfileModal() {
  document.getElementById('profileModal').classList.add('open');
}
function closeProfileModal() {
  document.getElementById('profileModal').classList.remove('open');
  document.getElementById('profilePreview').style.display = 'none';
  document.getElementById('profileFileInput').value = '';
  pendingProfileData = null;
}

// File input change
document.getElementById('profileFileInput').addEventListener('change', function() {
  const file = this.files[0];
  if (!file) return;
  const reader = new FileReader();
  reader.onload = function(e) {
    pendingProfileData = e.target.result;
    const prev = document.getElementById('profilePreview');
    prev.style.display = 'block';
    prev.innerHTML = `<img src="${e.target.result}" alt="Preview">`;
  };
  reader.readAsDataURL(file);
});

// Drag & drop for profile
setupDragDrop('profileDropZone', 'profileFileInput', handleProfileDrop);
function handleProfileDrop(file) {
  if (!file.type.startsWith('image/')) { showToast('⚠️ Please select an image file'); return; }
  const reader = new FileReader();
  reader.onload = function(e) {
    pendingProfileData = e.target.result;
    const prev = document.getElementById('profilePreview');
    prev.style.display = 'block';
    prev.innerHTML = `<img src="${e.target.result}" alt="Preview">`;
  };
  reader.readAsDataURL(file);
}

function saveProfilePicture() {
  if (!pendingProfileData) { showToast('⚠️ Please select a photo first'); return; }
  document.getElementById('profileImg').src = pendingProfileData;
  try { localStorage.setItem('akash_profilePic', pendingProfileData); } catch(e){}
  closeProfileModal();
  showToast('✅ Profile picture updated!');
}

// ══════════════════════════════════════
// RESUME MODAL
// ══════════════════════════════════════
let pendingResumeFile = null;

function openResumeModal() {
  document.getElementById('resumeModal').classList.add('open');
}
function closeResumeModal() {
  document.getElementById('resumeModal').classList.remove('open');
  document.getElementById('resumePreview').style.display = 'none';
  document.getElementById('resumeFileInput').value = '';
  pendingResumeFile = null;
}

document.getElementById('resumeFileInput').addEventListener('change', function() {
  const file = this.files[0];
  if (!file) return;
  pendingResumeFile = file;
  showResumePreview(file.name);
});

function showResumePreview(name) {
  const prev = document.getElementById('resumePreview');
  prev.style.display = 'block';
  prev.innerHTML = `<div class="fname">📄 ${name}</div>`;
}

setupDragDrop('resumeDropZone', 'resumeFileInput', handleResumeDrop);
function handleResumeDrop(file) {
  pendingResumeFile = file;
  showResumePreview(file.name);
}

function saveResume() {
  if (!pendingResumeFile) { showToast('⚠️ Please select a resume file first'); return; }
  const url = URL.createObjectURL(pendingResumeFile);
  const a = document.createElement('a');
  a.href = url;
  a.download = pendingResumeFile.name;
  a.click();
  URL.revokeObjectURL(url);
  closeResumeModal();
  showToast('✅ Resume download started!');
}

// ══════════════════════════════════════
// DRAG & DROP HELPER
// ══════════════════════════════════════
function setupDragDrop(zoneId, inputId, onDropCb) {
  const zone = document.getElementById(zoneId);
  if (!zone) return;
  zone.addEventListener('dragover', e => { e.preventDefault(); zone.classList.add('drag-over'); });
  zone.addEventListener('dragleave', () => zone.classList.remove('drag-over'));
  zone.addEventListener('drop', e => {
    e.preventDefault();
    zone.classList.remove('drag-over');
    const file = e.dataTransfer.files[0];
    if (file) {
      // Sync to input
      const dt = new DataTransfer();
      dt.items.add(file);
      document.getElementById(inputId).files = dt.files;
      onDropCb(file);
    }
  });
}

// Load saved profile
window.addEventListener('load', function() {
  try {
    const saved = localStorage.getItem('akash_profilePic');
    if (saved) document.getElementById('profileImg').src = saved;
  } catch(e){}
});

// ══════════════════════════════════════
// GENERIC MODALS
// ══════════════════════════════════════
function openModal(id) { document.getElementById(id).classList.add('open'); }
function closeModal(id) { document.getElementById(id).classList.remove('open'); }
document.querySelectorAll('.modal-overlay').forEach(m => {
  m.addEventListener('click', e => { if (e.target === m) m.classList.remove('open'); });
});
document.querySelectorAll('.upload-modal').forEach(m => {
  m.addEventListener('click', e => { if (e.target === m) m.classList.remove('open'); });
});

// ══════════════════════════════════════
// LIGHTBOX
// ══════════════════════════════════════
let certImgs = {}, awardImgs = {};
function openLightbox(src) {
  document.getElementById('lb-img').src = src;
  document.getElementById('lightbox').classList.add('open');
}
function closeLightbox() { document.getElementById('lightbox').classList.remove('open'); }
function closeLB(e) { if (e.target === document.getElementById('lightbox')) closeLightbox(); }

// ══════════════════════════════════════
// CERT / AWARD IMAGE UPLOAD
// ══════════════════════════════════════
function uploadCertImg(e, idx) {
  const file = e.target.files[0]; if (!file) return;
  const reader = new FileReader();
  reader.onload = function(ev) {
    certImgs[idx] = ev.target.result;
    const wrap = document.getElementById('cimg-' + idx);
    wrap.innerHTML = '<img src="' + ev.target.result + '" alt="Certificate" onclick="openLightbox(certImgs[' + idx + '])" style="cursor:zoom-in;">';
    const btn = document.getElementById('cvbtn-' + idx);
    if (btn) btn.style.display = 'inline-flex';
    showToast('✅ Certificate image uploaded!');
  };
  reader.readAsDataURL(file);
}
function viewCertImg(idx) { if (certImgs[idx]) openLightbox(certImgs[idx]); }

function uploadAwardImg(e, idx) {
  const file = e.target.files[0]; if (!file) return;
  const reader = new FileReader();
  reader.onload = function(ev) {
    awardImgs[idx] = ev.target.result;
    const wrap = document.getElementById('aimg-' + idx);
    wrap.innerHTML = '<img src="' + ev.target.result + '" alt="Award" onclick="openLightbox(awardImgs[' + idx + '])" style="cursor:zoom-in;">';
    const btn = document.getElementById('avbtn-' + idx);
    if (btn) btn.style.display = 'inline-flex';
    showToast('✅ Award image uploaded!');
  };
  reader.readAsDataURL(file);
}
function viewAwardImg(idx) { if (awardImgs[idx]) openLightbox(awardImgs[idx]); }

// ══════════════════════════════════════
// MODAL IMAGE PREVIEW
// ══════════════════════════════════════
function setupModalImgUpload(fileInputId, areaId, hiddenId) {
  document.getElementById(fileInputId).addEventListener('change', function(e) {
    const file = e.target.files[0]; if (!file) return;
    const reader = new FileReader();
    reader.onload = function(ev) {
      document.getElementById(hiddenId).value = ev.target.result;
      const area = document.getElementById(areaId);
      let img = area.querySelector('img.preview-img');
      if (!img) { img = document.createElement('img'); img.className='preview-img'; area.appendChild(img); }
      img.src = ev.target.result;
      img.style.cssText = 'position:absolute;inset:0;width:100%;height:100%;object-fit:cover;border-radius:10px;';
    };
    reader.readAsDataURL(file);
  });
}
setupModalImgUpload('cImgFile', 'cImgArea', 'cImgData');
setupModalImgUpload('aImgFile', 'aImgArea', 'aImgData');

// ══════════════════════════════════════
// SAVE NEW CERT
// ══════════════════════════════════════
let certCount = 3;
function saveCert() {
  const org = document.getElementById('c-org').value.trim();
  const name = document.getElementById('c-name').value.trim();
  const year = document.getElementById('c-year').value.trim();
  const imgData = document.getElementById('cImgData').value;
  if (!name) { showToast('⚠️ Please enter certification name'); return; }
  const idx = 'new_' + certCount++;
  certImgs[idx] = imgData;
  const grid = document.getElementById('certGrid');
  const addBtn = grid.querySelector('.add-cert-card');
  const card = document.createElement('div');
  card.className = 'cert-card';
  const imgSection = imgData
    ? `<div class="cert-img-wrap" style="cursor:zoom-in;" onclick="openLightbox(certImgs['${idx}'])"><img src="${imgData}" alt="Certificate"></div>`
    : `<div class="cert-img-wrap"><div class="cert-img-placeholder"><div class="upload-icon">🎓</div><div>${name}</div></div></div>`;
  card.innerHTML = imgSection + `<div class="cert-body"><div class="cert-org">${org||'Issuer'}</div><div class="cert-name">${name}</div><div class="cert-yr">${year?'✦ '+year:'✦ Year'}</div>${imgData?`<button class="cert-view-btn" onclick="openLightbox(certImgs['${idx}'])">🔍 View</button>`:''}</div>`;
  grid.insertBefore(card, addBtn);
  ['c-org','c-name','c-year'].forEach(id => document.getElementById(id).value='');
  document.getElementById('cImgData').value='';
  const img = document.getElementById('cImgArea').querySelector('img.preview-img');
  if (img) img.remove();
  closeModal('certModal');
  showToast('✅ Certification added!');
}

// ══════════════════════════════════════
// SAVE NEW AWARD
// ══════════════════════════════════════
let awardCount = 2;
function saveAward() {
  const title = document.getElementById('a-title').value.trim();
  const by = document.getElementById('a-by').value.trim();
  const desc = document.getElementById('a-desc').value.trim();
  const imgData = document.getElementById('aImgData').value;
  if (!title) { showToast('⚠️ Please enter award title'); return; }
  const idx = 'na_' + awardCount++;
  awardImgs[idx] = imgData;
  const grid = document.getElementById('awardsGrid');
  const addBtn = grid.querySelector('.add-award-card');
  const card = document.createElement('div');
  card.className = 'award-card';
  const imgSection = imgData
    ? `<div class="award-img-wrap" style="cursor:zoom-in;" onclick="openLightbox(awardImgs['${idx}'])"><img src="${imgData}" alt="Award"></div>`
    : `<div class="award-img-wrap"><div class="award-img-placeholder"><span style="font-size:2rem">🏆</span><div>${title}</div></div></div>`;
  card.innerHTML = imgSection + `<div class="award-body"><div class="award-badge">🏆 ${by||'Recognition'}</div><div class="award-title">${title}</div><div class="award-desc">${desc||'Award description.'}</div>${imgData?`<button class="cert-view-btn" onclick="openLightbox(awardImgs['${idx}'])">🔍 View</button>`:''}</div>`;
  grid.insertBefore(card, addBtn);
  ['a-title','a-by','a-desc'].forEach(id => document.getElementById(id).value='');
  document.getElementById('aImgData').value='';
  const img = document.getElementById('aImgArea').querySelector('img.preview-img');
  if (img) img.remove();
  closeModal('awardModal');
  showToast('✅ Award added!');
}

// ══════════════════════════════════════
// CHATBOT
// ══════════════════════════════════════
let chatOpen = false;
let chatHistory = [];

function toggleChat() {
  chatOpen = !chatOpen;
  const win = document.getElementById('chatbotWindow');
  const icon = document.getElementById('chatFabIcon');
  if (chatOpen) {
    win.classList.add('open');
    icon.textContent = '✕';
    document.getElementById('chatInput').focus();
  } else {
    win.classList.remove('open');
    icon.textContent = '💬';
  }
}

function quickAsk(question) {
  document.getElementById('chatInput').value = question;
  sendChat();
  // Hide quick buttons after first use
  document.getElementById('chatQuick').style.display = 'none';
}

async function sendChat() {
  const input = document.getElementById('chatInput');
  const msg = input.value.trim();
  if (!msg) return;
  input.value = '';

  appendMsg('user', msg);
  chatHistory.push({role:'user', content: msg});

  // Show typing
  const typingId = 'typing_' + Date.now();
  appendTyping(typingId);

  try {
    const response = await fetch('https://api.anthropic.com/v1/messages', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        model: 'claude-sonnet-4-20250514',
        max_tokens: 1000,
        system: PORTFOLIO_CONTEXT,
        messages: chatHistory
      })
    });
    const data = await response.json();
    removeTyping(typingId);

    let reply = '';
    if (data.content && data.content[0] && data.content[0].text) {
      reply = data.content[0].text;
    } else if (data.error) {
      reply = "I'm having trouble connecting right now. Please reach out to Akash directly at akash.kourav@email.com!";
    }
    appendMsg('bot', reply);
    chatHistory.push({role:'assistant', content: reply});
  } catch(e) {
    removeTyping(typingId);
    appendMsg('bot', "Connection issue — please contact Akash directly at akash.kourav@email.com or +91 98765 43210 😊");
  }
}

function appendMsg(role, text) {
  const container = document.getElementById('chatMessages');
  const div = document.createElement('div');
  div.className = 'chat-msg ' + role;
  const dot = document.createElement('div');
  dot.className = 'chat-dot';
  dot.textContent = role === 'bot' ? 'AK' : '👤';
  const bubble = document.createElement('div');
  bubble.className = 'chat-bubble';
  // Convert markdown-lite
  bubble.innerHTML = text
    .replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>')
    .replace(/\n• /g, '<br>• ')
    .replace(/\n- /g, '<br>• ')
    .replace(/\n/g, '<br>');
  div.appendChild(dot);
  div.appendChild(bubble);
  container.appendChild(div);
  container.scrollTop = container.scrollHeight;
}

function appendTyping(id) {
  const container = document.getElementById('chatMessages');
  const div = document.createElement('div');
  div.className = 'chat-msg bot';
  div.id = id;
  const dot = document.createElement('div');
  dot.className = 'chat-dot';
  dot.textContent = 'AK';
  const bubble = document.createElement('div');
  bubble.className = 'chat-bubble';
  bubble.innerHTML = '<div class="chat-typing"><span></span><span></span><span></span></div>';
  div.appendChild(dot);
  div.appendChild(bubble);
  container.appendChild(div);
  container.scrollTop = container.scrollHeight;
}

function removeTyping(id) {
  const el = document.getElementById(id);
  if (el) el.remove();
}
</script>
</body>
</html>
