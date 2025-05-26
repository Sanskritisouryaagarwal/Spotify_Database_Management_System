# 🎵 Spotify Database Management System

---

## 📖 Project Overview

The **Spotify Database Management System (DBMS)** is a full-scale simulation of Spotify's backend relational database, designed to model, manage, and query a digital music streaming service. It captures all core components of Spotify — such as songs, albums, playlists, subscriptions, artists, and users — while emphasizing **data normalization, indexing, query optimization**, and optional GUI and API integration.

The project was developed as part of a database systems course (CPS510), and aims to provide both a theoretical foundation and a practical implementation of how large-scale entertainment platforms like Spotify manage, store, and retrieve complex datasets.

---

## 🎯 Objectives

- Design a **normalized relational schema** for Spotify's ecosystem.
- Simulate **real-time user and artist interaction** through SQL queries.
- Enable **playlist creation**, **music exploration**, **search filtering**, and **subscription management**.
- Provide an optional **GUI** and **REST API** for accessible database interaction.
- Implement **performance optimization techniques** like indexing and join optimization for large-scale datasets.

---

## 🧩 Core Features

### 1. 🎼 Music Library Management
- Stores detailed metadata about songs, albums, and genres.
- Supports song attributes like title, language, duration, artist(s), number of streams, and album association.

### 2. 👤 User & Subscription System
- Manages user profiles with unique user IDs.
- Includes subscription tiers (Free, Individual, Duo, Family, Student).
- Tracks user payment history and subscription status.

### 3. 🎙️ Artist Profiles
- Artists have distinct IDs and can publish songs and albums.
- Artist data includes genre, region, and collaboration tracking (e.g., featuring artists).

### 4. 📀 Playlist Functionality
- Users can create, modify, and delete playlists.
- Playlists track name, description, song count, and creator.
- Auto-generated playlists are supported based on liked songs.

### 5. 🔍 Advanced Search System
- Filter by song title, genre, artist, language, and duration.
- Results include album art (simulated) and artist details.
- Optimized using indexes for faster retrieval.

### 6. 🧾 Social Features (Optional)
- Friend relationships stored as weak entities.
- Users can follow friends and view their recent listening activity.

---

## 🧠 Skills Demonstrated

### 📐 Database Design
- ER Modeling with dbdiagram.io / DrawSQL
- Normalization to 3NF for consistency and scalability
- Implementation of weak entities and composite relationships

### 📄 SQL Proficiency
- Inner, left, and self joins
- Nested subqueries, aggregation (GROUP BY, HAVING)
- Conditional filtering with CASE statements
- Views, indexes, triggers (optional)

### ⚙️ Backend Integration
- CRUD APIs with Flask or Django
- ORM tools: SQLAlchemy or Django ORM
- REST endpoints for playlist/user/song management

### 🖥️ GUI (Optional)
- Built with Python Tkinter for DB navigation
- React.js option for modern single-page interface

### 📊 Performance & Optimization
- Index creation for search-heavy columns (title, artist, genre)
- Query cost analysis and tuning
- Optional OLAP-style data cubes and analytics for admin dashboards

---

## 🛠️ Tools & Technologies

| Category              | Tools & Technologies                                      |
|-----------------------|-----------------------------------------------------------|
| DBMS                  | PostgreSQL, MySQL, SQLite                                 |
| Query Language        | SQL                                                       |
| Backend Framework     | Python (Flask/Django), SQLAlchemy, Django ORM            |
| GUI (Optional)        | Tkinter (Python), React.js                                |
| Design Tools          | dbdiagram.io, DrawSQL, Lucidchart                         |
| DevOps & Scripting    | Bash, Shell Scripts, Git, GitHub                          |

---

## 🗂️ Entity-Relationship Design

### 🧱 Key Entities:
- `User` (user_id, name, email, gender, date_of_birth)
- `Artist` (artist_id, name, genre, region)
- `Song` (song_id, title, duration, language, streams, album_id, artist_id)
- `Album` (album_id, title, release_date, artist_id)
- `Playlist` (playlist_id, title, description, creator_id)
- `Subscription` (subscription_id, plan_type, start_date, user_id)
- `Friend` (user_id, friend_id) – *Weak entity*

The ER diagram models 1:M and M:N relationships (e.g., artists collaborating on songs), supports **referential integrity**, and provides a **realistic schema** for music platforms.

> Full ER diagram available in `/docs/ERD_SpotifyDBMS.png`.

---

## 💻 Usage Guide

### 🔧 Setup

1. Install PostgreSQL or MySQL.
2. Clone this repository:
   ```bash
   git clone https://github.com/Sanskritisouryaagarwal/Spotify-DBMS.git


3. Load the schema:

   ```bash
   psql -U <username> -d spotify_db -f schema.sql
   ```
4. Run bash shell menu (for automated tasks):

   ```bash
   ./spotifydbms_shell_menu.sh
   ```

### 🧪 Sample Queries

* **Get all songs by a given artist:**

  ```sql
  SELECT s.title FROM Song s JOIN Artist a ON s.artist_id = a.artist_id WHERE a.name = 'Taylor Swift';
  ```

* **Top 5 most streamed songs:**

  ```sql
  SELECT title, streams FROM Song ORDER BY streams DESC LIMIT 5;
  ```

* **Friends currently online (Optional Feature):**

  ```sql
  SELECT f.friend_id, u.name FROM Friend f JOIN User u ON f.friend_id = u.user_id WHERE f.user_id = 101;
  ```

---

## 🌐 Web & GUI Interface

### Flask/Django REST API:

* `/users/<id>` – Get user profile
* `/playlists/<user_id>` – View user playlists
* `/songs/search?genre=pop` – Filtered music search

### GUI (Optional):

* Python Tkinter interface for managing users, songs, and playlists
* React.js version available for modern frontend

---

## ☁️ Deployment

| Platform | Purpose                        |
| -------- | ------------------------------ |
| Heroku   | Optional REST API hosting      |
| Docker   | Local containerized PostgreSQL |
| AWS EC2  | For full-scale production test |

---

## 📈 Project Structure

```
Spotify_DBMS/
├── schema.sql                 # DB schema definition
├── sample_data.sql            # Initial data entries
├── queries/                   # SQL query collection
├── gui/                       # Optional GUI scripts
├── backend/                   # Flask/Django backend APIs
├── scripts/                   # Shell scripts for automation
├── docs/                      # ER diagrams, documentation
└── README.md
```

---

## 🙋‍♀️ Author

**Sanskriti Sourya**

🎓 B.Tech in Computer Science & Engineering (2021–2025)

🏫 Malaviya National Institute of Technology (MNIT), Jaipur

📧 [sanskritisourya8448@gmail.com](mailto:sanskritisourya8448@gmail.com)

🔗 [GitHub](https://github.com/Sanskritisouryaagarwal)

🔗 [LinkedIn](https://linkedin.com/in/sanskriti-sourya)

---

## 🔮 Future Enhancements

* 🔐 Role-based user authentication and admin dashboards
* 📈 Advanced reporting (top artists, genre trends)
* 🧠 Song recommendation engine (based on genres & streams)
* 🌍 Multilingual support (UTF-8 music titles & tags)
* 🎧 Integration with real audio previews via Spotify API

---

## 📜 License

This project is licensed under the [MIT License](LICENSE). You're free to use, modify, and distribute this project with attribution.

---

## 🙌 Acknowledgments

* [Spotify](https://spotify.com) for platform inspiration
* Open-source tools: PostgreSQL, dbdiagram.io, Flask, and MySQL

```

