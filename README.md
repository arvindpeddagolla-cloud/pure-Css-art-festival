# Pure CSS Pikachu GameBoy Console ⚡

An interactive, animated Pikachu mascot housed inside a retro-modern console (GameBoy Color style), rendered **entirely in 100% pure HTML & CSS** (zero JavaScript, zero SVGs, zero canvas, and zero image/background URLs).

Built for the **CSS Art Festival** (Advanced Challenge).

---

## 🎮 Live Operations Manual

* **🔌 Power Switch (Top Left):** Click the slider to turn the console ON or OFF. Toggles CRT screen scanlines, HUD boot overlays, and status LEDs.
* **◀ D-Pad Left / SELECT:** Toggle Pikachu's **Dance Mode** (makes Pikachu jump, wags tail, twitches ears, and raises arms).
* **▶ D-Pad Right / START:** Toggle **Day/Night Cycle** (cycles backdrop from sunny blue to starry purple, settings moon/sun, and makes Pikachu's cheeks glow in the dark).
* **🅰 Button A:** Trigger **Thunderbolt Attack** (screen shakes violently, electrical sparks flash around, expansion waves emit, and the HUD HP bar drains to warning levels).
* **🅱 Button B:** Toggle **Sleep Mode** (Pikachu closes its eyes, breathing cycles slow down, ears fold, and "Zzz" particles float upward).

---

## 🛠️ Technical Highlights

### 1. Zero JavaScript State Machine (CSS Checkbox Hack)
All interactive controls are powered by linking visual `<label>` buttons to hidden `<input type="checkbox">` elements. Using the general sibling combinator `~`, state shifts dynamically trigger CSS animations:
```css
/* Breathing cycles and arm placement updates on Sleep Mode checked */
#sleep-toggle:checked ~ .console-wrapper .pikachu {
  animation: breathing 4s infinite ease-in-out;
}
```

### 2. Complex CSS Geometry & Artwork
* **Pikachu Anatomy:** Shapes (head, chubby body, arms, oval feet) are constructed via precise `border-radius` percentage structures.
* **Lightning Tail:** Built from 5 nested `div` segments positioned absolutely and transformed using `rotate()` and `skewX()` parameters to shape the classic zigzag pointer.
* **Electrical Sparks:** Created using rotated lines with rotated pseudo-element offsets to form zigzags.
* **Scanline CRT Overlay:** Rendered using multi-directional repeating linear gradients and transparency opacity.

---

## 🚀 Running Locally

Since the project is built in pure static HTML/CSS, you can run it instantly:

1. **Option A (Double-Click):** Double-click `index.html` to open it in any web browser.
2. **Option B (Local Web Server):** Serve the folder using any HTTP server:
   ```bash
   npx http-server -p 8080
   ```
   Open [http://localhost:8080](http://localhost:8080) in your browser.

---

## 📂 File Structure

* `index.html` - HTML structural layouts for the chassis, controls, environment, and Pikachu anatomy.
* `style.css` - Design tokens, layout grids, Pikachu curves, keyframe animations, and screen shaders.
* `how_i_developed.pdf` - PDF Development and Architecture Report detailing the technical build process.
