
<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PHV Speur en Spring</title>

<link href="https://fonts.googleapis.com/css2?family=Oswald:wght@400;600;700&display=swap" rel="stylesheet">

<style>
body {
  margin: 0;
  font-family: 'Oswald', sans-serif;
  background: #0a0a0a;
  color: #e5e5e5;
}

/* HEADER */
header {
  background: #000;
  padding: 25px;
  text-align: center;
  border-bottom: 3px solid #4b5320;
}

header h1 {
  margin: 0;
  letter-spacing: 2px;
}

header p {
  color: #9a9a9a;
}

/* NAV */
nav {
  display: flex;
  flex-direction: column;
  background: #111;
  width: 100%;
  z-index: 1000;
}

nav a {
  color: #9a9a9a;
  text-decoration: none;
  padding: 12px 15px;
  border-top: 1px solid #222;
}

nav a:hover {
  background: #4b5320;
  color: white;
}

/* HAMBURGER MENU */
.hamburger {
  display: none;
  font-size: 28px;
  padding: 15px;
  cursor: pointer;
  color: #e5e5e5;
  background: #111;
  border-bottom: 3px solid #4b5320;
}

/* HERO */
.hero {
  height: 65vh;
  background: url('images/hero.jpg') center/cover no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.hero h2 {
  background: rgba(0,0,0,0.7);
  padding: 20px;
  border: 2px solid #4b5320;
  text-shadow: 1px 1px 2px #000;
}

/* SECTIONS */
.section {
  padding: 40px 20px;
  max-width: 1000px;
  margin: 40px auto;
  background: #141414;
  border: 1px solid #222;
}

h2 {
  border-left: 5px solid #4b5320;
  padding-left: 10px;
  text-transform: uppercase;
  text-shadow: 1px 1px 2px #000;
}

/* TEAM */
.team-member {
  background: #101010;
  border-left: 4px solid #4b5320;
  padding: 10px;
  margin-bottom: 10px;
}

/* FOTOBOEK */
.fotoboek {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 10px;
}

.fotoboek img {
  width: 100%;
  filter: grayscale(40%);
  transition: 0.3s;
}

.fotoboek img:hover {
  filter: grayscale(0%);
  transform: scale(1.05);
}

/* FORMULIER */
input, select, textarea {
  width: 100%;
  padding: 10px;
  background: #0f0f0f;
  border: 1px solid #333;
  color: #e5e5e5;
}

label {
  font-weight: bold;
}

/* BUTTON */
button {
  background: #4b5320;
  border: none;
  padding: 10px 20px;
  color: white;
  cursor: pointer;
  font-weight: bold;
}

button:hover {
  background: #6b7a2f;
}

/* FOOTER */
footer {
  text-align: center;
  padding: 20px;
  background: #000;
  border-top: 3px solid #4b5320;
}

/* MOBIEL */
@media (max-width: 768px) {
  nav {
    display: none;
  }

  .hamburger {
    display: block;
  }
}
</style>
</head>

<body>

<header>
  <h1>PHV Speur en Spring</h1>
  <p>KNPV Werkhondenvereniging – Doetinchem</p>
</header>

<div class="hamburger" onclick="toggleMenu()">☰</div>

<nav>
  <a href="#home">Home</a>
  <a href="#over">Over ons</a>
  <a href="#training">Wat wij trainen</a>
  <a href="#team">Team</a>
  <a href="#zoeken">Wij zoeken</a>
  <a href="#fotoboek">Fotoboek</a>
  <a href="#aanmelden">Aanmelden</a>
  <a href="#contact">Contact</a>
</nav>

<section class="hero" id="home">
  <h2>PHV Speur en Spring – Doetinchem</h2>
</section>

<section class="section" id="over">
  <h2>Over ons</h2>
  <p>
    PHV Speur en Spring is een werkhondenvereniging in Doetinchem. 
    Wij trainen met passie, discipline en respect voor hond en geleider. 
    Onze club richt zich op het ontwikkelen van sterke, stabiele en betrouwbare werkhonden.
  </p>
</section>

<section class="section" id="training">
  <h2>Wat wij trainen</h2>
  <p>
    Wij trainen voornamelijk <strong>PH1</strong>, maar bieden ook begeleiding voor 
    <strong>PH2</strong> en <strong>Objectbewaking</strong>.
  </p>
  <ul>
    <li><strong>PH1</strong> – De basis van het KNPV‑programma.</li>
    <li><strong>PH2</strong> – Voor gevorderde combinaties.</li>
    <li><strong>Objectbewaking</strong> – Gericht op zelfstandigheid en controle.</li>
  </ul>
</section>

<section class="section" id="team">
  <h2>Team</h2>

  <div class="team-member">
    <h3>Keano</h3>
    <p>Hoofd pakwerker – verantwoordelijk voor training en pakwerk.</p>
  </div>

  <div class="team-member">
    <h3>Mats</h3>
    <p>Pakwerker en trainer – ondersteuning en begeleiding.</p>
  </div>
</section>

<section class="section" id="zoeken">
  <h2>Wij zoeken</h2>
  <ul>
    <li>Pakwerkers</li>
    <li>Vrijwilligers</li>
    <li>Materiaal voor trainingen</li>
  </ul>
</section>

<section class="section" id="fotoboek">
  <h2>Fotoboek</h2>
  <div class="fotoboek">
    <img src="images/foto1.jpg">
    <img src="images/foto2.jpg">
    <img src="images/foto3.jpg">
  </div>
</section>

<section class="section" id="aanmelden">
  <h2>Aanmelden</h2>

  <form onsubmit="sendMail(event)">
    <label>Naam:</label>
    <input type="text" id="naam" required><br><br>

    <label>Email:</label>
    <input type="email" id="email" required><br><br>

    <label>Telefoonnummer:</label>
    <input type="text" id="telefoon"><br><br>

    <label>Ervaring met KNPV:</label>
    <select id="knpv">
      <option>Geen ervaring</option>
      <option>Beginner</option>
      <option>Gevorderd</option>
      <option>PH1 gelopen</option>
      <option>PH2 gelopen</option>
    </select><br><br>

    <label>Ervaring met diensthonden:</label>
    <select id="dienst">
      <option>Geen ervaring</option>
      <option>Basiservaring</option>
      <option>Veel ervaring</option>
    </select><br><br>

    <label>Ben je pakwerker?</label>
    <select id="pakwerker">
      <option>Ja</option>
      <option>Nee</option>
      <option>In opleiding</option>
    </select><br><br>

    <label>Eigen hond:</label>
    <select id="hond">
      <option>Ja</option>
      <option>Nee</option>
    </select><br><br>

    <label>Extra informatie:</label>
    <textarea id="extra" rows="4"></textarea><br><br>

    <button type="submit">Versturen</button>
  </form>
</section>

<section class="section" id="contact">
  <h2>Contact</h2>
  <p>Doetinchem, Nederland</p>
  <p>Email: mats.weijers@icloud.com & mats.weijers@outlook.com</p>
</section>

<footer>
  <p>© 2026 PHV Speur en Spring</p>
</footer>

<script>
function toggleMenu() {
  const nav = document.querySelector('nav');
  if (nav.style.display === 'none' || nav.style.display === '') {
    nav.style.display = 'flex';
    nav.style.flexDirection = 'column';
  } else {
    nav.style.display = 'none';
  }
}

function sendMail(event) {
  event.preventDefault();

  const naam = encodeURIComponent(document.getElementById('naam').value);
  const email = encodeURIComponent(document.getElementById('email').value);
  const telefoon = encodeURIComponent(document.getElementById('telefoon').value);
  const knpv = encodeURIComponent(document.getElementById('knpv').value);
  const dienst = encodeURIComponent(document.getElementById('dienst').value);
  const pakwerker = encodeURIComponent(document.getElementById('pakwerker').value);
  const hond = encodeURIComponent(document.getElementById('hond').value);
  const extra = encodeURIComponent(document.getElementById('extra').value);

  const subject = encodeURIComponent("Aanmelding PHV Speur en Spring");

  const body =
    "Naam: " + naam + "%0D%0A" +
    "Email: " + email + "%0D%0A" +
    "Telefoon: " + telefoon + "%0D%0A" +
    "Ervaring KNPV: " + knpv + "%0D%0A" +
    "Ervaring diensthonden: " + dienst + "%0D%0A" +
    "Pakwerker: " + pakwerker + "%0D%0A" +
    "Eigen hond: " + hond + "%0D%0A" +
    "Extra info: " + extra;

  window.location.href =
    "mailto:mats.weijers@icloud.com,mats.weijers@outlook.com?subject=" + subject + "&body=" + body;
}
</script>

</body>
</html>
