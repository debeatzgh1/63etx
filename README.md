

# 🚀 Multi-Tab Launcher Generator

**Creator OS Script Factory**

A powerful **no-code / low-code generator** that lets creators build **multi-tab floating launchers** for any website, Blogger, or GitHub Pages — all from a single HTML file.

Designed and curated by **Debeatzgh**.

---

## ✨ What This Project Does

This tool allows you to:

* Generate **1 to 10 floating multi-tab launchers**
* Add **unlimited links per launcher**
* Choose between **Red, Yellow, or Green** themes
* Preview launchers live
* Copy a **ready-to-use HTML script**
* Embed the launcher on **any website**
* Build your own **Creator Operating System**

No frameworks. No backend. No dependencies.

---

## 🔥 Key Features

* 🧩 **Launcher Generator (1–10)**
* 🎨 **Color Themes** (Red / Yellow / Green)
* 🧠 **Smart UI for creators**
* 📋 **One-click script copy**
* 👁 **Live preview**
* 🧱 **Reusable embed script**
* ⚡ Works on **Blogger, WordPress, GitHub Pages**
* 📱 Mobile-friendly design

---

## 🖥 Demo Use Cases

* Personal portfolio launcher
* Blogger floating menu
* AI tools hub
* Digital product library
* Startup resource dashboard
* Creator OS web app

---

## 📦 How to Use

### 1️⃣ Download or Clone

```bash
git clone https://github.com/yourusername/multi-tab-launcher-generator.git
```

Or simply download the HTML file.

---

### 2️⃣ Open the File

Open `index.html` in any browser.

---

### 3️⃣ Generate Launchers

1. Choose how many launchers you want (1–10)
2. For each launcher:

   * Set button caption
   * Choose color theme
   * Paste your links (one per line)
3. Watch the **live preview**

---

### 4️⃣ Copy the Script

Click **📋 Copy Script**
Paste it into:

* Blogger → Layout → Gadget → HTML/JS
* WordPress (custom HTML block)
* Any website `<body>` section

---

## 🧪 Example Output

```html
<div class="cos-btn">
  <button onclick="openLauncher(1)">☰</button>
</div>
<div id="cos-view">
  <iframe src=""></iframe>
</div>
```

Your generated script is **self-contained** and ready to deploy.

---

## 🎨 Color Themes

| Theme     | Use Case                       |
| --------- | ------------------------------ |
| 🔴 Red    | Sales, alerts, promotions      |
| 🟡 Yellow | Tools, menus, navigation       |
| 🟢 Green  | Productivity, learning, growth |

---

## 🧠 Best Practices

* Use **1–3 launchers** for blogs
* Use **4–6 launchers** for creator portfolios
* Use **7–10 launchers** for full Creator OS systems
* Group related links per launcher
* Keep button captions short (icons work best)

---

## 🔧 Customization

You can easily:

* Change button size
* Move launcher position
* Add animations
* Add fullscreen / mini-player modes
* Extend with localStorage or favorites

All logic is written in **vanilla JavaScript**.

---

## 📁 Project Structure

```
multi-tab-launcher-generator/
│
├── index.html     # Main generator (all-in-one)
├── README.md      # Documentation
└── assets/        # (optional icons / logos)
```

---

## 💡 Roadmap (Optional Enhancements)

* Drag & drop link ordering
* Save / load presets
* User accounts (SaaS version)
* Pro templates
* White-label creator dashboards

---

## 📜 License

MIT License – Free to use, modify, and distribute.

Attribution appreciated but not required.

---

## 🙌 Credits

Built with ❤️ by **Debeatzgh**
Helping creators **build, launch, and monetize** digital systems.

🌐 GitHub Pages Friendly
🧠 Creator-first UX
🚀 Ready for production

---

## ⭐ Support the Project

If you find this useful:

* Star ⭐ the repo
* Share with other creators
* Build something amazing with it

<html lang="en">
<head>
<meta charset="UTF-8">
<title>Multi-Tab Launcher Generator – Creator OS</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
:root{
  --red:#dc2626;
  --yellow:#facc15;
  --green:#16a34a;
  --dark:#020617;
}
body{
  margin:0;
  font-family:system-ui,Arial,sans-serif;
  background:#0f172a;
  color:#e5e7eb;
}
.container{
  max-width:1200px;
  margin:auto;
  padding:20px;
}
h1,h2{margin:8px 0}
.card{
  background:#020617;
  border-radius:18px;
  padding:16px;
  margin-bottom:16px;
  box-shadow:0 20px 40px rgba(0,0,0,.4);
}
.selector button{
  margin:6px;
  padding:10px 16px;
  border:none;
  border-radius:999px;
  background:#2563eb;
  color:#fff;
  cursor:pointer;
}
.launcher{
  border:1px dashed #334155;
  border-radius:14px;
  padding:12px;
  margin-top:12px;
}
label{
  font-size:13px;
  opacity:.8;
  display:block;
  margin-top:10px;
}
input,select,textarea{
  width:100%;
  padding:9px;
  margin-top:6px;
  border-radius:10px;
  border:none;
  background:#020617;
  color:#fff;
  outline:1px solid #1e293b;
}
textarea{min-height:70px}
.copy{
  background:#16a34a;
  border:none;
  padding:10px 16px;
  border-radius:999px;
  color:#fff;
  cursor:pointer;
}
.output textarea{
  height:260px;
  font-family:monospace;
  font-size:12px;
}
.preview{
  min-height:120px;
  display:flex;
  gap:12px;
  flex-wrap:wrap;
}
.preview button{
  width:48px;height:48px;
  border-radius:50%;
  border:none;
  font-size:18px;
}
.footer{
  text-align:center;
  opacity:.6;
  font-size:13px;
}
</style>
</head>

<body>
<div class="container">

<h1>⚙️ Multi-Tab Launcher Generator</h1>
<p>Select how many launchers you want. Each launcher can hold unlimited links.</p>

<!-- SELECTOR -->
<div class="card selector">
<h2>1️⃣ Choose Number of Launchers</h2>
<div id="launcherButtons"></div>
</div>

<!-- BUILDER -->
<div class="card">
<h2>2️⃣ Configure Launchers</h2>
<div id="builder"></div>
</div>

<!-- PREVIEW -->
<div class="card">
<h2>👁 Live Preview</h2>
<div class="preview" id="preview"></div>
</div>

<!-- OUTPUT -->
<div class="card output">
<h2>📄 Generated Script</h2>
<textarea id="output"></textarea><br><br>
<button class="copy" onclick="copyCode()">📋 Copy Script</button>
</div>

<div class="footer">
Creator OS Launcher Factory • Designed by Debeatzgh
</div>

</div>

<script>
const launcherButtons=document.getElementById("launcherButtons");
const builder=document.getElementById("builder");
const preview=document.getElementById("preview");
const output=document.getElementById("output");

const colors={
 red:"var(--red)",
 yellow:"var(--yellow)",
 green:"var(--green)"
};

// Create selector buttons 1–10
for(let i=1;i<=10;i++){
  const b=document.createElement("button");
  b.textContent=i+" Launcher"+(i>1?"s":"");
  b.onclick=()=>buildLaunchers(i);
  launcherButtons.appendChild(b);
}

function buildLaunchers(count){
  builder.innerHTML="";
  for(let i=1;i<=count;i++){
    const div=document.createElement("div");
    div.className="launcher";
    div.innerHTML=`
      <h3>Launcher ${i}</h3>
      <label>Button Caption</label>
      <input id="cap${i}" value="☰">
      <label>Launcher Title</label>
      <input id="title${i}" value="Launcher ${i}">
      <label>Theme Color</label>
      <select id="color${i}">
        <option value="red">Red</option>
        <option value="yellow">Yellow</option>
        <option value="green">Green</option>
      </select>
      <label>Links (one per line)</label>
      <textarea id="links${i}">https://example.com</textarea>
    `;
    builder.appendChild(div);
  }
  generate(count);
}

function generate(count){
  let html="",buttons="";
  preview.innerHTML="";

  for(let i=1;i<=count;i++){
    const cap=document.getElementById(`cap${i}`).value;
    const col=document.getElementById(`color${i}`).value;
    buttons+=`
      <button style="background:${colors[col]}" onclick="openLauncher(${i})">${cap}</button>
    `;
    preview.innerHTML+=`
      <button style="background:${colors[col]}">${cap}</button>
    `;
  }

  html+=`
<style>
.cos-btn{position:fixed;right:16px;top:50%;transform:translateY(-50%);
display:flex;flex-direction:column;gap:10px;z-index:99999}
.cos-btn button{width:48px;height:48px;border-radius:50%;border:none;font-size:18px}
#cos-view{position:fixed;inset:0;background:#000c;display:none;z-index:99998}
#cos-view iframe{width:100%;height:100%;border:none}
</style>

<div class="cos-btn">${buttons}</div>
<div id="cos-view"><iframe id="cos-frame"></iframe></div>

<script>
function openLauncher(n){
 document.getElementById("cos-view").style.display="block";
 document.getElementById("cos-frame").src=links[n][0];
}
document.getElementById("cos-view").onclick=()=>{cos-view.style.display="none"};
const links={};
`;

  for(let i=1;i<=count;i++){
    const links=document.getElementById(`links${i}`).value.split("\n").filter(Boolean);
    html+=`links[${i}]=${JSON.stringify(links)};\n`;
  }

  html+="<\/script>";
  output.value=html;
}

function copyCode(){
  output.select();
  document.execCommand("copy");
  alert("Launcher script copied!");
}
</script>

</body>
</html>
