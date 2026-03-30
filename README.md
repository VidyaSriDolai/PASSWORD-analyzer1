# PASSWORD-analyzer1
# 🔐 Password Security Analyzer

> **CNS Lab Mini Project** | Development of a Password Strength Analysis and Attack Simulation Tool using Brute Force and Dictionary Techniques

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat-square&logo=python)
![HTML](https://img.shields.io/badge/HTML-5-orange?style=flat-square&logo=html5)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-green?style=flat-square)
![Matplotlib](https://img.shields.io/badge/Charts-Matplotlib-red?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square)

---

## 🌐 Live Demo

👉 **[Click here to open the Web App](https://vidyasridolai.github.io/PASSWORD-analyzer1/)**


## 📌 About the Project

The **Password Security Analyzer** is a simulation tool built as part of the Cryptography and Network Security (CNS) Lab Mini Project. It helps users understand:

- How strong or weak their password is
- How Brute Force attacks work
- How Dictionary attacks work
- What password entropy means

The tool is available in **two versions**:
- 🖥️ **Python Desktop App** — runs locally using Tkinter GUI
- 🌐 **Web App** — deployed on GitHub Pages, runs in any browser

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔎 **Strength Analyzer** | Checks length, character types, entropy and gives a score out of 8 |
| 💥 **Brute Force Simulation** | Tries all combinations of lowercase + digits up to 5 characters |
| 📖 **Dictionary Attack** | Matches password against a built-in wordlist of common passwords |
| 📊 **Visual Report** | Bar chart and entropy donut chart using Matplotlib / Chart.js |
| 🎨 **Cyber-noir Theme** | Dark UI with neon cyan and purple accents |
| ⚡ **Live Strength Bar** | Updates in real time as you type |

---

## 🖥️ Python Desktop Version

### Prerequisites

Make sure you have Python 3 installed. Then install the required library:

```bash
pip install matplotlib
```

### Project Structure

```
password_analyzer/
│
├── password_analyzer.py      ← Main Python file
├── dictionary.txt            ← Wordlist for dictionary attack
└── requirements.txt          ← Required libraries
```

### How to Run

```bash
python password_analyzer.py
```

### Screenshots

```
[PSA]  PASSWORD SECURITY ANALYZER    v2.0 | CYBER SECURITY TOOL    ● READY

  STRENGTH ANALYZER  |  BRUTE FORCE  |  DICTIONARY ATTACK  |  VISUAL REPORT
```

---

## 🌐 Web Version

The web version is a **single HTML file** with no dependencies to install.

### How to Use Locally

1. Download `index.html`
2. Double-click to open in any browser
3. All features work instantly ✅

### How to Deploy on GitHub Pages

1. Upload `index.html` to your GitHub repository
2. Go to **Settings → Pages**
3. Set Branch to **main** → Click **Save**
4. Your live URL: `https://your-username.github.io/your-repo-name/`

---

## 🔬 How It Works

### 1️⃣ Password Strength Analysis

The analyzer checks 5 criteria and assigns a score out of 8:

| Criteria | Points |
|---|---|
| Length ≥ 16 chars | +3 |
| Length ≥ 12 chars | +2 |
| Length ≥ 8 chars | +1 |
| Lowercase letters | +1 |
| Uppercase letters | +1 |
| Digits (0-9) | +1 |
| Special characters | +2 |

**Entropy Formula:**
```
Entropy = Length × log2(Character Set Size)
```

| Entropy Range | Strength |
|---|---|
| < 28 bits | Weak |
| 28 – 49 bits | Moderate |
| 50 – 79 bits | Strong |
| 80+ bits | Very Strong |

---

### 2️⃣ Brute Force Attack

```python
for length in range(1, max_length + 1):
    for combo in itertools.product(chars, repeat=length):
        guess = ''.join(combo)
        if guess == target:
            # PASSWORD CRACKED!
```

- Uses `itertools.product()` to generate all combinations
- Character set: `a-z` + `0-9` (36 characters)
- Max length: 5 characters (demo limit)

---

### 3️⃣ Dictionary Attack

```python
for word in wordlist:
    if word == target:
        # PASSWORD FOUND!
```

- Reads through a wordlist of common passwords
- Instant match if password is a common word
- Shows attempts and time taken

---

## 🧪 Test Results

| Password | Score | Strength | Entropy | Brute Force | Dictionary |
|---|---|---|---|---|---|
| `abc` | 1/8 | WEAK | 14.1 bits | ✅ Cracked | ❌ Not found |
| `password` | 2/8 | WEAK | 37.6 bits | ❌ Too long | ✅ Cracked |
| `vidya@098` | 5/8 | STRONG | 54.85 bits | ❌ Too long | ❌ Safe |
| `Vidya@098` | 6/8 | STRONG | 58.99 bits | ❌ Too long | ❌ Safe |
| `Vidya@098#Secure!` | 8/8 | VERY STRONG | 104.6 bits | ❌ Too long | ❌ Safe |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Python 3 | Core programming language |
| Tkinter | Desktop GUI framework |
| Matplotlib | Visual charts (desktop version) |
| itertools | Brute force combination generator |
| math.log2 | Entropy calculation |
| threading | Background attack simulation |
| HTML5 + CSS3 | Web app structure and styling |
| JavaScript | Web app logic and attack simulation |
| Chart.js | Visual charts (web version) |
| GitHub Pages | Free web deployment |

---

## 📁 File Structure

```
📦 password-analyzer/
│
├── 📄 index.html              ← Web app (deploy this on GitHub Pages)
├── 📄 password_analyzer.py    ← Python desktop app
├── 📄 dictionary.txt          ← Wordlist for dictionary attack
├── 📄 requirements.txt        ← Python dependencies
└── 📄 README.md               ← This file
```

---

## 🚀 Future Enhancements

- [ ] AI/ML based password crackability prediction
- [ ] Hash-based attack simulation (MD5, SHA-1, bcrypt)
- [ ] Rainbow table attack module
- [ ] Automatic strong password generator
- [ ] Support for larger wordlists (rockyou.txt)
- [ ] Flask/Django web backend version
- [ ] Multi-language wordlist support

---

## 📚 References

- [NIST Special Publication 800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html) — Digital Identity Guidelines
- [Shannon's Entropy Theory](https://en.wikipedia.org/wiki/Entropy_(information_theory)) — A Mathematical Theory of Communication
- [Python Documentation](https://docs.python.org/3/) — Python 3 Official Docs
- [OWASP Password Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
- [Tkinter Documentation](https://docs.python.org/3/library/tkinter.html)
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)

---

## 👩‍💻 Author

**Developed as part of CNS Lab Mini Project**
- Subject: Cryptography and Network Security
- Tool: Python 3 + HTML5
- IDE: Visual Studio Code

---

## 📄 License

This project is for **educational purposes** as part of a university lab mini project.

---

⭐ **If you found this useful, please star the repository!** ⭐
