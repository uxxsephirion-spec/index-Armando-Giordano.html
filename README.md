<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Armando Giordano</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://www.google.com/recaptcha/api.js" async defer onerror="recaptchaError()"></script>
  <style>
    body {
      font-family: 'Inter', sans-serif;
      background-image: url('https://thumbs.dreamstime.com/b/elegant-white-blue-ammonite-shell-intricate-spiral-patterns-watercolor-details-concept-marine-design-seafood-elements-364634629.jpg');
      background-repeat: no-repeat;
      background-position: center;
      background-size: cover;
      background-attachment: fixed;
      margin: 0;
      padding-top: 60px;
      color: #334155;
    }

    section {
      background-color: rgba(255, 255, 255, 0.9);
      padding: 20px;
      margin: 20px auto;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      max-width: 1000px;
    }

    section h2 {
      margin-top: 0;
      color: #004080;
    }

    p {
      line-height: 1.6;
      color: #333;
    }

    .contact-links {
      text-align: center;
    }
    .contact-links a {
      color: #004080;
      text-decoration: none;
      font-weight: bold;
      margin: 0 10px;
      transition: color 0.3s ease;
    }
    .contact-links a:hover {
      color: #0066cc;
    }

    #output-container, #result-area {
      min-height: 300px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-color: #cbd5e1;
      border-radius: 1rem;
      overflow: hidden;
      box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);
      position: relative;
    }
    #geological-image, #generated-image {
      max-width: 100%;
      max-height: 100%;
      border-radius: 1rem;
      transition: opacity 0.5s ease-in-out;
    }
    .loader {
      border: 4px solid #f3f3f3;
      border-top: 4px solid #3b82f6;
      border-radius: 50%;
      width: 40px;
      height: 40px;
      animation: spin 1s linear infinite;
    }
    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }
    #recaptcha-error {
      color: red;
      font-weight: bold;
      text-align: center;
      margin-top: 10px;
      display: none;
    }
  </style>
</head>
<body>

  <section id="contatti">
    <h2>Contatti</h2>
    <p class="contact-links">
      <a href="https://wa.me/393299824693" target="_blank">📱 WhatsApp</a> |
      <a href="https://www.linkedin.com/in/armando-giordano-192005370" target="_blank">💼 LinkedIn</a> |
      <a href="https://mail.google.com/mail/?view=cm&fs=1&to=uxxsephirion@gmail.com" target="_blank">📧 Gmail</a> |
      <a href="CV.Armando%20Giordano.pdf" download>📄 Scarica il CV</a>
    </p>
    <p id="recaptcha-error">Impossibile connettersi al servizio reCAPTCHA. Controlla la connessione a Internet e ricarica la pagina.</p>
  </section>

  <section id="obiettivo">
    <h2>Obiettivo professionale</h2>
    <p>
      Sono laureato in Scienze Geologiche e possiedo una solida preparazione in geotecnica, GIS e rilevamento geologico, 
      che ho arricchito con competenze trasversali in informatica, sicurezza digitale e programmazione (Python, JavaScript). 
      Di recente ho conseguito il certificato EIPASS, che attesta la mia padronanza degli strumenti digitali. 
      Cerco un'opportunità professionale che valorizzi il mio profilo tecnico-scientifico, in ambiti che integrino l’analisi ambientale, 
      la modellazione del sottosuolo, le georisorse o le applicazioni geospaziali.
    </p>
  </section>

  <section id="illustratore-geologico">
    <h2>Illustratore Geologico</h2>
    <textarea id="description-input" rows="4" class="w-full p-2 border rounded"></textarea>
    <button id="generate-button" class="g-recaptcha bg-blue-600 text-white px-4 py-2 rounded mt-2" data-sitekey="6LcVdpMrAAAAAIKuyfGMjjsjwqzeMX84q2fHMpNc" data-callback='onSubmitGeo' data-action='submit'>Genera Illustrazione</button>
    <div id="output-container">
      <img id="geological-image" class="hidden" alt="Illustrazione geologica">
      <a id="download-link-geologico" class="hidden mt-2 bg-green-600 text-white px-4 py-2 rounded" download="illustrazione_geologica.jpg">Scarica Immagine</a>
    </div>
  </section>

  <section id="fossili">
    <h2>Generatore di Immagini di Fossili</h2>
    <textarea id="fossil-description" rows="4" class="w-full p-2 border rounded"></textarea>
    <button id="fossil-generate-button" class="g-recaptcha bg-blue-600 text-white px-4 py-2 rounded mt-2" data-sitekey="6LcVdpMrAAAAAIKuyfGMjjsjwqzeMX84q2fHMpNc" data-callback='onSubmitFossil' data-action='submit'>Genera Fossile</button>
    <div id="result-area">
      <img id="generated-image" class="hidden" alt="Fossile generato">
      <a id="download-link-fossile" class="hidden mt-2 bg-green-600 text-white px-4 py-2 rounded" download="fossile.png">Scarica Immagine</a>
    </div>
  </section>

  <script>
    function recaptchaError() {
      document.getElementById('recaptcha-error').style.display = 'block';
    }

    function onSubmitGeo() {
      const desc = document.getElementById('description-input').value.trim();
      if(!desc) { alert('Inserisci una descrizione.'); return; }
      // simulazione generazione immagine
      document.getElementById('geological-image').src = 'https://via.placeholder.com/600x400?text=Illustrazione+Geologica';
      document.getElementById('geological-image').classList.remove('hidden');
      document.getElementById('download-link-geologico').href = document.getElementById('geological-image').src;
      document.getElementById('download-link-geologico').classList.remove('hidden');
    }

    function onSubmitFossil() {
      const desc = document.getElementById('fossil-description').value.trim();
      if(!desc) { alert('Inserisci una descrizione di fossile.'); return; }
      document.getElementById('generated-image').src = 'https://via.placeholder.com/600x400?text=Fossile';
      document.getElementById('generated-image').classList.remove('hidden');
      document.getElementById('download-link-fossile').href = document.getElementById('generated-image').src;
      document.getElementById('download-link-fossile').classList.remove('hidden');
    }
  </script>
</body>
</html>
