# -my-website
퍼스널컬러 화장품
[olive-fit-check.html](https://github.com/user-attachments/files/33964943/olive-fit-check.html)
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>핏체크 — 올리브영 상품 적합성 셀프 판단</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.min.css">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+KR:wght@600;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#F6F4EE; --surface:#FFFFFF; --ink:#24281C; --sub:#6B7060;
  --olive:#66802F; --olive-deep:#414F22; --olive-soft:#EFF3E3;
  --line:#E4E1D6;
  --caution:#B0503C; --caution-bg:#FBEFEC;
  --good:#4C7A45; --good-bg:#EEF5EC;
  --hold:#A07E2F; --hold-bg:#F8F2E2;
  --radius:16px;
  --shadow:0 2px 10px rgba(36,40,28,.06);
}
*{box-sizing:border-box; margin:0; padding:0;}
html{scroll-behavior:smooth;}
@media (prefers-reduced-motion: reduce){ html{scroll-behavior:auto;} *{transition:none !important; animation:none !important;} }
body{
  background:var(--bg); color:var(--ink);
  font-family:"Pretendard", -apple-system, "Apple SD Gothic Neo", "Malgun Gothic", sans-serif;
  font-size:15px; line-height:1.6;
}
button{font-family:inherit; cursor:pointer;}
input,select,textarea{font-family:inherit; font-size:14px;}
:focus-visible{outline:3px solid rgba(102,128,47,.45); outline-offset:2px; border-radius:6px;}

/* ---------- header ---------- */
header{
  position:sticky; top:0; z-index:50;
  background:rgba(246,244,238,.92); backdrop-filter:blur(8px);
  border-bottom:1px solid var(--line);
}
.head-in{max-width:960px; margin:0 auto; padding:12px 20px; display:flex; align-items:center; gap:14px;}
.logo{font-family:"Noto Serif KR", serif; font-weight:700; font-size:20px; letter-spacing:-.02em;}
.logo em{font-style:normal; color:var(--olive);}
.head-note{font-size:12px; color:var(--sub);}
.shade-chip{
  margin-left:auto; display:flex; align-items:center; gap:10px;
  background:var(--surface); border:1px solid var(--line); border-radius:999px;
  padding:5px 14px 5px 6px; box-shadow:var(--shadow);
}
.shade-dot{
  width:34px; height:34px; border-radius:50%;
  background:#E5C3A6; border:3px solid var(--surface);
  box-shadow:0 0 0 2px var(--line);
  transition:background .25s;
}
.shade-meta{line-height:1.25;}
.shade-meta b{font-size:12px; display:block;}
.shade-meta span{font-size:11px; color:var(--sub);}

/* ---------- layout ---------- */
main{max-width:960px; margin:0 auto; padding:28px 20px 80px;}
.intro{margin:6px 0 26px;}
.intro h1{font-family:"Noto Serif KR", serif; font-size:26px; font-weight:700; letter-spacing:-.02em; line-height:1.4;}
.intro p{color:var(--sub); font-size:14px; margin-top:6px; max-width:640px;}
section{margin-bottom:34px;}
.sec-head{display:flex; align-items:baseline; gap:10px; margin-bottom:12px;}
.sec-head .step{
  font-size:11px; font-weight:700; color:var(--olive-deep);
  background:var(--olive-soft); border-radius:999px; padding:3px 10px; letter-spacing:.05em;
}
.sec-head h2{font-family:"Noto Serif KR", serif; font-size:19px; font-weight:700;}
.card{
  background:var(--surface); border:1px solid var(--line);
  border-radius:var(--radius); box-shadow:var(--shadow); padding:20px;
}
.grid2{display:grid; grid-template-columns:1fr 1fr; gap:20px;}
@media (max-width:760px){ .grid2{grid-template-columns:1fr;} .head-note{display:none;} }

/* ---------- form ---------- */
.field{margin-bottom:14px;}
.field:last-child{margin-bottom:0;}
.field > label, .field > .lab{display:block; font-size:13px; font-weight:600; margin-bottom:6px;}
.hint{font-size:12px; color:var(--sub); font-weight:400;}
input[type=text], select, textarea{
  width:100%; border:1px solid var(--line); border-radius:10px;
  padding:9px 12px; background:#FCFBF8; color:var(--ink);
}
textarea{min-height:88px; resize:vertical;}
.chips{display:flex; flex-wrap:wrap; gap:8px;}
.chip{
  border:1px solid var(--line); background:#FCFBF8; border-radius:999px;
  padding:6px 14px; font-size:13px; color:var(--ink); transition:all .15s;
}
.chip[aria-pressed=true]{background:var(--olive-deep); border-color:var(--olive-deep); color:#fff;}
.slider-row{display:flex; align-items:center; gap:10px; margin-bottom:10px;}
.slider-row label{font-size:13px; width:88px; flex-shrink:0;}
.slider-row input[type=range]{flex:1; accent-color:var(--olive);}
.slider-row output{font-size:12px; color:var(--sub); width:34px; text-align:right;}
.btn{
  border:none; border-radius:10px; padding:10px 18px;
  font-size:14px; font-weight:600; transition:transform .1s;
}
.btn:active{transform:scale(.98);}
.btn-primary{background:var(--olive-deep); color:#fff;}
.btn-ghost{background:transparent; border:1px solid var(--line); color:var(--ink);}
.btn-sm{padding:6px 12px; font-size:12.5px; border-radius:8px;}

/* ---------- photo canvas ---------- */
.photo-zone{
  border:2px dashed var(--line); border-radius:12px; background:#FCFBF8;
  min-height:230px; display:flex; align-items:center; justify-content:center;
  flex-direction:column; gap:8px; text-align:center; padding:14px; position:relative;
}
.photo-zone.has-img{border-style:solid; padding:0; overflow:hidden; background:#111;}
#photoCanvas{max-width:100%; display:block; cursor:crosshair; border-radius:10px;}
.privacy{font-size:11.5px; color:var(--sub); margin-top:8px;}
.privacy b{color:var(--olive-deep);}
.tone-preview{
  display:flex; align-items:center; gap:12px; margin-top:14px;
  background:#FCFBF8; border:1px solid var(--line); border-radius:12px; padding:12px;
}
.tone-swatch{width:52px; height:52px; border-radius:12px; border:1px solid var(--line); flex-shrink:0; transition:background .25s;}
.tone-info{font-size:13px;}
.tone-info b{font-size:14px;}
.undertone-tag{
  display:inline-block; font-size:11px; font-weight:700; border-radius:6px; padding:1px 8px; margin-left:6px;
}
.ut-warm{background:#F8ECDD; color:#9A6A2E;}
.ut-cool{background:#E6EDF6; color:#3E5D8A;}
.ut-neutral{background:#EEEEE8; color:#5D6152;}

/* ---------- product samples ---------- */
.samples{display:flex; flex-wrap:wrap; gap:8px; margin-top:8px;}
.sample-btn{
  border:1px solid var(--line); background:var(--olive-soft); color:var(--olive-deep);
  border-radius:999px; padding:6px 13px; font-size:12.5px; font-weight:600;
}

/* ---------- result board ---------- */
.empty-board{color:var(--sub); font-size:14px; text-align:center; padding:34px 10px;}
.prod-card{margin-bottom:16px;}
.prod-head{display:flex; align-items:flex-start; gap:12px; flex-wrap:wrap;}
.prod-title{flex:1; min-width:200px;}
.prod-title h3{font-size:16.5px; font-weight:700;}
.prod-title .cat{font-size:12px; color:var(--sub);}
.verdict-btns{display:flex; gap:6px;}
.v-btn{border:1.5px solid var(--line); background:#FCFBF8; border-radius:999px; padding:5px 13px; font-size:12.5px; font-weight:600; color:var(--sub);}
.v-btn.on-fit{background:var(--good-bg); border-color:var(--good); color:var(--good);}
.v-btn.on-hold{background:var(--hold-bg); border-color:var(--hold); color:var(--hold);}
.v-btn.on-no{background:var(--caution-bg); border-color:var(--caution); color:var(--caution);}
.score-line{display:flex; align-items:center; gap:10px; margin:12px 0 4px;}
.score-bar{flex:1; height:8px; border-radius:99px; background:#EDEBE2; overflow:hidden;}
.score-bar i{display:block; height:100%; border-radius:99px; background:linear-gradient(90deg,#8CA653,var(--olive-deep)); transition:width .3s;}
.score-num{font-size:12.5px; font-weight:700; color:var(--olive-deep); width:110px; text-align:right;}
.check-list{margin-top:10px; display:flex; flex-direction:column; gap:7px;}
.check-item{display:flex; gap:9px; font-size:13.5px; align-items:flex-start; padding:8px 11px; border-radius:10px; background:#FBFAF6; border:1px solid #F0EEE5;}
.check-item .ico{font-weight:800; flex-shrink:0; width:18px; text-align:center;}
.ci-good{border-color:#DCEADA;} .ci-good .ico{color:var(--good);}
.ci-warn{border-color:#F3D9C9; background:var(--caution-bg);} .ci-warn .ico{color:var(--caution);}
.ci-info .ico{color:var(--sub);}
.ing-tags{display:flex; flex-wrap:wrap; gap:5px; margin-top:4px;}
.ing-tag{font-size:11.5px; border-radius:6px; padding:2px 8px; font-weight:600;}
.it-caution{background:var(--caution-bg); color:var(--caution);}
.it-good{background:var(--good-bg); color:var(--good);}
.it-allergen{background:#F3E8F3; color:#8A4E8A;}

/* shade compare */
.shade-compare{display:flex; align-items:center; gap:16px; margin-top:12px; background:#FBFAF6; border:1px solid #F0EEE5; border-radius:12px; padding:14px;}
.split-circle{width:84px; height:84px; border-radius:50%; overflow:hidden; display:flex; flex-shrink:0; border:1px solid var(--line);}
.split-circle div{width:50%; height:100%;}
.shade-compare .txt{font-size:13px;}
.shade-compare .txt b{font-size:13.5px;}

/* comparison table */
.cmp-wrap{overflow-x:auto; margin-top:8px;}
table{width:100%; border-collapse:collapse; font-size:13px; min-width:560px;}
th,td{padding:9px 11px; border-bottom:1px solid var(--line); text-align:left; vertical-align:top;}
th{font-size:12px; color:var(--sub); font-weight:600; background:#FBFAF6;}
.v-pill{font-size:11.5px; font-weight:700; border-radius:6px; padding:2px 8px;}
.vp-fit{background:var(--good-bg); color:var(--good);}
.vp-hold{background:var(--hold-bg); color:var(--hold);}
.vp-no{background:var(--caution-bg); color:var(--caution);}
.vp-none{background:#EEEEE8; color:var(--sub);}
.del-btn{background:none; border:none; color:var(--sub); font-size:12px; text-decoration:underline;}

/* ---------- records ---------- */
.rating-btns{display:flex; gap:6px;}
.r-btn{border:1.5px solid var(--line); background:#FCFBF8; border-radius:999px; padding:6px 14px; font-size:13px; font-weight:600; color:var(--sub);}
.r-btn[aria-pressed=true].r-good{background:var(--good-bg); border-color:var(--good); color:var(--good);}
.r-btn[aria-pressed=true].r-mid{background:var(--hold-bg); border-color:var(--hold); color:var(--hold);}
.r-btn[aria-pressed=true].r-bad{background:var(--caution-bg); border-color:var(--caution); color:var(--caution);}
.rec-list{display:flex; flex-direction:column; gap:10px; margin-top:14px;}
.rec-item{display:flex; gap:12px; align-items:flex-start; background:#FBFAF6; border:1px solid #F0EEE5; border-radius:12px; padding:12px 14px; flex-wrap:wrap;}
.rec-item .info{flex:1; min-width:180px;}
.rec-item .info b{font-size:14px;}
.rec-item .info .hint{display:block;}
.rec-actions{display:flex; gap:6px; align-items:center;}
.r-pill{font-size:11.5px; font-weight:700; border-radius:6px; padding:2px 9px; flex-shrink:0; margin-top:2px;}
.rp-good{background:var(--good-bg); color:var(--good);}
.rp-mid{background:var(--hold-bg); color:var(--hold);}
.rp-bad{background:var(--caution-bg); color:var(--caution);}
.io-row{display:flex; gap:8px; margin-top:14px; padding-top:12px; border-top:1px dashed var(--line); align-items:center; flex-wrap:wrap;}
.pref-insight{margin-top:14px; background:var(--olive-soft); border:1px solid #DCE4C4; border-radius:12px; padding:12px 14px; font-size:13px;}
.pref-insight b{color:var(--olive-deep);}

/* ---------- recommendations ---------- */
.reco-bar{display:flex; gap:10px; align-items:flex-end; flex-wrap:wrap;}
.reco-bar .field{flex:1; min-width:180px; margin-bottom:0;}
.reco-list{display:flex; flex-direction:column; gap:12px; margin-top:16px;}
.reco-card{border:1px solid var(--line); border-radius:12px; padding:14px 16px; background:#FCFBF8;}
.reco-top{display:flex; align-items:flex-start; gap:10px; flex-wrap:wrap;}
.reco-top .nm{flex:1; min-width:180px;}
.reco-top .nm b{font-size:15px;}
.brand-tag{display:inline-block; font-size:11px; font-weight:700; background:#EEEEE8; color:var(--sub); border-radius:6px; padding:1px 8px; margin-right:6px;}
.match-wrap{display:flex; align-items:center; gap:8px; width:190px;}
.match-bar{flex:1; height:7px; border-radius:99px; background:#EDEBE2; overflow:hidden;}
.match-bar i{display:block; height:100%; background:linear-gradient(90deg,#8CA653,var(--olive-deep));}
.match-num{font-size:12px; font-weight:700; color:var(--olive-deep); white-space:nowrap;}
.reco-reasons{margin-top:8px; display:flex; flex-direction:column; gap:4px; font-size:12.5px;}
.reco-reasons .rr{display:flex; gap:7px;}
.reco-reasons .rr .ic{width:14px; flex-shrink:0; font-weight:800; text-align:center;}
.rr-good .ic{color:var(--good);} .rr-warn .ic{color:var(--caution);} .rr-info .ic{color:var(--sub);}
.reco-foot{margin-top:10px; display:flex; gap:8px; align-items:center; flex-wrap:wrap;}

/* ---------- v2: onboarding / refill / buy / modal ---------- */
.onboard{max-width:960px; margin:0 0 22px; background:var(--olive-soft); border:1px solid #DCE4C4; border-radius:12px; padding:12px 16px; display:flex; align-items:center; gap:12px; flex-wrap:wrap;}
.onboard b{color:var(--olive-deep);}
.onboard .ob-dots{display:flex; gap:5px;}
.onboard .ob-dot{width:12px; height:12px; border-radius:50%; background:#DDE3C9; border:1px solid #C6D0A4;}
.onboard .ob-dot.on{background:var(--olive-deep); border-color:var(--olive-deep);}
.dday{font-size:11px; font-weight:700; border-radius:6px; padding:1px 7px; background:#EEEEE8; color:var(--sub); margin-left:6px;}
.dday.soon{background:var(--hold-bg); color:var(--hold);}
.dday.over{background:var(--caution-bg); color:var(--caution);}
.refill{margin-top:14px; background:#FFF9EE; border:1px solid #EEDFC0; border-radius:12px; padding:12px 14px;}
.refill h4{font-size:13.5px; margin-bottom:8px;}
.refill .rf-item{display:flex; align-items:center; gap:10px; font-size:13px; padding:6px 0; flex-wrap:wrap;}
.refill .rf-item b{flex:1; min-width:140px;}
.buy-row{margin-top:12px; background:var(--good-bg); border:1px solid #D6E6D3; border-radius:10px; padding:10px 13px; font-size:13px;}
.buy-link{color:var(--good); font-weight:700;}
.ocr-row{margin-top:6px; display:flex; gap:8px; align-items:center; flex-wrap:wrap;}
.modal-back{position:fixed; inset:0; background:rgba(36,40,28,.45); z-index:100; display:flex; align-items:center; justify-content:center; padding:20px;}
.modal-back[hidden]{display:none;}
.modal{background:var(--surface); border-radius:16px; max-width:440px; width:100%; padding:24px; box-shadow:0 12px 40px rgba(0,0,0,.2);}
.modal h3{font-family:"Noto Serif KR", serif; font-size:18px; margin-bottom:10px;}
.modal ul{margin:10px 0 14px 18px; font-size:13.5px; display:flex; flex-direction:column; gap:5px;}
.modal .m-close{float:right; background:none; border:none; font-size:18px; color:var(--sub);}

/* ---------- v3: chronicle / conflict / sync ---------- */
.conflict-panel{margin-top:14px; background:var(--caution-bg); border:1px solid #EBD2C8; border-radius:12px; padding:12px 14px;}
.conflict-panel h4{font-size:13.5px; margin-bottom:8px; color:var(--caution);}
.cf-item{font-size:13px; padding:6px 0; border-bottom:1px dashed #EBD2C8;}
.cf-item:last-child{border-bottom:none;}
.cf-sev{font-size:10.5px; font-weight:800; border-radius:5px; padding:1px 6px; margin-right:6px;}
.cf-high{background:var(--caution); color:#fff;}
.cf-med{background:var(--hold); color:#fff;}
.chron-group{border:1px solid var(--line); border-radius:12px; padding:14px 16px; background:#FCFBF8; margin-top:12px;}
.chron-group h4{font-size:14.5px; font-family:"Noto Serif KR",serif;}
.chron-tags{display:flex; flex-wrap:wrap; gap:6px; margin:8px 0;}
.chron-tag{font-size:11.5px; border-radius:6px; padding:2px 9px; background:#EEEEE8; color:var(--sub); font-weight:600;}
.chron-tag b{color:var(--olive-deep);}
.chron-prods{font-size:12.5px; color:var(--sub); margin-top:4px; line-height:1.8;}
.chron-insight{margin-top:6px; font-size:12.5px; color:var(--olive-deep); font-weight:600;}
.briefing{margin-top:6px; padding-left:12px; border-left:2px solid #EEDFC0; font-size:12.5px; color:var(--sub); width:100%;}
.briefing b{color:var(--ink);}
#syncText{width:100%; min-height:110px; font-size:11px; font-family:monospace; word-break:break-all;}

.grade-b{font-size:10px; font-weight:800; border-radius:4px; padding:1px 5px; margin-left:5px; vertical-align:1px; white-space:nowrap;}
.gA{background:#414F22; color:#fff;}
.gB{background:#8CA653; color:#fff;}
.gC{background:#C9C6B8; color:#3C3F33;}

/* ---------- quick nav ---------- */
.quicknav{position:sticky; top:57px; z-index:40; background:rgba(246,244,238,.96); backdrop-filter:blur(6px); border-bottom:1px solid var(--line); overflow-x:auto; white-space:nowrap; scrollbar-width:none;}
.quicknav::-webkit-scrollbar{display:none;}
.quicknav-in{max-width:960px; margin:0 auto; padding:8px 20px; display:flex; gap:8px;}
.qn-link{flex-shrink:0; font-size:12.5px; font-weight:600; color:var(--sub); background:var(--surface); border:1px solid var(--line); border-radius:999px; padding:5px 13px; text-decoration:none;}
.qn-link.active{background:var(--olive-deep); border-color:var(--olive-deep); color:#fff;}

/* ---------- ingredient lookup ---------- */
.lookup-box{position:relative;}
.lookup-results{position:absolute; top:100%; left:0; right:0; background:var(--surface); border:1px solid var(--line); border-radius:12px; box-shadow:0 8px 24px rgba(36,40,28,.12); margin-top:6px; max-height:360px; overflow-y:auto; z-index:30;}
.lookup-item{padding:12px 16px; border-bottom:1px solid #F0EEE5; cursor:default;}
.lookup-item:last-child{border-bottom:none;}
.lookup-item .li-head{display:flex; align-items:center; gap:8px; margin-bottom:4px;}
.lookup-item b{font-size:14px;}
.lookup-empty{padding:16px; text-align:center; color:var(--sub); font-size:13px;}
.lookup-tags{display:flex; gap:6px; margin-top:8px; flex-wrap:wrap;}

footer{max-width:960px; margin:0 auto; padding:0 20px 40px; font-size:11.5px; color:var(--sub); line-height:1.7;}
</style>
</head>
<body>

<header>
  <div class="head-in">
    <div class="logo">핏<em>체크</em></div>
    <div class="head-note">또 안 맞는 화장품 사기 전에, 한 번 거르기</div>
    <button class="btn btn-ghost btn-sm" id="premiumBtn" style="margin-left:auto;">프리미엄</button>
    <div class="shade-chip" title="현재 설정된 내 피부톤" style="margin-left:0;">
      <div class="shade-dot" id="headShade"></div>
      <div class="shade-meta">
        <b id="headShadeHex">피부톤 미설정</b>
        <span id="headShadeTone">사진에서 추출하세요</span>
      </div>
    </div>
  </div>
</header>

<div class="quicknav">
  <div class="quicknav-in" id="quicknavIn">
    <a class="qn-link" href="#step1" data-sec="step1">STEP1 프로필</a>
    <a class="qn-link" href="#stepRecord" data-sec="stepRecord">STEP2 기록</a>
    <a class="qn-link" href="#stepReco" data-sec="stepReco">STEP3 추천</a>
    <a class="qn-link" href="#stepChron" data-sec="stepChron">연대기</a>
    <a class="qn-link" href="#step2" data-sec="step2">STEP4 검증</a>
    <a class="qn-link" href="#step3" data-sec="step3">STEP5 보드</a>
    <a class="qn-link" href="#lookupSec" data-sec="lookupSec">성분사전</a>
  </div>
</div>

<main>
  <div class="intro">
    <h1>또 안 맞는 화장품에 돈 쓰기 전에, 내 실패 이력으로 거르세요</h1>
    <p>안 맞았던 제품의 성분이 진짜 데이터입니다. 써본 화장품을 기록하면 성분 취향을 학습해서, 새 제품이 나에게 맞는지 사기 전에 판단할 수 있습니다. 데이터는 이 기기에 자동 저장됩니다.</p>
  </div>

  <section id="lookupSec">
    <div class="sec-head"><span class="step">성분사전</span><h2>성분 하나만 빠르게 찾아보기</h2></div>
    <div class="card">
      <div class="field lookup-box">
        <input type="text" id="lookupInput" placeholder="성분명 입력 (예: 나이아신아마이드, 알코올, 향료)" autocomplete="off">
        <div class="lookup-results" id="lookupResults" hidden></div>
      </div>
      <p class="hint" style="margin-top:8px;">STEP 1에서 프로필을 설정하면 내 피부 기준으로 주의·도움 여부가 반영됩니다. 설정 전에는 일반 기준으로만 보여줍니다.</p>
    </div>
  </section>

  <div class="onboard" id="onboard" hidden>
    <span>🧴 <b>시작하기:</b> 지금 화장대에 있는 화장품 3개만 STEP 2에 등록해보세요. 3개부터 추천이 정확해집니다.</span>
    <div class="ob-dots" id="obDots"><span class="ob-dot"></span><span class="ob-dot"></span><span class="ob-dot"></span></div>
    <span class="hint" id="obCount">0/3</span>
    <button class="btn btn-ghost btn-sm" id="starterBtn">처음이라 기록이 없어요 → 저자극 스타터 추천</button>
  </div>

  <!-- STEP 1 -->
  <section id="step1">
    <div class="sec-head"><span class="step">STEP 1</span><h2>내 피부 프로필</h2></div>
    <div class="grid2">
      <div class="card">
        <div class="field">
          <span class="lab">얼굴 사진 <span class="hint">— 업로드 후 뺨/이마 부위를 클릭하면 피부톤을 추출합니다</span></span>
          <div class="photo-zone" id="photoZone">
            <span style="font-size:28px">📷</span>
            <button class="btn btn-primary btn-sm" id="uploadBtn">사진 선택</button>
            <span class="hint">그림자 없는 자연광 사진이 정확합니다</span>
            <input type="file" id="photoInput" accept="image/*" hidden>
          </div>
          <p class="privacy"><b>개인정보 안전:</b> 사진은 브라우저 안에서만 처리되며 어디로도 전송·저장되지 않습니다.</p>
        </div>
        <div class="field">
          <span class="lab">피부톤 미세 조절 <span class="hint">— 조명 때문에 실제와 다르면 보정하세요</span></span>
          <div class="slider-row">
            <label for="adjLight">밝기</label>
            <input type="range" id="adjLight" min="-40" max="40" value="0" step="1">
            <output id="adjLightOut">0</output>
          </div>
          <div class="slider-row">
            <label for="adjWarm">웜 ↔ 쿨</label>
            <input type="range" id="adjWarm" min="-30" max="30" value="0" step="1">
            <output id="adjWarmOut">0</output>
          </div>
          <div class="tone-preview">
            <div class="tone-swatch" id="toneSwatch"></div>
            <div class="tone-info">
              <b id="toneHex">아직 추출 전</b><span class="undertone-tag ut-neutral" id="undertoneTag" hidden>뉴트럴</span>
              <div class="hint" id="toneDesc">사진에서 피부 부위를 클릭하면 여기 표시됩니다.</div>
            </div>
          </div>
        </div>
      </div>

      <div class="card">
        <div class="field">
          <span class="lab">피부 타입</span>
          <div class="chips" id="skinTypeChips" role="group" aria-label="피부 타입">
            <button class="chip" data-v="건성" aria-pressed="false">건성</button>
            <button class="chip" data-v="지성" aria-pressed="false">지성</button>
            <button class="chip" data-v="복합성" aria-pressed="false">복합성</button>
            <button class="chip" data-v="민감성" aria-pressed="false">민감성</button>
            <button class="chip" data-v="중성" aria-pressed="false">중성</button>
          </div>
        </div>
        <div class="field">
          <span class="lab">피부 고민 <span class="hint">— 복수 선택</span></span>
          <div class="chips" id="concernChips" role="group" aria-label="피부 고민">
            <button class="chip" data-v="여드름" aria-pressed="false">여드름·트러블</button>
            <button class="chip" data-v="흉터" aria-pressed="false">여드름 흉터·자국</button>
            <button class="chip" data-v="색소침착" aria-pressed="false">색소침착·미백</button>
            <button class="chip" data-v="주름" aria-pressed="false">주름·탄력</button>
            <button class="chip" data-v="모공" aria-pressed="false">모공·피지</button>
            <button class="chip" data-v="각질" aria-pressed="false">각질·피부결</button>
            <button class="chip" data-v="건조" aria-pressed="false">건조·당김</button>
            <button class="chip" data-v="홍조" aria-pressed="false">홍조·진정</button>
          </div>
        </div>
        <div class="field">
          <label for="ageSel">연령대</label>
          <select id="ageSel">
            <option value="">선택 안 함</option>
            <option>10대</option><option>20대</option><option>30대</option>
            <option>40대</option><option>50대 이상</option>
          </select>
        </div>
        <div class="field">
          <span class="lab">임신·수유 <span class="hint">— 해당 시 주의 성분을 최우선으로 경고합니다</span></span>
          <div class="chips" id="pregChips" role="group" aria-label="임신 수유 여부">
            <button class="chip" data-v="preg" aria-pressed="false">🤰 임신·수유 중</button>
          </div>
        </div>
        <div class="field">
          <span class="lab">피해야 할 성분 <span class="hint">— 알레르기·기피 성분</span></span>
          <div class="chips" id="avoidChips" role="group" aria-label="기피 성분">
            <button class="chip" data-v="향료" aria-pressed="false">향료</button>
            <button class="chip" data-v="알코올" aria-pressed="false">알코올</button>
            <button class="chip" data-v="파라벤" aria-pressed="false">파라벤</button>
            <button class="chip" data-v="설페이트" aria-pressed="false">설페이트</button>
            <button class="chip" data-v="인공색소" aria-pressed="false">인공색소</button>
          </div>
          <input type="text" id="customAvoid" placeholder="직접 입력: 쉼표로 구분 (예: 티트리, 라놀린)" style="margin-top:8px">
        </div>
      </div>
    </div>
  </section>

  <!-- STEP 2: 사용 기록 -->
  <section id="stepRecord">
    <div class="sec-head"><span class="step">STEP 2</span><h2>내가 써본 화장품 기록</h2></div>
    <div class="card">
      <div class="grid2">
        <div>
          <div class="field">
            <label for="rName">제품명</label>
            <input type="text" id="rName" placeholder="예: ○○ 수분 크림">
          </div>
          <div class="field" style="display:flex; gap:10px;">
            <div style="flex:1">
              <label for="rBrand">브랜드 <span class="hint">(선택)</span></label>
              <input type="text" id="rBrand" placeholder="예: 라운드○">
            </div>
            <div style="flex:1">
              <label for="rCat">카테고리</label>
              <select id="rCat">
                <option value="토너">토너·스킨</option>
                <option value="에센스·세럼">에센스·세럼·앰플</option>
                <option value="로션·크림">로션·크림</option>
                <option value="선케어">선케어</option>
                <option value="클렌징">클렌징</option>
                <option value="기타">기타</option>
              </select>
            </div>
          </div>
          <div class="field">
            <span class="lab">나에게 어땠나요?</span>
            <div class="rating-btns" id="ratingBtns" role="group" aria-label="사용 평가">
              <button class="r-btn r-good" data-v="1" aria-pressed="false">😊 좋았음</button>
              <button class="r-btn r-mid" data-v="0" aria-pressed="false">😐 보통</button>
              <button class="r-btn r-bad" data-v="-1" aria-pressed="false">😖 안 맞았음</button>
            </div>
          </div>
          <div class="field">
            <span class="lab">사용감(텍스처)</span>
            <div class="chips" id="textureChips" role="group" aria-label="사용감">
              <button class="chip" data-v="워터리" aria-pressed="false">💧 워터리·산뜻</button>
              <button class="chip" data-v="젤" aria-pressed="false">젤</button>
              <button class="chip" data-v="로션" aria-pressed="false">로션</button>
              <button class="chip" data-v="크림·밤" aria-pressed="false">크림·밤 (무거움)</button>
              <button class="chip" data-v="유분감" aria-pressed="false">유분감 있음</button>
            </div>
          </div>
          <div class="field">
            <span class="lab">인증·라벨 <span class="hint">— 패키지/상세페이지 표기 기준, 복수 선택</span></span>
            <div class="chips" id="certChips" role="group" aria-label="인증 라벨">
              <button class="chip" data-v="기능성(미백)" aria-pressed="false">기능성 미백</button>
              <button class="chip" data-v="기능성(주름개선)" aria-pressed="false">기능성 주름개선</button>
              <button class="chip" data-v="기능성(자외선차단)" aria-pressed="false">기능성 자외선차단</button>
              <button class="chip" data-v="저자극 테스트" aria-pressed="false">저자극 테스트</button>
              <button class="chip" data-v="비건" aria-pressed="false">비건</button>
              <button class="chip" data-v="무향료" aria-pressed="false">무향료</button>
            </div>
          </div>
          <div class="field">
            <label for="rMemo">메모 <span class="hint">(선택 — 예: 트러블 올라옴, 겨울에 좋음)</span></label>
            <input type="text" id="rMemo" placeholder="한 줄 메모">
          </div>
          <div class="field" style="display:flex; gap:10px;">
            <div style="flex:1">
              <label for="rOpened">개봉일 <span class="hint">(선택)</span></label>
              <input type="date" id="rOpened" style="width:100%; border:1px solid var(--line); border-radius:10px; padding:8px 12px; background:#FCFBF8;">
            </div>
            <div style="flex:1">
              <label for="rCycle">예상 소진 주기</label>
              <select id="rCycle">
                <option value="">모름</option>
                <option value="1">약 1개월</option>
                <option value="2">약 2개월</option>
                <option value="3">약 3개월</option>
                <option value="6">약 6개월</option>
              </select>
            </div>
          </div>
        </div>
        <div>
          <div class="field">
            <label for="rIngredients">전성분 <span class="hint">— 추천 정확도의 핵심입니다. 상세페이지에서 복사하거나 라벨 사진으로 인식하세요</span></label>
            <textarea id="rIngredients" placeholder="정제수, 글리세린, 세라마이드엔피 ..." style="min-height:120px"></textarea>
            <div class="ocr-row">
              <button class="btn btn-ghost btn-sm" data-ocr="rIngredients">📷 라벨 사진으로 성분 인식 (OCR)</button>
              <span class="hint" id="ocr-rIngredients"></span>
            </div>
          </div>
          <div style="display:flex; justify-content:flex-end;">
            <button class="btn btn-primary" id="addRecordBtn">기록에 추가</button>
          </div>
        </div>
      </div>

      <div class="rec-list" id="recList"></div>
      <div class="refill" id="refillPanel" hidden>
        <h4>🔔 리필 레이더 — 소진 임박·초과 제품</h4>
        <div id="refillList"></div>
        <div style="display:flex; gap:8px; margin-top:10px; flex-wrap:wrap;">
          <button class="btn btn-ghost btn-sm" id="icsBtn">📅 소진 예정일 캘린더 파일(.ics) 받기</button>
          <button class="btn btn-ghost btn-sm" id="notifBtn">🔕 브라우저 알림 켜기</button>
        </div>
      </div>
      <div class="conflict-panel" id="conflictPanel" hidden>
        <h4>🧪 내 루틴 성분 충돌 검사</h4>
        <div id="conflictList"></div>
      </div>
      <div class="pref-insight" id="prefInsight" hidden></div>

      <div class="io-row">
        <span class="hint" style="flex:1">데이터는 이 기기에 자동 저장됩니다. 다른 기기로 옮기려면 파일 또는 동기화 코드를 쓰세요.</span>
        <button class="btn btn-ghost btn-sm" id="exportBtn">기록 내보내기 (JSON)</button>
        <button class="btn btn-ghost btn-sm" id="importBtn">기록 불러오기</button>
        <button class="btn btn-ghost btn-sm" id="syncBtn">🔄 기기 간 동기화</button>
        <input type="file" id="importInput" accept="application/json" hidden>
      </div>
    </div>
  </section>

  <!-- STEP 3: 추천 -->
  <section id="stepReco">
    <div class="sec-head"><span class="step">STEP 3</span><h2>기초화장품 맞춤 추천</h2></div>
    <div class="card">
      <div class="reco-bar">
        <div class="field">
          <label for="recoCat">추천받을 카테고리</label>
          <select id="recoCat">
            <option value="전체">전체 (기초 전 카테고리)</option>
            <option value="토너">토너·스킨</option>
            <option value="에센스·세럼">에센스·세럼·앰플</option>
            <option value="로션·크림">로션·크림</option>
            <option value="선케어">선케어</option>
            <option value="클렌징">클렌징</option>
          </select>
        </div>
        <button class="btn btn-primary" id="recoBtn">내 기록 기반으로 추천</button>
      </div>
      <p class="hint" style="margin-top:10px;">
        알고리즘: ① 좋았던 제품의 성분에 +, 안 맞았던 제품의 성분에 − 가중치를 학습 → ② 내 피부 프로필 적합도 → ③ 좋았던 제품과의 성분 유사도를 합산해 순위를 매깁니다.
        비교 카탈로그는 성분 구성 기반의 <b>가상 브랜드 예시</b>이며, 실제 구매 전엔 동일 컨셉의 실제 제품 전성분을 STEP 4에서 검증하세요.
      </p>
      <div class="reco-list" id="recoList"></div>
    </div>
  </section>

  <!-- 연대기 -->
  <section id="stepChron">
    <div class="sec-head"><span class="step">연대기</span><h2>내 피부 연대기 — 계절·상태 변화 추적</h2></div>
    <div class="card">
      <div class="field">
        <span class="lab">오늘 피부 상태 체크인 <span class="hint">— 주 1~2회면 충분합니다. 쌓이면 계절별 리포트가 만들어집니다</span></span>
        <div class="chips" id="checkinChips" role="group" aria-label="오늘 피부 상태">
          <button class="chip" data-v="좋음" aria-pressed="false">😊 좋음</button>
          <button class="chip" data-v="트러블" aria-pressed="false">트러블</button>
          <button class="chip" data-v="건조" aria-pressed="false">건조·당김</button>
          <button class="chip" data-v="유분과다" aria-pressed="false">유분 과다</button>
          <button class="chip" data-v="홍조" aria-pressed="false">홍조·예민</button>
        </div>
        <div style="display:flex; gap:8px; margin-top:10px;">
          <input type="text" id="checkinMemo" placeholder="메모 (선택 — 예: 환절기라 뒤집어짐)" style="flex:1">
          <button class="btn btn-primary btn-sm" id="checkinBtn">오늘 기록</button>
        </div>
      </div>
      <div id="chronBody"><p class="hint" style="text-align:center; padding:10px;">체크인과 화장품 기록이 쌓이면 계절별 타임라인이 여기 표시됩니다.</p></div>
    </div>
  </section>

  <!-- STEP 4 -->
  <section id="step2">
    <div class="sec-head"><span class="step">STEP 4</span><h2>새 상품 검증</h2></div>
    <div class="card">
      <div class="grid2">
        <div>
          <div class="field">
            <label for="pName">상품명</label>
            <input type="text" id="pName" placeholder="예: ○○ 수분 크림 50ml">
          </div>
          <div class="field">
            <label for="pCat">카테고리</label>
            <select id="pCat">
              <option value="스킨케어">스킨케어</option>
              <option value="베이스메이크업">베이스 메이크업 (쿠션·파운데이션)</option>
              <option value="색조">색조 (립·블러셔·섀도우)</option>
              <option value="선케어">선케어</option>
              <option value="클렌징">클렌징</option>
              <option value="마스크팩">마스크·팩</option>
              <option value="헤어/바디">헤어·바디</option>
            </select>
          </div>
          <div class="field" id="shadeField" hidden>
            <label for="pShade">제품 색상 <span class="hint">— 상세페이지 색상을 눈대중으로 맞추거나 호수 참고</span></label>
            <div style="display:flex; gap:10px; align-items:center;">
              <input type="color" id="pShade" value="#f2d5b8" style="width:56px; height:38px; border:1px solid var(--line); border-radius:8px; background:#FCFBF8; padding:2px;">
              <input type="text" id="pShadeName" placeholder="호수/색상명 (예: 21호 라이트베이지)" style="flex:1">
            </div>
          </div>
          <div class="field">
            <span class="lab">인증·라벨 표기 <span class="hint">— 있는 것만 선택</span></span>
            <div class="chips" id="vCertChips" role="group" aria-label="제품 인증 라벨">
              <button class="chip" data-v="기능성(미백)" aria-pressed="false">기능성 미백</button>
              <button class="chip" data-v="기능성(주름개선)" aria-pressed="false">기능성 주름개선</button>
              <button class="chip" data-v="기능성(자외선차단)" aria-pressed="false">기능성 자외선차단</button>
              <button class="chip" data-v="저자극 테스트" aria-pressed="false">저자극 테스트</button>
              <button class="chip" data-v="비건" aria-pressed="false">비건</button>
              <button class="chip" data-v="무향료" aria-pressed="false">무향료</button>
            </div>
          </div>
          <div class="field">
            <label for="vTexture">사용감(텍스처) <span class="hint">— 리뷰·상세페이지 참고 (선택)</span></label>
            <select id="vTexture">
              <option value="">모름</option>
              <option value="워터리">워터리·산뜻</option>
              <option value="젤">젤</option>
              <option value="로션">로션</option>
              <option value="크림·밤">크림·밤 (무거움)</option>
              <option value="유분감">유분감 있음</option>
            </select>
          </div>
        </div>
        <div>
          <div class="field">
            <label for="pIngredients">전성분 <span class="hint">— 올리브영 상세페이지 '화장품법에 따른 전성분'을 복사해 붙여넣기</span></label>
            <textarea id="pIngredients" placeholder="정제수, 글리세린, 나이아신아마이드, 향료, 리모넨 ..."></textarea>
            <div class="ocr-row">
              <button class="btn btn-ghost btn-sm" data-ocr="pIngredients">📷 라벨 사진으로 성분 인식 (OCR)</button>
              <span class="hint" id="ocr-pIngredients"></span>
            </div>
          </div>
          <div style="display:flex; gap:8px; justify-content:flex-end;">
            <button class="btn btn-ghost btn-sm" id="clearFormBtn">지우기</button>
            <button class="btn btn-primary" id="analyzeBtn">체크리스트 만들기</button>
          </div>
        </div>
      </div>
      <div class="field" style="margin-top:14px; border-top:1px dashed var(--line); padding-top:12px;">
        <span class="lab">예시 데이터로 먼저 써보기 <span class="hint">— 가상의 예시 상품입니다 (실제 제품 아님)</span></span>
        <div class="samples" id="sampleBtns"></div>
      </div>
    </div>
  </section>

  <!-- STEP 5 -->
  <section id="step3">
    <div class="sec-head"><span class="step">STEP 5</span><h2>판단 보드</h2></div>
    <p class="hint" style="margin:-6px 0 12px;">성분 근거 등급 — <span class="grade-b gA">근거 A</span> 식약처 고시·사용제한 근거 / <span class="grade-b gB">근거 B</span> 피부과학 문헌 컨센서스 / <span class="grade-b gC">근거 C</span> 사용자 보고·논란 수준</p>
    <div id="board"><div class="card empty-board">아직 분석한 상품이 없습니다. STEP 4에서 상품을 입력해보세요.</div></div>

    <div class="sec-head" style="margin-top:26px;"><span class="step">비교</span><h2>내 결정 한눈에 보기</h2></div>
    <div class="card">
      <div class="cmp-wrap">
        <table id="cmpTable">
          <thead><tr><th>상품</th><th>카테고리</th><th>참고 점수</th><th>주의 성분</th><th>내 판단</th><th></th></tr></thead>
          <tbody id="cmpBody"><tr><td colspan="6" style="color:var(--sub); text-align:center;">비교할 상품이 없습니다</td></tr></tbody>
        </table>
      </div>
    </div>
  </section>
</main>

<input type="file" id="ocrFile" accept="image/*" hidden>

<div class="modal-back" id="premiumModal" hidden>
  <div class="modal" role="dialog" aria-label="프리미엄 안내">
    <button class="m-close" id="premiumClose" aria-label="닫기">✕</button>
    <h3>핏체크 프리미엄</h3>
    <p style="font-size:13.5px; color:var(--sub);">아래 기능이 현재 버전에 포함되어 있습니다.</p>
    <ul>
      <li>피부 연대기 — 계절·상태 변화 리포트 (연대기 섹션)</li>
      <li>성분 조합 충돌 검사 — 루틴 자동 검사 + 새 제품 검증 시 경고</li>
      <li>재구매 주기 알림 — 리필 레이더 + 캘린더(.ics) + 브라우저 알림, 갈아타기 브리핑 자동 생성</li>
      <li>기기 간 동기화 — 동기화 코드 방식 (계정 기반 클라우드 동기화는 준비 중)</li>
    </ul>
    <div style="display:flex; gap:8px; align-items:center;">
      <button class="btn btn-primary btn-sm" id="interestBtn">계정 클라우드 동기화 필요해요 👍</button>
      <span class="hint" id="interestMsg"></span>
    </div>
    <p class="hint" style="margin-top:8px;">관심 표시 횟수만 이 기기에 저장됩니다. 개인정보는 수집하지 않습니다.</p>
  </div>
</div>

<div class="modal-back" id="syncModal" hidden>
  <div class="modal" role="dialog" aria-label="기기 간 동기화">
    <button class="m-close" id="syncClose" aria-label="닫기">✕</button>
    <h3>기기 간 동기화</h3>
    <p style="font-size:13px; color:var(--sub); margin-bottom:10px;">
      이 기기의 데이터를 코드로 만들어 다른 기기에 붙여넣으면 그대로 복원됩니다. 코드에는 프로필·기록·판정이 포함되니 타인과 공유하지 마세요.
    </p>
    <textarea id="syncText" placeholder="여기에 코드가 생성되거나, 다른 기기의 코드를 붙여넣으세요"></textarea>
    <div style="display:flex; gap:8px; margin-top:10px;">
      <button class="btn btn-primary btn-sm" id="syncGenBtn">이 기기 코드 생성</button>
      <button class="btn btn-ghost btn-sm" id="syncCopyBtn">복사</button>
      <button class="btn btn-ghost btn-sm" id="syncApplyBtn" style="margin-left:auto; border-color:var(--caution); color:var(--caution);">코드 적용 (현재 데이터 대체)</button>
    </div>
    <p class="hint" id="syncMsg" style="margin-top:8px;"></p>
  </div>
</div>

<div class="modal-back" id="metricsModal" hidden>
  <div class="modal" role="dialog" aria-label="운영 지표">
    <button class="m-close" id="metricsClose" aria-label="닫기">✕</button>
    <h3>운영 지표 (AARRR)</h3>
    <p style="font-size:12.5px; color:var(--sub); margin-bottom:10px;">이 기기에 기록된 계측값입니다. 서버 없이 로컬에서만 집계됩니다.</p>
    <div id="metricsBody" style="font-size:13px;"></div>
  </div>
</div>

<footer>
  ⚠ 본 도구의 성분 정보와 점수는 일반적인 참고용이며 의학적 조언이 아닙니다. 알레르기·피부 질환이 있다면 전문의와 상담하고, 새 제품은 팔 안쪽 패치 테스트 후 사용하세요.
  프로필·기록·판정은 이 기기(브라우저 저장소)에 자동 저장됩니다. 기기 변경 대비 백업은 STEP 2의 '기록 내보내기'를 사용하세요. 사진은 저장되지 않습니다.
  <a href="#" id="metricsBtn" style="color:var(--olive-deep);">운영 지표 보기</a>
</footer>

<script>
"use strict";
/* ================= state ================= */
const state = {
  tone: null,            // {r,g,b} raw sampled
  adjust: { light: 0, warm: 0 },
  skinType: null,
  concerns: new Set(),
  age: "",
  avoid: new Set(),
  products: [],          // {id,name,cat,shade,shadeName,ingredients,analysis,verdict}
  records: [],           // {id,name,brand,cat,rating,memo,ingredients,openedAt,cycle,tokens,keys}
  leads: [],             // 프리미엄 알림 신청 (가짜 문 검증용)
  checkins: [],          // {date, tags[], memo} 피부 상태 체크인
  metrics: {firstVisit:null, visits:[], activatedAt:null}, // AARRR 계측
  events: {recordsAdded:0, verdicts:0, exports:0, premiumOpens:0, ocrRuns:0, syncGens:0}
};
let pid = 0, rid = 0;
let hydrated = false;

/* ================= 영속화: window.storage(클라우드 아티팩트) → localStorage(로컬 파일) → 메모리 ================= */
const memStore = {};
const STORE_KEY = "fitcheck-v2";
async function storeSet(val){
  const s = JSON.stringify(val);
  try{ if(window.storage){ await window.storage.set(STORE_KEY, s); return; } }catch(e){}
  try{ localStorage.setItem(STORE_KEY, s); return; }catch(e){}
  memStore[STORE_KEY] = s;
}
async function storeGet(){
  try{ if(window.storage){ const r = await window.storage.get(STORE_KEY); if(r && r.value) return JSON.parse(r.value); } }catch(e){}
  try{ const v = localStorage.getItem(STORE_KEY); if(v) return JSON.parse(v); }catch(e){}
  return memStore[STORE_KEY] ? JSON.parse(memStore[STORE_KEY]) : null;
}
function snapshot(){
  return {
    version: 2,
    profile: {
      skinType: state.skinType, concerns: [...state.concerns], avoid: [...state.avoid],
      age: state.age, customAvoid: $("#customAvoid").value, pregnant: !!state.pregnant,
      tone: state.tone, adjust: state.adjust
    },
    records: state.records.map(({id,name,brand,cat,rating,memo,ingredients,openedAt,cycle,createdAt,texture,certs})=>({id,name,brand,cat,rating,memo,ingredients,openedAt,cycle,createdAt,texture,certs})),
    products: state.products.map(({name,cat,shade,shadeName,ingredients,verdict,texture,certs})=>({name,cat,shade,shadeName,ingredients,verdict,texture,certs})),
    checkins: state.checkins,
    metrics: state.metrics,
    leads: state.leads, events: state.events
  };
}
let saveTimer = null;
function saveAll(){
  if(!hydrated) return;
  clearTimeout(saveTimer);
  saveTimer = setTimeout(()=>storeSet(snapshot()), 300);
}
function reviveRecord(r){
  const tokens = tokenizeIngredients(r.ingredients||"");
  return {id:++rid, name:r.name, brand:r.brand||"", cat:r.cat||"기타",
    rating:[1,0,-1].includes(r.rating)?r.rating:0, memo:r.memo||"", ingredients:r.ingredients||"",
    openedAt:r.openedAt||"", cycle:r.cycle||"", createdAt:r.createdAt||r.openedAt||"",
    texture:r.texture||"", certs:Array.isArray(r.certs)?r.certs:[],
    tokens, nset:new Set(tokens.map(norm)), keys:matchKeys(tokens)};
}
function applyData(data){
  state.records.length = 0; state.products.length = 0;
  const p = data.profile||{};
  state.skinType = p.skinType||null;
  state.concerns = new Set(p.concerns||[]);
  state.avoid = new Set(p.avoid||[]);
  state.age = p.age||"";
  state.pregnant = !!p.pregnant;
  document.querySelectorAll("#pregChips .chip").forEach(b=>b.setAttribute("aria-pressed", state.pregnant?"true":"false"));
  state.tone = p.tone||null;
  state.adjust = p.adjust||{light:0,warm:0};
  state.leads = data.leads||[];
  state.checkins = Array.isArray(data.checkins)?data.checkins:[];
  state.metrics = Object.assign({firstVisit:null, visits:[], activatedAt:null}, data.metrics||{});
  state.events = Object.assign(state.events, data.events||{});
  $("#customAvoid").value = p.customAvoid||"";
  $("#ageSel").value = state.age;
  $("#adjLight").value = state.adjust.light; $("#adjLightOut").textContent = state.adjust.light;
  $("#adjWarm").value = state.adjust.warm; $("#adjWarmOut").textContent = state.adjust.warm;
  document.querySelectorAll("#skinTypeChips .chip").forEach(b=>b.setAttribute("aria-pressed", b.dataset.v===state.skinType?"true":"false"));
  document.querySelectorAll("#concernChips .chip").forEach(b=>b.setAttribute("aria-pressed", state.concerns.has(b.dataset.v)?"true":"false"));
  document.querySelectorAll("#avoidChips .chip").forEach(b=>b.setAttribute("aria-pressed", state.avoid.has(b.dataset.v)?"true":"false"));
  (data.records||[]).forEach(r=>{ if(r.name && r.ingredients) state.records.push(reviveRecord(r)); });
  (data.products||[]).forEach(pr=>{
    if(!pr.name || !pr.ingredients) return;
    const np = {id:++pid, name:pr.name, cat:pr.cat||"스킨케어", shade:pr.shade||null, shadeName:pr.shadeName||null,
      ingredients:pr.ingredients, verdict:pr.verdict||null, texture:pr.texture||"", certs:Array.isArray(pr.certs)?pr.certs:[]};
    np.analysis = analyzeProduct(np);
    state.products.push(np);
  });
}
async function hydrate(){
  const data = await storeGet();
  if(data) applyData(data);
  // 유입 채널 기록 (?ref=커뮤니티명 — SEO·크리에이터 링크 성과 측정용)
  try{
    const ref = new URLSearchParams(location.search).get("ref");
    if(ref){
      state.events.refs = state.events.refs || {};
      state.events.refs[ref] = (state.events.refs[ref]||0) + 1;
    }
  }catch(e){}
  // 방문 계측 (AARRR)
  const today = new Date().toISOString().slice(0,10);
  if(!state.metrics.firstVisit) state.metrics.firstVisit = today;
  if(!state.metrics.visits.includes(today)){
    state.metrics.visits.push(today);
    if(state.metrics.visits.length > 400) state.metrics.visits.shift();
  }
  hydrated = true;
  renderTone(); renderRecords(); renderBoard();
  notifyDueItems();
  saveAll();
}

/* ================= ingredient knowledge base ================= */
/* type: caution | good ; for: skin types or concerns it relates to */
const ING_DB = [
  {names:["에탄올","변성알코올","알코올","알콜","에틸알코올"], key:"알코올", type:"caution", for:["건성","민감성","건조","홍조"], note:"휘발되며 수분을 빼앗아 건성·민감성 피부에 자극이 될 수 있음"},
  {names:["향료","프래그런스","퍼퓸"], key:"향료", type:"caution", for:["민감성","홍조"], note:"민감성 피부에 접촉성 자극 가능성"},
  {names:["메틸파라벤","에틸파라벤","프로필파라벤","부틸파라벤","파라벤"], key:"파라벤", type:"caution", for:["민감성"], note:"보존제. 민감성 피부는 반응 여부 확인 권장"},
  {names:["소듐라우릴설페이트","소듐라우레스설페이트","암모늄라우릴설페이트"], key:"설페이트", type:"caution", for:["건성","민감성","건조"], note:"강한 세정력으로 피부 장벽 약화 가능"},
  {names:["적색","황색","청색","녹색","타르색소"], key:"인공색소", type:"caution", for:["민감성","여드름"], note:"타르 색소 계열. 민감·트러블 피부 주의"},
  {names:["이소프로필미리스테이트","이소프로필팔미테이트","코코넛오일","코코넛야자오일"], key:"코메도제닉 오일", type:"caution", for:["지성","여드름","모공"], note:"모공을 막을 수 있는 성분(코메도제닉) — 지성·트러블 피부 주의"},
  {names:["미네랄오일","페트롤라툼","파라핀"], key:"광물성 오일", type:"caution", for:["지성","여드름","모공"], note:"폐색막 형성. 지성·트러블 피부는 답답할 수 있음"},
  {names:["라놀린"], key:"라놀린", type:"caution", for:["민감성","여드름"], note:"양모 유래 성분. 알레르기 보고 사례 있음"},
  {names:["레티놀","레티닐팔미테이트","레틴알"], key:"레티노이드", type:"mixed", preg:"금기", goodFor:["주름"], cautionFor:["민감성","홍조"], note:"주름·탄력에 효과적이나 자극 가능 — 저농도부터 적응 필요, 임신 중 사용 금기"},
  {names:["살리실릭애씨드","살리실산","비에이치에이"], key:"BHA", type:"mixed", preg:"주의", goodFor:["여드름","모공","각질"], cautionFor:["건성","민감성","건조"], note:"피지·각질 케어에 효과적이나 건성·민감성엔 건조 유발 가능"},
  {names:["글라이콜릭애씨드","락틱애씨드","시트릭애씨드","에이에이치에이"], key:"AHA", type:"mixed", goodFor:["색소침착","모공","각질","흉터"], cautionFor:["민감성","홍조"], note:"각질 케어·톤 개선. 민감성 피부는 따가움 주의, 사용 시 자외선 차단 필수"},
  {names:["티트리","티트리잎오일","티트리잎추출물"], key:"티트리", type:"mixed", goodFor:["여드름"], cautionFor:["민감성"], note:"트러블 진정에 도움되나 고농도는 자극 가능"},
  {names:["나이아신아마이드"], key:"나이아신아마이드", type:"good", for:["색소침착","모공","여드름","흉터"], note:"미백 기능성 성분. 피지 조절·톤 개선·자국 완화에 도움"},
  {names:["아스코빅애씨드","비타민c","아스코빌글루코사이드"], key:"비타민C", type:"good", for:["색소침착","흉터"], note:"항산화·톤 개선·자국 완화에 도움"},
  {names:["아젤라익애씨드","아젤라산"], key:"아젤라익애씨드", type:"good", for:["여드름","흉터","홍조","색소침착"], note:"트러블·자국·홍조에 두루 도움되는 성분"},
  {names:["알부틴","알파-알부틴"], key:"알부틴", type:"good", for:["색소침착","흉터"], note:"미백 기능성 고시 성분"},
  {names:["트라넥사믹애씨드","트라넥삼산"], key:"트라넥사믹애씨드", type:"good", for:["색소침착","흉터","홍조"], note:"색소 자국·홍조 완화에 도움"},
  {names:["벤조일퍼옥사이드","과산화벤조일"], key:"벤조일퍼옥사이드", type:"mixed", preg:"주의", goodFor:["여드름"], cautionFor:["민감성","건성"], note:"여드름 케어에 효과적이나 자극·건조·탈색 유발 가능"},
  {names:["히알루로닉애씨드","소듐하이알루로네이트","하이알루로닉애씨드","히알루론산"], key:"히알루론산", type:"good", for:["건성","건조"], note:"수분 보습 대표 성분"},
  {names:["세라마이드","세라마이드엔피","세라마이드에이피"], key:"세라마이드", type:"good", for:["건성","민감성","건조"], note:"피부 장벽 강화에 도움"},
  {names:["판테놀"], key:"판테놀", type:"good", for:["민감성","건조","홍조"], note:"진정·보습에 도움"},
  {names:["마데카소사이드","센텔라아시아티카추출물","병풀추출물","아시아티코사이드"], key:"센텔라(병풀)", type:"good", for:["민감성","홍조","여드름","흉터"], note:"진정·재생 케어 대표 성분"},
  {names:["알란토인"], key:"알란토인", type:"good", for:["민감성","홍조"], note:"피부 컨디셔닝·진정에 도움"},
  {names:["아데노신"], key:"아데노신", type:"good", for:["주름"], note:"주름 개선 기능성 성분"},
  {names:["펩타이드","팔미토일펜타펩타이드","아세틸헥사펩타이드"], key:"펩타이드", type:"good", for:["주름"], note:"탄력·주름 케어에 도움"},
  {names:["스쿠알란"], key:"스쿠알란", type:"good", for:["건성","건조"], note:"가벼운 보습 오일"},
  {names:["시어버터"], key:"시어버터", type:"mixed", goodFor:["건성","건조"], cautionFor:["지성","여드름"], note:"고보습이나 지성 피부엔 무거울 수 있음"},
  {names:["글리세린"], key:"글리세린", type:"good", for:["건성","건조"], note:"기본 보습 성분"},
  {names:["징크옥사이드","티타늄디옥사이드"], key:"무기자차 성분", type:"good", for:["민감성","여드름","홍조"], note:"무기계 자외선 차단 성분 — 비교적 자극이 적음"},
  {names:["옥시벤존","아보벤존","옥토크릴렌","에칠헥실메톡시신나메이트"], key:"유기자차 성분", type:"caution", for:["민감성","홍조"], note:"유기계 자외선 차단 성분 — 일부 피부에서 눈시림·자극 보고"},
  {names:["메칠이소치아졸리논","메틸이소치아졸리논","메칠클로로이소치아졸리논","메틸클로로이소치아졸리논"], key:"MIT/CMIT", type:"caution", universal:true, for:["민감성"], note:"알레르기성 접촉피부염 보고가 많은 보존제 — 국내에서 씻어내는 제품 외 사용이 제한된 성분"},
  {names:["트리클로산"], key:"트리클로산", type:"caution", preg:"주의", universal:true, for:["민감성"], note:"내분비계 영향 우려로 국내외에서 사용이 제한·축소되어 온 살균 보존 성분"},
  {names:["자몽껍질오일","레몬껍질오일","오렌지껍질오일","베르가못오일","라임오일"], key:"시트러스 오일(광독성)", type:"caution", universal:true, for:["민감성"], note:"광독성 가능성 — 낮에 사용 시 자외선 차단이 필수인 성분"},
  {names:["페녹시에탄올"], key:"페녹시에탄올", type:"caution", for:["민감성","홍조"], note:"보존제. 허용 농도 내에서 대체로 안전하나 민감 피부는 따가움 보고 있음"},
  {names:["프로필렌글라이콜"], key:"프로필렌글라이콜", type:"caution", for:["민감성"], note:"보습·용제 성분. 민감 피부에서 접촉 자극 보고 사례 있음"},
  {names:["부틸하이드록시아니솔","부틸하이드록시톨루엔"], key:"BHA/BHT 산화방지제", type:"caution", for:["민감성"], note:"산화방지제. 민감 피부 자극 가능성이 논의되는 성분"},
  {names:["라벤더오일","페퍼민트오일","유칼립투스오일","로즈마리잎오일","일랑일랑꽃오일"], key:"에센셜 오일", type:"caution", for:["민감성","홍조"], note:"천연 유래여도 접촉 자극·알레르기 유발 가능"},
  {names:["위치하젤추출물","하마멜리스"], key:"위치하젤", type:"mixed", goodFor:["지성","모공"], cautionFor:["민감성","건성"], note:"수렴 효과가 있으나 탄닌 성분으로 민감·건성 피부엔 자극 가능"},
  {names:["다이메티콘","디메치콘","사이클로펜타실록세인","사이클로헥사실록세인"], key:"실리콘", type:"caution", for:["여드름","모공"], note:"발림성 개선 성분. 대체로 안전하나 일부 트러블 피부는 답답함을 호소"},
  {names:["탤크"], key:"탤크", type:"caution", for:["민감성"], note:"파우더 원료. 흡입 주의 및 원료 품질 논란 이력이 있는 성분"}
];

/* 착향제 알레르기 유발 고시 성분 (표시 의무 25종) */
const ALLERGEN_25 = ["리모넨","리날룰","시트랄","제라니올","유제놀","이소유제놀","쿠마린","신남알","신나밀알코올","벤질알코올","벤질벤조에이트","벤질신나메이트","벤질살리실레이트","파네솔","시트로넬올","헥실신남알","부틸페닐메틸프로피오날","알파-이소메틸이오논","아밀신남알","아밀신나밀알코올","하이드록시시트로넬알","아니스알코올","메틸2-옥티노에이트","참나무이끼추출물","나무이끼추출물"];

/* ================= sample products (가상 예시) ================= */
const SAMPLES = [
  {name:"[예시] 순한 수분 진정 크림", cat:"스킨케어",
   ing:"정제수, 글리세린, 세라마이드엔피, 마데카소사이드, 판테놀, 소듐하이알루로네이트, 알란토인, 스쿠알란, 부틸렌글라이콜"},
  {name:"[예시] 피지 케어 토너", cat:"스킨케어",
   ing:"정제수, 변성알코올, 살리실릭애씨드, 티트리잎추출물, 나이아신아마이드, 향료, 리모넨, 리날룰"},
  {name:"[예시] 커버 쿠션 21호", cat:"베이스메이크업", shade:"#f2d5b8", shadeName:"21호 라이트베이지",
   ing:"정제수, 사이클로펜타실록세인, 티타늄디옥사이드, 징크옥사이드, 향료, 리날룰, 시어버터"},
  {name:"[예시] 안티에이징 세럼", cat:"스킨케어",
   ing:"정제수, 나이아신아마이드, 부틸렌글라이콜, 아데노신, 레티놀, 아세틸헥사펩타이드, 글리세린"}
];

/* ================= helpers ================= */
const $ = s => document.querySelector(s);
const norm = s => s.replace(/\s+/g,"").replace(/[()\-·]/g,"").toLowerCase();
const hex = ({r,g,b}) => "#"+[r,g,b].map(v=>Math.max(0,Math.min(255,Math.round(v))).toString(16).padStart(2,"0")).join("");

function effectiveTone(){
  if(!state.tone) return null;
  const {light, warm} = state.adjust;
  return {
    r: state.tone.r + light + warm*0.7,
    g: state.tone.g + light,
    b: state.tone.b + light - warm*0.7
  };
}
function undertone(t){
  const d = t.r - t.b;
  if(d > 42) return "웜";
  if(d < 22) return "쿨";
  return "뉴트럴";
}
function toneName(t){
  const l = (t.r+t.g+t.b)/3;
  if(l>=205) return "밝은 톤";
  if(l>=180) return "라이트 톤";
  if(l>=150) return "미디엄 톤";
  return "딥 톤";
}
function colorDist(a,b){ // weighted RGB distance
  const dr=a.r-b.r, dg=a.g-b.g, db=a.b-b.b;
  return Math.sqrt(2*dr*dr + 4*dg*dg + 3*db*db);
}
function hexToRgb(h){
  const m = h.replace("#","");
  return {r:parseInt(m.slice(0,2),16), g:parseInt(m.slice(2,4),16), b:parseInt(m.slice(4,6),16)};
}

/* ================= tone UI ================= */
function renderTone(){
  const t = effectiveTone();
  const dot=$("#headShade"), hx=$("#headShadeHex"), hd=$("#headShadeTone");
  const sw=$("#toneSwatch"), th=$("#toneHex"), tg=$("#undertoneTag"), td=$("#toneDesc");
  if(!t){ return; }
  const h = hex(t), ut = undertone(t);
  dot.style.background = h; sw.style.background = h;
  hx.textContent = h.toUpperCase();
  hd.textContent = `${toneName(t)} · ${ut} 언더톤`;
  th.textContent = h.toUpperCase();
  tg.hidden = false;
  tg.textContent = ut === "웜" ? "웜톤" : ut === "쿨" ? "쿨톤" : "뉴트럴";
  tg.className = "undertone-tag " + (ut==="웜"?"ut-warm":ut==="쿨"?"ut-cool":"ut-neutral");
  td.textContent = `${toneName(t)}으로 추정됩니다. 조명 영향이 있다면 슬라이더로 보정하세요.`;
  // re-render shade comparisons on board
  state.products.forEach(p => { if(p.shade) updateShadeCompare(p); });
  saveAll();
}

/* photo upload + sampling */
const photoInput=$("#photoInput"), photoZone=$("#photoZone");
$("#uploadBtn").addEventListener("click", ()=>photoInput.click());
photoInput.addEventListener("change", e=>{
  const f = e.target.files[0]; if(!f) return;
  const img = new Image();
  img.onload = ()=>{
    photoZone.classList.add("has-img");
    photoZone.innerHTML = "";
    const canvas = document.createElement("canvas");
    canvas.id = "photoCanvas";
    const maxW = photoZone.clientWidth || 420;
    const scale = Math.min(1, maxW / img.width, 480 / img.height);
    canvas.width = Math.round(img.width*scale);
    canvas.height = Math.round(img.height*scale);
    const ctx = canvas.getContext("2d");
    ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
    photoZone.appendChild(canvas);
    const tip = document.createElement("div");
    tip.style.cssText="position:absolute;bottom:8px;left:50%;transform:translateX(-50%);background:rgba(36,40,28,.75);color:#fff;font-size:11.5px;padding:4px 12px;border-radius:99px;pointer-events:none;";
    tip.textContent="피부 부위를 클릭해 톤 추출";
    photoZone.appendChild(tip);
    canvas.addEventListener("click", ev=>{
      const r = canvas.getBoundingClientRect();
      const x = Math.round((ev.clientX-r.left) * canvas.width/r.width);
      const y = Math.round((ev.clientY-r.top) * canvas.height/r.height);
      const S=4, x0=Math.max(0,x-S), y0=Math.max(0,y-S);
      const w=Math.min(canvas.width-x0, S*2+1), h2=Math.min(canvas.height-y0, S*2+1);
      const d = ctx.getImageData(x0,y0,w,h2).data;
      let rr=0,gg=0,bb=0,n=0;
      for(let i=0;i<d.length;i+=4){ rr+=d[i]; gg+=d[i+1]; bb+=d[i+2]; n++; }
      state.tone = {r:rr/n, g:gg/n, b:bb/n};
      renderTone();
      tip.textContent = "추출 완료 — 다른 부위 클릭으로 다시 추출 가능";
    });
    URL.revokeObjectURL(img.src);
  };
  img.src = URL.createObjectURL(f);
});

/* sliders */
[["adjLight","light"],["adjWarm","warm"]].forEach(([id,key])=>{
  $("#"+id).addEventListener("input", e=>{
    state.adjust[key] = +e.target.value;
    $("#"+id+"Out").textContent = e.target.value;
    renderTone();
  });
});

/* chips */
function bindChips(sel, single, onSet){
  document.querySelectorAll(sel+" .chip").forEach(btn=>{
    btn.addEventListener("click", ()=>{
      if(single){
        document.querySelectorAll(sel+" .chip").forEach(b=>b.setAttribute("aria-pressed", b===btn && btn.getAttribute("aria-pressed")!=="true" ? "true":"false"));
      } else {
        btn.setAttribute("aria-pressed", btn.getAttribute("aria-pressed")==="true"?"false":"true");
      }
      onSet();
    });
  });
}
bindChips("#skinTypeChips", true, ()=>{
  const on = document.querySelector("#skinTypeChips .chip[aria-pressed=true]");
  state.skinType = on ? on.dataset.v : null;
  saveAll();
});
bindChips("#concernChips", false, ()=>{
  state.concerns = new Set([...document.querySelectorAll("#concernChips .chip[aria-pressed=true]")].map(b=>b.dataset.v));
  saveAll();
});
bindChips("#avoidChips", false, ()=>{
  state.avoid = new Set([...document.querySelectorAll("#avoidChips .chip[aria-pressed=true]")].map(b=>b.dataset.v));
  saveAll();
});
$("#ageSel").addEventListener("change", e=>{ state.age = e.target.value; saveAll(); });
$("#customAvoid").addEventListener("input", saveAll);
bindChips("#pregChips", false, ()=>{
  state.pregnant = document.querySelector("#pregChips .chip[aria-pressed=true]") ? true : false;
  state.products.forEach(p=>{ p.analysis = analyzeProduct(p); });
  renderBoard();
  saveAll();
});

/* category → shade field */
$("#pCat").addEventListener("change", e=>{
  $("#shadeField").hidden = !["베이스메이크업","색조"].includes(e.target.value);
});

/* samples */
SAMPLES.forEach((s,i)=>{
  const b = document.createElement("button");
  b.className="sample-btn"; b.textContent=s.name;
  b.addEventListener("click", ()=>{
    $("#pName").value=s.name; $("#pCat").value=s.cat;
    $("#pCat").dispatchEvent(new Event("change"));
    $("#pIngredients").value=s.ing;
    if(s.shade){ $("#pShade").value=s.shade; $("#pShadeName").value=s.shadeName||""; }
  });
  $("#sampleBtns").appendChild(b);
});
$("#clearFormBtn").addEventListener("click", ()=>{
  $("#pName").value=""; $("#pIngredients").value=""; $("#pShadeName").value="";
});

/* ================= analysis ================= */
function tokenizeIngredients(text){
  return text.split(/[,\n·|/]+/).map(s=>s.trim()).filter(s=>s.length>0);
}
function analyzeProduct(p){
  const tokens = tokenizeIngredients(p.ingredients);
  const profileTags = new Set([state.skinType, ...state.concerns].filter(Boolean));
  const found = {caution:[], good:[], allergen:[], avoidHit:[], neutral:[], preg:[]};

  tokens.forEach(tok=>{
    const nt = norm(tok);
    // allergen 25
    const alg = ALLERGEN_25.find(a=>nt.includes(norm(a)));
    if(alg && !found.allergen.some(x=>x.name===alg)) found.allergen.push({name:alg, token:tok});
    // user avoid list
    const avoidList = [...state.avoid, ...($("#customAvoid").value.split(",").map(s=>s.trim()).filter(Boolean))];
    avoidList.forEach(a=>{
      if(a && nt.includes(norm(a)) && !found.avoidHit.some(x=>x.name===a)) found.avoidHit.push({name:a, token:tok});
    });
    // knowledge base
    ING_DB.forEach(entry=>{
      if(entry.names.some(nm=>nt.includes(norm(nm)))){
        if(state.pregnant && entry.preg && !found.preg.some(x=>x.key===entry.key)){
          found.preg.push({key:entry.key, token:tok, level:entry.preg});
        }
        if(found.caution.some(x=>x.key===entry.key)||found.good.some(x=>x.key===entry.key)||found.neutral.some(x=>x.key===entry.key)) return;
        if(entry.type==="good"){
          const relevant = entry.for.some(t=>profileTags.has(t));
          (relevant?found.good:found.neutral).push({key:entry.key, token:tok, note:entry.note, relevant});
        } else if(entry.type==="caution"){
          const relevant = entry.universal || entry.for.some(t=>profileTags.has(t));
          if(relevant) found.caution.push({key:entry.key, token:tok, note:entry.note});
          else found.neutral.push({key:entry.key, token:tok, note:entry.note});
        } else { // mixed
          const isCaution = entry.cautionFor.some(t=>profileTags.has(t));
          const isGood = entry.goodFor.some(t=>profileTags.has(t));
          if(isCaution) found.caution.push({key:entry.key, token:tok, note:entry.note});
          else if(isGood) found.good.push({key:entry.key, token:tok, note:entry.note});
          else found.neutral.push({key:entry.key, token:tok, note:entry.note});
        }
      }
    });
  });

  // reference score (참고용)
  let score = 70;
  score += found.good.length * 8;
  score -= found.caution.length * 12;
  score -= found.avoidHit.length * 25;
  score -= found.allergen.length * 4;
  score -= found.preg.length * (found.preg.some(x=>x.level==="금기") ? 30 : 15);
  score = Math.max(5, Math.min(98, score));

  return {tokens, found, score};
}

/* shade compare */
function updateShadeCompare(p){
  const el = document.getElementById("shade-"+p.id);
  if(!el) return;
  const my = effectiveTone();
  const prod = hexToRgb(p.shade);
  const myDiv = el.querySelector(".sc-my"), prDiv = el.querySelector(".sc-prod"), txt = el.querySelector(".txt");
  prDiv.style.background = p.shade;
  if(!my){
    myDiv.style.background = "#ddd";
    txt.innerHTML = "<b>내 피부톤 미설정</b><div class='hint'>STEP 1에서 사진 톤을 추출하면 비교가 표시됩니다.</div>";
    return;
  }
  myDiv.style.background = hex(my);
  const d = colorDist(my, prod);
  const myUt = undertone(my), prUt = undertone(prod);
  let verdict, cls;
  if(d < 55) verdict = "톤 차이가 작습니다 — 잘 맞을 가능성이 높아요";
  else if(d < 110) verdict = "톤 차이가 다소 있습니다 — 매장 테스트를 권장해요";
  else verdict = "톤 차이가 큽니다 — 다른 호수를 고려해보세요";
  const utMatch = myUt === prUt ? "언더톤 일치" : `언더톤 다름 (나: ${myUt} / 제품: ${prUt})`;
  txt.innerHTML = `<b>${verdict}</b><div class="hint">색 거리 지수 ${Math.round(d)} · ${utMatch}${p.shadeName?` · ${p.shadeName}`:""}</div>`;
}

/* ================= board render ================= */
function renderBoard(){
  const board = $("#board");
  if(state.products.length===0){
    board.innerHTML = '<div class="card empty-board">아직 분석한 상품이 없습니다. STEP 4에서 상품을 입력해보세요.</div>';
    renderTable(); saveAll(); return;
  }
  board.innerHTML = "";
  state.products.forEach(p=>{
    const {found, score} = p.analysis;
    const card = document.createElement("div");
    card.className = "card prod-card";
    const checks = [];
    (found.preg||[]).forEach(pg=>checks.push({cls:"ci-warn", ico:"✗", html:`<b>임신·수유 중 ${pg.level}:</b> ${pg.key} (${pg.token})${gb(pg.key)} — ${pg.level==="금기"?"임신 중 사용을 피해야 하는 성분입니다.":"사용 전 의사·약사와 상담하세요."}`}));
    found.avoidHit.forEach(a=>checks.push({cls:"ci-warn", ico:"✗", html:`<b>기피 성분 포함:</b> ${a.token} — 직접 피하겠다고 설정한 성분입니다.`}));
    found.caution.forEach(c=>checks.push({cls:"ci-warn", ico:"⚠", html:`<b>${c.key}</b> (${c.token})${gb(c.key)} — ${c.note}`}));
    found.good.forEach(g=>checks.push({cls:"ci-good", ico:"✓", html:`<b>${g.key}</b> (${g.token})${gb(g.key)} — ${g.note}`}));
    if(found.allergen.length) checks.push({cls:"ci-warn", ico:"⚠", html:`<b>착향 알레르기 고시 성분 ${found.allergen.length}종</b><span class="grade-b gA">근거 A</span>: ${found.allergen.map(a=>a.name).join(", ")} — 향 알레르기 이력이 있다면 확인하세요.`});
    // 성분 조합 충돌: 이 제품 vs 사용 중 루틴, 그리고 제품 내부 조합
    try{
      const pKeys = matchKeys(p.analysis.tokens);
      const cfSeen = new Set();
      CONFLICTS.forEach(rule=>{
        const hasA = pKeys.has(rule.a), hasB = pKeys.has(rule.b);
        if(hasA && hasB && !cfSeen.has(rule.a+rule.b)){
          cfSeen.add(rule.a+rule.b);
          checks.push({cls:"ci-warn", ico:"⚠", html:`<b>제품 내 조합 주의:</b> ${rule.a} + ${rule.b} 동시 함유 — ${rule.note}`});
        }
        inUseRecords().forEach(r=>{
          const pair = (hasA && r.keys.has(rule.b)) ? [rule.a, rule.b] : (hasB && r.keys.has(rule.a)) ? [rule.b, rule.a] : null;
          if(pair){
            const k = rule.a+rule.b+r.name;
            if(cfSeen.has(k)) return; cfSeen.add(k);
            checks.push({cls:"ci-warn", ico:"⚠", html:`<b>루틴 충돌:</b> 이 제품(${pair[0]}) × 사용 중인 「${escapeHtml(r.name)}」(${pair[1]}) — ${rule.note}`});
          }
        });
      });
    }catch(e){}
    // 인증 라벨 신뢰 라인 + 텍스처 취향 대조
    if(p.certs && p.certs.length){
      const cr = certRelevance(p.certs, p.cat==="선케어"?"선케어":p.cat);
      const whyLine = cr.matches.length ? ` 특히 ${cr.matches.map(m=>m.cert).join(", ")}은(는) 내 프로필과 직결됩니다.` : "";
      checks.push({cls:"ci-good", ico:"✓", html:`<b>신뢰 라벨:</b> ${p.certs.map(escapeHtml).join(", ")} — 기능성 표기는 식약처 심사·보고 대상이라 일반 광고 문구보다 신뢰도가 높습니다.${whyLine}`});
    }
    if(p.texture){
      const tp2 = texturePref();
      const tv = tp2[p.texture]||0;
      if(tv>0.5) checks.push({cls:"ci-good", ico:"✓", html:`<b>텍스처:</b> ${escapeHtml(p.texture)} — 기록상 선호하는 사용감과 일치합니다.`});
      else if(tv<-0.5) checks.push({cls:"ci-warn", ico:"⚠", html:`<b>텍스처:</b> ${escapeHtml(p.texture)} — 과거 안 맞았던 제품들과 같은 사용감입니다.`});
      else checks.push({cls:"ci-info", ico:"·", html:`<b>텍스처:</b> ${escapeHtml(p.texture)} <span class="hint">(취향 데이터 부족 — 기록에 사용감을 남기면 학습됩니다)</span>`});
    }
    found.neutral.slice(0,4).forEach(n=>checks.push({cls:"ci-info", ico:"·", html:`<b>${n.key}</b> (${n.token})${gb(n.key)} — ${n.note} <span class="hint">(내 프로필과 직접 관련 낮음)</span>`}));
    if(checks.length===0) checks.push({cls:"ci-info", ico:"·", html:"성분 목록에서 특기할 항목을 찾지 못했습니다. 전성분을 정확히 붙여넣었는지 확인해보세요."});

    const profileWarn = (!state.skinType && state.concerns.size===0)
      ? `<div class="check-item ci-info"><span class="ico">·</span><span>피부 타입·고민을 설정하지 않아 일반 기준으로만 분석했습니다. STEP 1을 채우면 더 정확해집니다.</span></div>` : "";

    card.innerHTML = `
      <div class="prod-head">
        <div class="prod-title">
          <h3>${escapeHtml(p.name)}</h3>
          <span class="cat">${p.cat}${p.shadeName?` · ${escapeHtml(p.shadeName)}`:""} · 성분 ${p.analysis.tokens.length}개 인식</span>
        </div>
        <div class="verdict-btns" role="group" aria-label="내 판단">
          <button class="v-btn ${p.verdict==='적합'?'on-fit':''}" data-id="${p.id}" data-v="적합">✓ 적합</button>
          <button class="v-btn ${p.verdict==='보류'?'on-hold':''}" data-id="${p.id}" data-v="보류">… 보류</button>
          <button class="v-btn ${p.verdict==='부적합'?'on-no':''}" data-id="${p.id}" data-v="부적합">✗ 부적합</button>
        </div>
      </div>
      <div class="score-line">
        <div class="score-bar"><i style="width:${score}%"></i></div>
        <div class="score-num">참고 점수 ${score}/100</div>
      </div>
      <div class="hint" style="margin-bottom:4px;">점수는 성분 매칭 개수 기반 참고치일 뿐, 구매 판단은 아래 체크리스트를 보고 직접 내리세요.</div>
      ${p.shade ? `<div class="shade-compare" id="shade-${p.id}">
          <div class="split-circle"><div class="sc-my"></div><div class="sc-prod"></div></div>
          <div class="txt"></div>
        </div>` : ""}
      <div class="check-list">${profileWarn}${checks.map(c=>`<div class="check-item ${c.cls}"><span class="ico">${c.ico}</span><span>${c.html}</span></div>`).join("")}</div>
      ${p.verdict==='적합' ? `<div class="buy-row">✓ 적합 판정 완료 —
        <a class="buy-link" target="_blank" rel="noopener"
           href="https://www.oliveyoung.co.kr/store/search/getSearchMain.do?query=${encodeURIComponent(p.name.replace(/^\[.*?\]\s*/,""))}">올리브영에서 이 제품 검색하기 →</a>
        <span class="hint">구매 링크는 적합 판정 시에만 표시됩니다. <!-- 제휴(어필리에이트) 파라미터 연결 지점 --></span></div>` : ""}
    `;
    board.appendChild(card);
    if(p.shade) updateShadeCompare(p);
  });
  board.querySelectorAll(".v-btn").forEach(b=>{
    b.addEventListener("click", ()=>{
      const p = state.products.find(x=>x.id==b.dataset.id);
      p.verdict = p.verdict === b.dataset.v ? null : b.dataset.v;
      if(p.verdict) state.events.verdicts++;
      renderBoard();
    });
  });
  renderTable();
  saveAll();
}

function renderTable(){
  const tb = $("#cmpBody");
  if(state.products.length===0){
    tb.innerHTML = '<tr><td colspan="6" style="color:var(--sub); text-align:center;">비교할 상품이 없습니다</td></tr>';
    return;
  }
  tb.innerHTML = state.products.map(p=>{
    const f = p.analysis.found;
    const cautions = [...f.avoidHit.map(a=>a.name), ...f.caution.map(c=>c.key)];
    const vp = p.verdict==="적합"?"vp-fit":p.verdict==="보류"?"vp-hold":p.verdict==="부적합"?"vp-no":"vp-none";
    return `<tr>
      <td><b>${escapeHtml(p.name)}</b></td>
      <td>${p.cat}</td>
      <td>${p.analysis.score}/100</td>
      <td>${cautions.length? cautions.map(c=>`<span class="ing-tag it-caution">${escapeHtml(c)}</span>`).join(" ") : '<span class="hint">없음</span>'}</td>
      <td><span class="v-pill ${vp}">${p.verdict||"미정"}</span></td>
      <td><button class="del-btn" data-id="${p.id}">삭제</button></td>
    </tr>`;
  }).join("");
  tb.querySelectorAll(".del-btn").forEach(b=>b.addEventListener("click", ()=>{
    state.products = state.products.filter(x=>x.id!=b.dataset.id);
    renderBoard();
  }));
}

function escapeHtml(s){ return String(s).replace(/[&<>"']/g, c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c])); }

/* ================= 비교 카탈로그 (가상 브랜드 예시 — 성분 컨셉 기반) ================= */
const CATALOG = [
  {brand:"그린랩", name:"어성초 진정 토너", cat:"토너", price:"저가", texture:"워터리", certs:["비건"],
   ing:"정제수, 어성초추출물, 병풀추출물, 판테놀, 알란토인, 부틸렌글라이콜, 베타인"},
  {brand:"퓨어본", name:"하이드라 히알루론 토너", cat:"토너", price:"저가", texture:"워터리", certs:["무향료"],
   ing:"정제수, 소듐하이알루로네이트, 글리세린, 베타인, 판테놀, 트레할로스"},
  {brand:"더마셀", name:"약산성 BHA 모공 토너", cat:"토너", price:"중가", texture:"워터리", certs:[],
   ing:"정제수, 살리실릭애씨드, 나이아신아마이드, 위치하젤추출물, 부틸렌글라이콜"},
  {brand:"하이드라온", name:"AHA 리뉴얼 필링 토너", cat:"토너", price:"중가", texture:"워터리", certs:[],
   ing:"정제수, 글라이콜릭애씨드, 락틱애씨드, 글리세린, 판테놀"},
  {brand:"루미너스", name:"비타C 브라이트닝 세럼", cat:"에센스·세럼", price:"중가", texture:"워터리", certs:["기능성(미백)"],
   ing:"정제수, 아스코빅애씨드, 나이아신아마이드, 글리세린, 토코페롤"},
  {brand:"하이드라온", name:"나이아신 10 세럼", cat:"에센스·세럼", price:"저가", texture:"워터리", certs:["기능성(미백)","무향료"],
   ing:"정제수, 나이아신아마이드, 부틸렌글라이콜, 아연피씨에이, 판테놀"},
  {brand:"그린랩", name:"시카 리커버리 앰플", cat:"에센스·세럼", price:"중가", texture:"젤", certs:["저자극 테스트"],
   ing:"정제수, 센텔라아시아티카추출물, 마데카소사이드, 판테놀, 소듐하이알루로네이트"},
  {brand:"루미너스", name:"펩타이드 리프팅 세럼", cat:"에센스·세럼", price:"고가", texture:"로션", certs:["기능성(주름개선)"],
   ing:"정제수, 아세틸헥사펩타이드, 아데노신, 글리세린, 소듐하이알루로네이트"},
  {brand:"더마셀", name:"레티놀 0.1 나이트 세럼", cat:"에센스·세럼", price:"고가", texture:"로션", certs:["기능성(주름개선)"],
   ing:"정제수, 레티놀, 아데노신, 스쿠알란, 토코페롤, 부틸렌글라이콜"},
  {brand:"하이드라온", name:"아젤라 진정 스팟 세럼", cat:"에센스·세럼", price:"중가", texture:"젤", certs:["저자극 테스트"],
   ing:"정제수, 아젤라익애씨드, 나이아신아마이드, 판테놀, 알란토인"},
  {brand:"하이드라온", name:"시카 배리어 수분 크림", cat:"로션·크림", price:"중가", texture:"크림·밤", certs:["저자극 테스트","무향료"],
   ing:"정제수, 세라마이드엔피, 마데카소사이드, 스쿠알란, 글리세린, 판테놀"},
  {brand:"그린랩", name:"장벽 리페어 밤 크림", cat:"로션·크림", price:"고가", texture:"유분감", certs:[],
   ing:"정제수, 세라마이드엔피, 시어버터, 스쿠알란, 판테놀, 콜레스테롤"},
  {brand:"퓨어본", name:"아쿠아 수분 젤크림", cat:"로션·크림", price:"저가", texture:"젤", certs:["비건","무향료"],
   ing:"정제수, 글리세린, 소듐하이알루로네이트, 알로에베라잎추출물, 알란토인"},
  {brand:"루미너스", name:"탄력 아데노신 크림", cat:"로션·크림", price:"고가", texture:"크림·밤", certs:["기능성(주름개선)"],
   ing:"정제수, 아데노신, 팔미토일펜타펩타이드, 시어버터, 글리세린"},
  {brand:"더마셀", name:"무기자차 톤업 선크림 SPF50+", cat:"선케어", price:"중가", texture:"크림·밤", certs:["기능성(자외선차단)","저자극 테스트"],
   ing:"정제수, 징크옥사이드, 티타늄디옥사이드, 부틸렌글라이콜, 토코페롤"},
  {brand:"퓨어본", name:"워터핏 유기자차 선크림 SPF50+", cat:"선케어", price:"저가", texture:"워터리", certs:["기능성(자외선차단)"],
   ing:"정제수, 에칠헥실메톡시신나메이트, 옥토크릴렌, 글리세린, 향료, 리날룰"},
  {brand:"그린랩", name:"저자극 약산성 젤 클렌저", cat:"클렌징", price:"저가", texture:"젤", certs:["저자극 테스트","비건"],
   ing:"정제수, 코카미도프로필베타인, 글리세린, 판테놀, 알란토인"},
  {brand:"루미너스", name:"딥클린 버블 폼", cat:"클렌징", price:"저가", texture:"젤", certs:[],
   ing:"정제수, 소듐라우레스설페이트, 미리스틱애씨드, 글리세린, 향료, 리모넨"},
  {brand:"하이드라온", name:"세라마이드 크림 클렌저", cat:"클렌징", price:"중가", texture:"크림·밤", certs:["무향료"],
   ing:"정제수, 세라마이드엔피, 코카미도프로필베타인, 글리세린, 스쿠알란"}
];
CATALOG.forEach((c,i)=>{ c.id="c"+i; c.tokens=tokenizeIngredients(c.ing); c.nset=new Set(c.tokens.map(norm)); });

/* ================= 사용 기록 ================= */
let curRating = null;
bindChips("#textureChips", true, ()=>{});
bindChips("#certChips", false, ()=>{});
bindChips("#vCertChips", false, ()=>{});
document.querySelectorAll("#ratingBtns .r-btn").forEach(btn=>{
  btn.addEventListener("click", ()=>{
    const on = btn.getAttribute("aria-pressed")==="true";
    document.querySelectorAll("#ratingBtns .r-btn").forEach(b=>b.setAttribute("aria-pressed","false"));
    if(!on){ btn.setAttribute("aria-pressed","true"); curRating = +btn.dataset.v; }
    else curRating = null;
  });
});

$("#addRecordBtn").addEventListener("click", ()=>{
  const name = $("#rName").value.trim();
  const ing = $("#rIngredients").value.trim();
  if(!name){ alert("제품명을 입력하세요."); $("#rName").focus(); return; }
  if(curRating===null){ alert("사용 평가(좋았음/보통/안 맞았음)를 선택하세요."); return; }
  if(!ing){ alert("전성분을 붙여넣어 주세요. 성분이 있어야 추천 학습이 가능합니다."); $("#rIngredients").focus(); return; }
  const tokens = tokenizeIngredients(ing);
  state.records.push({
    id: ++rid, name, brand: $("#rBrand").value.trim(), cat: $("#rCat").value,
    rating: curRating, memo: $("#rMemo").value.trim(), ingredients: ing,
    openedAt: $("#rOpened").value, cycle: $("#rCycle").value,
    createdAt: new Date().toISOString().slice(0,10),
    texture: (document.querySelector("#textureChips .chip[aria-pressed=true]")||{}).dataset?.v || "",
    certs: [...document.querySelectorAll("#certChips .chip[aria-pressed=true]")].map(b=>b.dataset.v),
    tokens, nset: new Set(tokens.map(norm)), keys: matchKeys(tokens)
  });
  state.events.recordsAdded++;
  if(!state.metrics.activatedAt) state.metrics.activatedAt = new Date().toISOString().slice(0,10);
  $("#rName").value=""; $("#rBrand").value=""; $("#rMemo").value=""; $("#rIngredients").value="";
  $("#rOpened").value=""; $("#rCycle").value="";
  document.querySelectorAll("#textureChips .chip, #certChips .chip").forEach(b=>b.setAttribute("aria-pressed","false"));
  document.querySelectorAll("#ratingBtns .r-btn").forEach(b=>b.setAttribute("aria-pressed","false"));
  curRating = null;
  renderRecords();
});

function matchKeys(tokens){
  const keys = new Set();
  tokens.forEach(tok=>{
    const nt = norm(tok);
    ING_DB.forEach(e=>{ if(e.names.some(nm=>nt.includes(norm(nm)))) keys.add(e.key); });
  });
  return keys;
}

const RATING_LABEL = {1:"좋았음", 0:"보통", "-1":"안 맞았음"};
function ddayInfo(r){
  if(!r.openedAt || !r.cycle) return null;
  const opened = new Date(r.openedAt+"T00:00:00");
  if(isNaN(opened)) return null;
  const total = (+r.cycle)*30;
  const elapsed = Math.floor((Date.now()-opened.getTime())/86400000);
  const remain = total - elapsed;
  return {remain, ratio: elapsed/total};
}
function renderRecords(){
  const list = $("#recList");
  list.innerHTML = state.records.length===0
    ? '<div class="hint" style="text-align:center; padding:10px;">아직 기록이 없습니다. 써본 기초화장품부터 등록해보세요 — 많을수록 추천이 정확해집니다.</div>'
    : "";
  state.records.slice().reverse().forEach(r=>{
    const div = document.createElement("div");
    div.className = "rec-item";
    const rp = r.rating===1?"rp-good":r.rating===0?"rp-mid":"rp-bad";
    const dd = ddayInfo(r);
    const ddHtml = dd ? `<span class="dday ${dd.remain<0?'over':dd.ratio>=0.8?'soon':''}">${dd.remain<0?`소진 D+${-dd.remain}`:`소진 D-${dd.remain}`}</span>` : "";
    div.innerHTML = `
      <span class="r-pill ${rp}">${RATING_LABEL[r.rating]}</span>
      <div class="info">
        <b>${escapeHtml(r.name)}</b>${ddHtml}${r.texture?`<span class="dday">${escapeHtml(r.texture)}</span>`:""}
        <span class="hint">${r.brand?escapeHtml(r.brand)+" · ":""}${r.cat} · 성분 ${r.tokens.length}개${(r.certs&&r.certs.length)?` · ${r.certs.join(", ")}`:""}${r.memo?` · “${escapeHtml(r.memo)}”`:""}</span>
      </div>
      <div class="rec-actions">
        <button class="btn btn-ghost btn-sm" data-act="similar" data-id="${r.id}">비슷한 제품 찾기</button>
        <button class="del-btn" data-act="del" data-id="${r.id}">삭제</button>
      </div>`;
    list.appendChild(div);
  });
  list.querySelectorAll("[data-act=del]").forEach(b=>b.addEventListener("click", ()=>{
    state.records = state.records.filter(x=>x.id!=b.dataset.id);
    renderRecords();
  }));
  list.querySelectorAll("[data-act=similar]").forEach(b=>b.addEventListener("click", ()=>{
    const r = state.records.find(x=>x.id==b.dataset.id);
    $("#recoCat").value = ["토너","에센스·세럼","로션·크림","선케어","클렌징"].includes(r.cat) ? r.cat : "전체";
    runReco(r);
    document.getElementById("stepReco").scrollIntoView({behavior:"smooth", block:"start"});
  }));
  renderPrefInsight();
  renderOnboard();
  renderRefill();
  renderConflicts();
  renderChronicle();
  saveAll();
}

/* ================= 성분 조합 충돌 검사 ================= */
const CONFLICTS = [
  {a:"레티노이드", b:"AHA", sev:"high", note:"자극·피부 장벽 손상 위험이 큽니다. 같은 날 병용을 피하고 격일로 나누세요."},
  {a:"레티노이드", b:"BHA", sev:"high", note:"각질 제거 성분과의 병용은 자극을 크게 높입니다. 격일 또는 주기 분리를 권장합니다."},
  {a:"레티노이드", b:"비타민C", sev:"med", note:"동시 사용 시 자극 가능성이 있습니다. 비타민C는 아침, 레티놀은 저녁으로 분리하세요."},
  {a:"AHA", b:"BHA", sev:"med", note:"각질 제거가 중복됩니다. 저농도가 아니라면 같은 루틴에서 함께 쓰지 마세요."},
  {a:"AHA", b:"비타민C", sev:"med", note:"저pH 성분이 중첩되어 따가움·홍조가 생길 수 있습니다. 시간대를 분리하세요."},
  {a:"BHA", b:"비타민C", sev:"med", note:"산성 성분 중첩으로 자극 가능성이 있습니다. 아침/저녁으로 나눠 쓰세요."},
  {a:"레티노이드", b:"벤조일퍼옥사이드", sev:"high", note:"서로를 분해·비활성화할 수 있고 자극이 큽니다. 반드시 아침/저녁으로 분리하세요."},
  {a:"벤조일퍼옥사이드", b:"비타민C", sev:"med", note:"비타민C를 산화시켜 효과를 떨어뜨릴 수 있습니다. 시간대를 분리하세요."}
];
function inUseRecords(){
  return state.records.filter(r=>{
    if(r.rating === -1) return false;            // 안 맞았음 = 사용 중단으로 간주
    const dd = ddayInfo(r);
    return !dd || dd.remain > -14;               // 소진 2주 초과 경과 시 사용 종료로 간주
  });
}
function findConflicts(keySetsByName){
  const hits = [];
  CONFLICTS.forEach(rule=>{
    const carriersA = keySetsByName.filter(x=>x.keys.has(rule.a));
    const carriersB = keySetsByName.filter(x=>x.keys.has(rule.b));
    carriersA.forEach(ca=>carriersB.forEach(cb=>{
      if(ca.name === cb.name) {
        hits.push({rule, pa:ca.name, pb:cb.name, sameProduct:true});
      } else {
        hits.push({rule, pa:ca.name, pb:cb.name, sameProduct:false});
      }
    }));
  });
  // 중복 제거 (A-B / B-A)
  const seen = new Set();
  return hits.filter(h=>{
    const k = [h.rule.a, h.rule.b, ...[h.pa,h.pb].sort()].join("|");
    if(seen.has(k)) return false; seen.add(k); return true;
  });
}
function renderConflicts(){
  const panel = $("#conflictPanel");
  const inUse = inUseRecords();
  if(inUse.length < 1){ panel.hidden = true; return; }
  const sets = inUse.map(r=>({name:r.name, keys:r.keys}));
  const hits = findConflicts(sets);
  panel.hidden = hits.length===0;
  if(hits.length===0) return;
  $("#conflictList").innerHTML = hits.map(h=>`
    <div class="cf-item">
      <span class="cf-sev ${h.rule.sev==='high'?'cf-high':'cf-med'}">${h.rule.sev==='high'?'높음':'주의'}</span>
      <b>${h.rule.a} × ${h.rule.b}</b> —
      ${h.sameProduct
        ? `「${escapeHtml(h.pa)}」 한 제품 안에 두 성분이 함께 있습니다.`
        : `「${escapeHtml(h.pa)}」 + 「${escapeHtml(h.pb)}」 병용 중입니다.`}
      <span class="hint">${h.rule.note}</span>
    </div>`).join("");
}

/* ================= 피부 연대기 ================= */
const CHECKIN_TAGS = ["좋음","트러블","건조","유분과다","홍조"];
bindChips("#checkinChips", false, ()=>{});
$("#checkinBtn").addEventListener("click", ()=>{
  const tags = [...document.querySelectorAll("#checkinChips .chip[aria-pressed=true]")].map(b=>b.dataset.v);
  if(tags.length===0){ alert("오늘 피부 상태를 하나 이상 선택하세요."); return; }
  const today = new Date().toISOString().slice(0,10);
  state.checkins = state.checkins.filter(c=>c.date!==today); // 같은 날 재기록 시 대체
  state.checkins.push({date: today, tags, memo: $("#checkinMemo").value.trim()});
  $("#checkinMemo").value = "";
  document.querySelectorAll("#checkinChips .chip").forEach(b=>b.setAttribute("aria-pressed","false"));
  renderChronicle();
  saveAll();
});
function seasonOf(dateStr){
  const m = new Date(dateStr+"T00:00:00").getMonth()+1;
  if(isNaN(m)) return null;
  const y = dateStr.slice(0,4);
  if(m>=3 && m<=5) return `${y} 봄`;
  if(m>=6 && m<=8) return `${y} 여름`;
  if(m>=9 && m<=11) return `${y} 가을`;
  return m===12 ? `${y} 겨울` : `${+y-1} 겨울`;
}
function renderChronicle(){
  const body = $("#chronBody");
  const groups = new Map(); // season → {checkins:[], recs:[]}
  state.checkins.forEach(c=>{
    const s = seasonOf(c.date); if(!s) return;
    if(!groups.has(s)) groups.set(s, {checkins:[], recs:[], sortKey:c.date});
    const g = groups.get(s); g.checkins.push(c); if(c.date>g.sortKey) g.sortKey=c.date;
  });
  state.records.forEach(r=>{
    const d = r.createdAt || r.openedAt; if(!d) return;
    const s = seasonOf(d); if(!s) return;
    if(!groups.has(s)) groups.set(s, {checkins:[], recs:[], sortKey:d});
    const g = groups.get(s); g.recs.push(r); if(d>g.sortKey) g.sortKey=d;
  });
  if(groups.size===0){
    body.innerHTML = '<p class="hint" style="text-align:center; padding:10px;">체크인과 화장품 기록이 쌓이면 계절별 타임라인이 여기 표시됩니다.</p>';
    return;
  }
  const sorted = [...groups.entries()].sort((a,b)=>b[1].sortKey.localeCompare(a[1].sortKey));
  body.innerHTML = "";
  sorted.forEach(([season, g])=>{
    const counts = {};
    g.checkins.forEach(c=>c.tags.forEach(t=>counts[t]=(counts[t]||0)+1));
    const tagHtml = CHECKIN_TAGS.filter(t=>counts[t]).map(t=>`<span class="chron-tag">${t} <b>×${counts[t]}</b></span>`).join("");
    const topTag = Object.entries(counts).sort((a,b)=>b[1]-a[1])[0];
    const goodRecs = g.recs.filter(r=>r.rating===1).map(r=>escapeHtml(r.name));
    const badRecs = g.recs.filter(r=>r.rating===-1).map(r=>escapeHtml(r.name));
    const memos = g.checkins.filter(c=>c.memo).slice(-2).map(c=>`“${escapeHtml(c.memo)}”`);
    let insight = "";
    if(topTag && topTag[0]!=="좋음"){
      const tip = {트러블:"진정·저자극 성분(센텔라, 판테놀) 위주 루틴을 검토하세요.",
                   건조:"세라마이드·히알루론산 등 장벽·보습 성분 보강을 검토하세요.",
                   유분과다:"나이아신아마이드·BHA 등 피지 케어 성분을 검토하세요.",
                   홍조:"진정 성분 위주로 단순화하고 산성·레티노이드 사용 빈도를 점검하세요."}[topTag[0]];
      insight = `<div class="chron-insight">이 시기 최다 상태: ${topTag[0]} (${topTag[1]}회) — ${tip||""}</div>`;
    } else if(topTag){
      insight = `<div class="chron-insight">이 시기 피부가 대체로 안정적이었습니다. 현재 루틴을 기준선으로 기록해두세요.</div>`;
    }
    const div = document.createElement("div");
    div.className = "chron-group";
    div.innerHTML = `
      <h4>${season}</h4>
      ${tagHtml ? `<div class="chron-tags">${tagHtml}</div>` : ""}
      ${g.recs.length ? `<div class="chron-prods">
        ${goodRecs.length? `이 시기 잘 맞았던 것: ${goodRecs.join(", ")}<br>`:""}
        ${badRecs.length? `안 맞았던 것: ${badRecs.join(", ")}<br>`:""}
        등록 ${g.recs.length}개 · 체크인 ${g.checkins.length}회
      </div>` : `<div class="chron-prods">체크인 ${g.checkins.length}회</div>`}
      ${memos.length? `<div class="chron-prods">${memos.join(" · ")}</div>`:""}
      ${insight}`;
    body.appendChild(div);
  });
}

/* ================= 재구매 알림: 캘린더(.ics) + 브라우저 알림 ================= */
function icsDate(d){ return d.toISOString().slice(0,10).replace(/-/g,""); }
$("#icsBtn").addEventListener("click", ()=>{
  const items = state.records.map(r=>({r, dd:ddayInfo(r)})).filter(x=>x.dd);
  if(items.length===0){ alert("개봉일과 소진 주기가 입력된 기록이 없습니다."); return; }
  const now = new Date();
  const stamp = now.toISOString().replace(/[-:]/g,"").slice(0,15)+"Z";
  let ics = "BEGIN:VCALENDAR\r\nVERSION:2.0\r\nPRODID:-//fitcheck//KR\r\n";
  items.forEach(({r}, i)=>{
    const dueDate = new Date(new Date(r.openedAt+"T00:00:00").getTime() + (+r.cycle)*30*86400000);
    ics += "BEGIN:VEVENT\r\n"
      + `UID:fitcheck-${Date.now()}-${i}@local\r\n`
      + `DTSTAMP:${stamp}\r\n`
      + `DTSTART;VALUE=DATE:${icsDate(dueDate)}\r\n`
      + `SUMMARY:🧴 ${r.name.replace(/[\r\n,;]/g," ")} 소진 예정 — 재구매/갈아타기 점검\r\n`
      + "DESCRIPTION:핏체크 리필 레이더에서 갈아타기 브리핑을 확인하세요.\r\n"
      + "END:VEVENT\r\n";
  });
  ics += "END:VCALENDAR\r\n";
  const blob = new Blob([ics], {type:"text/calendar"});
  const a = document.createElement("a");
  a.href = URL.createObjectURL(blob);
  a.download = "fitcheck-refill.ics";
  a.click();
  URL.revokeObjectURL(a.href);
});
$("#notifBtn").addEventListener("click", async ()=>{
  if(!("Notification" in window)){ alert("이 브라우저는 알림을 지원하지 않습니다."); return; }
  const perm = await Notification.requestPermission();
  $("#notifBtn").textContent = perm==="granted" ? "🔔 브라우저 알림 켜짐" : "🔕 브라우저 알림 켜기";
  if(perm==="granted") notifyDueItems(true);
});
function notifyDueItems(force){
  try{
    if(!("Notification" in window) || Notification.permission!=="granted") return;
    const due = state.records.map(r=>({r, dd:ddayInfo(r)})).filter(x=>x.dd && x.dd.ratio>=0.8);
    if(due.length===0){ if(force) new Notification("핏체크", {body:"소진 임박 제품이 없습니다."}); return; }
    new Notification("핏체크 리필 레이더", {body:`소진 임박·초과 제품 ${due.length}개: ${due.slice(0,3).map(x=>x.r.name).join(", ")}${due.length>3?" 외":""}`});
  }catch(e){}
}

/* ================= 기기 간 동기화 (코드 방식) ================= */
const SYNC_PREFIX = "FC2:";
$("#syncBtn").addEventListener("click", ()=>{ $("#syncModal").hidden = false; $("#syncMsg").textContent=""; });
$("#syncClose").addEventListener("click", ()=>{ $("#syncModal").hidden = true; });
$("#syncModal").addEventListener("click", e=>{ if(e.target.id==="syncModal") $("#syncModal").hidden = true; });
$("#syncGenBtn").addEventListener("click", ()=>{
  const json = JSON.stringify(snapshot());
  $("#syncText").value = SYNC_PREFIX + btoa(unescape(encodeURIComponent(json)));
  state.events.syncGens = (state.events.syncGens||0) + 1;
  saveAll();
  $("#syncMsg").textContent = `코드 생성 완료 (${$("#syncText").value.length.toLocaleString()}자). 복사해서 다른 기기의 이 창에 붙여넣고 '코드 적용'을 누르세요.`;
});
$("#syncCopyBtn").addEventListener("click", async ()=>{
  const t = $("#syncText").value;
  if(!t){ $("#syncMsg").textContent = "먼저 코드를 생성하세요."; return; }
  try{ await navigator.clipboard.writeText(t); $("#syncMsg").textContent = "복사되었습니다."; }
  catch(e){ $("#syncText").select(); $("#syncMsg").textContent = "자동 복사가 막혀 있습니다. 전체 선택했으니 직접 복사(Ctrl+C)하세요."; }
});
$("#syncApplyBtn").addEventListener("click", ()=>{
  let t = $("#syncText").value.trim();
  if(!t){ $("#syncMsg").textContent = "다른 기기에서 생성한 코드를 붙여넣으세요."; return; }
  if(!t.startsWith(SYNC_PREFIX)){ $("#syncMsg").textContent = "올바른 핏체크 동기화 코드가 아닙니다."; return; }
  if(!confirm("현재 기기의 데이터를 코드의 데이터로 완전히 대체합니다. 계속할까요?")) return;
  try{
    const data = JSON.parse(decodeURIComponent(escape(atob(t.slice(SYNC_PREFIX.length)))));
    if(!data || data.version!==2) throw new Error("버전 불일치");
    applyData(data);
    renderTone(); renderRecords(); renderBoard();
    saveAll();
    $("#syncModal").hidden = true;
    alert("동기화 완료: 프로필과 기록이 복원되었습니다.");
  }catch(err){ $("#syncMsg").textContent = "적용 실패: 코드가 손상되었거나 형식이 다릅니다."; }
});

function renderOnboard(){
  const n = state.records.length;
  const box = $("#onboard");
  box.hidden = n >= 3;
  if(n < 3){
    $("#obCount").textContent = `${n}/3`;
    [...document.querySelectorAll("#obDots .ob-dot")].forEach((d,i)=>d.classList.toggle("on", i<n));
  }
}

function renderRefill(){
  const due = state.records.map(r=>({r, dd:ddayInfo(r)})).filter(x=>x.dd && x.dd.ratio>=0.8);
  const panel = $("#refillPanel");
  panel.hidden = due.length===0;
  if(due.length===0) return;
  $("#refillList").innerHTML = "";
  due.sort((a,b)=>a.dd.remain-b.dd.remain).forEach(({r,dd})=>{
    const row = document.createElement("div");
    row.className = "rf-item";
    // 갈아타기 브리핑 자동 생성: 해당 카테고리 상위 2개 후보 요약
    let brief = "";
    try{
      const top = computeReco(r, r.cat).filter(s=>!s.alreadyUsed).slice(0,2);
      if(top.length){
        brief = `<div class="briefing">갈아타기 브리핑: ` + top.map((s,i)=>{
          const why = s.prefHits.length ? `선호 성분 ${escapeHtml(s.prefHits[0])} 포함`
            : s.found.good.length ? `${s.found.good[0].key} 함유`
            : `프로필 충돌 없음`;
          return `${i+1}) <b>${s.c.brand} ${escapeHtml(s.c.name)}</b> (매칭 ${s.total} · ${why})`;
        }).join(" &nbsp;/&nbsp; ") + `</div>`;
      }
    }catch(e){}
    row.innerHTML = `
      <b>${escapeHtml(r.name)}</b>
      <span class="dday ${dd.remain<0?'over':'soon'}">${dd.remain<0?`소진 D+${-dd.remain}`:`D-${dd.remain}`}</span>
      <button class="btn btn-ghost btn-sm" data-rf="switch" data-id="${r.id}">후보 전체 보기</button>
      ${brief}`;
    $("#refillList").appendChild(row);
  });
  $("#refillList").querySelectorAll("[data-rf=switch]").forEach(b=>b.addEventListener("click", ()=>{
    const r = state.records.find(x=>x.id==b.dataset.id);
    $("#recoCat").value = ["토너","에센스·세럼","로션·크림","선케어","클렌징"].includes(r.cat) ? r.cat : "전체";
    runReco(r);
    document.getElementById("stepReco").scrollIntoView({behavior:"smooth", block:"start"});
  }));
}

/* ---- 선호 성분 학습: 성분키별 가중치 ---- */
function prefWeights(){
  const w = new Map(); // norm token → weight
  const kw = new Map(); // ING_DB key → weight
  state.records.forEach(r=>{
    const wt = r.rating===1 ? 1 : r.rating===0 ? 0.15 : -1.2;
    r.nset.forEach(nt=>{
      if(["정제수","부틸렌글라이콜","글리세린"].some(c=>nt===norm(c)) && wt>0) return; // 범용 베이스 성분은 양의 학습에서 제외
      w.set(nt, (w.get(nt)||0)+wt);
    });
    r.keys.forEach(k=>kw.set(k, (kw.get(k)||0)+wt));
  });
  return {w, kw};
}

function texturePref(){
  const m = {};
  state.records.forEach(r=>{
    if(!r.texture) return;
    const w = r.rating===1 ? 1 : r.rating===0 ? 0.15 : -1.2;
    m[r.texture] = (m[r.texture]||0) + w;
  });
  return m;
}
function certRelevance(certs, cat){
  const matches = []; let adj = 0;
  (certs||[]).forEach(c=>{
    if(c==="기능성(미백)" && (state.concerns.has("색소침착")||state.concerns.has("흉터"))){ adj+=4; matches.push({cert:c, why:"색소·자국 고민과 직결되는 식약처 고시 기능성"}); }
    else if(c==="기능성(주름개선)" && state.concerns.has("주름")){ adj+=4; matches.push({cert:c, why:"주름 고민에 해당하는 식약처 고시 기능성"}); }
    else if(c==="기능성(자외선차단)" && cat==="선케어"){ adj+=2; matches.push({cert:c, why:"차단 지수가 식약처 심사를 거친 표기"}); }
    else if(c==="저자극 테스트" && (state.skinType==="민감성"||state.concerns.has("홍조"))){ adj+=4; matches.push({cert:c, why:"민감 프로필에 신뢰 가점"}); }
    else if(c==="무향료" && (state.skinType==="민감성"||state.avoid.has("향료"))){ adj+=4; matches.push({cert:c, why:"향료 기피 설정과 부합"}); }
  });
  return {adj, matches};
}

function renderPrefInsight(){
  const box = $("#prefInsight");
  if(state.records.length===0){ box.hidden = true; return; }
  const {kw} = prefWeights();
  const liked = [...kw.entries()].filter(([,v])=>v>0.5).sort((a,b)=>b[1]-a[1]).slice(0,5).map(([k])=>k);
  const disliked = [...kw.entries()].filter(([,v])=>v<-0.5).sort((a,b)=>a[1]-b[1]).slice(0,5).map(([k])=>k);
  const tp = texturePref();
  const likedTex = Object.entries(tp).filter(([,v])=>v>0.5).sort((a,b)=>b[1]-a[1]).map(([t])=>t);
  const dislikedTex = Object.entries(tp).filter(([,v])=>v<-0.5).map(([t])=>t);
  box.hidden = false;
  box.innerHTML = `<b>학습된 내 취향</b> — `
    + (liked.length? `잘 맞는 성분: ${liked.map(k=>`<span class="ing-tag it-good">${k}</span>`).join(" ")}` : "잘 맞는 성분: 아직 데이터 부족")
    + (disliked.length? ` &nbsp;·&nbsp; 피하는 성분: ${disliked.map(k=>`<span class="ing-tag it-caution">${k}</span>`).join(" ")}` : "")
    + (likedTex.length? ` &nbsp;·&nbsp; 선호 텍스처: <span class="ing-tag it-good">${likedTex.join(", ")}</span>` : "")
    + (dislikedTex.length? ` &nbsp;·&nbsp; 기피 텍스처: <span class="ing-tag it-caution">${dislikedTex.join(", ")}</span>` : "");
}

/* ---- 추천 엔진 ---- */
function jaccard(a,b){
  let inter=0; a.forEach(x=>{ if(b.has(x)) inter++; });
  const uni = a.size + b.size - inter;
  return uni===0?0:inter/uni;
}
function profileFitScore(ingText){
  // analyzeProduct를 재사용해 프로필 적합도(0~1) 산출
  const res = analyzeProduct({ingredients: ingText});
  return {fit: res.score/100, found: res.found};
}

function computeReco(anchor, cat){
  const {w, kw} = prefWeights();
  const likedRecs = state.records.filter(r=>r.rating===1);
  const usedNames = new Set(state.records.map(r=>norm(r.name)));

  let pool = CATALOG.filter(c=> cat==="전체" ? true : c.cat===cat);
  if(anchor){
    pool = CATALOG.filter(c=>c.cat===anchor.cat || cat==="전체" && c.cat===anchor.cat);
    if(anchor.brand) pool = pool.filter(c=>norm(c.brand)!==norm(anchor.brand)); // 다른 브랜드 비교
  }

  const scored = pool.map(c=>{
    const {fit, found} = profileFitScore(c.ing);
    // 선호 성분 점수
    let pref = 0, prefHits = [], negHits = [];
    const seen = new Set();
    c.tokens.forEach(tok=>{
      const nt = norm(tok);
      if(seen.has(nt)) return; seen.add(nt);
      const v = w.get(nt)||0;
      pref += v;
      if(v>0.5) prefHits.push(tok);
      if(v<-0.5) negHits.push(tok);
    });
    const prefN = Math.max(0, Math.min(1, 0.5 + pref/6));
    // 유사도: 앵커 지정 시 앵커와, 아니면 좋았던 기록들과의 최대 유사도
    const base = anchor ? [anchor] : likedRecs;
    const sim = base.length ? Math.max(...base.map(r=>jaccard(c.nset, r.nset))) : 0;
    const simRef = anchor || (base.length ? base[[...base.map(r=>jaccard(c.nset, r.nset))].indexOf(Math.max(...base.map(r=>jaccard(c.nset, r.nset))))] : null);
    // 페널티: 기피 성분·부정 경험 성분키
    let penalty = 0;
    const avoidHits = found.avoidHit.map(a=>a.name);
    penalty += avoidHits.length * 0.25;
    penalty += (found.preg||[]).length * 0.3;
    const negKeyHits = [...matchKeys(c.tokens)].filter(k=>(kw.get(k)||0) < -0.8);
    penalty += negKeyHits.length * 0.15;

    const hasHistory = state.records.length>0;
    // 텍스처 취향 가감
    const tp = texturePref();
    let texAdj = 0, texState = null;
    if(c.texture){
      const tv = tp[c.texture]||0;
      if(tv>0.5){ texAdj = 6; texState = "like"; }
      else if(tv<-0.5){ texAdj = -8; texState = "dislike"; }
    }
    // 인증 라벨 가점
    const certRes = certRelevance(c.certs, c.cat);
    const base100 = Math.round(100 * Math.max(0,
      hasHistory ? (0.4*fit + 0.3*prefN + 0.3*Math.min(1,sim*2.2)) - penalty
                 : fit - penalty
    ));
    const total = Math.max(0, Math.min(100, base100 + texAdj + certRes.adj));
    return {c, total, fit, sim, simRef, prefHits:[...new Set(prefHits)].slice(0,4),
            negHits:[...new Set(negHits)].slice(0,3), negKeyHits, found, avoidHits,
            texState, certMatches: certRes.matches,
            alreadyUsed: usedNames.has(norm(c.name))};
  }).sort((a,b)=>b.total-a.total).slice(0,5);

  return scored;
}
function runReco(anchor){
  renderReco(computeReco(anchor, $("#recoCat").value), anchor);
}

/* ---- 성분 근거 등급: A 식약처 고시·사용제한 / B 문헌 컨센서스 / C 사용자 보고·논란 ---- */
const GRADE_A = new Set(["MIT/CMIT","트리클로산","나이아신아마이드","아데노신","알부틴","레티노이드","무기자차 성분","유기자차 성분"]);
const GRADE_C = new Set(["실리콘","위치하젤","페녹시에탄올","프로필렌글라이콜","BHA/BHT 산화방지제","탤크","에센셜 오일","파라벤","인공색소","라놀린","코메도제닉 오일","광물성 오일"]);
function gradeOf(key){ return GRADE_A.has(key) ? "A" : GRADE_C.has(key) ? "C" : "B"; }
function gb(key){ const g = gradeOf(key); return `<span class="grade-b g${g}">근거 ${g}</span>`; }

/* ---- 신규 사용자 저자극 스타터 추천 (기록 0개 온보딩 경로) ---- */
const STRONG_ACTIVES = ["레티노이드","AHA","BHA","벤조일퍼옥사이드"];
function runStarter(){
  const scored = CATALOG.map(c=>{
    const {fit, found} = profileFitScore(c.ing);
    let adj = 0;
    (c.certs||[]).forEach(x=>{ if(x==="저자극 테스트"||x==="무향료") adj += 6; });
    const keys = matchKeys(c.tokens);
    STRONG_ACTIVES.forEach(k=>{ if(keys.has(k)) adj -= 15; });
    adj -= (found.preg||[]).length * 20;
    const certRes = certRelevance(c.certs, c.cat);
    const total = Math.max(0, Math.min(100, Math.round(fit*100) + adj + certRes.adj));
    return {c, total, fit, sim:0, simRef:null, prefHits:[], negHits:[], negKeyHits:[], found,
            avoidHits: found.avoidHit.map(a=>a.name), texState:null, certMatches: certRes.matches, alreadyUsed:false};
  }).sort((a,b)=>b.total-a.total).slice(0,5);
  renderReco(scored, null,
    `<div class="check-item ci-info" style="margin-top:4px;"><span class="ico">·</span><span><b>저자극 스타터 추천</b> — 기록이 없어도 프로필 적합도와 저자극·무향료 라벨을 기준으로 골랐고, 처음 쓰기엔 강한 액티브 성분(레티노이드·AHA/BHA·벤조일퍼옥사이드)은 후순위로 뺐습니다. 하나씩 써보고 STEP 2에 기록을 남기면 추천이 개인화됩니다.</span></div>`);
  document.getElementById("stepReco").scrollIntoView({behavior:"smooth", block:"start"});
}
$("#starterBtn").addEventListener("click", runStarter);

function renderReco(scored, anchor, extraHead){
  const box = $("#recoList");
  const notice = [];
  if(!state.skinType && state.concerns.size===0) notice.push("STEP 1 프로필이 비어 있어 적합도 판단이 일반 기준입니다.");
  if(state.records.length===0) notice.push("사용 기록이 없어 프로필 적합도만으로 추천했습니다. 기록을 쌓으면 취향 학습이 반영됩니다.");
  const head = anchor
    ? `<div class="hint" style="margin-top:4px;">기준 제품: <b>${escapeHtml(anchor.name)}</b>${anchor.brand?` (${escapeHtml(anchor.brand)})`:""} — 같은 카테고리의 <b>다른 브랜드</b>에서 성분이 비슷한 순으로 정렬했습니다.</div>`
    : "";
  box.innerHTML = head + (extraHead||"") + (notice.length? `<div class="check-item ci-info" style="margin-top:8px;"><span class="ico">·</span><span>${notice.join(" ")}</span></div>` : "");

  if(scored.length===0){
    box.innerHTML += '<div class="hint" style="padding:14px; text-align:center;">해당 카테고리에 비교할 항목이 없습니다.</div>';
    return;
  }
  scored.forEach((s,rank)=>{
    const div = document.createElement("div");
    div.className = "reco-card";
    const reasons = [];
    if(s.sim>0.12 && s.simRef) reasons.push({cls:"rr-good", ic:"✓", t:`좋았던 「${escapeHtml(s.simRef.name)}」와 성분 유사도 ${(s.sim*100).toFixed(0)}%`});
    if(s.prefHits.length) reasons.push({cls:"rr-good", ic:"✓", t:`내가 선호하는 성분 포함: ${s.prefHits.map(escapeHtml).join(", ")}`});
    s.found.good.slice(0,3).forEach(g=>reasons.push({cls:"rr-good", ic:"✓", t:`${g.key} — 내 프로필(${state.skinType||""}${state.concerns.size?" · "+[...state.concerns].join(",")||"":""})에 도움`}));
    if(s.texState==="like") reasons.push({cls:"rr-good", ic:"✓", t:`선호 텍스처(${escapeHtml(s.c.texture)})와 일치`});
    if(s.texState==="dislike") reasons.push({cls:"rr-warn", ic:"⚠", t:`기피하는 텍스처(${escapeHtml(s.c.texture)})입니다`});
    s.certMatches.forEach(m=>reasons.push({cls:"rr-good", ic:"✓", t:`${m.cert} 라벨 — ${m.why}`}));
    if(s.negHits.length) reasons.push({cls:"rr-warn", ic:"⚠", t:`안 맞았던 제품과 겹치는 성분: ${s.negHits.map(escapeHtml).join(", ")}`});
    s.found.caution.slice(0,2).forEach(cc=>reasons.push({cls:"rr-warn", ic:"⚠", t:`${cc.key} — ${cc.note}`}));
    if(s.avoidHits.length) reasons.push({cls:"rr-warn", ic:"✗", t:`기피 설정 성분 포함: ${s.avoidHits.map(escapeHtml).join(", ")}`});
    (s.found.preg||[]).forEach(pg=>reasons.push({cls:"rr-warn", ic:"✗", t:`임신·수유 중 ${pg.level} 성분 포함: ${pg.key}`}));
    if(reasons.length===0) reasons.push({cls:"rr-info", ic:"·", t:"프로필과 충돌하는 성분이 없어 무난한 선택입니다."});

    div.innerHTML = `
      <div class="reco-top">
        <div class="nm">
          <b>${rank+1}. ${escapeHtml(s.c.name)}</b>${s.alreadyUsed?' <span class="ing-tag it-good">사용해봄</span>':''}
          <div style="margin-top:3px;"><span class="brand-tag">${s.c.brand} (가상)</span><span class="hint">${s.c.cat} · ${s.c.price}${s.c.texture?` · ${s.c.texture}`:""}</span>
          ${(s.c.certs&&s.c.certs.length)? s.c.certs.map(cc=>`<span class="ing-tag it-good" style="margin-left:4px;">${cc}</span>`).join("") : ""}</div>
        </div>
        <div class="match-wrap">
          <div class="match-bar"><i style="width:${s.total}%"></i></div>
          <span class="match-num">매칭 ${s.total}</span>
        </div>
      </div>
      <div class="reco-reasons">${reasons.map(r=>`<div class="rr ${r.cls}"><span class="ic">${r.ic}</span><span>${r.t}</span></div>`).join("")}</div>
      <div class="reco-foot">
        <button class="btn btn-ghost btn-sm" data-send="${s.c.id}">판단 보드에서 상세 검증</button>
        <span class="hint">실제 구매 시엔 같은 컨셉의 실제 제품 전성분으로 STEP 4 검증을 거치세요.</span>
      </div>`;
    box.appendChild(div);
  });
  box.querySelectorAll("[data-send]").forEach(b=>b.addEventListener("click", ()=>{
    const c = CATALOG.find(x=>x.id===b.dataset.send);
    const p = {id:++pid, name:`[카탈로그] ${c.brand} ${c.name}`, cat:"스킨케어", ingredients:c.ing, shade:null, shadeName:null, verdict:null};
    p.analysis = analyzeProduct(p);
    state.products.unshift(p);
    renderBoard();
    document.getElementById("step3").scrollIntoView({behavior:"smooth", block:"start"});
  }));
}

$("#recoBtn").addEventListener("click", ()=>runReco(null));

/* ---- 기록 내보내기/불러오기 ---- */
$("#exportBtn").addEventListener("click", ()=>{
  if(state.records.length===0){ alert("내보낼 기록이 없습니다."); return; }
  state.events.exports++;
  const data = snapshot();
  data.exported = new Date().toISOString();
  const blob = new Blob([JSON.stringify(data,null,2)],{type:"application/json"});
  const a = document.createElement("a");
  a.href = URL.createObjectURL(blob);
  a.download = "fitcheck-records.json";
  a.click();
  URL.revokeObjectURL(a.href);
  saveAll();
});
$("#importBtn").addEventListener("click", ()=>$("#importInput").click());
$("#importInput").addEventListener("change", e=>{
  const f = e.target.files[0]; if(!f) return;
  const fr = new FileReader();
  fr.onload = ()=>{
    try{
      const data = JSON.parse(fr.result);
      if(!Array.isArray(data.records)) throw new Error("형식 오류");
      let n = 0;
      data.records.forEach(r=>{
        if(!r.name || !r.ingredients) return;
        state.records.push(reviveRecord(r)); n++;
      });
      renderRecords();
      alert(`${n}건을 불러왔습니다.`);
    }catch(err){ alert("불러오기 실패: 올바른 기록 파일(JSON)이 아닙니다."); }
    e.target.value="";
  };
  fr.readAsText(f);
});

/* ---- OCR: 라벨 사진 → 전성분 텍스트 (Tesseract.js 지연 로드) ---- */
let ocrTarget = null;
function ocrStatus(msg){ if(ocrTarget) $("#ocr-"+ocrTarget).textContent = msg; }
async function loadTesseract(){
  if(window.Tesseract) return true;
  ocrStatus("OCR 엔진 로딩 중…");
  try{
    await new Promise((res,rej)=>{
      const s = document.createElement("script");
      s.src = "https://cdn.jsdelivr.net/npm/tesseract.js@5/dist/tesseract.min.js";
      s.onload = res; s.onerror = rej;
      document.head.appendChild(s);
    });
    return true;
  }catch(e){
    ocrStatus("오프라인이거나 로드 실패 — 텍스트로 붙여넣어 주세요.");
    return false;
  }
}
document.querySelectorAll("[data-ocr]").forEach(b=>{
  b.addEventListener("click", ()=>{ ocrTarget = b.dataset.ocr; $("#ocrFile").click(); });
});
$("#ocrFile").addEventListener("change", async e=>{
  const f = e.target.files[0]; e.target.value="";
  if(!f || !ocrTarget) return;
  if(!(await loadTesseract())) return;
  ocrStatus("인식 중… (수 초 소요)");
  try{
    const {data} = await Tesseract.recognize(f, "kor", {
      logger: m=>{ if(m.status==="recognizing text") ocrStatus(`인식 중 ${(m.progress*100).toFixed(0)}%`); }
    });
    let text = (data.text||"").replace(/\s*\n\s*/g, ", ").replace(/,\s*,+/g, ",").replace(/\s{2,}/g," ").trim();
    if(!text){ ocrStatus("텍스트를 찾지 못했습니다. 라벨을 밝고 평평하게 다시 찍어보세요."); return; }
    const ta = $("#"+ocrTarget);
    ta.value = ta.value ? ta.value + ", " + text : text;
    state.events.ocrRuns++;
    ocrStatus("인식 완료 — 오인식된 성분명은 직접 수정하세요.");
    saveAll();
  }catch(err){ ocrStatus("인식 실패 — 다른 사진으로 시도해보세요."); }
});

/* ---- 프리미엄 가짜 문 (지불 의사 검증) ---- */
$("#premiumBtn").addEventListener("click", ()=>{
  state.events.premiumOpens++;
  $("#premiumModal").hidden = false;
  saveAll();
});
$("#premiumClose").addEventListener("click", ()=>{ $("#premiumModal").hidden = true; });
$("#premiumModal").addEventListener("click", e=>{ if(e.target.id==="premiumModal") $("#premiumModal").hidden = true; });
$("#interestBtn").addEventListener("click", ()=>{
  state.events.premiumInterest = (state.events.premiumInterest||0) + 1;
  $("#interestMsg").textContent = "저장됐습니다. 감사합니다!";
  saveAll();
  setTimeout(()=>{ $("#premiumModal").hidden = true; $("#interestMsg").textContent=""; }, 900);
});

/* ---- 운영 지표 (AARRR) ---- */
function renderMetrics(){
  const m = state.metrics, e = state.events;
  const today = new Date().toISOString().slice(0,10);
  const last7 = m.visits.filter(d=>{
    const diff = (new Date(today) - new Date(d)) / 86400000;
    return diff >= 0 && diff < 7;
  }).length;
  let d7 = "판정 불가 (첫 방문 후 7일 미경과)";
  if(m.firstVisit){
    const fv = new Date(m.firstVisit);
    const daysSince = (new Date(today) - fv) / 86400000;
    if(daysSince >= 7){
      const revisit = m.visits.some(d=>{
        const diff = (new Date(d) - fv) / 86400000;
        return diff >= 1 && diff <= 7;
      });
      d7 = revisit ? "달성 ✓" : "미달성";
    }
  }
  const sameDayActivation = m.firstVisit && m.activatedAt ? (m.firstVisit===m.activatedAt ? "당일 ✓" : `+${Math.round((new Date(m.activatedAt)-new Date(m.firstVisit))/86400000)}일`) : "미활성";
  const refs = e.refs ? Object.entries(e.refs).map(([k,v])=>`${k}: ${v}회`).join(", ") : "직접 방문만";
  const row = (k,v)=>`<div style="display:flex; justify-content:space-between; padding:6px 0; border-bottom:1px dashed var(--line);"><span style="color:var(--sub);">${k}</span><b style="text-align:right;">${v}</b></div>`;
  $("#metricsBody").innerHTML =
    `<div style="font-weight:700; margin:8px 0 2px; color:var(--olive-deep);">Acquisition</div>`
    + row("총 방문일수", `${m.visits.length}일`)
    + row("유입 채널(ref)", refs)
    + `<div style="font-weight:700; margin:12px 0 2px; color:var(--olive-deep);">Activation</div>`
    + row("첫 방문일", m.firstVisit||"-")
    + row("첫 기록 등록", `${m.activatedAt||"아직"} (${sameDayActivation})`)
    + row("누적 기록 수", `${e.recordsAdded}개`)
    + `<div style="font-weight:700; margin:12px 0 2px; color:var(--olive-deep);">Retention</div>`
    + row("최근 7일 방문", `${last7}일`)
    + row("D7 재방문", d7)
    + row("체크인 누적", `${state.checkins.length}회`)
    + `<div style="font-weight:700; margin:12px 0 2px; color:var(--olive-deep);">Revenue (프록시)</div>`
    + row("프리미엄 열람", `${e.premiumOpens}회`)
    + row("프리미엄 관심 클릭", `${e.premiumInterest||0}회`)
    + `<div style="font-weight:700; margin:12px 0 2px; color:var(--olive-deep);">Referral (프록시)</div>`
    + row("동기화 코드 생성", `${e.syncGens||0}회`)
    + row("기록 파일 내보내기", `${e.exports}회`);
}
$("#metricsBtn").addEventListener("click", e=>{ e.preventDefault(); renderMetrics(); $("#metricsModal").hidden = false; });
$("#metricsClose").addEventListener("click", ()=>{ $("#metricsModal").hidden = true; });
$("#metricsModal").addEventListener("click", e=>{ if(e.target.id==="metricsModal") $("#metricsModal").hidden = true; });

/* ================= 성분 사전 검색 ================= */
function lookupSearch(q){
  const nq = norm(q);
  if(nq.length < 1) return [];
  const profileTags = new Set([state.skinType, ...state.concerns].filter(Boolean));
  const seen = new Set();
  const out = [];
  ING_DB.forEach(entry=>{
    const hit = entry.names.some(nm=>norm(nm).includes(nq) || nq.includes(norm(nm)));
    if(!hit || seen.has(entry.key)) return;
    seen.add(entry.key);
    let status = "neutral", note = entry.note;
    if(entry.type==="good"){ status = entry.for.some(t=>profileTags.has(t)) ? "good" : "neutral-good"; }
    else if(entry.type==="caution"){ status = (entry.universal || entry.for.some(t=>profileTags.has(t))) ? "caution" : "neutral-caution"; }
    else if(entry.type==="mixed"){
      if(entry.cautionFor && entry.cautionFor.some(t=>profileTags.has(t))) status = "caution";
      else if(entry.goodFor && entry.goodFor.some(t=>profileTags.has(t))) status = "good";
      else status = "neutral";
    }
    out.push({key: entry.key, aliases: entry.names.join(", "), note, status, universal: !!entry.universal, preg: entry.preg||null});
  });
  return out.slice(0, 8);
}
function renderLookup(results, query){
  const box = $("#lookupResults");
  if(!query){ box.hidden = true; return; }
  box.hidden = false;
  if(results.length===0){
    box.innerHTML = `<div class="lookup-empty">"${escapeHtml(query)}"에 대한 정보가 아직 없습니다. 성분 사전은 계속 늘어나고 있습니다.</div>`;
    return;
  }
  const STATUS_LABEL = {good:"내 프로필에 도움", "neutral-good":"일반적으로 도움", caution:"내 프로필에 주의", "neutral-caution":"참고(주의 성분)", neutral:"중립"};
  const STATUS_CLASS = {good:"ci-good", "neutral-good":"ci-good", caution:"ci-warn", "neutral-caution":"ci-info", neutral:"ci-info"};
  box.innerHTML = results.map(r=>`
    <div class="lookup-item">
      <div class="li-head">${gb(r.key)}<b>${escapeHtml(r.key)}</b></div>
      <div class="hint">${escapeHtml(r.aliases)}</div>
      <div class="check-item ${STATUS_CLASS[r.status]}" style="margin-top:6px;">
        <span class="ico">${r.status.includes("caution")?"⚠":r.status.includes("good")?"✓":"·"}</span>
        <span><b>${STATUS_LABEL[r.status]}</b> — ${escapeHtml(r.note)}${r.preg?` <span class="ing-tag it-caution">임신 중 ${r.preg}</span>`:""}${r.universal?` <span class="ing-tag it-caution">누구나 주의</span>`:""}</span>
      </div>
    </div>`).join("");
}
let lookupTimer = null;
$("#lookupInput").addEventListener("input", e=>{
  clearTimeout(lookupTimer);
  const q = e.target.value.trim();
  lookupTimer = setTimeout(()=>renderLookup(lookupSearch(q), q), 150);
});
document.addEventListener("click", e=>{
  if(!e.target.closest(".lookup-box")) $("#lookupResults").hidden = true;
  else if($("#lookupInput").value.trim()) $("#lookupResults").hidden = false;
});

/* ================= quicknav 활성 표시 ================= */
const qnLinks = [...document.querySelectorAll(".qn-link")];
const qnSections = qnLinks.map(a=>document.getElementById(a.dataset.sec)).filter(Boolean);
function updateQuicknav(){
  let activeIdx = 0;
  const line = 140;
  qnSections.forEach((sec, i)=>{ if(sec.getBoundingClientRect().top - line <= 0) activeIdx = i; });
  qnLinks.forEach((a,i)=>a.classList.toggle("active", i===activeIdx));
  const active = qnLinks[activeIdx];
  if(active){
    const nav = $("#quicknavIn");
    const r = active.getBoundingClientRect(), nr = nav.getBoundingClientRect();
    if(r.left < nr.left || r.right > nr.right) nav.scrollLeft += (r.left - nr.left) - 20;
  }
}
window.addEventListener("scroll", ()=>{ clearTimeout(window.__qnT); window.__qnT = setTimeout(updateQuicknav, 60); }, { passive: true });
updateQuicknav();

hydrate();

/* analyze button */
$("#analyzeBtn").addEventListener("click", ()=>{
  const name = $("#pName").value.trim();
  const ing = $("#pIngredients").value.trim();
  if(!name){ alert("상품명을 입력하세요."); $("#pName").focus(); return; }
  if(!ing){ alert("전성분을 붙여넣어 주세요. 올리브영 상세페이지 하단 '화장품법에 따른 전성분'에서 복사할 수 있습니다."); $("#pIngredients").focus(); return; }
  const cat = $("#pCat").value;
  const hasShade = ["베이스메이크업","색조"].includes(cat);
  const p = {
    id: ++pid, name, cat, ingredients: ing,
    shade: hasShade ? $("#pShade").value : null,
    shadeName: hasShade ? $("#pShadeName").value.trim() : null,
    texture: $("#vTexture").value,
    certs: [...document.querySelectorAll("#vCertChips .chip[aria-pressed=true]")].map(b=>b.dataset.v),
    verdict: null
  };
  p.analysis = analyzeProduct(p);
  state.products.unshift(p);
  document.querySelectorAll("#vCertChips .chip").forEach(b=>b.setAttribute("aria-pressed","false"));
  $("#vTexture").value = "";
  renderBoard();
  document.getElementById("step3").scrollIntoView({behavior:"smooth", block:"start"});
});
</script>
</body>
</html>
