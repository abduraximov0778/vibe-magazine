# vibe-magazine

<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta name="description" content="VIBE Magazine — zamonaviy yangiliklar, moda, texnologiya va hayot tarzi jurnali.">
<meta name="theme-color" content="#101010">

<title>VIBE MAGAZINE | Zamonaviy jurnal</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  background: #f5f5f5;
  color: #171717;
  transition: .3s;
}

body.dark {
  background: #111;
  color: white;
}

header {
  padding: 22px 7%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 18px;
  background: inherit;
}

.logo {
  font-size: 30px;
  font-weight: 900;
  letter-spacing: 3px;
}

.logo span {
  color: #ff416c;
}

nav {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

nav a {
  text-decoration: none;
  color: inherit;
  font-size: 14px;
}

nav a:hover {
  color: #ff416c;
}

button {
  cursor: pointer;
  border: none;
  padding: 12px 18px;
  border-radius: 7px;
  background: #ff416c;
  color: white;
}

.hero {
  margin: 20px 7%;
  min-height: 430px;
  border-radius: 20px;
  padding: 50px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  color: white;
  background:
    linear-gradient(90deg,#000c,#0003),
    url("https://images.unsplash.com/photo-1497366754035-f200968a6e72");
  background-position: center;
  background-size: cover;
}

.hero small {
  color: #ff9ab0;
  letter-spacing: 4px;
}

.hero h1 {
  font-size: clamp(38px,6vw,70px);
  max-width: 650px;
  margin: 20px 0;
}

.hero p {
  font-size: 17px;
  line-height: 1.6;
}

.container {
  padding: 45px 7%;
}

.section-title {
  font-size: 32px;
  margin-bottom: 25px;
}

.search {
  width: 100%;
  padding: 15px;
  border: 1px solid #ddd;
  border-radius: 8px;
  margin-bottom: 22px;
  font-size: 15px;
}

.categories {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  margin-bottom: 25px;
}

.categories button {
  background: #222;
}

.categories button.active {
  background: #ff416c;
}

.grid {
  display: grid;
  grid-template-columns: repeat(
    auto-fit,minmax(min(100%,260px),1fr)
  );
  gap: 25px;
}

.card {
  background: white;
  color: #171717;
  border-radius: 14px;
  overflow: hidden;
  transition: .3s;
  box-shadow: 0 5px 20px #0000000c;
}

.dark .card {
  background: #242424;
  color: white;
}

.card:hover {
  transform: translateY(-7px);
}

.card img {
  width: 100%;
  height: 210px;
  object-fit: cover;
}

.card-content {
  padding: 22px;
}

.card small {
  color: #ff416c;
  font-weight: bold;
}

.card h3 {
  font-size: 22px;
  margin: 12px 0;
}

.card p {
  color: #888;
  line-height: 1.6;
}

.card button {
  margin-top: 18px;
}

.newsletter {
  background: #171717;
  color: white;
  padding: 65px 20px;
  text-align: center;
}

.newsletter h2 {
  font-size: 32px;
  margin-bottom: 15px;
}

.newsletter input {
  padding: 14px;
  border-radius: 7px;
  border: none;
  margin: 15px 5px;
  width: min(260px,90%);
}

footer {
  padding: 30px;
  text-align: center;
  background: #0c0c0c;
  color: white;
}

.article-page {
  padding: 40px 8%;
  min-height: 60vh;
}

.article-page h1 {
  font-size: 38px;
  margin: 25px 0;
}

.article-page p {
  font-size: 19px;
  line-height: 1.9;
  margin-bottom: 20px;
}

@media(max-width:600px) {
  header {
    justify-content: center;
  }

  nav {
    justify-content: center;
  }

  .hero {
    padding: 30px;
    min-height: 350px;
  }

  .container {
    padding: 35px 5%;
  }
}
</style>
</head>

<body>

<header>
  <div class="logo">VIBE<span>.</span></div>

  <nav>
    <a href="#" onclick="home()">Bosh sahifa</a>
    <a href="#articles">Maqolalar</a>
    <a href="#categories">Kategoriyalar</a>
    <a href="#about">Biz haqimizda</a>
  </nav>

  <button onclick="toggleTheme()">☾</button>
</header>

<main id="main">

<section class="hero">
  <small>WELCOME TO VIBE MAGAZINE</small>
  <h1>G‘oyalar. Hayot. Ilhom.</h1>
  <p>Zamonaviy dunyoning eng qiziqarli hikoyalari bir joyda.</p>
</section>

<section class="container" id="articles">

  <h2 class="section-title">So‘nggi maqolalar</h2>

  <input
    class="search"
    id="search"
    placeholder="Maqolalarni qidirish..."
  >

  <div class="categories" id="categories">
    <button class="active" onclick="filter('all',this)">Barchasi</button>
    <button onclick="filter('Texnologiya',this)">Texnologiya</button>
    <button onclick="filter('Moda',this)">Moda</button>
    <button onclick="filter('Hayot',this)">Hayot</button>
    <button onclick="filter('Sport',this)">Sport</button>
  </div>

  <div class="grid" id="grid"></div>

</section>

<section class="newsletter" id="about">
  <h2>VIBE Magazine</h2>
  <p>Biz bilan dunyodan xabardor bo‘ling!</p>
  <p style="margin-top:15px">Zamonaviy fikrlar. Yangi g‘oyalar. Yangi imkoniyatlar.</p>
</section>

</main>

<footer>
  © 2026 VIBE MAGAZINE. Barcha huquqlar himoyalangan.
</footer>

<script>

const articles = [
 {
  title:"Kelajak texnologiyalari",
  category:"Texnologiya",
  image:"https://images.unsplash.com/photo-1519389950473-47ba0277781c",
  description:"Sun'iy intellekt va yangi texnologiyalar dunyoni qanday o‘zgartirmoqda?",
  content:"Texnologiya kundalik hayotimizning muhim qismiga aylanmoqda. Sun'iy intellekt, robototexnika va yangi innovatsiyalar kelajak uchun katta imkoniyatlar yaratmoqda."
 },
 {
  title:"2026-yil zamonaviy modasi",
  category:"Moda",
  image:"https://images.unsplash.com/photo-1483985988355-763728e1935b",
  description:"Yangi kiyinish uslublari va zamonaviy obrazlar.",
  content:"Moda insonning o‘ziga xosligini ko‘rsatadi. Zamonaviy uslubda qulaylik, ranglar va individuallik muhim o‘rin egallaydi."
 },
 {
  title:"Orzular sari olg‘a",
  category:"Hayot",
  image:"https://images.unsplash.com/photo-1497366754035-f200968a6e72",
  description:"Maqsad va muvaffaqiyatga erishish haqida.",
  content:"Muvaffaqiyat kichik qadamlardan boshlanadi. Har kuni yangi bilim olish va o‘z ustingda ishlash seni maqsadingga yaqinlashtiradi."
 },
 {
  title:"Sport va sog‘lom hayot",
  category:"Sport",
  image:"https://images.unsplash.com/photo-1461896836934-ffe607ba8211",
  description:"Faol hayot va sportning foydalari.",
  content:"Sport insonning jismoniy faolligi va kundalik energiyasini oshirishga yordam beradi. Harakatni kundalik odatga aylantirish muhim."
 }
];

const grid = document.getElementById("grid");

function render(list) {
 grid.innerHTML = "";

 list.forEach(article => {
  const card = document.createElement("article");
  card.className = "card";

  const img = document.createElement("img");
  img.src = article.image;
  img.alt = article.title;
  img.loading = "lazy";

  const content = document.createElement("div");
  content.className = "card-content";

  const category = document.createElement("small");
  category.textContent = article.category.toUpperCase();

  const title = document.createElement("h3");
  title.textContent = article.title;

  const description = document.createElement("p");
  description.textContent = article.description;

  const button = document.createElement("button");
  button.textContent = "Batafsil →";
  button.addEventListener("click", () => readArticle(article));

  content.append(category,title,description,button);
  card.append(img,content);
  grid.appendChild(card);
 });
}

function filter(category,btn) {
 document.querySelectorAll(".categories button")
 .forEach(b => b.classList.remove("active"));

 btn.classList.add("active");

 render(
  category === "all"
  ? articles
  : articles.filter(a => a.category === category)
 );
}

document.getElementById("search").addEventListener("input",function(){
 const value = this.value.toLowerCase();

 render(articles.filter(a =>
  (a.title + " " + a.category + " " + a.description)
  .toLowerCase().includes(value)
 ));
});

function readArticle(article) {
 const main = document.getElementById("main");
 main.innerHTML = "";

 const page = document.createElement("section");
 page.className = "article-page";

 const back = document.createElement("button");
 back.textContent = "← Orqaga";
 back.onclick = home;

 const title = document.createElement("h1");
 title.textContent = article.title;

 const img = document.createElement("img");
 img.src = article.image;
 img.alt = article.title;
 img.style.width = "100%";
 img.style.maxHeight = "400px";
 img.style.objectFit = "cover";
 img.style.borderRadius = "15px";

 const paragraph = document.createElement("p");
 paragraph.textContent = article.content;

 page.append(back,title,img,paragraph);
 main.appendChild(page);

 window.scrollTo(0,0);
}

function home() {
 location.reload();
}

function toggleTheme() {
 document.body.classList.toggle("dark");
}

render(articles);

</script>

</body>
</html>
