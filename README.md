# Finer-Group
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Landing Finer Group</title>
<style>
  :root{
    --brand:#0b54d6;
    --brand-dark:#093f9f;
    --bg:#f6f8fb;
    --text:#1f2937;
    --muted:#6b7280;
    --radius:16px;
  }
  *{box-sizing:border-box}
  body{
    margin:0; font-family:system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,Helvetica,Arial,sans-serif;
    color:var(--text); background:var(--bg);
  }
  header{
    background:var(--brand); padding:18px 16px; text-align:center;
  }
  header img{
    max-height:120px; border-radius:50%;
  }
  .wrap{
    max-width:720px; margin:22px auto; padding:0 16px;
  }
  .card{
    background:#fff; border-radius:var(--radius); padding:20px;
    box-shadow:0 10px 30px rgba(0,0,0,.08);
  }
  .progress{height:8px; background:#e5e7eb; border-radius:999px; overflow:hidden; margin-bottom:18px;}
  .progress > span{display:block; height:100%; width:0%; background:var(--brand); transition:width .3s ease;}
  h1{font-size:22px; margin:0 0 8px}
  p.lead{color:var(--muted); margin:0 0 18px}
  .step{display:none; animation:fade .25s ease}
  .step.active{display:block}
  @keyframes fade{from{opacity:.5; transform:translateY(4px)} to{opacity:1; transform:none}}
  .grid{display:grid; gap:12px}
  @media(min-width:640px){ .grid.cols-2{ grid-template-columns:1fr 1fr } }
  label{font-size:14px; color:#374151; display:block; margin-bottom:6px}
  input, select, textarea{width:100%; padding:12px 14px; border:1px solid #d1d5db; border-radius:10px; font:inherit; outline:none; background:#fff;}
  input:focus, select:focus, textarea:focus{ border-color:var(--brand); box-shadow:0 0 0 3px rgba(11,84,214,.15) }
  .actions{display:flex; gap:10px; margin-top:14px; flex-wrap:wrap}
  .btn{appearance:none; border:0; border-radius:12px; padding:12px 18px; cursor:pointer; font-weight:600}
  .btn.primary{ background:var(--brand); color:#fff }
  .btn.primary:hover{ background:var(--brand-dark) }
  .btn.ghost{ background:#eef2ff; color:#1e40af }
  .muted{ color:var(--muted); font-size:13px; margin-top:8px }
  .review{ background:#f9fafb; border:1px solid #e5e7eb; border-radius:12px; padding:12px; font-size:15px }
  .error{ color:#b91c1c; font-size:13px; margin-top:4px; display:none }
  .invalid input, .invalid select, .invalid textarea{ border-color:#ef4444 }
</style>
</head>
<body>

<header>
  <img src="finer.png" alt="Finer Group Logo">
</header>

<div class="wrap">
  <form id="wizardForm" class="card" action="https://formspree.io/f/xpwjapjy" method="POST" novalidate>
    <!-- seguridad/honeypot -->
    <input type="text" name="_gotcha" style="display:none" tabindex="-1" autocomplete="off" />
    <!-- asunto opcional -->
    <input type="hidden" name="_subject" value="Nuevo registro de landing" />
    <!-- redirección opcional después de enviar -->
    <!-- <input type="hidden" name="_redirect" value="https://tusitio.com/gracias.html" /> -->

    <div class="progress" aria-hidden="true"><span id="bar"></span></div>
    <h1>Personalicemos tu experiencia</h1>
    <p class="lead">Completa los pasos. No tardas más de 1 minuto.</p>

    <!-- PASO nombre -->
    <section class="step active" data-step="1">
        <h1>Por favor, proporcione su nombre para que podamos personalizar su experiencia</h1>
      <div class="grid cols-2">
        <div class="field">
          <label for="nombre">Nombre *</label>
          <input id="nombre" name="nombre" type="text" required />
          <div class="error">Ingresa tu nombre.</div>
        </div>
        <div class="field">
          <label for="apellido">Apellido *</label>
          <input id="apellido" name="apellido" type="text" required />
          <div class="error">Ingresa tu apellido.</div>
        </div>
      </div>
      <div class="actions">
        <button type="button" class="btn primary next">Continuar ➜</button>
      </div>
      <div class="muted">Paso 1 de 6</div>
    </section>

    <!-- PASO email -->
    <section class="step" data-step="2">
        <h1>Ingresa una dirección de correo electrónico valida a continuación</h1>
      <div class="grid cols-2">
        <div class="field">
          <label for="email">Correo electrónico *</label>
          <input id="email" name="email" type="email" required />
          <div class="error">Ingresa un correo válido.</div>
        </div>
      </div>

      <div class="actions">
        <button type="button" class="btn ghost prev">← Atrás</button>
        <button type="button" class="btn primary next">Continuar ➜</button>
      </div>
      <div class="muted">Paso 2 de 6</div>
    </section>

    <!-- PASO postal -->
    <section class="step" data-step="3">
        <h1> Proporcione un código postal valido a continuación </h1>
      <div class="grid cols-2">
        <div class="field">
          <label for="codigo">Codigo (opcional)</label>
          <input id="codigo" name="codigo" type="cod" inputmode="cod" />
        </div>
      </div>
      <div class="actions">
        <button type="button" class="btn ghost prev">← Atrás</button>
        <button type="button" class="btn primary next">Continuar ➜</button>
      </div>
      <div class="muted">Paso 3 de 6</div>
    </section>

    <!-- PASO telefono -->
    <section class="step" data-step="4">
        <h1> Proporcione un número de teléfono móvil válido para acceder directamente a nuestra guía por SMS/MMS</h1>
      <div class="grid cols-2">
        <div class="field">
          <label for="telefono">Teléfono (opcional)</label>
          <input id="telefono" name="telefono" type="tel" inputmode="tel" />
        </div>
      </div>
      <div class="actions">
        <button type="button" class="btn ghost prev">← Atrás</button>
        <button type="button" class="btn primary next">Continuar ➜</button>
      </div>
      <div class="muted">Paso 4 de 6</div>
    </section>

            <!-- PASO PRGUNTAS -->
    <section class="step" data-step="5">
      <div class="field" style="margin-top:8px">
        <label for="pregunta">¿Desea recibir una consulta personalizada?</label>
        <select id="pregunta" name="pregunta">
          <option value="">Selecciona una opción</option>
          <option value="Si">Si</option>
          <option value="No">No</option>
        </select>
      </div>
      <div class="actions">
        <button type="button" class="btn ghost prev">← Atrás</button>
        <button type="button" class="btn primary next">Continuar ➜</button>
      </div>
      <div class="muted">Paso 5 de 6</div>
    </section>

    <!-- PASO 6 (REVISIÓN + MENSAJE) -->
    <section class="step" data-step="6">

      <h2 style="margin:14px 0 8px; font-size:18px">Revisa tus datos</h2>
      <div class="review" id="reviewBox" aria-live="polite"></div>
      <h2 style="margin:14px 0 8px; font-size:18px">Si mañana usted faltara, ¿su familia estaría protegida o tendría que enfrentar sola deudas, impuestos y la corte?</h2>
        <!-- Imagen agregada -->
        <div class="image-box" style="margin:16px 0; text-align:center;">
          <img src="Planificación Inteligente proteja su patrimonio, evite problemas y deje un legado.pdf.png" 
              alt="Planificación Inteligente - Proteja su patrimonio, evite problemas y deje un legado"
              style="max-width:50%; height:auto; border-radius:8px; box-shadow:0 2px 6px rgba(0,0,0,0.2);" />
        </div>

      <div class="actions">
        <button type="button" class="btn ghost prev">← Atrás</button>
        <button type="submit" class="btn primary">Enviar</button>
        
        <!-- Botón extra para la descarga -->
        <button type="button" class="btn secondary" id="downloadFileBtn"> Descargar Nuestra Guia </button>
      </div>
      <div class="muted">Paso 6 de 6</div>
    </section>

    <script>
      // TODO: Implementar aquí la lógica para descargar un archivo desde Google Drive.
      // Por ejemplo, usando la API de Drive o un enlace directo compartido.

      document.getElementById("downloadFileBtn").addEventListener("click", () => {
        // Ejemplo con un enlace directo (debes reemplazar con tu URL de Drive compartido)
        const driveFileUrl = "https://drive.google.com/file/d/1TcbF1_8WO2s5gX475eoMgb4Ku70j_pAC/view?usp=sharing";
        window.open(driveFileUrl, "_blank");
      });
    </script>



  </form>

  <p class="muted" style="text-align:center">Tus datos se envían de forma segura a través de Formspree.</p>
</div>

<script>
(function(){
  const form = document.getElementById('wizardForm');
  const steps = Array.from(form.querySelectorAll('.step'));
  const nextBtns = form.querySelectorAll('.next');
  const prevBtns = form.querySelectorAll('.prev');
  const bar = document.getElementById('bar');
  const reviewBox = document.getElementById('reviewBox');

  let current = 0; // índice de paso

  function updateProgress(){
    const pct = ((current+1)/steps.length)*100;
    bar.style.width = pct + '%';
  }

  function showStep(i){
    steps.forEach((s, idx)=> s.classList.toggle('active', idx===i));
    current = i;
    updateProgress();
    if (steps[i].dataset.step === '6') fillReview();
  }

  function validateStep(i){
    const section = steps[i];
    let ok = true;
    section.querySelectorAll('.field').forEach(f=>{
      f.classList.remove('invalid');
      const input = f.querySelector('input, select, textarea');
      const err = f.querySelector('.error');
      if(!input) return;
      if (input.hasAttribute('required') && !input.value.trim()){
        ok = false; f.classList.add('invalid'); if (err) err.style.display='block';
      }else{
        if (err) err.style.display='none';
      }
      // validación simple de email
      if(ok && input.type==='email' && input.value){
        const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        if(!re.test(input.value)){ ok=false; f.classList.add('invalid'); if (err) err.style.display='block'; }
      }
    });
    return ok;
  }

  function fillReview(){
    const datos = new FormData(form);
    // lista legible para el usuario
    const fields = ['nombre','apellido','email','telefono','codigo','pregunta','mensaje',];
    const labels = {
      nombre:'Nombre', apellido:'Apellido', email:'Correo', codigo:'Codigo', telefono:'Teléfono', pregunta:'Pregunta', mensaje:'Mensaje'
    };
    reviewBox.innerHTML = fields.map(k=>{
      const v = (datos.get(k) || '').toString().trim();
      if (!v) return '';
      return `<div><strong>${labels[k]}:</strong> ${escapeHtml(v)}</div>`;
    }).join('') || '<em>No agregaste información adicional.</em>';
  }

  function escapeHtml(str){
    return str.replace(/[&<>"']/g, m=>({ '&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#039;' }[m]));
  }

  nextBtns.forEach(btn=>{
    btn.addEventListener('click', ()=>{
      if(!validateStep(current)) return;
      showStep(Math.min(current+1, steps.length-1));
    });
  });

  prevBtns.forEach(btn=>{
    btn.addEventListener('click', ()=> showStep(Math.max(current-1,0)));
  });

  // Accesibilidad: permitir Enter para avanzar, salvo en textareas
  form.addEventListener('keydown', (e)=>{
    if(e.key === 'Enter'){
      const el = e.target;
      const tag = el.tagName.toLowerCase();
      if(tag !== 'textarea'){
        e.preventDefault();
        const isLast = current === steps.length-1;
        if(isLast) form.requestSubmit(); else document.querySelector('.step.active .next')?.click();
      }
    }
  });

  // feedback opcional después de enviar (sin redirección)
  form.addEventListener('submit', function(){
    // puedes mostrar un loader si quieres
  });

  // init
  updateProgress();
})();
</script>
</body>

</html>
