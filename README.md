## **README.md**

```markdown
# Grok Star Effect

A simple, beautiful HTML5 canvas animation of a rotating starfield with flickering stars and occasional shooting stars.  
Fully customizable — change star sizes, glow intensity, number of stars, and shooting star frequency with just a few variable tweaks.

![Starfield Preview](preview.gif) <!-- optional: add a gif/screenshot -->

---

## 🚀 Demo
Open `index.html` in any modern browser — no build tools or dependencies needed.

---

## 📂 Project Structure
```

index.html   → main HTML file
style.css    → styling for full-screen canvas
script.js    → animation logic and customization variables

````

---

## ⚙️ Customization

All key settings are inside **`script.js`**.

### 1️⃣ Number of stars
```javascript
const numStars = 360; // increase for denser starfield, decrease for lighter
````

---

### 2️⃣ Star size

Inside `initStars()`:

```javascript
size: Math.random() * 1.6 + 0.6, // min size = 0.6px, max = 2.2px
```

**Increase size range:**

```javascript
size: Math.random() * 3 + 1; // 1px to 4px
```

**All stars same size:**

```javascript
size: 2; // constant 2px
```

---

### 3️⃣ Glow / flicker intensity

Glow is simulated via opacity flicker in `animate()`:

```javascript
const flicker = 0.4 + Math.abs(Math.sin(Date.now() * 0.0015 + i)) * 0.5;
```

* Increase `0.5` → more flicker range (brighter glow peaks)
* Decrease `0.4` → dimmer base brightness

---

### 4️⃣ Shooting star frequency

Controlled by:

```javascript
if (shootingStars.length === 0 && Math.random() < 0.01) {
```

* `0.01` = 1% chance per frame (\~rare)
* Increase to `0.05` for more frequent shooting stars
* Decrease to `0.005` for very rare ones

---

### 5️⃣ Shooting star speed

Inside `spawnShootingStar()`:

```javascript
vx: 3 + Math.random() * 2, // horizontal speed
vy: 1 + Math.random() * 1.5, // vertical speed
```

Increase values for faster streaks, decrease for slower.

---

## 🖥️ Usage

1. Clone or download the repo
2. Open `index.html` in your browser
3. Edit `script.js` to customize

---

## 📜 License

MIT — free to use, modify, and share.

---

## 💡 Ideas for Extensions

* Add mouse-controlled parallax
* Use a darker gradient background for depth
* Make stars twinkle in different colors