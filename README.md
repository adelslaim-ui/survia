[index.html.html](https://github.com/user-attachments/files/27019667/index.html.html)
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Survia — عرض المستثمر 2026</title>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;500;600;700;900&family=Tajawal:wght@300;400;500;700;800;900&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<style>
*{box-sizing:border-box;margin:0;padding:0;scroll-behavior:smooth;}
:root{
  --ink:#050810;--navy:#080D1A;--navy2:#0D1528;
  --gold:#C9A84C;--gold2:#E8C96A;
  --gold-dim:rgba(201,168,76,0.12);--gold-line:rgba(201,168,76,0.25);
  --white:#F5F3EE;--dim:rgba(245,243,238,0.5);--faint:rgba(245,243,238,0.15);
  --border:rgba(201,168,76,0.18);--bdr2:rgba(245,243,238,0.07);
  --teal:#5DCAA5;--teal-dim:rgba(93,202,165,0.1);--teal-line:rgba(93,202,165,0.25);
}
html{scroll-snap-type:y mandatory;overflow-y:scroll;}
body{font-family:'Cairo',sans-serif;background:var(--ink);color:var(--white);overflow-x:hidden;}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:100;padding:14px 44px;display:flex;align-items:center;justify-content:space-between;background:rgba(5,8,16,0.88);backdrop-filter:blur(14px);border-bottom:1px solid var(--border);}
.nav-logo{display:flex;align-items:center;gap:10px;}
.logo-mark{width:32px;height:32px;border-radius:8px;background:var(--gold);display:flex;align-items:center;justify-content:center;font-size:14px;font-weight:900;color:var(--ink);}
.logo-name{font-size:17px;font-weight:700;color:var(--white);}
.nav-right{display:flex;align-items:center;gap:14px;}
.slide-no{font-size:11px;color:var(--dim);letter-spacing:.5px;}
.cta-nav{background:var(--gold);color:var(--ink);border:none;border-radius:8px;padding:8px 20px;font-size:13px;font-weight:700;cursor:pointer;font-family:'Cairo',sans-serif;transition:opacity .2s;}
.cta-nav:hover{opacity:.85;}

/* SECTIONS */
section{min-height:100vh;scroll-snap-align:start;display:flex;flex-direction:column;justify-content:center;position:relative;overflow:hidden;padding:88px 7% 56px;}

/* DECORATIVE */
.dg{position:absolute;inset:0;background-image:linear-gradient(rgba(201,168,76,0.035) 1px,transparent 1px),linear-gradient(90deg,rgba(201,168,76,0.035) 1px,transparent 1px);background-size:60px 60px;pointer-events:none;}
.dc{position:absolute;border-radius:50%;border:1px solid var(--border);pointer-events:none;}
.glow{position:absolute;border-radius:50%;filter:blur(80px);pointer-events:none;}

/* REVEAL */
.r{opacity:0;transform:translateY(24px);transition:opacity .65s ease,transform .65s ease;}
.r.v{opacity:1;transform:translateY(0);}
.r.d1{transition-delay:.1s;}.r.d2{transition-delay:.2s;}.r.d3{transition-delay:.3s;}.r.d4{transition-delay:.4s;}.r.d5{transition-delay:.5s;}

/* HERO */
#hero{align-items:center;text-align:center;}
#hero .glow{width:500px;height:500px;background:var(--gold);top:50%;left:50%;transform:translate(-50%,-50%);opacity:.06;}
.hero-badge{display:inline-flex;align-items:center;gap:8px;border:1px solid var(--gold-line);border-radius:20px;padding:6px 18px;font-size:12px;color:var(--gold);margin-bottom:26px;background:var(--gold-dim);}
.bdot{width:6px;height:6px;border-radius:50%;background:var(--gold);animation:pulse 1.6s infinite;}
@keyframes pulse{0%,100%{opacity:1;}50%{opacity:.25;}}
.hero-title{font-family:'Tajawal',sans-serif;font-size:clamp(44px,6vw,76px);font-weight:900;line-height:1.12;margin-bottom:18px;letter-spacing:-1px;}
.hero-title span{color:var(--gold);}
.hero-sub{font-size:clamp(14px,1.8vw,18px);color:var(--dim);max-width:640px;margin:0 auto 30px;line-height:1.85;}
.hero-formula{display:inline-flex;align-items:center;gap:14px;margin-bottom:32px;padding:14px 26px;background:rgba(255,255,255,0.03);border:1px solid var(--gold-line);border-radius:14px;flex-wrap:wrap;justify-content:center;}
.hf-item{display:flex;align-items:center;gap:8px;font-size:14px;font-weight:600;color:var(--white);}
.hf-ico{width:32px;height:32px;border-radius:8px;background:var(--gold-dim);display:flex;align-items:center;justify-content:center;font-size:15px;}
.hf-plus{font-size:20px;color:var(--gold);font-weight:900;}
.hf-eq{font-size:20px;color:var(--gold);font-weight:900;}
.hf-result{color:var(--gold);font-weight:900;font-family:'Tajawal',sans-serif;}
.hero-ask{display:inline-flex;align-items:center;gap:0;background:var(--gold-dim);border:1px solid var(--gold-line);border-radius:14px;overflow:hidden;margin-bottom:32px;}
.ask-item{padding:16px 30px;text-align:center;border-left:1px solid var(--gold-line);}
.ask-item:last-child{border-left:none;}
.ask-label{font-size:10px;color:var(--dim);text-transform:uppercase;letter-spacing:.7px;margin-bottom:4px;}
.ask-val{font-size:24px;font-weight:900;color:var(--gold);font-family:'Tajawal',sans-serif;}
.hero-stats{display:flex;gap:0;border:1px solid var(--border);border-radius:14px;overflow:hidden;}
.hs{padding:18px 24px;text-align:center;border-left:1px solid var(--border);}
.hs:last-child{border-left:none;}
.hs .v{font-size:20px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;}
.hs .l{font-size:10px;color:var(--dim);margin-top:3px;}

/* SECTION HEADER */
.sec-label{font-size:10px;font-weight:700;letter-spacing:2px;color:var(--gold);text-transform:uppercase;margin-bottom:8px;}
.sec-title{font-family:'Tajawal',sans-serif;font-size:clamp(28px,3.8vw,46px);font-weight:900;line-height:1.2;margin-bottom:14px;}
.sec-desc{font-size:14px;color:var(--dim);line-height:1.9;max-width:680px;}

/* CARDS */
.card{background:rgba(255,255,255,0.025);border:1px solid var(--border);border-radius:14px;padding:22px 20px;transition:border-color .25s;}
.card:hover{border-color:var(--gold);}
.badge{display:inline-block;padding:2px 10px;border-radius:5px;font-size:11px;font-weight:700;}
.b-gold{background:var(--gold-dim);color:var(--gold);border:1px solid var(--gold-line);}
.b-dim{background:rgba(255,255,255,0.04);color:var(--dim);border:1px solid var(--bdr2);}
.pb{height:5px;border-radius:3px;background:rgba(255,255,255,0.06);overflow:hidden;}
.pf{height:5px;border-radius:3px;}

/* PROBLEM */
.prob-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:36px;}
.pc{position:relative;overflow:hidden;}
.pc::before{content:'';position:absolute;top:0;right:0;width:50px;height:50px;background:var(--gold-dim);border-radius:0 0 0 50px;}
.pc-num{font-size:10px;font-weight:700;color:var(--gold);letter-spacing:1px;margin-bottom:10px;}
.pc-title{font-size:16px;font-weight:700;margin-bottom:8px;line-height:1.4;}
.pc-desc{font-size:12px;color:var(--dim);line-height:1.75;}
.pc-stat{font-size:38px;font-weight:900;color:var(--gold);font-family:'Tajawal',sans-serif;margin-top:14px;}
.pc-stat-lbl{font-size:10px;color:var(--dim);margin-top:2px;}

/* SOLUTION — TWO PILLARS */
.pillars{display:grid;grid-template-columns:1fr 1fr;gap:20px;margin-top:24px;}
.pillar{background:rgba(255,255,255,0.025);border:1px solid var(--border);border-radius:16px;padding:24px;position:relative;}
.pillar-tech{border-color:var(--gold-line);}
.pillar-human{border-color:var(--teal-line);background:linear-gradient(180deg,rgba(93,202,165,0.04) 0%,rgba(255,255,255,0.025) 100%);}
.pillar-head{display:flex;align-items:center;gap:12px;margin-bottom:6px;}
.pillar-ico{width:44px;height:44px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:20px;}
.pillar-tech .pillar-ico{background:var(--gold-dim);border:1px solid var(--gold-line);}
.pillar-human .pillar-ico{background:var(--teal-dim);border:1px solid var(--teal-line);}
.pillar-tag{font-size:10px;font-weight:700;letter-spacing:1px;margin-bottom:3px;}
.pillar-tech .pillar-tag{color:var(--gold);}
.pillar-human .pillar-tag{color:var(--teal);}
.pillar-title{font-size:20px;font-weight:800;font-family:'Tajawal',sans-serif;}
.pillar-desc{font-size:12px;color:var(--dim);line-height:1.75;margin:10px 0 16px;}
.pillar-list{display:flex;flex-direction:column;gap:10px;}
.pl-item{display:flex;align-items:flex-start;gap:10px;padding:10px 12px;background:rgba(255,255,255,0.02);border:1px solid var(--bdr2);border-radius:10px;}
.pl-ico{width:30px;height:30px;border-radius:7px;display:flex;align-items:center;justify-content:center;font-size:14px;flex-shrink:0;}
.pillar-tech .pl-ico{background:var(--gold-dim);}
.pillar-human .pl-ico{background:var(--teal-dim);}
.pl-name{font-size:13px;font-weight:700;margin-bottom:2px;}
.pl-sub{font-size:11px;color:var(--dim);line-height:1.55;}
.formula-row{display:flex;align-items:center;justify-content:center;gap:10px;margin-top:22px;padding:14px;background:var(--gold-dim);border:1px solid var(--gold-line);border-radius:12px;flex-wrap:wrap;}
.fr-text{font-size:14px;font-weight:600;color:var(--white);}
.fr-text .g{color:var(--gold);font-weight:800;}
.fr-text .t{color:var(--teal);font-weight:800;}

/* JOURNEY */
.tiers{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:28px;}
.tier{background:rgba(255,255,255,0.025);border:1px solid var(--border);border-radius:16px;padding:22px 20px;position:relative;display:flex;flex-direction:column;}
.tier.featured{border-color:var(--gold);background:linear-gradient(180deg,rgba(201,168,76,0.08) 0%,rgba(255,255,255,0.025) 100%);}
.tier-tag{position:absolute;top:-10px;right:20px;background:var(--gold);color:var(--ink);font-size:10px;font-weight:800;padding:4px 12px;border-radius:6px;letter-spacing:.5px;}
.tier-name{font-size:11px;font-weight:700;color:var(--gold);letter-spacing:1.5px;margin-bottom:6px;}
.tier-title{font-size:19px;font-weight:800;font-family:'Tajawal',sans-serif;margin-bottom:4px;}
.tier-for{font-size:11px;color:var(--dim);margin-bottom:16px;}
.tier-price{padding:12px 0;border-top:1px solid var(--border);border-bottom:1px solid var(--border);margin-bottom:14px;}
.tier-price .amt{font-size:22px;font-weight:900;color:var(--gold);font-family:'Tajawal',sans-serif;}
.tier-price .period{font-size:11px;color:var(--dim);margin-top:2px;}
.tier-feat{display:flex;flex-direction:column;gap:8px;flex:1;}
.tf{display:flex;align-items:flex-start;gap:8px;font-size:12px;color:var(--white);line-height:1.55;}
.tf::before{content:'✓';color:var(--gold);font-weight:900;flex-shrink:0;font-size:13px;}
.tf.off{color:var(--dim);opacity:.5;}
.tf.off::before{content:'—';color:var(--dim);}
.tf strong{color:var(--gold);font-weight:700;}

/* JOURNEY STAGES */
.stages{margin-top:26px;padding:22px 20px;background:rgba(255,255,255,0.02);border:1px solid var(--border);border-radius:14px;}
.stages-head{font-size:13px;font-weight:700;color:var(--gold);margin-bottom:14px;text-align:center;letter-spacing:.5px;}
.stage-row{display:grid;grid-template-columns:repeat(7,1fr);gap:8px;position:relative;}
.stage-row::before{content:'';position:absolute;top:26px;right:5%;left:5%;height:1px;background:var(--gold-line);z-index:0;}
.stage{position:relative;z-index:1;text-align:center;}
.stage-num{width:40px;height:40px;border-radius:50%;background:var(--navy);border:2px solid var(--gold-line);display:flex;align-items:center;justify-content:center;margin:0 auto 8px;font-size:14px;font-weight:900;color:var(--gold);font-family:'Tajawal',sans-serif;}
.stage-num.hi{background:var(--gold);color:var(--ink);border-color:var(--gold);}
.stage-name{font-size:11px;font-weight:700;line-height:1.4;margin-bottom:3px;}
.stage-by{font-size:9px;color:var(--dim);line-height:1.4;}
.stage-by .h{color:var(--teal);font-weight:700;}
.stage-by .a{color:var(--gold);font-weight:700;}

/* TEAM DEEPER */
.experts-row{display:grid;grid-template-columns:repeat(5,1fr);gap:10px;margin-top:18px;}
.expert{background:rgba(93,202,165,0.04);border:1px solid var(--teal-line);border-radius:10px;padding:14px 12px;text-align:center;}
.expert-ico{font-size:20px;margin-bottom:8px;}
.expert-role{font-size:11px;font-weight:700;color:var(--teal);margin-bottom:4px;}
.expert-task{font-size:10px;color:var(--dim);line-height:1.5;}

/* ROADMAP */
.phases{display:grid;grid-template-columns:repeat(3,1fr);gap:0;border:1px solid var(--border);border-radius:14px;overflow:hidden;margin-top:32px;}
.phase{padding:24px 20px;border-left:1px solid var(--border);}
.phase:last-child{border-left:none;}
.phase.hl{background:var(--gold-dim);}
.ph-num{font-size:10px;font-weight:700;color:var(--gold);letter-spacing:1px;margin-bottom:5px;}
.ph-period{font-size:12px;color:var(--dim);margin-bottom:12px;display:flex;align-items:center;gap:6px;}
.ph-period::before{content:'';display:inline-block;width:16px;height:1px;background:var(--gold);}
.ph-title{font-size:17px;font-weight:700;margin-bottom:12px;line-height:1.3;}
.ph-items{display:flex;flex-direction:column;gap:7px;}
.pi{display:flex;align-items:flex-start;gap:7px;font-size:12px;color:var(--dim);line-height:1.6;}
.pi::before{content:'◆';font-size:6px;color:var(--gold);margin-top:5px;flex-shrink:0;}
.ph-kpi{margin-top:16px;padding-top:12px;border-top:1px solid var(--border);}
.ph-kpi .k{font-size:10px;color:var(--dim);margin-bottom:2px;}
.ph-kpi .v{font-size:18px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;}
.timeline-row{display:flex;align-items:center;margin-top:16px;background:rgba(255,255,255,0.02);border:1px solid var(--border);border-radius:10px;padding:14px 20px;gap:0;}
.tl-item{flex:1;text-align:center;position:relative;}
.tl-item::after{content:'';position:absolute;top:8px;left:0;right:0;height:1px;background:var(--gold-line);z-index:0;}
.tl-item:last-child::after{display:none;}
.tl-dot{width:16px;height:16px;border-radius:50%;background:var(--gold);border:2px solid var(--navy);position:relative;z-index:1;margin:0 auto 6px;}
.tl-dot.e{background:rgba(255,255,255,0.12);}
.tl-lbl{font-size:9px;color:var(--dim);}

/* MARKET */
.market-layout{display:grid;grid-template-columns:1fr 1fr;gap:36px;align-items:start;margin-top:28px;}
.mc{display:flex;align-items:center;gap:14px;padding:16px 18px;}
.mc-icon{font-size:26px;width:48px;height:48px;border-radius:10px;background:var(--gold-dim);display:flex;align-items:center;justify-content:center;flex-shrink:0;}
.mc-val{font-size:20px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;}
.mc-lbl{font-size:11px;color:var(--dim);margin-top:2px;}
.tg{padding:14px 18px;}
.tg-top{display:flex;justify-content:space-between;align-items:center;margin-bottom:8px;}
.tg-name{font-size:13px;font-weight:600;}
.tg-cnt{font-size:16px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;}
.g2{display:grid;grid-template-columns:1fr 1fr;gap:10px;}

/* FINANCIAL */
.fin-layout{display:grid;grid-template-columns:1fr 1fr;gap:36px;align-items:start;margin-top:24px;}
.year-row{display:flex;justify-content:space-between;align-items:center;padding:13px 18px;border-bottom:1px solid var(--border);}
.year-row:last-child{border-bottom:none;}
.yr-name{font-size:13px;font-weight:600;}
.yr-sub{font-size:11px;color:var(--dim);margin-top:2px;}
.yr-val{font-size:18px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;text-align:left;}
.yr-note{font-size:10px;color:var(--dim);text-align:left;margin-top:2px;}
.yr-bar{flex:1;margin:0 16px;}
.chart-wrap{background:rgba(255,255,255,0.02);border:1px solid var(--border);border-radius:12px;padding:18px;}
.pricing-note{background:rgba(255,255,255,0.03);border:1px solid var(--gold-line);border-radius:10px;padding:14px 16px;margin-top:12px;}
.pn-title{font-size:12px;font-weight:700;color:var(--gold);margin-bottom:5px;}
.pn-body{font-size:12px;color:var(--dim);line-height:1.7;}
.rev-mix{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-top:14px;}
.rm{background:rgba(255,255,255,0.02);border:1px solid var(--border);border-radius:10px;padding:12px;text-align:center;}
.rm .p{font-size:20px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;}
.rm .n{font-size:11px;color:var(--white);margin-top:4px;font-weight:600;}
.rm .d{font-size:10px;color:var(--dim);margin-top:2px;}

/* INVESTMENT */
.inv-layout{display:grid;grid-template-columns:1fr 1.1fr;gap:40px;align-items:center;margin-top:28px;}
.inv-circle{width:190px;height:190px;border-radius:50%;border:2px solid var(--gold-line);display:flex;flex-direction:column;align-items:center;justify-content:center;margin:0 auto 20px;background:var(--gold-dim);position:relative;}
.inv-circle::before{content:'';position:absolute;inset:-8px;border-radius:50%;border:1px solid var(--border);}
.inv-circle::after{content:'';position:absolute;inset:-16px;border-radius:50%;border:1px solid rgba(201,168,76,0.08);}
.inv-amount{font-size:32px;font-weight:900;color:var(--gold);font-family:'Tajawal',sans-serif;}
.inv-label{font-size:11px;color:var(--dim);margin-top:3px;}
.ib{padding:14px 16px;margin-bottom:8px;}
.ib-top{display:flex;justify-content:space-between;align-items:center;margin-bottom:8px;}
.ib-name{font-size:13px;font-weight:600;}
.ib-pct{font-size:11px;color:var(--dim);}
.ib-val{font-size:16px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;}
.returns{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-top:18px;}
.ret{text-align:center;background:rgba(255,255,255,0.02);border:1px solid var(--border);border-radius:10px;padding:12px;}
.ret .v{font-size:17px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;}
.ret .l{font-size:10px;color:var(--dim);margin-top:3px;}

/* TEAM */
.team-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:14px;margin-top:32px;}
.tm{padding:22px 20px;text-align:center;transition:border-color .25s;}
.tm:hover{border-color:var(--gold);}
.tm-av{width:60px;height:60px;border-radius:50%;background:var(--gold-dim);border:2px solid var(--gold-line);display:flex;align-items:center;justify-content:center;font-size:20px;font-weight:800;color:var(--gold);margin:0 auto 12px;font-family:'Tajawal',sans-serif;}
.tm-name{font-size:15px;font-weight:700;margin-bottom:3px;}
.tm-role{font-size:11px;color:var(--gold);margin-bottom:6px;font-weight:600;}
.tm-desc{font-size:12px;color:var(--dim);line-height:1.7;}
.tm-exp{display:inline-block;margin-top:8px;font-size:10px;padding:2px 8px;border-radius:4px;background:var(--gold-dim);color:var(--gold);border:1px solid var(--gold-line);}

/* CTA */
#cta{align-items:center;text-align:center;}
#cta .glow{width:350px;height:350px;background:var(--gold);top:50%;left:50%;transform:translate(-50%,-50%);opacity:.08;}
.cta-title{font-family:'Tajawal',sans-serif;font-size:clamp(38px,5vw,64px);font-weight:900;line-height:1.2;margin-bottom:18px;}
.cta-title span{color:var(--gold);}
.cta-sub{font-size:15px;color:var(--dim);max-width:500px;margin:0 auto 36px;line-height:1.9;}
.cta-btns{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;}
.btn-gold{background:var(--gold);color:var(--ink);border:none;border-radius:12px;padding:15px 34px;font-size:14px;font-weight:800;cursor:pointer;font-family:'Cairo',sans-serif;transition:all .2s;}
.btn-gold:hover{background:var(--gold2);transform:translateY(-2px);}
.btn-outline{background:transparent;color:var(--gold);border:1px solid var(--gold-line);border-radius:12px;padding:14px 28px;font-size:13px;font-weight:600;cursor:pointer;font-family:'Cairo',sans-serif;transition:all .2s;}
.btn-outline:hover{background:var(--gold-dim);}
.contact-row{display:flex;gap:24px;justify-content:center;margin-top:36px;flex-wrap:wrap;}
.ct-item{display:flex;align-items:center;gap:8px;font-size:13px;color:var(--dim);}
.ct-item .ico{color:var(--gold);}

::-webkit-scrollbar{width:3px;}
::-webkit-scrollbar-thumb{background:rgba(201,168,76,0.3);border-radius:3px;}
@media print{nav,.glow{display:none!important;}section{min-height:auto;page-break-after:always;padding:40px 7%;}html{scroll-snap-type:none;}}
@media (max-width:900px){
  .prob-grid,.pillars,.tiers,.phases,.market-layout,.fin-layout,.inv-layout,.team-grid{grid-template-columns:1fr!important;}
  .stage-row{grid-template-columns:repeat(3,1fr);gap:14px;}
  .stage-row::before{display:none;}
  .experts-row{grid-template-columns:repeat(2,1fr);}
  .hero-formula{flex-direction:column;gap:8px;}
  .hero-ask,.hero-stats{flex-wrap:wrap;}
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">
    <div class="logo-mark">S</div>
    <div class="logo-name">Survia</div>
  </div>
  <div class="nav-right">
    <div class="slide-no" id="slideNo">1 / 10</div>
    <button class="cta-nav" onclick="document.getElementById('investment').scrollIntoView({behavior:'smooth'})">طلب الاستثمار</button>
  </div>
</nav>

<!-- ══════════ HERO ══════════ -->
<section id="hero">
  <div class="dg"></div>
  <div class="dc" style="width:480px;height:480px;top:50%;left:50%;transform:translate(-50%,-50%);"></div>
  <div class="dc" style="width:680px;height:680px;top:50%;left:50%;transform:translate(-50%,-50%);opacity:.5;"></div>
  <div class="glow"></div>
  <div class="r">
    <div class="hero-badge"><span class="bdot"></span>منصة ذكاء بحثي — AI + فريق خبراء · المملكة العربية السعودية 2026</div>
  </div>
  <div class="r d1">
    <h1 class="hero-title">نصنع لك <span>القرار الصحيح</span><br>بالسؤال الصحيح</h1>
  </div>
  <div class="r d2">
    <p class="hero-sub">Survia ليست مجرد منصة — هي فريق بحث متكامل مدعوم بالذكاء الاصطناعي. نصمم الدراسة، نكتب الأسئلة، نجمع البيانات عبر 7 قنوات، ونحوّلها إلى توصيات استراتيجية قابلة للتنفيذ.</p>
  </div>
  <div class="r d3">
    <div class="hero-formula">
      <div class="hf-item"><span class="hf-ico">🧠</span><span>فريق خبراء بحثيين</span></div>
      <span class="hf-plus">+</span>
      <div class="hf-item"><span class="hf-ico">🤖</span><span>ذكاء اصطناعي</span></div>
      <span class="hf-plus">+</span>
      <div class="hf-item"><span class="hf-ico">📡</span><span>7 قنوات جمع</span></div>
      <span class="hf-eq">=</span>
      <div class="hf-item"><span class="hf-result">Survia</span></div>
    </div>
  </div>
  <div class="r d3">
    <div class="hero-ask">
      <div class="ask-item">
        <div class="ask-label">الاستثمار المطلوب</div>
        <div class="ask-val">900,000 ر.س</div>
      </div>
      <div class="ask-item">
        <div class="ask-label">الحصة المقدَّمة</div>
        <div class="ask-val">15%</div>
      </div>
      <div class="ask-item">
        <div class="ask-label">المرحلة</div>
        <div class="ask-val">Friends &amp; Family</div>
      </div>
      <div class="ask-item">
        <div class="ask-label">التقييم</div>
        <div class="ask-val">4.5M ر.س</div>
      </div>
    </div>
  </div>
  <div class="r d4">
    <div class="hero-stats">
      <div class="hs"><div class="v">$17.5B</div><div class="l">حجم السوق العالمي 2026</div></div>
      <div class="hs"><div class="v">منصة + فريق</div><div class="l">ركيزتان متكاملتان</div></div>
      <div class="hs"><div class="v">3 مسارات</div><div class="l">من ذاتي إلى خدمة كاملة</div></div>
      <div class="hs"><div class="v">32M ر.س</div><div class="l">إيرادات متوقعة 5 سنوات</div></div>
    </div>
  </div>
</section>

<!-- ══════════ PROBLEM ══════════ -->
<section id="problem">
  <div class="dg"></div>
  <div class="glow" style="width:300px;height:300px;background:#8B1C1C;right:8%;top:25%;opacity:.25;"></div>
  <div class="r"><div class="sec-label">المشكلة</div><h2 class="sec-title">الشركات تتخذ قرارات مليونية<br>بناءً على أسئلة خاطئة</h2><p class="sec-desc">المشكلة ليست في جمع البيانات فقط — بل في أن 78٪ من الشركات السعودية تبني استبياناتها دون منهجية بحثية، فتحصل على إجابات مضللة تقودها لقرارات خاطئة.</p></div>
  <div class="prob-grid">
    <div class="card pc r d1">
      <div class="pc-num">المشكلة الأولى</div>
      <div class="pc-title">الأسئلة غير احترافية</div>
      <div class="pc-desc">معظم الشركات تصيغ أسئلتها بنفسها دون منهجية إحصائية، فتحصل على بيانات متحيّزة لا تعكس الحقيقة، وتبني عليها قرارات خاطئة تكلّف الملايين.</div>
      <div class="pc-stat">63٪</div>
      <div class="pc-stat-lbl">من الاستبيانات بها أخطاء منهجية</div>
    </div>
    <div class="card pc r d2">
      <div class="pc-num">المشكلة الثانية</div>
      <div class="pc-title">معدلات استجابة منخفضة</div>
      <div class="pc-desc">الاستبيانات التقليدية عبر البريد تحصل على معدل استجابة لا يتجاوز 5-14٪ — والقرارات تُبنى على عيّنة غير ممثِّلة ولا يمكن الاعتماد عليها.</div>
      <div class="pc-stat">14٪</div>
      <div class="pc-stat-lbl">متوسط استجابة السوق الحالي</div>
    </div>
    <div class="card pc r d3">
      <div class="pc-num">المشكلة الثالثة</div>
      <div class="pc-title">تحليل سطحي بلا قيمة</div>
      <div class="pc-desc">جمع البيانات وتحليلها يستغرق أسابيع، والنتائج غالباً أرقام بلا تفسير، دون توصيات عملية يمكن لصانع القرار التحرك بناءً عليها فوراً.</div>
      <div class="pc-stat">3-4</div>
      <div class="pc-stat-lbl">أسابيع لتقرير بلا توصيات</div>
    </div>
  </div>
</section>

<!-- ══════════ SOLUTION — TWO PILLARS ══════════ -->
<section id="solution">
  <div class="dg"></div>
  <div class="glow" style="width:320px;height:320px;background:var(--gold);right:5%;top:20%;opacity:.05;"></div>
  <div class="r"><div class="sec-label">الحل</div><h2 class="sec-title">ركيزتان متكاملتان —<br>منصة ذكية + فريق خبراء</h2><p class="sec-desc">الأدوات وحدها لا تكفي، والخبراء وحدهم بطيئون ومكلفون. Survia تجمع الاثنين: منصة تقنية تدار من قِبل فريق بحثي متخصص يصمم لك الدراسة من الصفر ويحلّل نتائجها.</p></div>
  <div class="pillars">
    <!-- PILLAR 1: TECHNOLOGY -->
    <div class="pillar pillar-tech r d1">
      <div class="pillar-head">
        <div class="pillar-ico">🤖</div>
        <div>
          <div class="pillar-tag">الركيزة الأولى · التقنية</div>
          <div class="pillar-title">منصة AI + 7 قنوات</div>
        </div>
      </div>
      <div class="pillar-desc">البنية التقنية التي تُسرّع وتُوسّع نطاق البحث — تجمع البيانات بكفاءة عالية عبر القنوات التي يستخدمها العميل فعلياً.</div>
      <div class="pillar-list">
        <div class="pl-item">
          <div class="pl-ico">📞</div>
          <div><div class="pl-name">Call AI + WhatsApp AI</div><div class="pl-sub">مكالمات ومحادثات ذكية بالعربية</div></div>
        </div>
        <div class="pl-item">
          <div class="pl-ico">📱</div>
          <div><div class="pl-name">قنوات التواصل والرسائل</div><div class="pl-sub">تويتر، إنستقرام، SMS، إيميل</div></div>
        </div>
        <div class="pl-item">
          <div class="pl-ico">📊</div>
          <div><div class="pl-name">Smart Reports لحظية</div><div class="pl-sub">لوحة تحكم + تقارير آلية</div></div>
        </div>
        <div class="pl-item">
          <div class="pl-ico">🎯</div>
          <div><div class="pl-name">تحليل المشاعر والبيانات</div><div class="pl-sub">NLP عربي + إحصاء متقدم</div></div>
        </div>
      </div>
    </div>

    <!-- PILLAR 2: HUMAN EXPERTISE -->
    <div class="pillar pillar-human r d2">
      <div class="pillar-head">
        <div class="pillar-ico">🧠</div>
        <div>
          <div class="pillar-tag">الركيزة الثانية · البشرية</div>
          <div class="pillar-title">فريق خبراء البحث</div>
        </div>
      </div>
      <div class="pillar-desc">الفرق الحقيقي — فريق متخصص يصمم الأسئلة الصحيحة، ويفسّر النتائج، ويحوّلها إلى توصيات استراتيجية. هذا ما يميّزنا عن أي منصة أدوات.</div>
      <div class="pillar-list">
        <div class="pl-item">
          <div class="pl-ico">📝</div>
          <div><div class="pl-name">كتّاب المحتوى البحثي</div><div class="pl-sub">صياغة أسئلة منهجية خالية من التحيّز</div></div>
        </div>
        <div class="pl-item">
          <div class="pl-ico">📐</div>
          <div><div class="pl-name">مصمّمو الدراسات</div><div class="pl-sub">منهجية علمية + تحديد العيّنة المناسبة</div></div>
        </div>
        <div class="pl-item">
          <div class="pl-ico">📈</div>
          <div><div class="pl-name">محلّلون إحصائيون</div><div class="pl-sub">تحليل متقدم: SPSS · NPS · CSAT · Van Westendorp</div></div>
        </div>
        <div class="pl-item">
          <div class="pl-ico">🎓</div>
          <div><div class="pl-name">خبراء قطاعيون</div><div class="pl-sub">صحة · تجزئة · عقار · حكومة · تعليم</div></div>
        </div>
      </div>
    </div>
  </div>
  <div class="formula-row r d3">
    <span class="fr-text">
      <span class="t">الفريق البشري</span> يصوغ السؤال الصحيح،
      <span class="g">الذكاء الاصطناعي</span> يجمع ويحلّل،
      <span class="g">المنصة</span> تعرض النتائج للعميل.
    </span>
  </div>
</section>

<!-- ══════════ CUSTOMER JOURNEY ══════════ -->
<section id="journey">
  <div class="dg"></div>
  <div class="glow" style="width:300px;height:300px;background:var(--gold);left:10%;top:20%;opacity:.05;"></div>
  <div class="r"><div class="sec-label">رحلة العميل</div><h2 class="sec-title">ثلاثة مسارات — لكل حجم شركة<br>مسار يناسب حجمها وميزانيتها</h2><p class="sec-desc">من الاستخدام الذاتي للشركات الناشئة، إلى الخدمة الكاملة للمؤسسات الكبرى. في كل مسار، العميل يختار مستوى مشاركة فريقنا البحثي.</p></div>

  <div class="tiers">
    <!-- TIER 1: SELF-SERVE -->
    <div class="tier r d1">
      <div class="tier-name">المسار الأول · ذاتي</div>
      <div class="tier-title">Survia Starter</div>
      <div class="tier-for">للشركات الصغيرة والمتوسطة — SaaS</div>
      <div class="tier-price">
        <div class="amt">من 4,999 ر.س</div>
        <div class="period">شهرياً — اشتراك</div>
      </div>
      <div class="tier-feat">
        <div class="tf">وصول كامل للمنصة و<strong>7 قنوات الجمع</strong></div>
        <div class="tf">مساعد AI لاقتراح الأسئلة</div>
        <div class="tf">قوالب جاهزة لكل قطاع</div>
        <div class="tf">تقارير آلية لحظية</div>
        <div class="tf off">مراجعة خبير بشري للأسئلة</div>
        <div class="tf off">تحليل إحصائي متخصص</div>
        <div class="tf off">توصيات استراتيجية</div>
      </div>
    </div>

    <!-- TIER 2: PROFESSIONAL (FEATURED) -->
    <div class="tier featured r d2">
      <span class="tier-tag">الأكثر طلباً</span>
      <div class="tier-name">المسار الثاني · مدعوم بخبير</div>
      <div class="tier-title">Survia Professional</div>
      <div class="tier-for">للشركات النامية والعلامات التجارية</div>
      <div class="tier-price">
        <div class="amt">من 14,999 ر.س</div>
        <div class="period">للمشروع الواحد + اشتراك المنصة</div>
      </div>
      <div class="tier-feat">
        <div class="tf">كل مزايا Starter</div>
        <div class="tf"><strong>استشاري بحثي مخصص</strong> لمراجعة الأسئلة</div>
        <div class="tf"><strong>كاتب محتوى بحثي</strong> يصيغ الاستبيان</div>
        <div class="tf">تصميم العيّنة ومنهجية الدراسة</div>
        <div class="tf">تحليل إحصائي متوسط + تقرير تنفيذي</div>
        <div class="tf">ورشة عرض النتائج والتوصيات</div>
        <div class="tf off">فريق بحث كامل ومتعدد التخصصات</div>
      </div>
    </div>

    <!-- TIER 3: ENTERPRISE -->
    <div class="tier r d3">
      <div class="tier-name">المسار الثالث · خدمة كاملة</div>
      <div class="tier-title">Survia Enterprise</div>
      <div class="tier-for">للمؤسسات الكبرى والجهات الحكومية</div>
      <div class="tier-price">
        <div class="amt">من 39,999 ر.س</div>
        <div class="period">للدراسة — تسعير مخصص</div>
      </div>
      <div class="tier-feat">
        <div class="tf">كل مزايا Professional</div>
        <div class="tf"><strong>فريق بحثي كامل</strong>: مصمم + كاتب + محلل + خبير قطاعي</div>
        <div class="tf">دراسات كمية ونوعية متعددة المراحل</div>
        <div class="tf">مقابلات معمّقة + مجموعات نقاشية</div>
        <div class="tf">تحليل إحصائي متقدم (SPSS / R)</div>
        <div class="tf">تقارير استراتيجية + خارطة طريق تنفيذية</div>
        <div class="tf">مدير حساب مخصص + متابعة 12 شهراً</div>
      </div>
    </div>
  </div>

  <!-- 7-STAGE JOURNEY VISUALIZATION -->
  <div class="stages r d4">
    <div class="stages-head">رحلة العميل في سبع مراحل — من الهدف إلى القرار</div>
    <div class="stage-row">
      <div class="stage">
        <div class="stage-num">1</div>
        <div class="stage-name">اكتشاف الهدف</div>
        <div class="stage-by"><span class="h">خبير</span></div>
      </div>
      <div class="stage">
        <div class="stage-num">2</div>
        <div class="stage-name">تصميم المنهجية</div>
        <div class="stage-by"><span class="h">خبير</span></div>
      </div>
      <div class="stage">
        <div class="stage-num hi">3</div>
        <div class="stage-name">كتابة المحتوى والأسئلة</div>
        <div class="stage-by"><span class="h">خبير</span> + <span class="a">AI</span></div>
      </div>
      <div class="stage">
        <div class="stage-num">4</div>
        <div class="stage-name">اختيار القنوات</div>
        <div class="stage-by"><span class="a">AI</span></div>
      </div>
      <div class="stage">
        <div class="stage-num">5</div>
        <div class="stage-name">جمع البيانات</div>
        <div class="stage-by"><span class="a">AI</span> · 7 قنوات</div>
      </div>
      <div class="stage">
        <div class="stage-num">6</div>
        <div class="stage-name">التحليل الإحصائي</div>
        <div class="stage-by"><span class="h">خبير</span> + <span class="a">AI</span></div>
      </div>
      <div class="stage">
        <div class="stage-num hi">7</div>
        <div class="stage-name">التوصيات الاستراتيجية</div>
        <div class="stage-by"><span class="h">خبير</span></div>
      </div>
    </div>
  </div>

  <!-- EXPERT TEAM ROW -->
  <div class="r d5">
    <div style="font-size:12px;color:var(--dim);margin-top:22px;margin-bottom:10px;font-weight:700;letter-spacing:.6px;text-align:center;">فريق الخبراء — شبكة استشاريين متخصصين</div>
    <div class="experts-row">
      <div class="expert">
        <div class="expert-ico">📋</div>
        <div class="expert-role">مستشار البحوث</div>
        <div class="expert-task">تحديد الأهداف والمنهجية المناسبة</div>
      </div>
      <div class="expert">
        <div class="expert-ico">✍️</div>
        <div class="expert-role">كاتب المحتوى البحثي</div>
        <div class="expert-task">صياغة أسئلة منهجية وخالية من التحيّز</div>
      </div>
      <div class="expert">
        <div class="expert-ico">📊</div>
        <div class="expert-role">محلل إحصائي</div>
        <div class="expert-task">SPSS، R، NPS، Van Westendorp</div>
      </div>
      <div class="expert">
        <div class="expert-ico">🏥</div>
        <div class="expert-role">خبير قطاعي</div>
        <div class="expert-task">صحة · تجزئة · عقار · حكومة · تعليم</div>
      </div>
      <div class="expert">
        <div class="expert-ico">🎯</div>
        <div class="expert-role">مستشار استراتيجي</div>
        <div class="expert-task">تحويل النتائج إلى خطة عمل قابلة للتنفيذ</div>
      </div>
    </div>
  </div>
</section>

<!-- ══════════ ROADMAP ══════════ -->
<section id="roadmap">
  <div class="dg"></div>
  <div class="r"><div class="sec-label">خطة العمل</div><h2 class="sec-title">ثلاث مراحل — اثنا عشر شهراً</h2><p class="sec-desc">خارطة طريق مدروسة تبدأ ببناء المنتج وشبكة الخبراء في مايو 2026، تمر بالتسجيل الرسمي، وتنتهي بانتشار واسع في السوق السعودي.</p></div>
  <div class="phases r d1">
    <div class="phase hl">
      <div class="ph-num">المرحلة الأولى</div>
      <div class="ph-period">مايو — يونيو 2026</div>
      <div class="ph-title">بناء المنتج + شبكة الخبراء</div>
      <div class="ph-items">
        <div class="pi">تطوير Call AI وWhatsApp AI بالعربية</div>
        <div class="pi">بناء لوحة التقارير اللحظية</div>
        <div class="pi">استقطاب 8-12 خبيراً بحثياً بالتعاقد</div>
        <div class="pi">تطوير قوالب الدراسات لـ 6 قطاعات</div>
        <div class="pi">إطلاق نسخة تجريبية مع عملاء أوليين</div>
      </div>
      <div class="ph-kpi"><div class="k">الهدف</div><div class="v">MVP + شبكة خبراء ✓</div></div>
    </div>
    <div class="phase">
      <div class="ph-num">المرحلة الثانية</div>
      <div class="ph-period">يوليو — أكتوبر 2026</div>
      <div class="ph-title">التسجيل والعقود المؤسسية</div>
      <div class="ph-items">
        <div class="pi">تسجيل كمزوّد خدمة في الجهات الحكومية</div>
        <div class="pi">شهادات الجودة والأمن السيبراني</div>
        <div class="pi">إطلاق المسارات الثلاثة رسمياً</div>
        <div class="pi">إبرام عقود Enterprise مع 3-5 مؤسسات</div>
        <div class="pi">بناء قاعدة دراسات حالة موثّقة</div>
      </div>
      <div class="ph-kpi"><div class="k">الهدف</div><div class="v">إيرادات 400K ر.س</div></div>
    </div>
    <div class="phase">
      <div class="ph-num">المرحلة الثالثة</div>
      <div class="ph-period">نوف 2026 — أبريل 2027</div>
      <div class="ph-title">التسويق والنمو والانتشار</div>
      <div class="ph-items">
        <div class="pi">حملات رقمية لصنّاع القرار</div>
        <div class="pi">المشاركة في معارض الأعمال السعودية</div>
        <div class="pi">برنامج إحالة للشركاء والوكلاء</div>
        <div class="pi">توسيع شبكة الخبراء إلى 25 متخصصاً</div>
        <div class="pi">توسّع إقليمي نحو الإمارات والكويت</div>
      </div>
      <div class="ph-kpi"><div class="k">الهدف</div><div class="v">40+ عميل نشط</div></div>
    </div>
  </div>
  <div class="timeline-row r d2">
    <div class="tl-item"><div class="tl-dot"></div><div class="tl-lbl">مايو '26</div></div>
    <div class="tl-item"><div class="tl-dot"></div><div class="tl-lbl">يونيو '26</div></div>
    <div class="tl-item"><div class="tl-dot e"></div><div class="tl-lbl">يوليو '26</div></div>
    <div class="tl-item"><div class="tl-dot e"></div><div class="tl-lbl">سبتمبر '26</div></div>
    <div class="tl-item"><div class="tl-dot e"></div><div class="tl-lbl">أكتوبر '26</div></div>
    <div class="tl-item"><div class="tl-dot e"></div><div class="tl-lbl">يناير '27</div></div>
    <div class="tl-item"><div class="tl-dot e"></div><div class="tl-lbl">أبريل '27</div></div>
  </div>
</section>

<!-- ══════════ MARKET ══════════ -->
<section id="market">
  <div class="dg"></div>
  <div class="glow" style="width:280px;height:280px;background:var(--gold);left:5%;bottom:20%;opacity:.05;"></div>
  <div class="r"><div class="sec-label">حجم السوق</div><h2 class="sec-title">سوق مزدوج —<br>منصات + خدمات بحثية</h2><p class="sec-desc">السوق العالمي يجمع سوقين: أدوات الاستبيان 17.5 مليار دولار، وخدمات أبحاث السوق 84 مليار دولار. Survia تستهدف الاثنين معاً — وهذا ما يضاعف حجم الفرصة.</p></div>
  <div class="market-layout">
    <div class="r d1">
      <div style="font-size:11px;font-weight:700;color:var(--dim);margin-bottom:10px;text-transform:uppercase;letter-spacing:.6px;">أرقام السوق — 2026</div>
      <div class="card mc" style="margin-bottom:10px;"><div class="mc-icon">🌍</div><div><div class="mc-val">$17.5 مليار</div><div class="mc-lbl">سوق منصات الاستبيان — نمو 18%</div></div></div>
      <div class="card mc" style="margin-bottom:10px;"><div class="mc-icon">📊</div><div><div class="mc-val">$84 مليار</div><div class="mc-lbl">سوق خدمات أبحاث السوق عالمياً</div></div></div>
      <div class="card mc" style="margin-bottom:10px;"><div class="mc-icon">🇸🇦</div><div><div class="mc-val">$500 مليون</div><div class="mc-lbl">السوق السعودي — نمو 24%</div></div></div>
      <div class="card mc"><div class="mc-icon">📈</div><div><div class="mc-val">+1.3M منشأة</div><div class="mc-lbl">السوق المستهدف في المملكة</div></div></div>
    </div>
    <div class="r d2">
      <div style="font-size:11px;font-weight:700;color:var(--dim);margin-bottom:10px;text-transform:uppercase;letter-spacing:.6px;">القطاعات المستهدفة</div>
      <div class="card tg" style="margin-bottom:8px;"><div class="tg-top"><span class="tg-name">العقارات والمدن الاقتصادية</span><span class="tg-cnt">80+</span></div><div class="pb"><div class="pf" style="width:80%;background:var(--gold);"></div></div></div>
      <div class="card tg" style="margin-bottom:8px;"><div class="tg-top"><span class="tg-name">التجزئة والتسوق</span><span class="tg-cnt">300+</span></div><div class="pb"><div class="pf" style="width:65%;background:var(--gold);"></div></div></div>
      <div class="card tg" style="margin-bottom:8px;"><div class="tg-top"><span class="tg-name">الرعاية الصحية</span><span class="tg-cnt">200+</span></div><div class="pb"><div class="pf" style="width:55%;background:var(--gold);"></div></div></div>
      <div class="card tg" style="margin-bottom:8px;"><div class="tg-top"><span class="tg-name">التعليم والجامعات</span><span class="tg-cnt">150+</span></div><div class="pb"><div class="pf" style="width:48%;background:var(--gold);"></div></div></div>
      <div class="card tg" style="margin-bottom:8px;"><div class="tg-top"><span class="tg-name">الحكومة والهيئات</span><span class="tg-cnt">100+</span></div><div class="pb"><div class="pf" style="width:40%;background:var(--gold);"></div></div></div>
      <div class="card tg"><div class="tg-top"><span class="tg-name">الخدمات المالية</span><span class="tg-cnt">80+</span></div><div class="pb"><div class="pf" style="width:32%;background:var(--gold);"></div></div></div>
    </div>
  </div>
</section>

<!-- ══════════ FINANCIAL ══════════ -->
<section id="financial">
  <div class="dg"></div>
  <div class="r"><div class="sec-label">النموذج المالي</div><h2 class="sec-title">32 مليون ريال<br>إجمالي إيرادات 5 سنوات</h2><p class="sec-desc">نموذج إيرادات ثلاثي: اشتراكات المنصة + خدمات استشارية بحثية + عقود مؤسسية كاملة. الخدمات البشرية تضاعف متوسط قيمة الصفقة 4-8 مرات.</p></div>
  <div class="fin-layout">
    <div class="r d1">
      <div class="card" style="margin-bottom:12px;">
        <div class="year-row"><div><div class="yr-name">النصف الثاني 2026</div><div class="yr-sub">إطلاق + عقود Enterprise أولى</div></div><div><div class="yr-val">600,000</div><div class="yr-note">ريال سعودي</div></div></div>
        <div class="year-row"><div><div class="yr-name">السنة الثانية 2027</div><div class="yr-sub">نمو الاشتراكات + توسع خدمات البحث</div></div><div><div class="yr-val">3,200,000</div><div class="yr-note">ريال سعودي</div></div></div>
        <div class="year-row"><div><div class="yr-name">السنة الثالثة 2028</div><div class="yr-sub">توسع إقليمي + قطاعات جديدة</div></div><div><div class="yr-val">6,800,000</div><div class="yr-note">ريال سعودي</div></div></div>
        <div class="year-row"><div><div class="yr-name">السنة الرابعة 2029</div><div class="yr-sub">قيادة السوق + الإمارات والكويت</div></div><div><div class="yr-val">9,800,000</div><div class="yr-note">ريال سعودي</div></div></div>
        <div class="year-row"><div><div class="yr-name">السنة الخامسة 2030</div><div class="yr-sub">نضج المنصة + نمو عضوي قوي</div></div><div><div class="yr-val">11,600,000</div><div class="yr-note">ريال سعودي</div></div></div>
        <div style="background:var(--gold-dim);border-top:1px solid var(--gold-line);padding:12px 18px;display:flex;justify-content:space-between;align-items:center;border-radius:0 0 12px 12px;">
          <div style="font-size:13px;font-weight:700;color:var(--gold);">الإجمالي التراكمي (5 سنوات)</div>
          <div style="font-size:20px;font-weight:900;color:var(--gold);font-family:'Tajawal',sans-serif;">32,000,000 ر.س</div>
        </div>
      </div>
      <div class="rev-mix">
        <div class="rm"><div class="p">25٪</div><div class="n">اشتراكات</div><div class="d">Starter SaaS</div></div>
        <div class="rm"><div class="p">40٪</div><div class="n">مشاريع بحثية</div><div class="d">Professional</div></div>
        <div class="rm"><div class="p">35٪</div><div class="n">عقود مؤسسية</div><div class="d">Enterprise</div></div>
      </div>
      <div class="pricing-note">
        <div class="pn-title">لماذا الخدمات البشرية تضاعف الإيرادات؟</div>
        <div class="pn-body">متوسط اشتراك المنصة 60,000 ريال سنوياً. أما مشروع بحثي واحد بمسار Professional يبدأ من 15,000 ريال، وعقد Enterprise يتجاوز 200,000 ريال. 75٪ من الإيرادات تأتي من الخدمات البشرية.</div>
      </div>
    </div>
    <div class="chart-wrap r d2">
      <div style="font-size:12px;color:var(--dim);margin-bottom:14px;font-weight:600;">مسار الإيرادات حسب المصدر — 5 سنوات (بالمليون ريال)</div>
      <div style="position:relative;height:300px;"><canvas id="revChart"></canvas></div>
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:14px;">
        <div style="background:rgba(255,255,255,0.03);border:1px solid var(--border);border-radius:8px;padding:12px;text-align:center;"><div style="font-size:17px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;">18-20 شهر</div><div style="font-size:10px;color:var(--dim);margin-top:2px;">نقطة التعادل (مُحسَّنة)</div></div>
        <div style="background:rgba(255,255,255,0.03);border:1px solid var(--border);border-radius:8px;padding:12px;text-align:center;"><div style="font-size:17px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;">3.8x</div><div style="font-size:10px;color:var(--dim);margin-top:2px;">العائد المتوقع / 3 سنوات</div></div>
      </div>
    </div>
  </div>
</section>

<!-- ══════════ INVESTMENT ══════════ -->
<section id="investment">
  <div class="dg"></div>
  <div class="glow" style="width:400px;height:400px;background:var(--gold);left:50%;top:50%;transform:translate(-50%,-50%);opacity:.05;"></div>
  <div class="r"><div class="sec-label">طلب الاستثمار</div><h2 class="sec-title">900,000 ريال<br>لبناء المنصة + شبكة الخبراء</h2><p class="sec-desc">استثمار مدروس يُموّل بناء المنتج التقني، وتأسيس شبكة الخبراء البحثيين، والدخول الرسمي للسوق.</p></div>
  <div class="inv-layout">
    <div class="r d1" style="text-align:center;">
      <div class="inv-circle">
        <div class="inv-amount">900K</div>
        <div class="inv-label">ريال سعودي</div>
      </div>
      <div style="font-size:13px;color:var(--dim);margin-bottom:18px;">مقابل 15% من الشركة — مرحلة Friends &amp; Family</div>
      <div class="returns">
        <div class="ret"><div class="v">4.5M</div><div class="l">التقييم الحالي</div></div>
        <div class="ret"><div class="v">3.8x</div><div class="l">العائد / 3 سنوات</div></div>
        <div class="ret"><div class="v">18-20</div><div class="l">شهر للتعادل</div></div>
      </div>
    </div>
    <div class="r d2">
      <div style="font-size:12px;font-weight:700;color:var(--dim);margin-bottom:12px;text-transform:uppercase;letter-spacing:.6px;">توزيع الاستثمار</div>
      <div class="card ib" style="margin-bottom:8px;"><div class="ib-top"><div><div class="ib-name">تطوير المنتج والذكاء الاصطناعي</div><div class="ib-pct">35٪ — هندسة + خوادم + API</div></div><div><div class="ib-val">315,000</div></div></div><div class="pb"><div class="pf" style="width:35%;background:var(--gold);"></div></div></div>
      <div class="card ib" style="margin-bottom:8px;"><div class="ib-top"><div><div class="ib-name">بناء شبكة الخبراء البحثيين</div><div class="ib-pct">20٪ — استقطاب + تعاقدات + تدريب</div></div><div><div class="ib-val">180,000</div></div></div><div class="pb"><div class="pf" style="width:20%;background:var(--teal);"></div></div></div>
      <div class="card ib" style="margin-bottom:8px;"><div class="ib-top"><div><div class="ib-name">المبيعات والتسويق</div><div class="ib-pct">20٪ — فريق + حملات رقمية</div></div><div><div class="ib-val">180,000</div></div></div><div class="pb"><div class="pf" style="width:20%;background:var(--gold);"></div></div></div>
      <div class="card ib" style="margin-bottom:8px;"><div class="ib-top"><div><div class="ib-name">التسجيل والامتثال القانوني</div><div class="ib-pct">15٪ — وزارات + شهادات + مستشارون</div></div><div><div class="ib-val">135,000</div></div></div><div class="pb"><div class="pf" style="width:15%;background:var(--gold);"></div></div></div>
      <div class="card ib" style="margin-bottom:8px;"><div class="ib-top"><div><div class="ib-name">العمليات والبنية التحتية</div><div class="ib-pct">7٪ — مكتب + أدوات + إدارة</div></div><div><div class="ib-val">63,000</div></div></div><div class="pb"><div class="pf" style="width:7%;background:var(--gold);"></div></div></div>
      <div class="card ib"><div class="ib-top"><div><div class="ib-name">احتياطي وطوارئ</div><div class="ib-pct">3٪ — مخصص للمتغيرات</div></div><div><div class="ib-val">27,000</div></div></div><div class="pb"><div class="pf" style="width:3%;background:var(--gold);"></div></div></div>
    </div>
  </div>
</section>

<!-- ══════════ TEAM ══════════ -->
<section id="team">
  <div class="dg"></div>
  <div class="r"><div class="sec-label">الفريق</div><h2 class="sec-title">الفريق القيادي<br>+ شبكة الخبراء البحثيين</h2><p class="sec-desc">القيادة التأسيسية تجمع 52 سنة من الخبرة في التقنية والأعمال. الشبكة الاستشارية تضيف عمقاً تخصصياً في البحث والتحليل لكل قطاع.</p></div>
  <div class="team-grid">
    <div class="card tm r d1">
      <div class="tm-av">ع</div>
      <div class="tm-name">عادل الرسلاني</div>
      <div class="tm-role">Managing Director — MD</div>
      <div class="tm-desc">يقود المسيرة التجارية والاستراتيجية للشركة بخبرة واسعة في تطوير الأعمال وإدارة المشاريع التقنية الكبرى.</div>
      <span class="tm-exp">+15 سنة خبرة</span>
    </div>
    <div class="card tm r d2">
      <div class="tm-av">ع</div>
      <div class="tm-name">عبدالله سيف</div>
      <div class="tm-role">Chief Technology Officer — CTO</div>
      <div class="tm-desc">يقود الرؤية التقنية وهندسة المنصة والذكاء الاصطناعي بتجربة تمتد لعقود في بناء منظومات تقنية ضخمة ومعقدة.</div>
      <span class="tm-exp">+20 سنة خبرة</span>
    </div>
    <div class="card tm r d3">
      <div class="tm-av">م</div>
      <div class="tm-name">محمد كنعان</div>
      <div class="tm-role">مسؤول المبيعات وإدارة العملاء</div>
      <div class="tm-desc">يبني علاقات استراتيجية مع المؤسسات ويقود دورة مبيعات B2B بخبرة عميقة في إدارة العملاء المؤسسيين السعوديين.</div>
      <span class="tm-exp">+5 سنوات خبرة</span>
    </div>
    <div class="card tm r d4">
      <div class="tm-av">م</div>
      <div class="tm-name">محمد شفيق</div>
      <div class="tm-role">مطوّر رئيسي — Lead Developer</div>
      <div class="tm-desc">يبني المنصة والأدوات التقنية بكفاءة عالية وجودة مؤسسية، مع تجربة واسعة في أنظمة SaaS المعقدة والذكاء الاصطناعي التطبيقي.</div>
      <span class="tm-exp">+12 سنة خبرة</span>
    </div>
  </div>
  <div style="display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin-top:16px;" class="r d5">
    <div style="background:rgba(255,255,255,0.02);border:1px solid var(--border);border-radius:10px;padding:14px;text-align:center;"><div style="font-size:20px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;">KAEC</div><div style="font-size:10px;color:var(--dim);margin-top:3px;">عميل رئيسي أول</div></div>
    <div style="background:rgba(255,255,255,0.02);border:1px solid var(--border);border-radius:10px;padding:14px;text-align:center;"><div style="font-size:20px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;">679</div><div style="font-size:10px;color:var(--dim);margin-top:3px;">استجابة جُمعت بالنسخة التجريبية</div></div>
    <div style="background:rgba(255,255,255,0.02);border:1px solid var(--border);border-radius:10px;padding:14px;text-align:center;"><div style="font-size:20px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;">8-12</div><div style="font-size:10px;color:var(--dim);margin-top:3px;">خبير بحثي (المرحلة الأولى)</div></div>
    <div style="background:rgba(255,255,255,0.02);border:1px solid var(--border);border-radius:10px;padding:14px;text-align:center;"><div style="font-size:20px;font-weight:800;color:var(--gold);font-family:'Tajawal',sans-serif;">52 سنة</div><div style="font-size:10px;color:var(--dim);margin-top:3px;">مجموع خبرات الفريق القيادي</div></div>
  </div>
</section>

<!-- ══════════ CTA ══════════ -->
<section id="cta">
  <div class="dg"></div>
  <div class="dc" style="width:360px;height:360px;top:50%;left:50%;transform:translate(-50%,-50%);"></div>
  <div class="glow"></div>
  <div class="r">
    <div style="width:52px;height:52px;border-radius:12px;background:var(--gold);display:flex;align-items:center;justify-content:center;font-size:20px;font-weight:900;color:var(--ink);margin:0 auto 22px;">S</div>
  </div>
  <div class="r d1">
    <h2 class="cta-title">نبني معاً<br><span>مستقبل البحث الذكي</span><br>في الخليج</h2>
  </div>
  <div class="r d2">
    <p class="cta-sub">منصة + فريق خبراء + ذكاء اصطناعي — ثلاثية تصنع الفرق. نحتاج شريكاً مؤمناً بقوة البيانات وأثرها على قرارات الأعمال.</p>
  </div>

  <div class="contact-row r d4">
    <div class="ct-item"><span class="ico">✉</span><span>info@survia.sa</span></div>
    <div class="ct-item"><span class="ico">☎</span><span>+966 503455511</span></div>
    <div class="ct-item"><span class="ico">🌐</span><span>www.survia.sa</span></div>
    <div class="ct-item"><span class="ico">📍</span><span>الرياض، المملكة العربية السعودية</span></div>
  </div>
  <div style="margin-top:44px;padding-top:24px;border-top:1px solid var(--border);text-align:center;" class="r d5">
    <div style="font-size:10px;color:var(--faint);letter-spacing:.5px;">© 2026 Survia · جميع الحقوق محفوظة · وثيقة سرية للمستثمرين فقط · Friends &amp; Family Round</div>
  </div>
</section>

<script>
// REVENUE CHART - STACKED BAR SHOWING TIER MIX
new Chart(document.getElementById('revChart'),{
  type:'bar',
  data:{
    labels:['H2 2026','2027','2028','2029','2030'],
    datasets:[
      {
        label:'اشتراكات Starter',
        data:[0.15,0.8,1.7,2.45,2.9],
        backgroundColor:'rgba(201,168,76,0.45)',
        borderRadius:4,
        stack:'s'
      },
      {
        label:'مشاريع Professional',
        data:[0.25,1.3,2.7,3.9,4.65],
        backgroundColor:'rgba(201,168,76,0.7)',
        borderRadius:4,
        stack:'s'
      },
      {
        label:'عقود Enterprise',
        data:[0.2,1.1,2.4,3.45,4.05],
        backgroundColor:'rgba(93,202,165,0.75)',
        borderRadius:4,
        stack:'s'
      }
    ]
  },
  options:{
    responsive:true,maintainAspectRatio:false,
    plugins:{
      legend:{position:'bottom',rtl:true,labels:{color:'rgba(245,243,238,0.65)',font:{size:11,family:'Cairo'},padding:10,boxWidth:12}},
      tooltip:{callbacks:{label:ctx=>ctx.dataset.label+': '+ctx.parsed.y+'M ر.س'}}
    },
    scales:{
      x:{stacked:true,ticks:{color:'rgba(245,243,238,0.45)',font:{size:11,family:'Cairo'}},grid:{display:false}},
      y:{stacked:true,ticks:{callback:v=>v+'M',color:'rgba(245,243,238,0.4)',font:{size:10}},grid:{color:'rgba(201,168,76,0.07)'}}
    }
  }
});

// REVEAL OBSERVER
const obs=new IntersectionObserver(e=>{e.forEach(x=>{if(x.isIntersecting)x.target.classList.add('v');});},{threshold:.12});
document.querySelectorAll('.r').forEach(el=>obs.observe(el));

// SLIDE COUNTER
const secs=['hero','problem','solution','journey','roadmap','market','financial','investment','team','cta'];
const total=secs.length;
const slideNo=document.getElementById('slideNo');
const secObs=new IntersectionObserver(e=>{
  e.forEach(x=>{
    if(x.isIntersecting){
      const i=secs.indexOf(x.target.id);
      if(i>-1)slideNo.textContent=(i+1)+' / '+total;
    }
  });
},{threshold:.4});
secs.forEach(id=>{const el=document.getElementById(id);if(el)secObs.observe(el);});
</script>
</body>
</html>
