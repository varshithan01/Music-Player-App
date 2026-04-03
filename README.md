# Music-Player-App
A modern music streaming app built with React Native using the JioSaavn API, featuring clean UI, smooth playback, and efficient state management.
<img width="712" height="1007" alt="image" src="https://github.com/user-attachments/assets/c1df585d-22c4-4629-a654-a576f9e60d96" />


# 🎵 Mume Music – Smart Music Streaming App

Mume Music is a modern, high-performance music streaming application built using React Native (Expo).  
It delivers a seamless experience with real-time playback, smart data fetching, offline fallback, and persistent user data.

---

## 📱 App Preview

<p align="center">
  <img src="assets/home.png" width="250"/>
  <img src="assets/player.png" width="250"/>
</p>

---

## 🚀 Features

✨ Smart Hybrid Data Fetching (API + Fallback)  
🎧 Background Audio Playback  
📱 Mini Player + Full Player Sync  
❤️ Favorites & Recently Played  
🎨 Dark / Light Theme Support  
⚡ Fast Loading (No Blank Screen UX)  
📊 Scalable Architecture (Production Ready)  

---

## 📦 Tech Stack

- Frontend: React Native (Expo + TypeScript)  
- State Management: Zustand  
- Navigation: React Navigation v6  
- Audio Engine: expo-av  
- Storage: AsyncStorage  
- API: JioSaavn API (via Axios)  

---

## 🏗️ Architecture Overview

The app follows a **Modular MVC-Inspired Architecture** ensuring scalability and separation of concerns.

```

src/
├── components/      # Reusable UI (MiniPlayer, Cards)
├── screens/         # App Screens (Home, Player, Settings)
├── store/           # Zustand Global State
├── services/        # API + Smart Fallback Logic
├── utils/           # Audio Manager, Theme, Dummy Data

```

---

## 🧠 Core Architecture Logic

### 1️⃣ State Management (Zustand)

- Manages:
  - currentSong 🎵  
  - queue 📃  
  - favorites ❤️  
  - history 🕘  
- Eliminates prop drilling  
- Keeps Mini Player & Full Player in sync  

---

### 2️⃣ Smart Data Fetching (Hybrid Strategy)

Flow:
```

UI → Smart Service → API → Fallback → UI

```

- API fetch attempted first  
- Timeout (>6 sec) triggers fallback  
- Offline mode uses local dummy data  
- Ensures **Zero Blank Screen Experience**  

---

### 3️⃣ Parallel Data Loading

```

Promise.all([
getSongsSmart(),
getArtistsSmart(),
getAlbumsSmart()
]);

```

- Reduces loading time  
- Improves performance  

---

### 4️⃣ Audio Engine (Decoupled)

- Managed via `audioManager.ts`
- Handles:
  - Play / Pause  
  - Seek  
  - Single audio instance  
- Prevents memory leaks  
- Works across screens  

---

### 5️⃣ Persistent Storage (AsyncStorage)

Stored locally:
- Favorites ❤️  
- Recently Played 🕘  
- User Preferences ⚙️  

Flow:
```

User Action → Zustand → AsyncStorage → Reload → Restore

```

---

## 🔄 Application Flow

1. App starts → Theme + Storage loaded  
2. Home screen → Smart API fetch  
3. User selects song → Store updates  
4. Audio Manager starts playback  
5. Mini Player appears  
6. Data persists locally  

---

## 💾 Data Strategy

### 🔹 Local Database
- AsyncStorage  
- Stores user data (favorites, history, profile)  

### 🔹 Remote Database
- JioSaavn API  
- Fetches songs, artists, albums  

---

## ⚖️ Trade-offs & Decisions

| Decision | Reason | Trade-off |
|--------|--------|-----------|
| Zustand over Redux | Lightweight & simple | Fewer dev tools |
| Hybrid Data Strategy | No blank UI | Slight bundle increase |
| Expo Managed | Faster development | Slightly larger app size |
| AsyncStorage | Easy persistence | Not relational DB |

---

## ⚙️ Setup Instructions

### 1️⃣ Install Dependencies
```

npm install

```

### 2️⃣ Start Development Server
```

npx expo start

```

### 3️⃣ Run App
- 📱 Scan QR (Expo Go)  
- 🤖 Press `a` → Android  
- 🍎 Press `i` → iOS  

---

## 📦 Build APK

```

npx expo install eas-cli
eas build -p android --profile preview

```

---

## 🎥 Demo

(Add your demo video link here)

---

## 🧑‍💻 Author

**Varshitha N**  
React Native Developer 🚀  

---

## ⭐ Final Note

This project demonstrates:

✔ Scalable Architecture  
✔ Smooth User Experience  
✔ Reliable Data Handling  
✔ Real-world App Design  

---



