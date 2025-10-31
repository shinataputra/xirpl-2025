# 🚀 Modul: Membangun Portofolio Pribadi dengan React, GitHub, dan Vercel

Modul ini membimbing kamu membuat website portofolio profesional menggunakan **React**, **GitHub**, dan **Vercel** — dari nol sampai online.

---

## 🎯 Tujuan Akhir
Website portofolio online dengan domain:
```
https://namamu.vercel.app
```

---

## 🧱 1. Persiapan Awal

### 🔧 Install yang Dibutuhkan
Pastikan sudah terpasang:
- [Node.js](https://nodejs.org) (versi LTS)
- [Git](https://git-scm.com)
- Text editor seperti VS Code

Cek versi:
```bash
node -v
git --version
```

---

## ⚙️ 2. Membuat Project React

### A. Buat Project Baru
```bash
npx create-react-app my-portfolio
```

Masuk ke folder project:
```bash
cd my-portfolio
```

Jalankan:
```bash
npm start
```

> Browser akan terbuka di `http://localhost:3000`

---

## 🎨 3. Menambahkan CSS Manual

Edit file `src/index.css`:
```css
body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  background-color: #f5f5f5;
  color: #333;
}

nav {
  background: #000;
  color: white;
  padding: 16px 0;
}

nav h1 {
  font-size: 1.25rem;
}

nav ul {
  display: flex;
  list-style: none;
  gap: 24px;
}

nav a {
  color: white;
  text-decoration: none;
}

nav a:hover {
  color: gold;
}

section {
  padding: 80px 20px;
}

button, a.btn {
  background: black;
  color: gold;
  padding: 10px 20px;
  border-radius: 25px;
  text-decoration: none;
  transition: 0.3s;
}

button:hover, a.btn:hover {
  background: gold;
  color: black;
}

footer {
  background: #000;
  color: white;
  padding: 20px;
  text-align: center;
}
```

---

## 🧩 4. Struktur Komponen

Buat folder:
```
src/components/
```

Tambahkan file berikut:

### 🧭 Navbar.js
```jsx
export default function Navbar() {
  return (
    <nav>
      <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", maxWidth: "900px", margin: "0 auto", padding: "0 20px" }}>
        <h1>Bro’s Portfolio</h1>
        <ul>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
    </nav>
  );
}
```

### 💫 Hero.js
```jsx
export default function Hero() {
  return (
    <section style={{ textAlign: "center", background: "#eee" }}>
      <h1 style={{ fontSize: "3rem", marginBottom: "10px" }}>Halo, Saya Bro 👋</h1>
      <p>Guru • Web Developer • Pembelajar Seumur Hidup</p>
      <a href="#projects" className="btn" style={{ display: "inline-block", marginTop: "20px" }}>
        Lihat Proyek Saya
      </a>
    </section>
  );
}
```

### 💼 Projects.js
```jsx
export default function Projects() {
  const data = [
    { name: "GUMEL APP", desc: "Aplikasi manajemen nilai guru", link: "#" },
    { name: "AI Generate Text", desc: "Aplikasi AI berbasis PHP MVC", link: "#" },
    { name: "Kurikulum App", desc: "Sistem manajemen kurikulum sekolah", link: "#" },
  ];

  return (
    <section id="projects" style={{ background: "#fff" }}>
      <div style={{ maxWidth: "900px", margin: "0 auto", textAlign: "center" }}>
        <h2 style={{ fontSize: "2rem", marginBottom: "40px" }}>🧱 Proyek Saya</h2>
        <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit, minmax(250px, 1fr))", gap: "20px" }}>
          {data.map((p, i) => (
            <div key={i} style={{ border: "1px solid #ddd", borderRadius: "12px", padding: "20px", background: "#fafafa" }}>
              <h3>{p.name}</h3>
              <p>{p.desc}</p>
              <a href={p.link} style={{ color: "gold" }}>Lihat Detail →</a>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
}
```

### 📬 Contact.js
```jsx
export default function Contact() {
  return (
    <section id="contact" style={{ background: "#eee", textAlign: "center" }}>
      <h2 style={{ fontSize: "2rem" }}>Hubungi Saya</h2>
      <p style={{ marginBottom: "20px" }}>Tertarik bekerja sama atau diskusi santai?</p>
      <a href="mailto:emailkamu@gmail.com" className="btn">Kirim Email</a>
    </section>
  );
}
```

### ⚓ Footer.js
```jsx
export default function Footer() {
  return (
    <footer>
      <p>© {new Date().getFullYear()} Bro’s Portfolio — Dibangun dengan ❤️ + React</p>
    </footer>
  );
}
```

---

## 🧩 5. Gabungkan di `App.js`
```jsx
import Navbar from "./components/Navbar";
import Hero from "./components/Hero";
import Projects from "./components/Projects";
import Contact from "./components/Contact";
import Footer from "./components/Footer";

function App() {
  return (
    <>
      <Navbar />
      <Hero />
      <Projects />
      <Contact />
      <Footer />
    </>
  );
}

export default App;
```

---

## 💾 6. Simpan ke GitHub
```bash
git init
git add .
git commit -m "first commit - portfolio"
git branch -M main
git remote add origin https://github.com/username/my-portfolio.git
git push -u origin main
```

---

## ☁️ 7. Deploy ke Vercel

1. Login ke [Vercel](https://vercel.com)
2. Klik **Add New → Project**
3. Pilih repo `my-portfolio`
4. Klik **Deploy**

🎉 Selesai!  
Portofoliomu online di:
```
https://my-portfolio.vercel.app
```

---

## ✨ 8. Bonus Tambahan
- Ubah title & favicon di `/public/index.html`
- Tambahkan foto profil & link GitHub, LinkedIn
- Bisa tambahkan animasi ringan pakai CSS
- Custom domain bisa diatur di **Vercel → Settings → Domains**

---

## 📂 Struktur Akhir Folder
```
my-portfolio/
├── public/
├── src/
│   ├── components/
│   │   ├── Navbar.js
│   │   ├── Hero.js
│   │   ├── Projects.js
│   │   ├── Contact.js
│   │   └── Footer.js
│   ├── App.js
│   ├── index.css
│   └── index.js
├── package.json
└── README.md
```

---

## 🏁 Hasil Akhir
Website portofolio modern, cepat, dan gratis, siap dibagikan ke calon klien, HRD, atau murid 😎
