# 📖 Pashto Quran API

> Complete Pashto translation of the Holy Quran in REST API format.

[![Surahs](https://img.shields.io/badge/Surahs-114-blue.svg)](https://github.com/malikzaijahid/quran-pashto-api)
[![Verses](https://img.shields.io/badge/Verses-6236-green.svg)](https://github.com/malikzaijahid/quran-pashto-api)
[![Language](https://img.shields.io/badge/Language-Pashto-orange.svg)](https://github.com/malikzaijahid/quran-pashto-api)
[![License](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)
[![jsDelivr](https://img.shields.io/badge/CDN-jsDelivr-red.svg)](https://www.jsdelivr.com/)

A complete, free, and CDN-hosted Pashto translation of the Holy Quran, formatted as a REST API compatible with the [fawazahmed0/quran-api](https://github.com/fawazahmed0/quran-api) structure.

---

## 🌐 Live API

**Base URL:**
```
https://cdn.jsdelivr.net/gh/malikzaijahid/quran-pashto-api@main/editions/pus-pashto/
```

**Example (Surah An-Najm - 53):**
```
https://cdn.jsdelivr.net/gh/malikzaijahid/quran-pashto-api@main/editions/pus-pashto/53.min.json
```

---

## ✨ Features

- ✅ **Complete** — All 114 surahs, 6236 verses
- ✅ **Free** — No API key, no authentication, no rate limits
- ✅ **Fast** — Served via jsDelivr's global CDN
- ✅ **CORS Enabled** — Works from any domain
- ✅ **UTF-8** — Full Pashto script support
- ✅ **Standard Format** — Same structure as `fawazahmed0/quran-api`
- ✅ **Two Formats** — Pretty (`.json`) and Minified (`.min.json`)
- ✅ **Well Documented** — Examples in multiple languages

---

## 📊 Statistics

| Feature | Value |
|---------|-------|
| **Surahs** | 114 |
| **Verses** | 6,236 |
| **Language** | Pashto (پښتو) |
| **Direction** | RTL (Right-to-Left) |
| **Translator** | Abdulwali Khan |
| **Format** | JSON |
| **CDN** | jsDelivr |
| **License** | MIT |

---

## 🚀 Quick Start

### 1. Get a Surah (cURL)

```bash
# Surah Al-Fatiha (1)
curl https://cdn.jsdelivr.net/gh/malikzaijahid/quran-pashto-api@main/editions/pus-pashto/1.min.json

# Surah An-Najm (53)
curl https://cdn.jsdelivr.net/gh/malikzaijahid/quran-pashto-api@main/editions/pus-pashto/53.min.json
```

### 2. JavaScript (Browser)

```javascript
const surahNumber = 1;
const url = `https://cdn.jsdelivr.net/gh/malikzaijahid/quran-pashto-api@main/editions/pus-pashto/${surahNumber}.min.json`;

const response = await fetch(url);
const data = await response.json();

data.chapter.forEach(item => {
  console.log(`Verse ${item.verse}: ${item.text}`);
});
```

### 3. Python

```python
import requests

surah = 1
url = f'https://cdn.jsdelivr.net/gh/malikzaijahid/quran-pashto-api@main/editions/pus-pashto/{surah}.min.json'

data = requests.get(url).json()

for item in data['chapter']:
    print(f"Verse {item['verse']}: {item['text']}")
```

### 4. React

```jsx
import { useEffect, useState } from 'react';

function PashtoVerse({ surahNum = 1 }) {
  const [verses, setVerses] = useState([]);

  useEffect(() => {
    const url = `https://cdn.jsdelivr.net/gh/malikzaijahid/quran-pashto-api@main/editions/pus-pashto/${surahNum}.min.json`;
    
    fetch(url)
      .then(r => r.json())
      .then(data => setVerses(data.chapter));
  }, [surahNum]);

  return (
    <div dir="rtl">
      {verses.map(v => (
        <div key={v.verse}>
          <span>{v.verse}. </span>
          <span>{v.text}</span>
        </div>
      ))}
    </div>
  );
}
```

### 5. Node.js

```javascript
const https = require('https');

function fetchSurah(surahNumber) {
  return new Promise((resolve, reject) => {
    const url = `https://cdn.jsdelivr.net/gh/malikzaijahid/quran-pashto-api@main/editions/pus-pashto/${surahNumber}.min.json`;
    
    https.get(url, res => {
      let data = '';
      res.on('data', chunk => data += chunk);
      res.on('end', () => resolve(JSON.parse(data)));
    }).on('error', reject);
  });
}

fetchSurah(1).then(data => {
  data.chapter.forEach(v => console.log(`${v.verse}. ${v.text}`));
});
```

---

## 📡 API Reference

### Endpoints

| Endpoint | Description |
|----------|-------------|
| `/editions/pus-pashto/{surah}.json` | Pretty JSON for a specific surah |
| `/editions/pus-pashto/{surah}.min.json` | Minified JSON for a specific surah |

**Parameters:**
- `{surah}` — Surah number (1-114)

### Response Format

```json
{
  "chapter": [
    {
      "chapter": 1,
      "verse": 1,
      "text": "د الله په نامه سره (شروع كوم) چې ډېر زیات مهربان، بې حده رحم كوونكى دى"
    },
    {
      "chapter": 1,
      "verse": 2,
      "text": "ټول (د كمال) صفتونه خاص د الله لپاره دي چې د ټولو عالَمونو ښه پالونكى دى"
    }
  ]
}
```

**Fields:**

| Field | Type | Description |
|-------|------|-------------|
| `chapter` | number | The surah number (repeated for consistency) |
| `verse` | number | The verse number within the surah (1-based) |
| `text` | string | The Pashto translation of the verse |

---

## 📖 Sample Verses

### Surah Al-Fatiha (الفاتحة)

| # | Pashto |
|---|--------|
| 1 | د الله په نامه سره (شروع كوم) چې ډېر زیات مهربان، بې حده رحم كوونكى دى |
| 2 | ټول (د كمال) صفتونه خاص د الله لپاره دي چې د ټولو عالَمونو ښه پالونكى دى |
| 3 | ډېر زیات مهربان، بې حده رحم كوونكى دى |
| 4 | د بَدلې د ورځې مالك دى |
| 5 | مونږ خاص ستا عبادت كوو او خاص له تا نه مدد غواړو |
| 6 | ته مونږ ته سَمَه (نېغه) لاره وښَیَه |
| 7 | د هغو خلقو لاره چې تا پر هغوى باندې انعام كړى دى؛ چې نه پر هغوى باندې غضب شوى او نه ګمراهان دي |

### Surah An-Najm (النجم) — First 5 Verses

| # | Pashto |
|---|--------|
| 1 | قسم دى په ستوریو كله چې پرېوځي |
| 2 | ستاسو ملګرى نه ګمراه شوى دى او نه (په عقيده كې) بې لارې شوى دى |
| 3 | او دى له خپل خواهش نه خبرې نه كوي |
| 4 | نه دى دا (قرآ ن) مګر وحي چې (ده ته) وحي كول شي |
| 5 | ده ته (دا) د ډېرو سختو قوتونو والا (جبریل) ښودلى دى |

---

## 📚 Available Surahs

All 114 surahs are available. Just replace `{surah}` with any number from 1 to 114.

| # | Arabic | Pashto | English | Verses |
|---|--------|--------|---------|--------|
| 1 | الفاتحة | فاتحه | Al-Fatiha | 7 |
| 2 | البقرة | بقره | Al-Baqarah | 286 |
| 3 | آل عمران | آل عمران | Aal-e-Imran | 200 |
| 4 | النساء | نساء | An-Nisa | 176 |
| 5 | المائدة | مائده | Al-Maidah | 120 |
| 6 | الأنعام | انعام | Al-An'am | 165 |
| 7 | الأعراف | اعراف | Al-A'raf | 206 |
| 8 | الأنفال | انفال | Al-Anfal | 75 |
| 9 | التوبة | توبه | At-Tawbah | 129 |
| 10 | يونس | یونس | Yunus | 109 |
| ... | ... | ... | ... | ... |
| 114 | الناس | ناس | An-Nas | 6 |

*Full list available in the `editions/pus-pashto/` folder.*

---

## 🗂️ Project Structure

```
quran-pashto-api/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── .gitignore
├── editions/
│   └── pus-pashto/
│       ├── 1.json
│       ├── 1.min.json
│       ├── 2.json
│       ├── 2.min.json
│       ├── ...
│       ├── 114.json
│       └── 114.min.json
├── examples/
│   ├── javascript.md
│   ├── python.md
│   ├── react.md
│   └── curl.md
└── scripts/
    ├── split_quran.py
    └── verify.py
```

---

## 🔧 How It Was Generated

This API was generated from the source Pashto translation using a Python script.

### Source Format

The source file follows this format:

```
1|1|د الله په نامه سره (شروع كوم) چې ډېر زیات مهربان، بې حده رحم كوونكى دى
1|2|ټول (د كمال) صفتونه خاص د الله لپاره دي چې د ټولو عالَمونو ښه پالونكى دى
53|1|قسم دى په ستوریو كله چې پرېوځي
```

Each line: `surah|verse|translation`

### Generation Command

```bash
python scripts/split_quran.py pashto.txt editions/pus-pashto
```

This generates:
- 114 `.json` files (pretty format)
- 114 `.min.json` files (minified format)

### Verification

```bash
python scripts/verify.py editions/pus-pashto
```

---

## 🌍 Use Cases

- 📱 Mobile apps (iOS, Android, React Native, Flutter)
- 💻 Web applications (React, Vue, Angular)
- 📚 Educational tools
- 🔍 Quran search engines
- 📖 Reading apps
- 🎓 Islamic learning platforms
- 🕌 Mosque & Madrasa software
- 📻 Radio & streaming apps

---

## 📱 Complete Example App

```html
<!DOCTYPE html>
<html dir="rtl" lang="ps">
<head>
  <meta charset="UTF-8">
  <title>قرآن کریم - پښتو</title>
  <style>
    body { font-family: Tahoma, sans-serif; padding: 20px; background: #f5efe0; }
    .verse { background: white; padding: 15px; margin: 10px 0; border-radius: 8px; }
    .verse-num { 
      background: #b68b40; color: white; border-radius: 50%;
      padding: 4px 10px; margin-left: 10px; font-weight: bold;
    }
    select { padding: 8px; font-size: 16px; }
  </style>
</head>
<body>
  <h1>📖 قرآن کریم - پښتو ژباړه</h1>
  
  <select id="surahSelect"></select>
  <div id="verses"></div>

  <script>
    const surahs = [
      {num: 1, name: 'الفاتحة'}, {num: 2, name: 'البقرة'},
      {num: 3, name: 'آل عمران'}, {num: 4, name: 'النساء'},
      {num: 5, name: 'المائدة'}, {num: 6, name: 'الأنعام'},
      {num: 7, name: 'الأعراف'}, {num: 8, name: 'الأنفال'},
      {num: 9, name: 'التوبة'}, {num: 10, name: 'يونس'}
      // ... add all 114
    ];

    document.getElementById('surahSelect').innerHTML = 
      surahs.map(s => `<option value="${s.num}">${s.num}. ${s.name}</option>`).join('');

    async function loadSurah(num) {
      const url = `https://cdn.jsdelivr.net/gh/malikzaijahid/quran-pashto-api@main/editions/pus-pashto/${num}.min.json`;
      const data = await fetch(url).then(r => r.json());
      
      document.getElementById('verses').innerHTML = 
        data.chapter.map(v => `
          <div class="verse">
            <span class="verse-num">${v.verse}</span>
            <span>${v.text}</span>
          </div>
        `).join('');
    }

    document.getElementById('surahSelect').addEventListener('change', e => {
      loadSurah(e.target.value);
    });

    loadSurah(1);
  </script>
</body>
</html>
```

---

## 🎯 Related Projects

- [fawazahmed0/quran-api](https://github.com/fawazahmed0/quran-api) — Original API structure
- [everyayah.com](https://everyayah.com) — Audio recitations
- [alquran.cloud](https://alquran.cloud) — Alternative Quran API
- [quran.com](https://quran.com) — Quran.com API

---

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details.

### Ways to Contribute

- 🐛 Report bugs
- 💡 Suggest features
- 📝 Improve documentation
- 🌍 Add translations
- ⭐ Star the repo

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

The Pashto translation itself is by **Abdulwali Khan** and is provided for free use for the benefit of the Pashto-speaking community.

---

## 🙏 Credits

- **Translation**: Abdulwali Khan
- **API Structure**: Inspired by [fawazahmed0/quran-api](https://github.com/fawazahmed0/quran-api)
- **CDN**: [jsDelivr](https://www.jsdelivr.com/)
- **Developer**: [Ikramullah Malikzai](https://github.com/malikzaijahid)

---

## ⭐ Show Your Support

If this project helps you, please:

- ⭐ **Star** this repository
- 🐦 **Share** with others
- 📝 **Write** about it
- 🤝 **Contribute** improvements

---

## 📞 Contact

- **GitHub**: [@malikzaijahid](https://github.com/malikzaijahid)
- **Issues**: [Open an issue](https://github.com/malikzaijahid/quran-pashto-api/issues)

---

<div align="center">

**Made with ❤️ for the Pashto-speaking community**

**د پښتو ژبې ټولنې لپاره په ❤️ سره جوړ شوی**

[⬆ Back to Top](#-pashto-quran-api)

</div>
