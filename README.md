# ⌨️ Mobile Keyboard App - Production CDN Resources

Complete, white-labeled, production-ready static assets package for Custom Mobile Keyboard Apps (iOS & Android).

All resources are structured for **high-speed delivery via jsDelivr CDN** directly from this public GitHub repository:
`https://github.com/Cursor10Ju/khriuehwr`

---

## 🌐 jsDelivr CDN Base URL
```
https://cdn.jsdelivr.net/gh/Cursor10Ju/khriuehwr@main/
```

### 📡 Core API Catalog Endpoints

| Endpoint | Direct CDN URL | Description |
| :--- | :--- | :--- |
| **Global Manifest** | `https://cdn.jsdelivr.net/gh/Cursor10Ju/khriuehwr@main/cdn_manifest.json` | Root index of all available themes, DIY assets, and GIFs |
| **Themes Catalog** | `https://cdn.jsdelivr.net/gh/Cursor10Ju/khriuehwr@main/themes/themes.json` | Complete catalog of 851 custom keyboard themes |
| **DIY Assets Catalog** | `https://cdn.jsdelivr.net/gh/Cursor10Ju/khriuehwr@main/assets/assets.json` | 259 DIY assets (TrueType fonts, typing sounds, button styles) |
| **Searchable GIFs Catalog** | `https://cdn.jsdelivr.net/gh/Cursor10Ju/khriuehwr@main/gifs/gifs.json` | 1,200 HD animated GIFs with search keywords & tags across 36 categories |

---

## 📁 Directory Structure

```
khriuehwr/
├── README.md                      <- CDN Integration Guide & Documentation
├── cdn_manifest.json              <- Master manifest of all assets
├── themes/
│   ├── themes.json                <- 851 White-labeled Themes Metadata
│   ├── previews/                  <- 813 Preview Images (.webp / .png)
│   └── downloads/                 <- 536 Theme ZIP packages
├── assets/
│   ├── assets.json                <- 259 DIY Assets Metadata
│   ├── previews/                  <- 259 Asset Preview Images (.png / .gif)
│   └── downloads/                 <- 259 Asset Files (.ttf fonts, .caf sounds, .gif)
└── gifs/
    ├── gifs.json                  <- 1,200 Searchable GIFs Catalog
    ├── previews/                  <- 1,200 Lightweight Preview GIFs (~100 KB each)
    └── downloads/                 <- 1,200 Full-Resolution Animated GIFs
```

---

## 🎨 Asset Categories & Features

### 1. 🎭 Themes (`themes/`)
* **Total Themes:** 851 curated themes
* **Categories:** New, Premium, Simple, Trending, Cartoon, Cute, Love, Neon, Anime, 3D, Glitter, Flower, Cool, Kitty, Transparent, Live Themes, HOT Themes, DIY Live Themes.
* **Direct URLs:** Every item in `themes.json` has pre-configured `preview_url` and `download_url`.

### 2. 🧩 DIY Assets (`assets/`)
* **Total Assets:** 259 items
* **Breakdown:**
  * **Keyboard Fonts:** 40 TrueType (`.ttf`) font files (playable offline in iOS & Android).
  * **Typing Sounds:** 36 Core Audio Format (`.caf`) sound effects for keypresses.
  * **Key Buttons:** High-res button styling assets.
  * **Swipe & Special Effects:** Particle and gesture animations.
  * **GIF Backgrounds:** 175 looping animated backgrounds.

### 3. 🎬 Searchable GIFs (`gifs/`)
* **Total GIFs:** 1,200 unique animated GIFs
* **Categories (36 total):** Trending, Happy, Love, Laugh & LOL, Sad & Crying, Dance & Vibing, Shocked & OMG, Angry, Confused & Shrug, Cute & Kawaii, Cats & Kittens, Dogs & Puppies, Thank You, Good Morning, Good Night, Hello & Hi, Bye, Yes, No, Applause, Birthday, Celebrate, Hugs, Gaming, Music, Workout, Coffee, Study, Relax, Food, Sleepy, Bored, Wink, Fire & Lit, Mind Blown, Cheers, Sorry, Facepalm, Excited, Thumbs Up.
* **Dual Resolution:**
  * `previews/` (~100 KB): Ultra-fast rendering in keyboard search grid.
  * `downloads/` (~1.5 MB): Full-resolution animated GIF for sending to chat.
* **Instant Offline Search:** Each item contains `search_keywords` and `tags` pre-indexed for client-side or SQLite searching.

---

## 🚀 How to Use in Mobile Apps (Flutter / React Native / Swift / Kotlin)

### 1. Fetching Themes Directly in App
```dart
final response = await http.get(
  Uri.parse("https://cdn.jsdelivr.net/gh/Cursor10Ju/khriuehwr@main/themes/themes.json")
);
final List themes = jsonDecode(response.body);

// Each item has direct URLs ready to display:
String previewUrl = themes[0]['preview_url'];
String downloadZipUrl = themes[0]['download_url'];
```

### 2. Fetching DIY Assets (Fonts, Sounds, Buttons)
```dart
final response = await http.get(
  Uri.parse("https://cdn.jsdelivr.net/gh/Cursor10Ju/khriuehwr@main/assets/assets.json")
);
final List assets = jsonDecode(response.body);

// Font download URL example:
String fontTtfUrl = assets[10]['download_url'];
```

### 3. Client-Side GIF Search Example
```dart
final response = await http.get(
  Uri.parse("https://cdn.jsdelivr.net/gh/Cursor10Ju/khriuehwr@main/gifs/gifs.json")
);
final Map data = jsonDecode(response.body);
final List allGifs = data['gifs'];

List searchGifs(String query) {
  final q = query.toLowerCase().trim();
  return allGifs.where((gif) {
    final List keywords = gif['search_keywords'] ?? [];
    return keywords.any((k) => k.contains(q));
  }).toList();
}
```

---

## 🔒 White-Label Status
* **0% Third-party references:** Zero mentions of Kika, Art Keyboard, Coloring Keyboard, or Tenor.
* **Sequential Clean IDs:** `theme_0001`, `asset_0001`, `gif_0001`.
* **Zero external dependencies:** 100% self-hosted on your own repository.
