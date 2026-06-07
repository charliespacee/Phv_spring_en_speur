<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PHV Speur en Spring</title>

<style>
body { margin:0; font-family:Arial; background:#0a0a0a; color:#e5e5e5; }
header { background:#000; padding:20px; text-align:center; border-bottom:3px solid #4b5320; }
nav { display:none; flex-direction:column; background:#111; }
nav a { color:#ccc; padding:12px; text-decoration:none; border-top:1px solid #222; }
nav a:hover { background:#4b5320; color:white; }
.hamburger { display:block; background:#111; color:white; padding:15px; font-size:24px; cursor:pointer; }
.section { padding:20px; max-width:900px; margin:auto; background:#141414; border:1px solid #222; margin-top:20px; }
input,select,textarea { width:100%; padding:10px; margin-top:5px; background:#0f0f0f; border:1px solid #333; color:white; }
button { background:#4b5320; color:white; padding:10px 20px; border:none; cursor:pointer; margin-top:10px; }
button:hover { background:#6b7a2f; }
footer { text-align:center; padding:20px; background:#000; border-top:3px solid #4b5320; margin-top:20px; }
</style>
</head>

<body>

<header>
  <h1>PHV Speur en Spring</h1>
  <p>KNPV Werkhondenvereniging – Doetinchem</p>
</header>

<div class="hamburger" onclick="toggleMenu()">☰ Menu</div>

<nav id="menu">
  <a href="#over">Over ons</a>
  <a href="#training">Training</a>
  <a href="#team">Team</a>
  <a href="#aanmelden">Aanmelden</a>
  <a href="#contact">Contact</a>
</nav>

<div class="section" id="over">
  <h2>Over ons</h2>
  <p>Wij zijn PHV Speur en Spring uit Doetinchem.</p>
</div>

<div class="section" id="training">
  <h2>Wat wij trainen</h2>
  <p>PH1 – PH2 – Objectbewaking</p>
</div>

<div class="section" id="team">
  <h2>Team</h2>
  <p><b>Keano</b> – Hoofd pakwerker</p>
  <p><b>Mats</b> – Pakwerker & trainer</p>
</div>

<div class="section" id="aanmelden">
  <h2>Aanmelden</h2>

  <form onsubmit="sendMail(event)">
    <label>Naam:</label>
    <input id="naam" required>

    <label>Email:</label>
    <input id="email" type="email" required>

    <label>Telefoon:</label>
    <input id="telefoon">

    <label>Ervaring KNPV:</label>
    <select id="knpv">
      <option>Geen</option><option>Beginner</option><option>Gevorderd</option>
      <option>PH1 gelopen</option><option>PH2 gelopen</option>
    </select>

    <label>Ervaring diensthonden:</label>
    <select id="dienst">
      <option>Geen</option><option>Basis</option><option>Veel</option>
    </select>

    <label>Ben je pakwerker?</label>
    <select id="pakwerker">
      <option>Ja</option><option>Nee</option><option>In opleiding</option>
    </select>

    <label>Eigen hond?</label>
    <select id="hond">
      <option>Ja</option><option>Nee</option>
    </select>

    <label>Extra info:</label>
    <textarea id="extra"></textarea>

    <button type="submit">Versturen</button>
  </form>
</div>

<div class="section" id="contact">
  <h2>Contact</h2>
  <p>Email: mats.weijers@icloud.com & mats.weijers@outlook.com</p>
</div>

<footer>© 2026 PHV Speur en Spring</footer>

<script>
function toggleMenu() {
  const menu = document.getElementById("menu");
  menu.style.display = menu.style.display === "flex" ? "none" : "flex";
}

function sendMail(e) {
  e.preventDefault();
  const data = [
    "Naam: " + document.getElementById('naam').value,
    "Email: " + document.getElementById('email').value,
    "Telefoon: " + document.getElementById('telefoon').value,
    "KNPV: " + document.getElementById('knpv').value,
    "Diensthonden: " + document.getElementById('dienst').value,
    "Pakwerker: " + document.getElementById('pakwerker').value,
    "Eigen hond: " + document.getElementById('hond').value,
    "Extra: " + document.getElementById('extra').value
  ].join("%0D%0A");

  window.location.href =
    "mailto:mats.weijers@icloud.com,mats.weijers@outlook.com?subject=Aanmelding&body=" + data;
}
</script>

</body>
</html>


