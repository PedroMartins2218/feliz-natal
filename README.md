<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Feliz Natal, Bianca 🎄</title>
  <meta name="description" content="Um cartão de Natal interativo, leve e fofo.">
  <style>
    :root{
      --bg1:#0b1020;
      --bg2:#0f1b3a;
      --card:rgba(255,255,255,.94);
      --ink:#0f172a;
      --muted:#475569;
      --accent:#ef4444;
      --accent2:#22c55e;
      --ring:rgba(239,68,68,.25);
      --radius:18px;
      --shadow:0 14px 40px rgba(0,0,0,.28);
    }
    *{box-sizing:border-box}
    html,body{height:auto}
body{
  margin:0;
  font-family: ui-sans-serif, -apple-system, Segoe UI, Roboto, Helvetica, Arial;
  color:#fff;
  background:
    radial-gradient(900px 380px at 20% 0%, rgba(255,255,255,.10), transparent),
    radial-gradient(900px 380px at 80% 10%, rgba(34,197,94,.10), transparent),
    linear-gradient(180deg, var(--bg1), var(--bg2));
overflow-x:hidden;
  overflow-y:auto;
}
.stars{
      position:fixed; inset:0; pointer-events:none; opacity:.55;
      background-image:
        radial-gradient(2px 2px at 10% 20%, rgba(255,255,255,.85) 50%, transparent 55%),
        radial-gradient(1.6px 1.6px at 30% 70%, rgba(255,255,255,.75) 50%, transparent 55%),
        radial-gradient(1.8px 1.8px at 70% 30%, rgba(255,255,255,.8) 50%, transparent 55%),
        radial-gradient(1.2px 1.2px at 85% 60%, rgba(255,255,255,.7) 50%, transparent 55%),
        radial-gradient(1.4px 1.4px at 55% 15%, rgba(255,255,255,.75) 50%, transparent 55%),
        radial-gradient(1.2px 1.2px at 40% 40%, rgba(255,255,255,.65) 50%, transparent 55%);
      filter: blur(.1px);
    }
   main{
  position:relative;
  min-height:100vh;
  display:flex;
  justify-content:center;
  align-items:flex-start;
  padding:18px;
  z-index:1;
   }
.card{
      width:min(860px, 94vw);
      background:var(--card);
      color:var(--ink);
      border-radius:var(--radius);
      box-shadow:var(--shadow);
      border:1px solid rgba(255,255,255,.65);
      padding:clamp(18px, 3vw, 28px);
    }
    header{
      display:flex; align-items:flex-start; justify-content:space-between; gap:14px;
      margin-bottom:10px;
    }
    .badge{
      display:inline-flex; align-items:center; gap:8px;
      font-size:12px; color:#fff;
      background: linear-gradient(135deg, var(--accent), #fb7185);
      padding:8px 12px; border-radius:999px;
      box-shadow:0 10px 22px var(--ring);
      letter-spacing:.2px;
      white-space:nowrap;
    }
    h1{
      margin:6px 0 6px;
      font-size:clamp(22px, 4.6vw, 34px);
      line-height:1.15;
    }
    p.lead{margin:0; color:var(--muted);}
    .grid{display:grid; gap:12px; margin-top:14px;}
    @media(min-width:820px){ .grid{ grid-template-columns: 1.15fr .85fr; align-items:start; } }
    .panel{
      background:linear-gradient(180deg, #fff, #fff7ed);
      border:1px solid #fde68a;
      border-radius:14px;
      padding:14px;
    }
    .panel h2{margin:0 0 10px; font-size:16px;}
    .note{
      border-left:3px solid #c7d2fe;
      padding-left:10px;
      color:#334155;
      margin:10px 0 0;
      font-size:13px;
    }
    .questions{display:grid; gap:10px; margin-top:12px;}
    .q{
      background:#fff;
      border:1px solid #e2e8f0;
      border-radius:12px;
      padding:12px;
    }
    .q b{display:block; margin-bottom:6px;}
    .choices{display:flex; flex-wrap:wrap; gap:8px;}
    button.chip{
      appearance:none; border:none; cursor:pointer;
      background:#f8fafc;
      border:1px solid #e2e8f0;
      color:#0f172a;
      padding:8px 10px;
      border-radius:999px;
      transition: transform .05s ease, box-shadow .2s ease, border-color .2s ease;
      font-size:13px;
    }
    button.chip:hover{border-color:#cbd5e1; box-shadow:0 10px 20px rgba(2,6,23,.08);}
    button.chip:active{ transform: translateY(1px); }
    button.chip[aria-pressed="true"]{
      border-color:#86efac;
      box-shadow:0 10px 22px rgba(34,197,94,.22);
      background:linear-gradient(180deg, #ffffff, #f0fdf4);
    }
    .actions{
      display:flex; gap:10px; flex-wrap:wrap; justify-content:flex-end;
      margin-top:14px;
    }
    .btn{
      appearance:none; border:none; cursor:pointer; text-decoration:none;
      display:inline-flex; align-items:center; gap:8px;
      padding:11px 13px;
      border-radius:12px;
      background: linear-gradient(135deg, var(--accent2), #16a34a);
      color:#fff;
      box-shadow:0 10px 22px rgba(34,197,94,.22);
      transition: transform .05s ease, filter .2s ease;
      font-size:14px;
    }
    .btn:hover{ filter:brightness(1.03) saturate(1.03); }
    .btn:active{ transform: translateY(1px) scale(.998); }
    .ghost{ background:#fff; color:#0f172a; border:1px solid #e2e8f0; box-shadow:none; }
    .music{
      display:grid; gap:10px;
      background:linear-gradient(180deg, #fff, #eff6ff);
      border:1px solid #bfdbfe;
      border-radius:14px;
      padding:14px;
    }
    .music h2{margin:0; font-size:16px;}
    .field{display:flex; gap:8px; flex-wrap:wrap;}
    input[type="url"]{
      flex: 1 1 240px;
      padding:11px 12px;
      border-radius:12px;
      border:1px solid #cbd5e1;
      outline:none;
      font-size:14px;
    }
    input[type="url"]:focus{ border-color:#93c5fd; box-shadow:0 0 0 4px rgba(147,197,253,.35); }
    .tiny{font-size:12px; color:var(--muted); margin:0;}
    footer{
      display:flex; justify-content:space-between; gap:10px; flex-wrap:wrap;
      margin-top:12px; color:#64748b; font-size:12px;
    }
    .flake{
      position:fixed; top:-10vh;
      width:8px; height:8px;
      border-radius:50%;
      background: rgba(255,255,255,.9);
      box-shadow:0 0 10px rgba(255,255,255,.25);
      opacity:.8;
      animation: snow linear forwards;
      z-index:0;
    }
    @keyframes snow{ to{ transform: translate3d(var(--x), 110vh, 0); opacity:.95; } }
    .reindeer{
      position:fixed;
      left:-15vw;
      top:var(--top);
      font-size:clamp(22px, 3.2vw, 34px);
      filter: drop-shadow(0 10px 22px rgba(0,0,0,.35));
      opacity:.95;
      z-index:0;
      animation: fly linear forwards;
      transform: translate3d(-20vw,0,0);
    }
    @keyframes fly{ to{ transform: translate3d(130vw, 0, 0); } }
    .heart{
      display:inline-block;
      background:linear-gradient(135deg, #fb7185, #f43f5e);
      color:#fff;
      padding:2px 8px;
      border-radius:999px;
      font-size:12px;
      vertical-align:middle;
      margin-left:6px;
    }
  </style>
</head>
<body>
  <div class="stars" aria-hidden="true"></div>
  <main>
    <div class="card" role="main" aria-labelledby="t">
      <header>
        <div>
          <div class="badge">🎄 Cartão de Natal • versão interativa</div>
          <h1 id="t">Feliz Natal, Bibi Berti ✨</h1>
          <p class="lead">
            Passando pra te desejar um Feliz Natal, e saber como você tá
            e... dizer que estou com um pouco de saudade 🤦‍♂️
          
  <span class="heart">de verdade</span>
          </p>
        </div>
        <div style="text-align:right; color:#64748b; font-size:12px;">
          <div>feito com</div>
          <div><b>HTML • CSS • JavaScript</b></div>
        </div>
      </header>

  <div class="grid">
        <section class="panel" aria-label="Mensagem">
          <h2>Te desejo um feliz natal para você e toda a sua Família</h2>
          <p style="margin:0; color:#334155;">
            Eu sei que a gente acabou se afastando. Não vou complicar nem insistir além do necessário —
            só queria deixar um carinho aqui e dizer que gosto muito de você.
          </p>
          <p class="note">
            Gostaria muito de saber como ta indo as suas férias e como você tá
            Deu uma acalmada na rotina? kkkkkkkk
          </p>

  <div class="questions" aria-label="Perguntas para puxar assunto">
            <div class="q" data-q="1">
              <b>Como estão as suas férias?</b>
              <div class="choices">
                <button class="chip" data-val="Bem tranquilas">Bem tranquilas</button>
                <button class="chip" data-val="Corridas (como sempre)">Corridas (como sempre)</button>
                <button class="chip" data-val="Uma mistura dos dois">Uma mistura dos dois</button>
              </div>
            </div>

  <div class="q" data-q="2">
              <b>vai fazer o que nos próximos dias?</b>
              <div class="choices">
                <button class="chip" data-val="Ficar em casa com a família">Ficar em casa com a família</button>
                <button class="chip" data-val="Ir muito pra praia e torrar no sol">Ir muito pra praia e torrar no sol</button>
                <button class="chip" data-val="Organizar as minhas coisas">Organizar as minhas coisas</button>
              </div>
            </div>

  <div class="q" data-q="3">
              <b>Como vai passar o natal?</b>
              <div class="choices">
                <button class="chip" data-val="Com a família">Com a família</button>
                <button class="chip" data-val="Com os amigos">Com os amigos</button>
                <button class="chip" data-val="Preferia falar depois">Sozinha 😕</button>
              </div>
            </div>
          </div>

  <div class="actions">
            <button class="btn ghost" id="reset">Limpar</button>
            <button class="btn" id="send">Responder com um clique</button>
          </div>
          <p class="tiny" style="text-align:right;margin:8px 0 0;">
            Isso vai abrir um rascunho no WhatsApp, selecione o meu contato e me envie a sua resposta
          </p>
        </section>

  <aside class="music" aria-label="Música">
          <h2>Essa música resume o meus pensamentos nas ultimas semanas...</h2>
          <p class="tiny" style="margin:0;">
            Porque você não sai da minha cabeça
            Porque você não sai da minha cabeça

            
  </p>
          <div class="field">
            <input id="musicUrl" type="url" placeholder="https://vt.tiktok.com/ZSP3rEBhU/" />
            <button class="btn" id="openMusic">Abrir música</button>
          </div>
          <p class="tiny" style="margin:0;">
           

  <div class="panel" style="margin-top:10px;border-color:#e2e8f0;background:linear-gradient(180deg,#fff,#f8fafc)">
            <h2>Espero que goste</h2>
            <p style="margin:0;color:#334155">
              Eu só queria te mandar uma mensagem mesmo, mas não queria que fosse algo comum, então... programei esse cartãozinho de Natal interativo pra você.
            </p>
          </div>

  <div class="actions" style="justify-content:flex-start;margin-top:12px;">
            <button class="btn ghost" id="copyMsg">Copiar mensagem de Natal</button>
          </div>
        </aside>
      </div>
<footer>
        <span>🎁 Sem pressão. Só uma lembrança boa de Natal.</span>
        <span>Dica: renomeie o arquivo pra <b>index.html</b> antes de subir no GitHub Pages.</span>
      </footer>
    </div>
  </main>

  <script>
    function spawnFlake(){
      const f = document.createElement('div');
      f.className = 'flake';
      f.style.left = Math.random()*100 + 'vw';
      f.style.animationDuration = (8 + Math.random()*7) + 's';
      f.style.animationDelay = (Math.random()*-6) + 's';
      f.style.setProperty('--x', (Math.random()*30 - 15) + 'vw');
      f.style.width = (6 + Math.random()*7) + 'px';
      f.style.height = f.style.width;
      document.body.appendChild(f);
      setTimeout(()=>f.remove(), 16000);
    }
    for(let i=0;i<18;i++) spawnFlake();
    setInterval(spawnFlake, 650);

    function flyReindeer(){
      const r = document.createElement('div');
      r.className = 'reindeer';
      const herd = ['🦌','🦌','🛷','🦌'];
      r.textContent = herd[Math.floor(Math.random()*herd.length)];
      r.style.setProperty('--top', (10 + Math.random()*35) + 'vh');
      r.style.animationDuration = (10 + Math.random()*10) + 's';
      r.style.animationDelay = (Math.random()*-6) + 's';
      document.body.appendChild(r);
      setTimeout(()=>r.remove(), 22000);
    }
    for(let i=0;i<4;i++) setTimeout(flyReindeer, i*1200);
    setInterval(flyReindeer, 4500);

    const answers = {};
    document.querySelectorAll('.q').forEach(q=>{
      const key = q.dataset.q;
      q.querySelectorAll('.chip').forEach(btn=>{
        btn.addEventListener('click', ()=>{
          q.querySelectorAll('.chip').forEach(b=>b.setAttribute('aria-pressed','false'));
          btn.setAttribute('aria-pressed','true');
          answers[key] = btn.dataset.val;
        });
      });
    });

    document.getElementById('reset').addEventListener('click', ()=>{
      Object.keys(answers).forEach(k=>delete answers[k]);
      document.querySelectorAll('.chip').forEach(b=>b.setAttribute('aria-pressed','false'));
    });

    function compose(){
      const a1 = answers['1'] ? `• Férias: ${answers['1']}` : null;
      const a2 = answers['2'] ? `• Vibe: ${answers['2']}` : null;
      const a3 = answers['3'] ? `• Como tá: ${answers['3']}` : null;
      const lines = [a1,a2,a3].filter(Boolean).join('\n');

      return [
        'Feliz Natal, Bianca 🎄✨',
        'Passei só pra te desejar um Natal leve e perguntar como você tá.',
      ].join('\n');
    }

    document.getElementById('send').addEventListener('click', ()=>{
      const msg = encodeURIComponent(compose());
      window.open(`https://wa.me/?text=${msg}`, '_blank', 'noopener');
    });

    document.getElementById('openMusic').addEventListener('click', ()=>{
      const url = document.getElementById('musicUrl').value.trim();
      if(!url){ alert('Cole um link primeiro 🙂'); return; }
      try{ const u = new URL(url); window.open(u.toString(), '_blank', 'noopener'); }
      catch(e){ alert('Esse link parece inválido. Cola o link completo (com https://).'); }
    });

    document.getElementById('copyMsg').addEventListener('click', async ()=>{
      const txt = "Feliz Natal, Bianca 🎄✨\nPassei só pra te desejar coisas boas e perguntar como você tá. Se quiser, me conta como estão suas férias 🙂";
      try{ await navigator.clipboard.writeText(txt); alert('Mensagem copiada!'); }
      catch(e){ prompt('Copie a mensagem:', txt); }
    });
  </script>
</body>
</html>
