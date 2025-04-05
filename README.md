
# wpmx — Terminal Typing Speed Test & Trainer

`wpmx` is a minimalist, high-performance terminal-based typing speed tool written in Python. It helps you **measure**, **improve**, and **track** your typing skills over time—directly from your terminal.

This project is built upon the original [wpm project](https://github.com/cslarsen/wpm) by Christian Stigen Larsen, extending and modernizing it for 2025 and beyond.

---

## 🚀 Features

- 🔥 Lightning-fast and responsive typing interface (Curses-based)
- 🧠 Over **4,900 quotes** from [typeracerdata.com](https://typeracerdata.com)
- 🎯 Real-time accuracy and WPM tracking
- 📉 Historical stats saved in `.csv` format (TypeRacer-compatible)
- 📁 Load your own texts or JSON quote packs
- 🏷️ Tag runs by keyboard layout, device, or mood!
- 📊 Built-in statistics viewer by tag
- 👨‍💻 Works offline and with zero external dependencies

---

## 📦 Installation

**Recommended:**

```bash
pip install wpmx
```

**User-local install (no sudo):**

```bash
pip install --user wpmx
```

**From source:**

```bash
git clone https://github.com/Gabriel-Rockson/wpmx
cd wpmx
pip install .  # or: pip install --user .
```

**Quick run without installing:**

```bash
make run
```

---

## 🎮 Usage

Launch it from your terminal:

```bash
wpmx
```

Or:

```bash
python -m wpmx
```

- ⌨️ The timer starts with your first keystroke.
- 🛑 Press `ESC` to quit any time.
- ⬅️ Use `Backspace` to fix the current word.
- 🚫 Accuracy drops with each typo.

---

## 📈 WPM Calculation

WPM is computed with:

```
WPM = (Characters per second / 5) * 60
```

This is a commonly used method that might differ slightly from online tests like TypeRacer.

---

## 📚 Custom Texts

### Load plain text:

```bash
wpm --load path/to/yourfile.txt
```

### Load structured quote packs (JSON):

```bash
wpm --load-json path/to/quotes.json
```

```json
[
  {
    "author": "Author Name",
    "title": "Work Title",
    "text": "Text you want to practice typing."
  }
]
```

---

## 🧵 Tagging and Tracking

Add a tag to your run to track stats per keyboard, layout, time, etc.:

```bash
wpm --tag=qwerty
```

Tags are saved with your results and can be analyzed later:

```bash
wpm --stats
```

---

## 📁 Race History Format

All results are saved to `~/.wpm.csv` in a TypeRacer-compatible format, plus extra fields:

| Column     | Type   | Description                                 |
|------------|--------|---------------------------------------------|
| race       | int    | Unique race ID                              |
| wpm        | float  | Typing speed in words per minute            |
| accuracy   | float  | Typing accuracy (0.0 to 1.0)                |
| rank       | int    | Always 1                                    |
| racers     | int    | Always 1                                    |
| text_id    | int    | Unique text ID                              |
| timestamp  | str    | Race time in UTC                            |
| database   | str    | Source (default or filename)                |
| tag        | str    | User-defined tag                            |

---

## ⚙️ Configuration (`~/.wpmrc`)

Editable config file is created on first run.

| Section  | Key             | Default | Description                             |
|----------|----------------|---------|-----------------------------------------|
| curses   | escdelay       | 15      | ms delay for ESC key follow-ups         |
| curses   | window_timeout | 20      | ms timeout waiting for keypress         |
| wpm      | confidence_level | 0.95  | Confidence level for stats              |
| wpm      | wrap_width     | -1      | Custom text wrap width (optional)       |
| wpm      | tab_spaces     | 1       | Tabs converted to spaces                |

---

## 🧪 Dev Features

Set environment variable `WPM_DEVFEATURES` to enable extra features:

```bash
WPM_DEVFEATURES=feature1:feature2 wpm
```

See `src/wpm/devfeatures.py` for a full list.

---

## 💡 Tips for Improving Typing Speed

- Learn touch typing (no looking at the keyboard!)
- Use **all your fingers**
- Sit properly and relax your wrists
- Practice often, but **don’t overdo it**
- Focus on *words*, not *characters*
- Slow down on hard parts to reduce errors

---

## 💻 Best Performance

For **lowest latency typing**:

- Linux: Switch to a virtual console (`Ctrl+Alt+F2`)
- macOS: Use **Terminal.app** (faster than iTerm)
- Linux GUI: Try **Ghostty**, **Kitty**, **Alacritty**, or **uxterm**

---

## 🧑‍💻 Credits

This project is a **continuation and modernization** of the original [`wpm`](https://github.com/cslarsen/wpm) project by Christian Stigen Larsen (2017–2018), licensed under the **AGPL v3 or later**.

The original quotes database is **not** covered by the AGPL.

---

## 📜 License

This project is licensed under the **GNU Affero General Public License v3.0**. See `LICENSE.txt` for more.

---

## 🌟 Contribute

Pull requests, suggestions, and issues are welcome! Fork this repo, experiment, and send your improvements. Let’s make terminal typing even cooler.
