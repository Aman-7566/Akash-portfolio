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
/* TAB NAV */
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

/* HERO PAGE - OPTIMIZED FIT */
.hero{
  min-height:100vh;display:flex;align-items:center;justify-content:space-between;
  padding:7rem 4rem 2rem;position:relative;overflow:hidden;gap:2rem;
}
.deco1,.deco2{position:absolute;border-radius:50%;border:1px dashed rgba(255,255,255,0.055);pointer-events:none;}
.deco1{width:520px;height:520px;right:-100px;top:-80px;}
.deco2{width:320px;height:320px;left:-100px;bottom:-80px;}
.hero-left{flex:1;max-width:510px;}
.hero-eyebrow{color:var(--muted);font-size:1.05rem;font-weight:400;margin-bottom:.15rem;}
.hero-name{color:var(--orange);font-size:clamp(2rem,4vw,3.6rem);font-weight:800;line-height:1.05;margin-bottom:.15rem;}
.hero-role{font-size:clamp(1.3rem,2.5vw,2rem);font-weight:700;margin-bottom:1rem;}
.hero-desc{color:var(--muted);font-size:.87rem;font-weight:300;line-height:1.85;max-width:400px;margin-bottom:1.5rem;}
.hero-ctas{display:flex;align-items:center;gap:1rem;margin-bottom:1.5rem;flex-wrap:wrap;}
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

/* profile circle with editable picture */
.hero-right{flex:1;display:flex;justify-content:center;align-items:center;position:relative;}
.pwrap{position:relative;width:350px;height:350px;}
.ring{position:absolute;inset:0;border-radius:50%;border:2px solid var(--orange);animation:spin 22s linear infinite;}
.pcircle{position:absolute;top:24px;left:24px;width:302px;height:302px;border-radius:50%;background:linear-gradient(145deg,#7a2d12,var(--orange));display:flex;align-items:center;justify-content:center;overflow:hidden;cursor:pointer;transition:opacity .3s;}
.pcircle:hover{opacity:0.8;}
.pimg{width:100%;height:100%;object-fit:cover;}
.pinit{font-size:6rem;font-weight:900;color:rgba(255,255,255,0.14);user-select:none;line-height:1;}
.profile-upload{position:absolute;bottom:0;right:0;width:50px;height:50px;background:var(--orange);border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:all .2s;box-shadow:0 4px 12px rgba(240,90,40,.3);}
.profile-upload:hover{background:var(--orange2);transform:scale(1.1);}
.profile-upload input{display:none;}
.profile-upload span{font-size:1.5rem;}

.fcard{position:absolute;background:rgba(10,15,35,.88);backdrop-filter:blur(12px);border:1px solid rgba(255,255,255,.13);border-radius:13px;padding:.7rem 1rem;text-align:center;min-width:115px;}
.fcard-num{font-size:1.6rem;font-weight:800;line-height:1;}
.fcard-lbl{font-size:.67rem;color:var(--muted);margin-top:2px;}
.fcard-stars{color:#f5a623;font-size:11px;margin-bottom:3px;}
.fc1{top:18px;right:-50px;animation:float1 3s ease-in-out infinite;}
.fc2{top:50%;left:-60px;animation:float2 3.5s ease-in-out .5s infinite;}
.fc3{bottom:30px;right:-25px;animation:float3 3s ease-in-out 1s infinite;}
@keyframes spin{to{transform:rotate(360deg);}}
@keyframes float1{0%,100%{transform:translateY(0);}50%{transform:translateY(-8px);}}
@keyframes float2{0%,100%{transform:translateY(-50%);}50%{transform:translateY(calc(-50% - 8px));}}
@keyframes float3{0%,100%{transform:translateY(0);}50%{transform:translateY(-7px);}}

/* STATS SHOWCASE - ATTRACTIVE */
.stats-showcase{padding:3rem 4rem;background:linear-gradient(135deg,rgba(240,90,40,.05),rgba(240,90,40,.02));border-top:1px solid rgba(240,90,40,.2);border-bottom:1px solid rgba(240,90,40,.2);}
.stats-title{text-align:center;margin-bottom:2.5rem;}
.stats-title h3{font-size:1.3rem;font-weight:700;margin-bottom:.5rem;}
.stats-title p{color:var(--muted);font-size:.9rem;}
.stats-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:2rem;max-width:1200px;margin:0 auto;}
.stat-card{
  background:rgba(255,255,255,.04);border:1px solid rgba(240,90,40,.25);border-radius:16px;
  padding:1.8rem;text-align:center;transition:all .3s ease;position:relative;overflow:hidden;
}
.stat-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--orange),transparent);opacity:0;transition:opacity .3s;}
.stat-card:hover{
  background:rgba(240,90,40,.08);border-color:rgba(240,90,40,.5);transform:translateY(-6px);
}
.stat-card:hover::before{opacity:1;}
.stat-icon{font-size:2.5rem;margin-bottom:.8rem;}
.stat-value{font-size:2rem;font-weight:800;color:var(--orange);line-height:1;margin-bottom:.3rem;}
.stat-label{font-size:.85rem;color:var(--muted);font-weight:500;}
.stat-desc{font-size:.75rem;color:rgba(255,255,255,.06);margin-top:.5rem;line-height:1.5;}

/* INNER SECTIONS */
.sec{padding:5.5rem 4rem 4rem;}
.sec-label{color:var(--orange);font-size:.73rem;letter-spacing:.12em;text-transform:uppercase;margin-bottom:.4rem;}
h2.sec-h{font-size:clamp(1.6rem,2.8vw,2.3rem);font-weight:800;margin-bottom:.6rem;}
.abar{height:3px;width:50px;background:var(--orange);border-radius:3px;margin-bottom:2.2rem;}
.sec-sub{color:var(--muted);font-size:.87rem;line-height:1.75;max-width:480px;margin-bottom:2.5rem;}

/* ABOUT */
.about-grid{display:grid;grid-template-columns:280px 1fr;gap:3.5rem;align-items:center;max-width:1050px;}
.about-img{aspect-ratio:3/4;background:linear-gradient(145deg,var(--navy3),#261540);border-radius:22px;border:1px solid var(--border);display:flex;align-items:center;justify-content:center;font-size:5rem;}
.about-img::after{content:'AK';position:absolute;font-size:6rem;font-weight:900;color:rgba(240,90,40,.12);}
.about-body p{color:var(--muted);font-size:.86rem;line-height:1.8;margin-bottom:.8rem;}
.chips{display:flex;flex-wrap:wrap;gap:.5rem;margin-top:1.2rem;}
.chip{background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.28);color:var(--orange);padding:.28rem .85rem;border-radius:100px;font-size:.74rem;font-weight:500;}

/* SKILLS - ATTRACTIVE DISPLAY */
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
.cert-card{
  background:var(--card);border:1px solid var(--border);
  border-radius:18px;overflow:hidden;
  transition:border-color .3s,transform .3s;
}
.cert-card:hover{border-color:rgba(240,90,40,.45);transform:translateY(-4px);}
.cert-img-wrap{
  width:100%;height:180px;background:var(--navy3);
  position:relative;overflow:hidden;cursor:pointer;
  display:flex;align-items:center;justify-content:center;
}
.cert-img-wrap img{width:100%;height:100%;object-fit:cover;display:block;}
.cert-img-placeholder{
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  gap:.5rem;color:var(--muted);font-size:.78rem;text-align:center;padding:1rem;
  width:100%;height:100%;
}
.cert-img-placeholder .upload-icon{font-size:2rem;margin-bottom:.2rem;}
.cert-upload-btn{
  background:rgba(240,90,40,.15);border:1px dashed rgba(240,90,40,.4);
  color:var(--orange);padding:.35rem .9rem;border-radius:8px;
  font-size:.72rem;font-weight:600;cursor:pointer;
  transition:background .2s;margin-top:.3rem;
}
.cert-upload-btn:hover{background:rgba(240,90,40,.25);}
.cert-body{padding:1.1rem 1.3rem 1.3rem;}
.cert-org{font-size:.7rem;color:var(--muted);margin-bottom:.2rem;}
.cert-name{font-weight:700;font-size:.9rem;margin-bottom:.3rem;}
.cert-yr{font-size:.72rem;color:var(--orange);}
.cert-view-btn{
  display:inline-flex;align-items:center;gap:.3rem;
  margin-top:.7rem;font-size:.72rem;color:var(--orange);
  background:rgba(240,90,40,.1);border:1px solid rgba(240,90,40,.25);
  padding:.28rem .7rem;border-radius:6px;cursor:pointer;
  transition:background .2s;border:none;font-family:'Poppins',sans-serif;
}
.cert-view-btn:hover{background:rgba(240,90,40,.22);}
.add-cert-card{
  background:rgba(255,255,255,.03);
  border:1.5px dashed rgba(255,255,255,.12);
  border-radius:18px;
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  gap:.6rem;cursor:pointer;min-height:280px;
  transition:border-color .3s,background .3s;
  color:var(--muted);font-size:.85rem;
}
.add-cert-card:hover{border-color:var(--orange);background:rgba(240,90,40,.05);color:var(--orange);}
.add-cert-card span{font-size:2rem;}

/* AWARDS */
.awards-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(290px,1fr));gap:1.5rem;}
.award-card{
  background:var(--card);border:1px solid var(--border);
  border-radius:18px;overflow:hidden;
  transition:border-color .3s,transform .3s;
}
.award-card:hover{border-color:rgba(240,90,40,.45);transform:translateY(-4px);}
.award-img-wrap{
  width:100%;height:170px;background:var(--navy3);
  position:relative;overflow:hidden;cursor:pointer;
  display:flex;align-items:center;justify-content:center;
}
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
.lightbox{
  display:none;position:fixed;inset:0;z-index:999;
  background:rgba(0,0,0,.88);backdrop-filter:blur(8px);
  align-items:center;justify-content:center;
}
.lightbox.open{display:flex;}
.lb-inner{position:relative;max-width:90vw;max-height:90vh;}
.lb-inner img{max-width:90vw;max-height:85vh;border-radius:12px;object-fit:contain;box-shadow:0 20px 60px rgba(0,0,0,.5);}
.lb-close{position:absolute;top:-14px;right:-14px;width:32px;height:32px;border-radius:50%;background:var(--orange);color:#fff;border:none;font-size:1.1rem;cursor:pointer;display:flex;align-items:center;justify-content:center;}

/* MODAL (add cert/award) */
.modal-overlay{display:none;position:fixed;inset:0;z-index:500;background:rgba(0,0,0,.75);backdrop-filter:blur(6px);align-items:center;justify-content:center;}
.modal-overlay.open{display:flex;}
.modal{background:var(--navy2);border:1px solid var(--border);border-radius:20px;padding:2rem;width:100%;max-width:480px;position:relative;}
.modal h3{font-size:1.1rem;font-weight:700;margin-bottom:1.2rem;}
.modal-close{position:absolute;top:1rem;right:1rem;background:none;border:none;color:var(--muted);font-size:1.3rem;cursor:pointer;}
.modal-close:hover{color:#fff;}
.form-group{margin-bottom:1rem;}
.form-group label{display:block;font-size:.78rem;color:var(--muted);margin-bottom:.4rem;font-weight:500;}
.form-group input,.form-group textarea{
  width:100%;background:rgba(255,255,255,.06);border:1px solid var(--border);
  border-radius:10px;padding:.65rem .9rem;color:#fff;font-family:'Poppins',sans-serif;font-size:.85rem;
  outline:none;transition:border-color .2s;
}
.form-group input:focus,.form-group textarea:focus{border-color:var(--orange);}
.form-group textarea{resize:none;height:80px;}
.img-upload-area{
  width:100%;height:130px;border:1.5px dashed rgba(240,90,40,.4);border-radius:10px;
  display:flex;flex-direction:column;align-items:center;justify-content:center;gap:.4rem;
  cursor:pointer;font-size:.8rem;color:var(--muted);transition:background .2s;
  position:relative;overflow:hidden;
}
.img-upload-area:hover{background:rgba(240,90,40,.06);}
.img-upload-area img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;}
.img-upload-area input[type=file]{position:absolute;inset:0;opacity:0;cursor:pointer;}
.modal-save{width:100%;padding:.75rem;background:var(--orange);color:#fff;border:none;border-radius:100px;font-family:'Poppins',sans-serif;font-weight:700;font-size:.9rem;cursor:pointer;margin-top:.5rem;transition:background .2s;}
.modal-save:hover{background:var(--orange2);}

/* UPLOAD MODALS */
.profile-modal{display:none;position:fixed;inset:0;z-index:600;background:rgba(0,0,0,.8);align-items:center;justify-content:center;}
.profile-modal.open{display:flex;}
.profile-modal-content{background:var(--navy2);border-radius:20px;padding:2rem;max-width:500px;width:100%;position:relative;border:1px solid var(--border);}
.profile-modal-content h3{font-size:1.2rem;margin-bottom:1.5rem;font-weight:700;}
.profile-modal-content .close-btn{position:absolute;top:1rem;right:1rem;background:none;border:none;color:var(--muted);font-size:1.3rem;cursor:pointer;}
.file-input-wrapper{margin:1.5rem 0;}
.file-input-label{display:block;font-size:.85rem;color:var(--muted);margin-bottom:.8rem;font-weight:500;}
.file-drop-zone{
  border:2px dashed rgba(240,90,40,.4);border-radius:12px;padding:2rem;
  text-align:center;cursor:pointer;transition:all .2s;
  background:rgba(240,90,40,.05);
}
.file-drop-zone:hover{background:rgba(240,90,40,.1);border-color:rgba(240,90,40,.6);}
.file-drop-zone input[type="file"]{display:none;}
.file-drop-icon{font-size:2.5rem;margin-bottom:.5rem;}
.file-drop-text{color:var(--muted);font-size:.85rem;}
.file-preview{margin:1.5rem 0;text-align:center;}
.file-preview img{max-width:100%;max-height:200px;border-radius:10px;border:1px solid rgba(240,90,40,.3);}
.profile-modal-actions{display:flex;gap:1rem;margin-top:1.5rem;}
.profile-modal-actions button{flex:1;padding:.75rem;border-radius:100px;border:none;font-family:'Poppins',sans-serif;font-weight:600;cursor:pointer;transition:all .2s;}
.btn-save{background:var(--orange);color:#fff;}
.btn-save:hover{background:var(--orange2);}
.btn-cancel{background:rgba(255,255,255,.1);color:var(--muted);}
.btn-cancel:hover{background:rgba(255,255,255,.15);}

/* FOOTER */
footer{padding:1.5rem 4rem;border-top:1px solid rgba(255,255,255,.05);display:flex;justify-content:space-between;align-items:center;color:var(--muted);font-size:.77rem;}

@media(max-width:900px){
  nav{padding:.9rem 1.2rem;gap:.5rem;flex-wrap:wrap;}
  .nav-tabs{gap:.1rem;padding:.25rem;order:3;width:100%;}
  .nav-actions{order:2;}
  .hero{flex-direction:column;padding:6rem 1.5rem 2rem;gap:1.5rem;}
  .pwrap{width:270px;height:270px;margin:0 auto;}
  .ring{width:270px;height:270px;}
  .pcircle{width:238px;height:238px;top:16px;left:16px;}
  .fc1{right:-10px;}.fc2{left:-10px;}.fc3{right:0px;}
  .sec{padding:4rem 1.5rem 3rem;}
  .about-grid{grid-template-columns:1fr;}
  .stats-showcase{padding:2rem 1.5rem;}
  .stats-grid{gap:1.5rem;}
  footer{flex-direction:column;gap:.4rem;padding:1.2rem;text-align:center;}
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

<!-- PROFILE PICTURE UPLOAD MODAL -->
<div class="profile-modal" id="profileModal">
  <div class="profile-modal-content">
    <button class="close-btn" onclick="closeProfileModal()">✕</button>
    <h3>Update Profile Picture</h3>
    <div class="file-input-wrapper">
      <label class="file-input-label">Select or drag your profile image</label>
      <div class="file-drop-zone" id="profileDropZone">
        <div class="file-drop-icon">📷</div>
        <div class="file-drop-text">Click to upload or drag and drop</div>
        <input type="file" id="profileFile" accept="image/*" onchange="previewProfileImg()">
      </div>
    </div>
    <div class="file-preview" id="profilePreview"></div>
    <div class="profile-modal-actions">
      <button class="btn-save" onclick="saveProfilePicture()">Save Picture</button>
      <button class="btn-cancel" onclick="closeProfileModal()">Cancel</button>
    </div>
  </div>
</div>

<!-- RESUME UPLOAD MODAL -->
<div class="profile-modal" id="resumeModal">
  <div class="profile-modal-content">
    <button class="close-btn" onclick="closeResumeModal()">✕</button>
    <h3>Update Resume</h3>
    <div class="file-input-wrapper">
      <label class="file-input-label">Select your resume PDF</label>
      <div class="file-drop-zone" id="resumeDropZone">
        <div class="file-drop-icon">📄</div>
        <div class="file-drop-text">Click to upload or drag and drop</div>
        <input type="file" id="resumeFile" accept=".pdf,.doc,.docx" onchange="previewResume()">
      </div>
    </div>
    <div class="file-preview" id="resumePreview"></div>
    <div class="profile-modal-actions">
      <button class="btn-save" onclick="saveResume()">Save Resume</button>
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
        <input type="file" accept="image/*" onchange="previewImg(event,'cImgArea','cImgData')">
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
        <input type="file" accept="image/*" onchange="previewImg(event,'aImgArea','aImgData')">
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
  <div class="hero-right">
    <div class="pwrap">
      <div class="ring"></div>
      <div class="pcircle" onclick="openProfileModal()" title="Click to change profile picture">
        <img id="profileImg" class="pimg" src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect fill='%23f05a28' width='100' height='100'/%3E%3Ctext x='50' y='50' font-size='40' font-weight='bold' fill='white' text-anchor='middle' dy='0.3em'%3EAK%3C/text%3E%3C/svg%3E" alt="Profile">
      </div>
      <div class="profile-upload" onclick="openProfileModal()" title="Update Profile Picture">
        <input type="file" id="profileInputFile" accept="image/*" onchange="handleProfileFileSelect()" style="display:none;">
        <span>📷</span>
      </div>
      <div class="fcard fc1"><div class="fcard-num">10+</div><div class="fcard-lbl">Dashboards built</div></div>
      <div class="fcard fc2"><div class="fcard-num">2+</div><div class="fcard-lbl">Years experience</div></div>
      <div class="fcard fc3"><div class="fcard-stars">★★★★★</div><div class="fcard-num" style="font-size:1.1rem;">BI Pro</div><div class="fcard-lbl">Specialist</div></div>
    </div>
  </div>
</div>

<!-- STATS SHOWCASE SECTION -->
<div class="stats-showcase">
  <div class="stats-title">
    <h3>What I Bring To The Table</h3>
    <p>Proven expertise in turning data chaos into actionable insights</p>
  </div>
  <div class="stats-grid">
    <div class="stat-card">
      <div class="stat-icon">📊</div>
      <div class="stat-value">50+</div>
      <div class="stat-label">Dashboards Created</div>
      <div class="stat-desc">Production-ready Power BI & Tableau solutions</div>
    </div>
    <div class="stat-card">
      <div class="stat-icon">⚡</div>
      <div class="stat-value">40%</div>
      <div class="stat-label">Time Saved</div>
      <div class="stat-desc">Through automated reporting & ETL pipelines</div>
    </div>
    <div class="stat-card">
      <div class="stat-icon">🎯</div>
      <div class="stat-value">100%</div>
      <div class="stat-label">Data Accuracy</div>
      <div class="stat-desc">SQL-optimized queries & data validation</div>
    </div>
    <div class="stat-card">
      <div class="stat-icon">🚀</div>
      <div class="stat-value">8+</div>
      <div class="stat-label">Tools Mastered</div>
      <div class="stat-desc">Power BI, Tableau, SQL, Python & more</div>
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
    <div class="about-img"></div>
    <div class="about-body">
      <h3>Hi, I'm Akash 👋</h3>
      <p>I'm an Associate Analyst in Business Intelligence based in Mumbai. I specialize in designing interactive dashboards, building data pipelines, and translating complex datasets into narratives that drive business decisions.</p>
      <p>My work sits at the intersection of analytics, visualization, and business strategy — helping teams move from gut-feel to evidence-based decision making with Power BI, SQL, Python, and Tableau.</p>
      <p>When I'm not wrangling data, I'm exploring new BI tools, sharpening my SQL skills, or mentoring others on data storytelling.</p>
      <div class="chips">
        <span class="chip">📍 Mumbai, India</span>
        <span class="chip">💼 Associate Analyst – BI</span>
        <span class="chip">🎓 Open to opportunities</span>
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
    <div class="sk">
      <div class="sk-icon">📊</div><div class="sk-title">BI &amp; Visualization</div>
      <div class="tags"><span class="tag h">Power BI</span><span class="tag h">Tableau</span><span class="tag">Looker</span><span class="tag">Data Studio</span></div>
    </div>
    <div class="sk">
      <div class="sk-icon">🗄️</div><div class="sk-title">Databases &amp; Query</div>
      <div class="tags"><span class="tag h">SQL</span><span class="tag h">MySQL</span><span class="tag">PostgreSQL</span><span class="tag">BigQuery</span><span class="tag">Excel</span></div>
    </div>
    <div class="sk">
      <div class="sk-icon">🐍</div><div class="sk-title">Programming</div>
      <div class="tags"><span class="tag h">Python</span><span class="tag">Pandas</span><span class="tag">NumPy</span><span class="tag">DAX</span><span class="tag">M Query</span></div>
    </div>
    <div class="sk">
      <div class="sk-icon">⚙️</div><div class="sk-title">Analytics</div>
      <div class="tags"><span class="tag h">ETL</span><span class="tag">Data Modeling</span><span class="tag">KPI Design</span><span class="tag">Root Cause</span></div>
    </div>
    <div class="sk">
      <div class="sk-icon">☁️</div><div class="sk-title">Cloud &amp; Platforms</div>
      <div class="tags"><span class="tag">Azure</span><span class="tag">Google Cloud</span><span class="tag">SharePoint</span><span class="tag">Jira</span></div>
    </div>
    <div class="sk">
      <div class="sk-icon">🤝</div><div class="sk-title">Soft Skills</div>
      <div class="tags"><span class="tag h">Storytelling</span><span class="tag">Stakeholder Mgmt</span><span class="tag">Agile</span><span class="tag">Documentation</span></div>
    </div>
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
    <div class="pj">
      <div class="pj-type">Power BI · DAX · SQL</div>
      <div class="pj-title">Executive Sales Dashboard</div>
      <p class="pj-desc">Multi-page Power BI dashboard consolidating sales data from 3 regions. Leaders can drill from KPIs down to rep-level performance instantly.</p>
      <div class="tags"><span class="tag h">Power BI</span><span class="tag">SQL</span><span class="tag">DAX</span></div>
    </div>
    <div class="pj">
      <div class="pj-type">Python · ETL · Automation</div>
      <div class="pj-title">Automated Reporting Pipeline</div>
      <p class="pj-desc">Python ETL pipeline that replaced 8 hours of weekly manual reporting with a fully automated scheduled process feeding clean data to dashboards.</p>
      <div class="tags"><span class="tag h">Python</span><span class="tag">Pandas</span><span class="tag">Excel</span></div>
    </div>
    <div class="pj">
      <div class="pj-type">Tableau · Data Modeling</div>
      <div class="pj-title">Customer Churn Analysis</div>
      <p class="pj-desc">Tableau story with predictive churn indicators built on customer behavior data. Helped surface at-risk accounts and reduce churn rate.</p>
      <div class="tags"><span class="tag h">Tableau</span><span class="tag">MySQL</span><span class="tag">Python</span></div>
    </div>
    <div class="pj">
      <div class="pj-type">SQL · BigQuery · Looker</div>
      <div class="pj-title">Operations Performance Tracker</div>
      <p class="pj-desc">Real-time ops tracker using BigQuery and Looker, monitoring SLA compliance and team productivity metrics end-to-end.</p>
      <div class="tags"><span class="tag h">BigQuery</span><span class="tag">Looker</span><span class="tag">SQL</span></div>
    </div>
  </div>
</section>
</div>

<!-- ═══ PAGE: CERTIFICATIONS ═══ -->
<div class="page" id="page-certifications">
<section class="sec">
  <p class="sec-label">Credentials</p>
  <h2 class="sec-h">Certifications</h2>
  <div class="abar"></div>
  <p class="sec-sub">Click any certification image to view it full size. Upload your own certificate images below.</p>
  <div class="cert-grid" id="certGrid">
    <!-- Default certs -->
    <div class="cert-card">
      <div class="cert-img-wrap" id="cimg-0">
        <div class="cert-img-placeholder">
          <div class="upload-icon">🪟</div>
          <div>Microsoft Power BI</div>
          <label class="cert-upload-btn">Upload Certificate
            <input type="file" accept="image/*" style="display:none" onchange="uploadCertImg(event,0)">
          </label>
        </div>
      </div>
      <div class="cert-body">
        <div class="cert-org">Microsoft</div>
        <div class="cert-name">PL-300: Power BI Data Analyst Associate</div>
        <div class="cert-yr">✦ Add your year</div>
        <button class="cert-view-btn" onclick="viewCertImg(0)" style="display:none" id="cvbtn-0">🔍 View Full Size</button>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-img-wrap" id="cimg-1">
        <div class="cert-img-placeholder">
          <div class="upload-icon">🐍</div>
          <div>Google Analytics</div>
          <label class="cert-upload-btn">Upload Certificate
            <input type="file" accept="image/*" style="display:none" onchange="uploadCertImg(event,1)">
          </label>
        </div>
      </div>
      <div class="cert-body">
        <div class="cert-org">Google / Coursera</div>
        <div class="cert-name">Google Data Analytics Professional Certificate</div>
        <div class="cert-yr">✦ Add your year</div>
        <button class="cert-view-btn" onclick="viewCertImg(1)" style="display:none" id="cvbtn-1">🔍 View Full Size</button>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-img-wrap" id="cimg-2">
        <div class="cert-img-placeholder">
          <div class="upload-icon">📊</div>
          <div>Tableau Specialist</div>
          <label class="cert-upload-btn">Upload Certificate
            <input type="file" accept="image/*" style="display:none" onchange="uploadCertImg(event,2)">
          </label>
        </div>
      </div>
      <div class="cert-body">
        <div class="cert-org">Tableau</div>
        <div class="cert-name">Tableau Desktop Specialist</div>
        <div class="cert-yr">✦ Add your year</div>
        <button class="cert-view-btn" onclick="viewCertImg(2)" style="display:none" id="cvbtn-2">🔍 View Full Size</button>
      </div>
    </div>
    <!-- Add new cert card -->
    <div class="add-cert-card" onclick="openModal('certModal')">
      <span>＋</span>
      <div>Add Certification</div>
    </div>
  </div>
</section>
</div>

<!-- ═══ PAGE: AWARDS ═══ -->
<div class="page" id="page-awards">
<section class="sec">
  <p class="sec-label">Recognition</p>
  <h2 class="sec-h">Awards &amp; Appreciation</h2>
  <div class="abar"></div>
  <p class="sec-sub">Achievements and recognition received throughout my career. Upload your award certificates below.</p>
  <div class="awards-grid" id="awardsGrid">
    <!-- Default award placeholder -->
    <div class="award-card">
      <div class="award-img-wrap" id="aimg-0">
        <div class="award-img-placeholder">
          <span style="font-size:2rem">🏆</span>
          <div>Star Performer Award</div>
          <label class="cert-upload-btn">Upload Image
            <input type="file" accept="image/*" style="display:none" onchange="uploadAwardImg(event,0)">
          </label>
        </div>
      </div>
      <div class="award-body">
        <div class="award-badge">🏆 Recognition</div>
        <div class="award-title">Star Performer Award</div>
        <div class="award-desc">Add a description of this award and what you achieved to earn this recognition.</div>
        <button class="cert-view-btn" onclick="viewAwardImg(0)" style="display:none" id="avbtn-0">🔍 View Certificate</button>
      </div>
    </div>
    <div class="award-card">
      <div class="award-img-wrap" id="aimg-1">
        <div class="award-img-placeholder">
          <span style="font-size:2rem">🌟</span>
          <div>Appreciation Letter</div>
          <label class="cert-upload-btn">Upload Image
            <input type="file" accept="image/*" style="display:none" onchange="uploadAwardImg(event,1)">
          </label>
        </div>
      </div>
      <div class="award-body">
        <div class="award-badge">🌟 Appreciation</div>
        <div class="award-title">Client Appreciation Letter</div>
        <div class="award-desc">Add a description of this appreciation and the context in which it was received.</div>
        <button class="cert-view-btn" onclick="viewAwardImg(1)" style="display:none" id="avbtn-1">🔍 View Letter</button>
      </div>
    </div>
    <!-- Add new award -->
    <div class="add-award-card" onclick="openModal('awardModal')">
      <span>＋</span>
      <div>Add Award / Appreciation</div>
    </div>
  </div>
</section>
</div>

<footer>
  <span>© 2025 Akash Kourav</span>
  <span style="color:rgba(255,255,255,.12)">Built with precision &amp; purpose</span>
</footer>

<script>
let profilePictureData = null;
let resumeFileData = null;

// ── PAGE SWITCHING ──
function showPage(id, tabEl) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
  document.getElementById('page-' + id).classList.add('active');
  if (tabEl) tabEl.classList.add('active');
  window.scrollTo({top: 0, behavior: 'smooth'});
}

// ── PROFILE PICTURE MODAL ──
function openProfileModal() {
  document.getElementById('profileModal').classList.add('open');
}
function closeProfileModal() {
  document.getElementById('profileModal').classList.remove('open');
  document.getElementById('profileFile').value = '';
  document.getElementById('profilePreview').innerHTML = '';
}
function previewProfileImg() {
  const file = document.getElementById('profileFile').files[0];
  if (!file) return;
  const reader = new FileReader();
  reader.onload = function(e) {
    const preview = document.getElementById('profilePreview');
    preview.innerHTML = `<img src="${e.target.result}" alt="Preview">`;
    profilePictureData = e.target.result;
  };
  reader.readAsDataURL(file);
}
function saveProfilePicture() {
  if (!profilePictureData) {
    alert('Please select an image first');
    return;
  }
  document.getElementById('profileImg').src = profilePictureData;
  localStorage.setItem('profilePicture', profilePictureData);
  closeProfileModal();
  alert('Profile picture saved successfully!');
}

// ── RESUME MODAL ──
function openResumeModal() {
  document.getElementById('resumeModal').classList.add('open');
}
function closeResumeModal() {
  document.getElementById('resumeModal').classList.remove('open');
  document.getElementById('resumeFile').value = '';
  document.getElementById('resumePreview').innerHTML = '';
}
function previewResume() {
  const file = document.getElementById('resumeFile').files[0];
  if (!file) return;
  const fileName = file.name;
  const preview = document.getElementById('resumePreview');
  preview.innerHTML = `<div style="text-align:center;color:var(--muted);"><div style="font-size:2rem;margin-bottom:.5rem;">📄</div><div>${fileName}</div></div>`;
  const reader = new FileReader();
  reader.onload = function(e) {
    resumeFileData = {name: fileName, data: e.target.result};
  };
  reader.readAsDataURL(file);
}
function saveResume() {
  if (!resumeFileData) {
    alert('Please select a resume file first');
    return;
  }
  localStorage.setItem('resumeFile', JSON.stringify(resumeFileData));
  alert('Resume saved successfully!');
  closeResumeModal();
}

// Load saved data on page load
window.addEventListener('load', function() {
  const savedProfile = localStorage.getItem('profilePicture');
  if (savedProfile) {
    document.getElementById('profileImg').src = savedProfile;
  }
});

// ── MODALS ──
function openModal(id) { document.getElementById(id).classList.add('open'); }
function closeModal(id) { document.getElementById(id).classList.remove('open'); }
document.querySelectorAll('.modal-overlay').forEach(m => {
  m.addEventListener('click', e => { if (e.target === m) m.classList.remove('open'); });
});

// ── LIGHTBOX ──
let certImgs = {}, awardImgs = {};
function openLightbox(src) {
  document.getElementById('lb-img').src = src;
  document.getElementById('lightbox').classList.add('open');
}
function closeLightbox() { document.getElementById('lightbox').classList.remove('open'); }
function closeLB(e) { if (e.target === document.getElementById('lightbox')) closeLightbox(); }

// ── CERT IMAGE UPLOAD (default cards) ──
function uploadCertImg(e, idx) {
  const file = e.target.files[0]; if (!file) return;
  const reader = new FileReader();
  reader.onload = function(ev) {
    certImgs[idx] = ev.target.result;
    const wrap = document.getElementById('cimg-' + idx);
    wrap.innerHTML = '<img src="' + ev.target.result + '" alt="Certificate" onclick="openLightbox(certImgs[' + idx + '])" style="cursor:zoom-in;">';
    document.getElementById('cvbtn-' + idx).style.display = 'inline-flex';
  };
  reader.readAsDataURL(file);
}
function viewCertImg(idx) { if (certImgs[idx]) openLightbox(certImgs[idx]); }

// ── AWARD IMAGE UPLOAD (default cards) ──
function uploadAwardImg(e, idx) {
  const file = e.target.files[0]; if (!file) return;
  const reader = new FileReader();
  reader.onload = function(ev) {
    awardImgs[idx] = ev.target.result;
    const wrap = document.getElementById('aimg-' + idx);
    wrap.innerHTML = '<img src="' + ev.target.result + '" alt="Award" onclick="openLightbox(awardImgs[' + idx + '])" style="cursor:zoom-in;">';
    document.getElementById('avbtn-' + idx).style.display = 'inline-flex';
  };
  reader.readAsDataURL(file);
}
function viewAwardImg(idx) { if (awardImgs[idx]) openLightbox(awardImgs[idx]); }

// ── MODAL IMAGE PREVIEW ──
function previewImg(e, areaId, hiddenId) {
  const file = e.target.files[0]; if (!file) return;
  const reader = new FileReader();
  reader.onload = function(ev) {
    document.getElementById(hiddenId).value = ev.target.result;
    const area = document.getElementById(areaId);
    let img = area.querySelector('img');
    if (!img) { img = document.createElement('img'); area.appendChild(img); }
    img.src = ev.target.result;
    img.style.cssText = 'position:absolute;inset:0;width:100%;height:100%;object-fit:cover;border-radius:10px;';
  };
  reader.readAsDataURL(file);
}

// ── SAVE NEW CERT ──
let certCount = 3;
function saveCert() {
  const org = document.getElementById('c-org').value.trim();
  const name = document.getElementById('c-name').value.trim();
  const year = document.getElementById('c-year').value.trim();
  const imgData = document.getElementById('cImgData').value;
  if (!name) { alert('Please enter certification name'); return; }
  const idx = 'new_' + certCount++;
  certImgs[idx] = imgData;
  const grid = document.getElementById('certGrid');
  const addBtn = grid.querySelector('.add-cert-card');
  const card = document.createElement('div');
  card.className = 'cert-card';
  const imgSection = imgData
    ? `<div class="cert-img-wrap" id="cimg-${idx}" style="cursor:zoom-in;" onclick="openLightbox(certImgs['${idx}'])"><img src="${imgData}" alt="Certificate"></div>`
    : `<div class="cert-img-wrap" id="cimg-${idx}"><div class="cert-img-placeholder"><div class="upload-icon">🎓</div><div>${name}</div></div></div>`;
  card.innerHTML = imgSection + `
    <div class="cert-body">
      <div class="cert-org">${org || 'Issuer'}</div>
      <div class="cert-name">${name}</div>
      <div class="cert-yr">${year ? '✦ ' + year : '✦ Year'}</div>
      ${imgData ? `<button class="cert-view-btn" onclick="openLightbox(certImgs['${idx}'])">🔍 View Full Size</button>` : ''}
    </div>`;
  grid.insertBefore(card, addBtn);
  ['c-org','c-name','c-year'].forEach(id => document.getElementById(id).value = '');
  document.getElementById('cImgData').value = '';
  const area = document.getElementById('cImgArea');
  const img = area.querySelector('img'); if (img) img.remove();
  closeModal('certModal');
}

// ── SAVE NEW AWARD ──
let awardCount = 2;
function saveAward() {
  const title = document.getElementById('a-title').value.trim();
  const by = document.getElementById('a-by').value.trim();
  const desc = document.getElementById('a-desc').value.trim();
  const imgData = document.getElementById('aImgData').value;
  if (!title) { alert('Please enter award title'); return; }
  const idx = 'na_' + awardCount++;
  awardImgs[idx] = imgData;
  const grid = document.getElementById('awardsGrid');
  const addBtn = grid.querySelector('.add-award-card');
  const card = document.createElement('div');
  card.className = 'award-card';
  const imgSection = imgData
    ? `<div class="award-img-wrap" id="aimg-${idx}" style="cursor:zoom-in;" onclick="openLightbox(awardImgs['${idx}'])"><img src="${imgData}" alt="Award"></div>`
    : `<div class="award-img-wrap" id="aimg-${idx}"><div class="award-img-placeholder"><span style="font-size:2rem">🏆</span><div>${title}</div></div></div>`;
  card.innerHTML = imgSection + `
    <div class="award-body">
      <div class="award-badge">🏆 ${by || 'Recognition'}</div>
      <div class="award-title">${title}</div>
      <div class="award-desc">${desc || 'Award description.'}</div>
      ${imgData ? `<button class="cert-view-btn" onclick="openLightbox(awardImgs['${idx}'])">🔍 View Certificate</button>` : ''}
    </div>`;
  grid.insertBefore(card, addBtn);
  ['a-title','a-by','a-desc'].forEach(id => document.getElementById(id).value = '');
  document.getElementById('aImgData').value = '';
  const area = document.getElementById('aImgArea');
  const img = area.querySelector('img'); if (img) img.remove();
  closeModal('awardModal');
}

// ── DYNAMIC UPLOAD (newly added cards) ──
function uploadCertImgDyn(e, idx) {
  const file = e.target.files[0]; if (!file) return;
  const reader = new FileReader();
  reader.onload = ev => {
    certImgs[idx] = ev.target.result;
    const wrap = document.getElementById('cimg-' + idx);
    wrap.style.cursor = 'zoom-in';
    wrap.onclick = () => openLightbox(certImgs[idx]);
    wrap.innerHTML = '<img src="' + ev.target.result + '" alt="Certificate">';
  };
  reader.readAsDataURL(file);
}
function uploadAwardImgDyn(e, idx) {
  const file = e.target.files[0]; if (!file) return;
  const reader = new FileReader();
  reader.onload = ev => {
    awardImgs[idx] = ev.target.result;
    const wrap = document.getElementById('aimg-' + idx);
    wrap.style.cursor = 'zoom-in';
    wrap.onclick = () => openLightbox(awardImgs[idx]);
    wrap.innerHTML = '<img src="' + ev.target.result + '" alt="Award">';
  };
  reader.readAsDataURL(file);
}

// Drag and drop for profile modal
const profileDropZone = document.getElementById('profileDropZone');
if (profileDropZone) {
  profileDropZone.addEventListener('dragover', (e) => {
    e.preventDefault();
    profileDropZone.style.background = 'rgba(240,90,40,.15)';
  });
  profileDropZone.addEventListener('dragleave', () => {
    profileDropZone.style.background = 'rgba(240,90,40,.05)';
  });
  profileDropZone.addEventListener('drop', (e) => {
    e.preventDefault();
    profileDropZone.style.background = 'rgba(240,90,40,.05)';
    const file = e.dataTransfer.files[0];
    if (file && file.type.startsWith('image')) {
      document.getElementById('profileFile').files = e.dataTransfer.files;
      previewProfileImg();
    }
  });
}

// Drag and drop for resume modal
const resumeDropZone = document.getElementById('resumeDropZone');
if (resumeDropZone) {
  resumeDropZone.addEventListener('dragover', (e) => {
    e.preventDefault();
    resumeDropZone.style.background = 'rgba(240,90,40,.15)';
  });
  resumeDropZone.addEventListener('dragleave', () => {
    resumeDropZone.style.background = 'rgba(240,90,40,.05)';
  });
  resumeDropZone.addEventListener('drop', (e) => {
    e.preventDefault();
    resumeDropZone.style.background = 'rgba(240,90,40,.05)';
    const file = e.dataTransfer.files[0];
    if (file) {
      document.getElementById('resumeFile').files = e.dataTransfer.files;
      previewResume();
    }
  });
}
</script>
</body>
</html>
