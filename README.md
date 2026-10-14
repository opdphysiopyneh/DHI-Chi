# DHI-Chi

<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <title>東區尤德夫人那打素醫院 物理治療部 - 暈眩障礙問卷（DHI）</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0, shrink-to-fit=no, viewport-fit=cover">
  <style>
    :root {
      --primary: #007AFF;
      --primary-active: #0056b3;
      --bg: #F2F2F7;
      --card-bg: #FFFFFF;
      --text-main: #000000;
      --text-muted: #6C6C70;
      --border: #D1D1D6;
      --selected-bg: #E3F0FF;
      --error-border: #FF3B30;
      --error-bg: #FFF2F2;
    }

    * {
      box-sizing: border-box;
      -webkit-tap-highlight-color: transparent;
      -webkit-text-size-adjust: 100%;
    }

    html, body {
      width: 100%;
      overflow-x: hidden;
      scroll-behavior: smooth;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", "SF Pro Display", "PingFang HK", "PingFang TC", "Noto Sans TC", sans-serif;
      background-color: var(--bg);
      color: var(--text-main);
      margin: 0;
      padding: env(safe-area-inset-top, 12px) 14px calc(36px + env(safe-area-inset-bottom, 20px)) 14px;
      font-size: clamp(17px, 4.8vw, 20px);
      line-height: 1.45;
    }

    .container {
      width: 100%;
      max-width: 600px;
      margin: 0 auto;
    }

    .header-card {
      background: var(--card-bg);
      border-radius: 16px;
      padding: 16px 14px;
      margin-top: 6px;
      margin-bottom: 14px;
      text-align: center;
      box-shadow: 0 1px 4px rgba(0,0,0,0.06);
      border: 1px solid var(--border);
    }

    .hospital-title {
      font-size: clamp(0.95rem, 3.8vw, 1.1rem);
      color: #636366;
      font-weight: 600;
      margin-bottom: 4px;
      white-space: pre-line;
    }

    .main-title {
      font-size: clamp(1.4rem, 5.5vw, 1.85rem);
      font-weight: 800;
      margin: 0 0 8px 0;
      color: var(--text-main);
      line-height: 1.25;
      white-space: pre-line;
    }

    .instruction {
      font-size: clamp(1.05rem, 4.2vw, 1.2rem);
      color: var(--text-muted);
      margin: 0;
      line-height: 1.5;
    }

    /* Slider Cards */
    .slider-card {
      background: var(--card-bg);
      border-radius: 16px;
      padding: 18px 14px;
      margin-bottom: 14px;
      box-shadow: 0 1px 4px rgba(0,0,0,0.05);
      border: 1.5px solid var(--border);
    }

    .slider-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      margin-bottom: 8px;
    }

    .slider-badge {
      font-size: 1.6rem;
      font-weight: 800;
      color: var(--primary);
    }

    .optional-tag {
      font-size: 0.9rem;
      color: #C66900;
      background: #FFF3D6;
      padding: 3px 10px;
      border-radius: 12px;
      font-weight: 700;
      margin-left: 8px;
    }

    .slider-container {
      margin: 20px 0 10px 0;
    }

    .custom-slider {
      -webkit-appearance: none;
      width: 100%;
      height: 10px;
      border-radius: 5px;
      outline: none;
      cursor: pointer;
    }

    .nrs-gradient {
      background: linear-gradient(to right, #34C759 0%, #FFCC00 50%, #FF3B30 100%);
    }

    .groc-gradient {
      background: linear-gradient(to right, #FF3B30 0%, #FFCC00 50%, #34C759 100%);
    }

    .custom-slider::-webkit-slider-thumb {
      -webkit-appearance: none;
      appearance: none;
      width: 28px;
      height: 28px;
      border-radius: 50%;
      background: #FFFFFF;
      border: 3px solid var(--primary);
      box-shadow: 0 2px 6px rgba(0,0,0,0.3);
      cursor: pointer;
      transition: transform 0.1s;
    }

    .custom-slider::-webkit-slider-thumb:active {
      transform: scale(1.15);
    }

    .slider-labels {
      display: flex;
      justify-content: space-between;
      margin-top: 10px;
      font-size: 0.95rem;
      font-weight: 700;
    }

    .label-left {
      color: #28A745;
      text-align: left;
    }

    .label-right {
      color: #DC3545;
      text-align: right;
    }

    .label-center {
      color: var(--text-muted);
      text-align: center;
    }

    .clear-btn {
      width: 100%;
      margin-top: 10px;
      padding: 12px;
      font-size: 1rem;
      background: #E5E5EA;
      color: #1C1C1E;
      border: none;
      border-radius: 12px;
      font-weight: 700;
      cursor: pointer;
      transition: background 0.15s;
    }

    .clear-btn:active {
      background: #D1D1D6;
    }

    /* Question Cards */
    .question-card {
      background: var(--card-bg);
      border-radius: 16px;
      padding: 18px 14px;
      margin-bottom: 14px;
      box-shadow: 0 1px 4px rgba(0,0,0,0.05);
      border: 1.5px solid var(--border);
      transition: border-color 0.2s, background-color 0.2s;
    }

    .question-card.highlight-error {
      border-color: var(--error-border) !important;
      background-color: var(--error-bg);
      animation: pulse-border 1.5s infinite;
    }

    @keyframes pulse-border {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.01); }
    }

    .question-title {
      font-size: clamp(1.2rem, 4.8vw, 1.4rem);
      font-weight: 700;
      color: var(--text-main);
      line-height: 1.35;
      margin-bottom: 12px;
    }

    .options-group {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .option-item {
      display: flex;
      align-items: center;
      padding: 14px 14px;
      border-radius: 14px;
      background: #F8F8FA;
      border: 2px solid transparent;
      cursor: pointer;
      font-size: clamp(1.05rem, 4.2vw, 1.2rem);
      color: #1C1C1E;
      transition: all 0.15s ease-in-out;
      user-select: none;
    }

    .option-item:active {
      transform: scale(0.99);
      background: #E5E5EA;
    }

    .option-item.selected {
      background: var(--selected-bg);
      border-color: var(--primary);
      color: #004CB8;
      font-weight: 700;
    }

    .custom-radio {
      width: 24px;
      height: 24px;
      border-radius: 50%;
      border: 2px solid #8E8E93;
      margin-right: 12px;
      flex-shrink: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #FFF;
      transition: border-color 0.15s, background-color 0.15s;
    }

    .option-item.selected .custom-radio {
      border-color: var(--primary);
      background: var(--primary);
    }

    .option-item.selected .custom-radio::after {
      content: "";
      width: 10px;
      height: 10px;
      background: #FFF;
      border-radius: 50%;
    }

    .option-text {
      flex-grow: 1;
      line-height: 1.4;
    }

    .hidden-radio {
      position: absolute;
      opacity: 0;
      pointer-events: none;
    }

    .calc-btn {
      margin-top: 16px;
      padding: 18px;
      width: 100%;
      background: var(--primary);
      color: #FFFFFF;
      font-size: clamp(1.2rem, 5vw, 1.35rem);
      font-weight: 700;
      border: none;
      border-radius: 16px;
      cursor: pointer;
      box-shadow: 0 4px 14px rgba(0, 122, 255, 0.35);
      transition: background 0.15s, transform 0.1s;
    }

    .calc-btn:active {
      background: var(--primary-active);
      transform: scale(0.98);
    }

    /* Modal */
    .modal {
      display: none;
      position: fixed;
      z-index: 999;
      inset: 0;
      background: rgba(0, 0, 0, 0.5);
      backdrop-filter: blur(8px);
      -webkit-backdrop-filter: blur(8px);
      align-items: center;
      justify-content: center;
      padding: 16px;
    }

    .modal-content {
      background: #FFFFFF;
      padding: 24px 18px;
      border-radius: 22px;
      width: 100%;
      max-width: 400px;
      text-align: center;
      box-shadow: 0 12px 36px rgba(0,0,0,0.25);
    }

    .modal-content h2 {
      margin: 0 0 12px 0;
      font-size: 1.6rem;
    }

    .result-block {
      background: #F8F8FA;
      border-radius: 14px;
      padding: 12px;
      margin-bottom: 12px;
    }

    .result-label {
      font-size: 1rem;
      color: var(--text-muted);
      margin: 0 0 4px 0;
    }

    .result-val {
      font-size: 2.2rem;
      font-weight: 800;
      color: var(--primary);
      margin: 0;
    }

    .notice-box {
      background: #FFF9E6;
      border: 1.5px solid #FFD666;
      padding: 14px;
      margin: 16px 0;
      font-size: 1.05rem;
      color: #874D00;
      border-radius: 12px;
      line-height: 1.5;
      font-weight: 700;
    }

    .close-btn {
      width: 100%;
      padding: 16px;
      background: #1C1C1E;
      color: #FFF;
      font-size: 1.2rem;
      font-weight: 700;
      border: none;
      border-radius: 14px;
      cursor: pointer;
    }
  </style>
</head>
<body>

<div class="container">
  <div class="header-card">
    <div class="hospital-title" id="hospitalTitle"></div>
    <h1 class="main-title" id="formTitle"></h1>
    <p class="instruction" id="formInstruction"></p>
  </div>

  <form id="evaluationForm">
    <!-- 暈眩程度量度計 (NRS 0–10) -->
    <div class="slider-card" id="nrsCard">
      <div class="slider-header">
        <span class="question-title" style="margin-bottom: 0;">暈眩程度量度計（NRS）</span>
        <span id="nrsValueDisplay" class="slider-badge">0 / 10 分</span>
      </div>
      <p style="font-size: 0.95rem; color: var(--text-muted); margin: 4px 0 14px 0;">請根據你今天的情況，評估你的暈眩程度：</p>
      
      <div class="slider-container">
        <input type="range" min="0" max="10" value="0" step="1" class="custom-slider nrs-gradient" id="nrsSlider" oninput="updateNrs(this.value)">
      </div>
      
      <div class="slider-labels">
        <span class="label-left">0 分<br>完全沒有暈眩</span>
        <span class="label-right">10 分<br>暈眩得最厲害</span>
      </div>
    </div>

    <!-- 整體情況轉變量度計 (NGRCS -10 ~ +10, 可選) -->
    <div class="slider-card" id="grocCard">
      <div class="slider-header">
        <div>
          <span class="question-title" style="margin-bottom: 0;">整體情況轉變量度計（NGRCS）</span>
          <span class="optional-tag">可選</span>
        </div>
        <span id="grocValueDisplay" class="slider-badge" style="font-size: 1.25rem;">未評估</span>
      </div>
      <p style="font-size: 0.95rem; color: var(--text-muted); margin: 4px 0 14px 0;">請滑動拉桿評估整體情況轉變（如未開始治療或不適用可略過）：</p>
      
      <div class="slider-container">
        <input type="range" min="-10" max="10" value="0" step="1" class="custom-slider groc-gradient" id="grocSlider" oninput="updateGroc(this.value)">
      </div>
      
      <div class="slider-labels">
        <span class="label-left" style="color: #DC3545;">-10 分<br>最大轉壞</span>
        <span class="label-center">0 分<br>完全沒有轉變</span>
        <span class="label-right" style="color: #28A745;">+10 分<br>最大轉好</span>
      </div>
      <button type="button" class="clear-btn" onclick="clearGroc()">略過 / 清除轉變量度選擇</button>
    </div>

    <div id="questionsContainer"></div>
    
    <button type="button" class="calc-btn" onclick="submitAssessment()">計算評估結果</button>
  </form>
</div>

<div id="scoreModal" class="modal" role="dialog" aria-modal="true" aria-labelledby="modalTitle" onclick="handleBackdropClick(event)">
  <div class="modal-content" onclick="event.stopPropagation()">
    <h2 id="modalTitle">評估結果</h2>
    
    <div class="result-block" id="modalNrsBlock">
      <p class="result-label">今日暈眩程度（NRS）</p>
      <p id="modalNrsText" class="result-val">0 / 10 分</p>
    </div>

    <div class="result-block" id="modalGrocBlock" style="display: none;">
      <p class="result-label">整體情況轉變（NGRCS）</p>
      <p id="modalGrocText" class="result-val" style="font-size: 1.6rem;">0 分</p>
    </div>

    <div class="result-block">
      <p class="result-label" id="modalScoreTitle">暈眩障礙總分（DHI）</p>
      <p id="modalScoreValue" class="result-val">0 / 100 分</p>
      <p id="modalScoreSubtitle" style="font-size: 0.95rem; margin: 6px 0 0 0; color: var(--text-muted);"></p>
    </div>

    <div class="notice-box">
      請不要離開此畫面，並出示給您的治療師。<br>
      您亦可以進行螢幕截圖。<br>
      謝謝。
    </div>
    
    <button type="button" class="close-btn" onclick="closeModal()">關閉</button>
  </div>
</div>

<script>
// 常規題目選項：會 (4分) / 有時會 (2分) / 不會 (0分)
const defaultOptions = [
  { key: "yes", value: 4, label: "會" },
  { key: "sometimes", value: 2, label: "有時會" },
  { key: "no", value: 0, label: "不會" }
];

// 第10題與第22題專用選項：有 (4分) / 有時有 (2分) / 沒有 (0分)
const experienceOptions = [
  { key: "yes", value: 4, label: "有" },
  { key: "sometimes", value: 2, label: "有時有" },
  { key: "no", value: 0, label: "沒有" }
];

const CONFIG = {
  hospitalTitle: "醫院管理局 東區尤德夫人那打素醫院\n物理治療部",
  title: "暈眩障礙問卷\n（Dizziness Handicap Inventory, DHI）",
  instruction: "此評估用作辨明你的暈眩或身體不穩定而體驗到的困難。<br><strong>請根據你最近的情況回答下列問題：</strong>",
  items: [
    { title: "把眼睛往上望會不會使問題惡化？", options: defaultOptions },
    { title: "這問題會不會使你感到灰心失意？", options: defaultOptions },
    { title: "你會不會因為這問題而限制自己的商務遠行或康樂活動？", options: defaultOptions },
    { title: "超級市場的通道行走會不會使問題惡化？", options: defaultOptions },
    { title: "這問題會不會使你難於上床下床？", options: defaultOptions },
    { title: "這問題會不會限制你參與各種社交活動，例如：外出用膳、外出看電影、跳舞或參加舞會？", options: defaultOptions },
    { title: "這問題會不會使你難於閱讀？", options: defaultOptions },
    { title: "進行運動跳舞或家務雜活（例如：打掃或收拾碗碟）等較有難度的活動會不會使問題惡化？", options: defaultOptions },
    { title: "這問題會不會使你害怕單獨離家外出？", options: defaultOptions },
    { title: "這問題有沒有曾經使你在別人面前感到難堪？", options: experienceOptions },
    { title: "快速移動頭部會不會使問題惡化？", options: defaultOptions },
    { title: "這問題會不會使你有畏高的情況？", options: defaultOptions },
    { title: "在床上翻轉身體會不會使問題惡化？", options: defaultOptions },
    { title: "這問題會不會使你難於處理消耗體力的家務園務？", options: defaultOptions },
    { title: "你會不會因這問題而害怕別人把自己看成無法自制的？", options: defaultOptions },
    { title: "這問題會不會使你難於獨自外出散步？", options: defaultOptions },
    { title: "在行人道上走路會不會使問題惡化？", options: defaultOptions },
    { title: "這問題會不會使你難於集中精神？", options: defaultOptions },
    { title: "這問題會不會使你難於在漆黑的房子走動？", options: defaultOptions },
    { title: "這問題會不會使你害怕獨自留在家中？", options: defaultOptions },
    { title: "這問題會不會使你覺得自己的身體有缺憾？", options: defaultOptions },
    { title: "這問題有沒有曾經影響你與家人或朋友的關係？", options: experienceOptions },
    { title: "這問題會不會使你沮喪？", options: defaultOptions },
    { title: "這問題會不會妨礙你的工作或家務？", options: defaultOptions },
    { title: "向前彎腰會不會使問題惡化？", options: defaultOptions }
  ]
};

let grocEngaged = false;

document.addEventListener("DOMContentLoaded", () => {
  initQuestionnaire();
});

function initQuestionnaire() {
  const hospEl = document.getElementById("hospitalTitle");
  if (CONFIG.hospitalTitle) {
    hospEl.textContent = CONFIG.hospitalTitle;
  } else {
    hospEl.style.display = "none";
  }

  document.getElementById("formTitle").textContent = CONFIG.title;
  document.getElementById("formInstruction").innerHTML = CONFIG.instruction;

  const container = document.getElementById("questionsContainer");
  container.innerHTML = "";

  CONFIG.items.forEach((item, index) => {
    const qNum = index + 1;
    const card = document.createElement("div");
    card.className = "question-card";
    card.id = `card-q${qNum}`;

    const title = document.createElement("div");
    title.className = "question-title";
    title.textContent = `${qNum}. ${item.title}`;
    card.appendChild(title);

    const optionsGroup = document.createElement("div");
    optionsGroup.className = "options-group";

    item.options.forEach(opt => {
      const label = document.createElement("label");
      label.className = "option-item";
      label.htmlFor = `q${qNum}_${opt.key}`;

      const radio = document.createElement("input");
      radio.type = "radio";
      radio.name = `q${qNum}`;
      radio.id = `q${qNum}_${opt.key}`;
      radio.value = opt.value;
      radio.className = "hidden-radio";

      radio.addEventListener("change", () => {
        optionsGroup.querySelectorAll(".option-item").forEach(el => el.classList.remove("selected"));
        if (radio.checked) {
          label.classList.add("selected");
          card.classList.remove("highlight-error");
        }
      });

      const dot = document.createElement("span");
      dot.className = "custom-radio";
      dot.setAttribute("aria-hidden", "true");

      const itemText = document.createElement("span");
      itemText.className = "option-text";
      itemText.textContent = opt.label;

      label.append(radio, dot, itemText);
      optionsGroup.appendChild(label);
    });

    card.appendChild(optionsGroup);
    container.appendChild(card);
  });
}

function updateNrs(val) {
  document.getElementById("nrsValueDisplay").textContent = `${val} / 10 分`;
}

function updateGroc(val) {
  grocEngaged = true;
  let text = `${val} 分`;
  if (val > 0) text = `+${val} 分（好轉）`;
  else if (val < 0) text = `${val} 分（轉壞）`;
  else text = `0 分（無轉變）`;

  document.getElementById("grocValueDisplay").textContent = text;
}

function clearGroc() {
  grocEngaged = false;
  document.getElementById("grocSlider").value = 0;
  document.getElementById("grocValueDisplay").textContent = "未評估";
}

function submitAssessment() {
  const unanswered = [];
  document.querySelectorAll(".question-card").forEach(c => c.classList.remove("highlight-error"));

  for (let i = 1; i <= CONFIG.items.length; i++) {
    if (!document.querySelector(`input[name="q${i}"]:checked`)) {
      unanswered.push(i);
    }
  }

  if (unanswered.length > 0) {
    unanswered.forEach(num => {
      const card = document.getElementById(`card-q${num}`);
      if (card) card.classList.add("highlight-error");
    });

    const firstCard = document.getElementById(`card-q${unanswered[0]}`);
    if (firstCard) {
      firstCard.scrollIntoView({ behavior: "smooth", block: "center" });
    }
    return;
  }

  let totalScore = 0;
  let count4 = 0;
  let count2 = 0;
  let count0 = 0;

  for (let i = 1; i <= CONFIG.items.length; i++) {
    const selected = document.querySelector(`input[name="q${i}"]:checked`);
    const val = parseInt(selected.value, 10);
    totalScore += val;
    if (val === 4) count4++;
    else if (val === 2) count2++;
    else if (val === 0) count0++;
  }

  const nrsVal = document.getElementById("nrsSlider").value;
  document.getElementById("modalNrsText").textContent = `${nrsVal} / 10 分`;

  if (grocEngaged) {
    document.getElementById("modalGrocBlock").style.display = "block";
    const grocVal = document.getElementById("grocSlider").value;
    let grocText = `${grocVal} 分`;
    if (grocVal > 0) grocText = `+${grocVal} 分（好轉）`;
    else if (grocVal < 0) grocText = `${grocVal} 分（轉壞）`;
    else grocText = `0 分（無轉變）`;
    document.getElementById("modalGrocText").textContent = grocText;
  } else {
    document.getElementById("modalGrocBlock").style.display = "none";
  }

  document.getElementById("modalScoreValue").textContent = `${totalScore} / 100 分`;
  document.getElementById("modalScoreSubtitle").innerHTML = 
    `選「會/有」(4分)：<strong>${count4}</strong> 題 ｜ 選「有時」(2分)：<strong>${count2}</strong> 題 ｜ 選「不會/沒有」(0分)：<strong>${count0}</strong> 題`;

  const modal = document.getElementById("scoreModal");
  modal.style.display = "flex";
}

function closeModal() {
  document.getElementById
