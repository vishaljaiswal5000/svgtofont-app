# svgtofont Library Guide

The `svgtofont` library is a tool designed to convert **SVG (Scalable Vector Graphics)** files into **font files**. It takes a collection of SVG icons and packages them into a font that can be used in web projects.

---

## 🔧 Key Features

### 🔹 Icon Fonts
Creates icon fonts that replace individual image files, improving performance and scalability.

### 🔹 Font File Generation
Generates various font formats:
- **TTF**
- **EOT**
- **WOFF**
- **WOFF2**
- **SVG**

Ensures **cross-browser compatibility**.

### 🔹 CSS Generation
Includes features to **generate CSS files** for easy integration into web projects.

### 🔹 Streamlining Icon Usage
Simplifies the process of using icons in frontend development.

---

## 📚 Useful Links

- **Official Documentation**: [https://wangchujiang.com/svgtofont/](https://wangchujiang.com/svgtofont/)
- **NPM Package**: [https://www.npmjs.com/package/svgtofont](https://www.npmjs.com/package/svgtofont)
- **Reference Repo**: [svgtofont-app GitHub](https://github.com/vishaljaiswal5000/svgtofont-app)

---

## 🚀 Getting Started

### Step 1 — Install via NPM

```bash
npm i svgtofont
```

#### Project Structure Example

```
project-root/
│
├── assets/
│   ├── icons/              # Source SVG icons
│   └── generated-icons/    # Output font and CSS files
├── .svgtofontrc.json       # Configuration file
└── package.json
```

---

### Step 2 — Create `.svgtofontrc.json` Configuration File

```json
{
  "emptyDist": true,
  "fontName": "icon",
  "log": true,
  "outSVGReact": false,
  "generateInfoData": true,
  "css": {
    "cssPath": "./assets/generated-icons/",
    "include": "\\.(scss)$"
  },
  "svgicons2svgfont": {
    "fontHeight": 1000,
    "normalize": true
  },
  "website": {
    "title": "SVG to fonts",
    "meta": {
      "description": "Converts SVG fonts to TTF/EOT/WOFF/WOFF2/SVG format.",
      "keywords": "svgtofont,TTF,EOT,WOFF,WOFF2,SVG"
    }
  }
}
```

---

### 🧩 Configuration Breakdown

Key options explained:

- `emptyDist`: Clear output directory before generating.
- `fontName`: Name of the generated font.
- `log`: Enables logs.
- `css`: If enabled, generates CSS file.
- `outSVGReact`: If enabled, outputs React components.
- `svgicons2svgfont`: SVG to font generation settings like `fontHeight`, `normalize`, etc.
- `outputFormats`: Fonts to generate — `["woff", "woff2", "ttf", "eot", "svg"]`
- `cssOptions`, `htmlOptions`, `jsonOptions`: Customize output paths, templates, and styles.

---

### Step 3 — Update `package.json` Scripts

```json
"scripts": {
  "svgtofont": "svgtofont --sources ./src/assets/icons --output ./src/assets/generated-icons"
}
```

---

### Step 4 — Run svgtofont Command

```bash
npm run svgtofont
```

- Font files are generated in `generated-icons/`
- Preview: Open `generated-icons/index.html` in your browser

---

### Step 5 — Import Generated SCSS in App

```scss
// App.scss or main.scss
@import './assets/generated-icons/icons.scss';
```

Use generated icon classes in your app:

```tsx
// App.tsx
<span className="icon icon-home"></span>
```

---

## 🧠 Summary

The `svgtofont` library bridges the gap between **SVG icons** and **web font technology**, giving developers a **powerful** and **efficient** way to use vector-based icons in frontend applications.

---