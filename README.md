# 🎬 Find Movies App

A fast, responsive movie search application built with **React + Vite**, powered by **TMDB API**, and integrated with **Appwrite** to track trending searches. This project demonstrates real-world frontend development skills including API integration, debouncing, backend interaction, and deployment.

---

## 🚀 Live Demo

*Deployed on Render*

🔗 **Live URL:** (https://find-movies-wlvd.onrender.com/)

---

## ✨ Features

### 🔍 Search Movies (Live Search)

* Search movies in real-time using TMDB API
* Debounced input prevents unnecessary API calls
* Displays rich movie details: poster, rating, release date

### 📈 Trending Movies (Powered by Appwrite)

* Each search updates a counter in Appwrite database
* Trending section ranks top-searched movies

### 🎨 Beautiful UI

* Responsive layout using Tailwind CSS
* Modern card design
* Smooth loading animation (Spinner)

### ⚡ Built for Performance

* Powered by **Vite** (super fast dev server + optimized build)
* API key environment variables baked at build time

### 🌐 Fully Deployed on Render

* Static site hosting
* Integrated environment variables
* Automatic GitHub deployment

---

## 🛠️ Tech Stack

### **Frontend**

* React 18+
* Vite
* Tailwind CSS
* React Hooks
* useDebounce (react-use)

### **Backend (Trending Movie Tracking)**

* Appwrite Cloud
* Database Collection
* CRUD operations to track trending movies

### **API**

* TMDB API (v3)

### **Deployment**

* Render Static Site Hosting

---

## 📁 Project Structure

```
find-movies/
 ├── public/
 ├── src/
 │    ├── components/
 │    │    ├── MovieCard.jsx
 │    │    ├── Search.jsx
 │    │    └── Spinner.jsx
 │    ├── App.jsx
 │    ├── appwrite.js
 │    ├── main.jsx
 │    ├── index.css
 │    └── App.css
 ├── package.json
 ├── vite.config.js
 └── README.md
```

---

## 🔑 Environment Variables

Create a `.env` file in your project root:

```
VITE_TMDB_API_KEY=your_tmdb_v3_key_here
VITE_APPWRITE_PROJECT_ID=your_appwrite_project_id
VITE_APPWRITE_DATABASE_ID=your_database_id
VITE_APPWRITE_COLLECTION_ID=your_collection_id
VITE_APPWRITE_ENDPOINT=https://your-appwrite-endpoint/v1
```

⚠️ **Important:**
TMDB **v3** keys must be sent as:

```
?api_key=YOUR_KEY
```

and NOT as Bearer tokens.

---

## 🧠 Core Logic Explained

### 🎬 Fetching Movies (TMDB API)

```js
const endpoint = `${API_BASE_URL}/search/movie?query=${query}&api_key=${API_KEY}`;
const response = await fetch(endpoint);
```

### ⏳ Debounced Search

```js
useDebounce(() => setDebouncedSearchTerm(searchTerm), 500, [searchTerm]);
```

### 📊 Tracking Trending Searches (Appwrite)

```js
await updateSearchCount(query, data.results[0]);
```

### 🎥 Displaying Movie Cards

```jsx
<MovieCard key={movie.id} movie={movie} />
```

---

## 🏗️ Setup Instructions

### 1️⃣ Clone the repository

```
git clone https://github.com/your-user/find-movies.git
cd find-movies
```

### 2️⃣ Install dependencies

```
npm install
```

### 3️⃣ Run development server

```
npm run dev
```

### 4️⃣ Build for production

```
npm run build
```

### 5️⃣ Preview production build

```
npm run preview
```

---

## 🌐 Deployment (Render)

Ensure these settings:

### **Build Command:**

```
npm install && npm run build
```

### **Publish Directory:**

```
dist
```

### **Environment Variables:**

Add all VITE_ variables exactly as in `.env` (no quotes).

---

## 🐛 Common Issues

### ❌ 401 Unauthorized from TMDB

**Cause:** Using v3 key with Bearer header.

**Fix:** Always append key as query param.

```
?api_key=XXXXX
```

### ❌ Render says: "Publish directory dist does not exist"

**Fix:** Add Build Command in Render settings.

### ❌ Env variables not updating on Render

**Fix:** Clear Cache & Deploy.

---

## 👨‍💻 Future Improvements

* Pagination for movie results
* Movie detail page
* Watchlist using Appwrite
* Dark/Light theme toggle
* Image lazy loading

---

## 🙌 Author

Amit Halder

* GitHub: https://github.com/amitkumh9529
* Portfolio: *your link*

---

## ⭐ Like this project?

If you found this helpful, please star the repo!
