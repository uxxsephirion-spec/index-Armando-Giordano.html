<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Armando Giordano</title>
  <style>
    body {
      font-family: sans-serif;
      background-image: url('https://thumbs.dreamstime.com/b/elegant-white-blue-ammonite-shell-intricate-spiral-patterns-watercolor-details-concept-marine-design-seafood-elements-364634629.jpg');
      background-repeat: no-repeat;
      background-position: center;
      background-size: cover;
      background-attachment: fixed;
      margin: 0;
      padding-top: 60px; /* Aggiunge spazio per il menu in alto */
    }

    /* Stili per il menu di navigazione */
    .navbar {
      width: 100%;
      background-color: #004080;
      overflow: hidden;
      position: fixed; /* Rende il menu fisso in alto */
      top: 0;
      left: 0;
      display: flex;
      justify-content: center;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
      z-index: 1000;
      padding: 10px 0;
    }

    .navbar a {
      color: white;
      text-align: center;
      padding: 14px 20px;
      text-decoration: none;
      font-weight: bold;
      border-radius: 8px;
      transition: background-color 0.3s ease;
      margin: 0 5px;
    }

    .navbar a:hover {
      background-color: #0066cc;
    }

    /* Stili esistenti */
    h1, h2 {
      text-align: center;
      color: #004080;
    }

    section {
      background-color: rgba(255, 255, 255, 0.85);
      padding: 20px;
      margin: 20px auto;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      max-width: 800px;
    }

    section h2 {
        margin-top: 0;
    }

    p {
      line-height: 1.6;
      color: #333;
    }

    .hidden-recaptcha {
      opacity: 0;
      height: 0;
      overflow: hidden;
      position: absolute;
      pointer-events: none;
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

    .contact-links {
        text-align: center;
    }

  </style>
</head>
<body>

  <!-- Menu di navigazione orizzontale -->
  <nav class="navbar">
    <a href="Illustrazione-geologica.html">🌐 Illustrazione Geologica</a>
    <a href="Generatore-di-Fossili.html">🖼️ Generatore di Immagini di Fossili</a>
  </nav>

  <section>
    <h2>Obiettivo professionale</h2>
    <p>
      Sono laureato in Scienze Geologiche e possiedo una solida preparazione in geotecnica, GIS e rilevamento geologico, 
      che ho arricchito con competenze trasversali in informatica, sicurezza digitale e programmazione (Python, JavaScript). 
      Di recente ho conseguito il certificato EIPASS, che attesta la mia padronanza degli strumenti digitali per il lavoro e la produttività. 
      Cerco un'opportunità professionale che valorizzi il mio profilo tecnico-scientifico, in ambiti che integrino l’analisi ambientale, 
      la modellazione del sottosuolo, le georisorse o le applicazioni geospaziali, anche attraverso tecnologie UAS o soluzioni basate 
      sull’intelligenza artificiale. Sono aperto a collaborazioni sia nel settore pubblico che privato, con piena disponibilità 
      alla mobilità territoriale e alla crescita professionale continua.
    </p>
  </section>

  <section>
    <h2>Contatti</h2>
    <p class="contact-links">
      <a href="https://wa.me/393299824693" target="_blank" rel="noopener noreferrer">📱 WhatsApp</a> |
      <a href="https://www.linkedin.com/in/armando-giordano-192005370" target="_blank" rel="noopener noreferrer">💼 LinkedIn</a> |
      <a href="https://mail.google.com/mail/?view=cm&fs=1&to=uxxsephirion@gmail.com" target="_blank" rel="noopener noreferrer">📧 Gmail</a> |
      <a href="CV.Armando%20Giordano.pdf" download>📄 Scarica il CV</a>
    </p>
 

  <!-- Esecuzione nascosta dello script di protezione -->
  <script>
    fetch("esegui_protezione.php")
      .then(() => console.log("Script di protezione avviato in background."));
  </script>

  <!-- reCAPTCHA nascosto -->
  <div class="hidden-recaptcha">
    <script src="https://www.google.com/recaptcha/api.js" async defer></script>
    <form action="submit_form.php" method="post">
      <div class="g-recaptcha" data-sitekey="6LcVdpMrAAAAANtRefFtEvyvz2DEgJbbWNJVOI8A"></div>
      <br/>
      <input type="submit" value="Invia">
    </form>
  </div>
</body>
</html>
