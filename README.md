# ArkeoLive
ArkeoLive lets you watch live archaeological digs and interact with experts uncovering history. Join the adventure by helping to catalog artifacts and explore discoveries in real time. Dive into archaeology from anywhere and be part of preserving our past!
<!DOCTYPE html>
<html lang="no">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>ArkeoLive - Live arkeologi og katalogisering</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background: #f0f4f8;
    color: #333;
    margin: 0; padding: 0;
  }
  header {
    background: #2c3e50;
    color: white;
    padding: 1rem;
    text-align: center;
  }
  main {
    max-width: 900px;
    margin: 2rem auto;
    padding: 0 1rem;
  }
  h1, h2 {
    color: #34495e;
  }
  section {
    margin-bottom: 2rem;
    background: white;
    padding: 1rem;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  }
  #live-video {
    width: 100%;
    height: 400px;
    background: #000;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 1.5rem;
  }
  form label {
    display: block;
    margin-top: 1rem;
  }
  form input, form textarea {
    width: 100%;
    padding: .5rem;
    margin-top: .3rem;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }
  form button {
    margin-top: 1rem;
    background: #2980b9;
    color: white;
    border: none;
    padding: 0.7rem 1.2rem;
    border-radius: 4px;
    cursor: pointer;
  }
  form button:hover {
    background: #1c5980;
  }
  #finds-list {
    list-style: none;
    padding-left: 0;
  }
  #finds-list li {
    background: #e9f0f7;
    margin-bottom: 0.8rem;
    padding: 0.8rem;
    border-radius: 4px;
  }
</style>
</head>
<body>

<header>
  <h1>ArkeoLive</h1>
  <p>Følg arkeologene grave live og bidra til katalogisering av funn</p>
</header>

<main>

  <section id="live-section">
    <h2>Live utgravning</h2>
    <div id="live-video">Live-stream kommer her</div>
    <p>Se arkeologene i aksjon, still spørsmål og lær mer om historien som graves frem.</p>
  </section>

  <section id="catalog-section">
    <h2>Katalogiser funn</h2>
    <form id="catalog-form">
      <label for="item-name">Navn på funn:</label>
      <input type="text" id="item-name" name="itemName" required />

      <label for="item-description">Beskrivelse:</label>
      <textarea id="item-description" name="itemDescription" rows="3" required></textarea>

      <label for="item-location">Sted funnet (valgfritt):</label>
      <input type="text" id="item-location" name="itemLocation" />

      <button type="submit">Legg til funn</button>
    </form>
  </section>

  <section id="finds-section">
    <h2>Registrerte funn</h2>
    <ul id="finds-list"></ul>
  </section>

</main>

<script>
  const form = document.getElementById('catalog-form');
  const findsList = document.getElementById('finds-list');

  form.addEventListener('submit', (e) => {
    e.preventDefault();

    // Hent verdi fra skjema
    const name = form.itemName.value.trim();
    const description = form.itemDescription.value.trim();
    const location = form.itemLocation.value.trim();

    if(name && description){
      const li = document.createElement('li');
      li.innerHTML = `<strong>${name}</strong><br>${description}` + (location ? `<br><em>Sted: ${location}</em>` : '');
      findsList.appendChild(li);

      // Nullstill skjema
      form.reset();
    }
  });
</script>

</body>
</html>
