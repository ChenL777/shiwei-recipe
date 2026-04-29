# SHIWEI · Personal Recipe Manager
## Web Technologies Assignment Documentation
### 1. App Title & Purpose
**Title:** Shiwei (食味) · Personal Recipe Manager

**Purpose:**  
Shiwei is a full-stack dynamic web application that allows users to discover, share, and manage Chinese home-cooking recipes. The platform enables registered users to post their own recipes with images, browse dishes by cuisine category, search by ingredients, and interact through comments. The design follows a Japanese minimalist aesthetic with clean typography, generous whitespace, and warm earth tones.

**Target Users:**  
Home cooks, food enthusiasts, and anyone interested in authentic Chinese cuisine.

---

### 2. Key Features

| Feature | Description | Technical Implementation |
|---------|-------------|------------------------|
| **User Authentication** | Register, login, logout with session persistence | PHP sessions, password_hash(), password_verify() |
| **Recipe CRUD** | Create, read, update, delete recipes | PDO prepared statements, file upload handling |
| **Search & Filter** | Search by title/ingredients, filter by cuisine category | SQL LIKE queries, dynamic WHERE clauses |
| **Comments System** | Logged-in users can comment on recipes | INSERT with foreign keys (recipe_id, user_id) |
| **Ranking Page** | Top recipes sorted by likes | ORDER BY likes DESC |
| **Responsive Design** | Works on desktop, tablet, mobile | CSS Grid, Flexbox, media queries |
| **Image Upload** | Users can upload recipe photos | move_uploaded_file(), file type validation |

**Cuisine Categories:** Sichuan, Cantonese, Hunan, Jiangsu, Shandong, Home Style, Quick & Easy

---

### 3. Technical Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML5, CSS3, JavaScript |
| Backend | PHP 8.x |
| Database | MySQL with PDO |
| Server | Apache (XAMPP local / InfinityFree hosting) |

---

### 4. Database Schema

**Tables Structure**

- **users** (user_id, username, email, password_hash, created_at)
- **recipes** (recipe_id, user_id [foreign key], title, category, cook_time, difficulty, image, description, ingredients, steps, likes, created_at)
- **comments** (comment_id, recipe_id [foreign key], user_id [foreign key], content, created_at)
---

### 5. Challenges & Solutions

| Challenge | Solution |
|-----------|----------|
| SQL injection prevention | Used PDO prepared statements for all database queries |
| Password security | Implemented password_hash() with bcrypt algorithm |
| Image upload validation | Checked file type (jpg/png/gif) and size limit (2MB) |
| Responsive card layout | CSS Grid with auto-fill and minmax() |
| Session persistence across pages | session_start() in header.php with $_SESSION variables |
| Hosting deployment | Migrated from localhost to InfinityFree with updated db credentials |

---

### 6. Screenshots

[Include 4-6 screenshots here:]

1. **Homepage** - Recipe grid with hero banner ![Homepage](./网站的截图/Homepage.png)
2. **Recipe Detail** - Ingredients, steps, comments![ingredinents](./网站的截图/Ingredients.png) ![steps,comments](./网站的截图/steps,%20comments.png)
3. **Add Recipe Form** - Image upload, textarea inputs![Add Recipe Form](./网站的截图/Add%20Recipe%20Form.png)
4. **Login/Register** - Form validation![login](./网站的截图/login.png) ![Register](./网站的截图/Sign%20Up.png)
5. **Ranking Page** - Top recipes with badges ![ranking page](./网站的截图/Ranking%20Page排行榜.png)
6. **Mobile View** - Responsive layout ![mobile view](./网站的截图/Mobile%20View.png)

---

### 7. File Structure


```text
WT_Personal recipe/
├── includes/
│   ├── db.php          # Database connection (PDO)
│   ├── functions.php   # Helper functions
│   ├── header.php      # Navigation + session start
│   └── footer.php      # Footer template
├── css/
│   └── style.css       # All styles (responsive)
├── js/
│   └── app.js          # Client-side validation
├── uploads/            # User-uploaded images
├── sql/
│   └── database.sql    # Schema + sample data
├── index.php           # Homepage
├── register.php        # User registration
├── login.php           # User login
├── logout.php          # Session destroy
├── add.php             # Create recipe
├── edit.php            # Update recipe
├── delete.php          # Delete recipe
├── view.php            # Recipe detail + comments
├── recipes.php         # Search + list
├── ranking.php         # Top recipes
└── README.md           # Setup instructions
```

---

### 8. Live URL & Repository

- **Hosted URL:** http://shiwei-recipe.rf.gd

- **GitHub:** https://github.com/ChenL777/shiwei-recipe/tree/main

---
Team name ：Personal Recipe Management

Student 1: [Chen Li]   ID:[2024020134]

Student 2: [Zhuo Chen]   ID: [2024020127]  

Date: April , 30, 2026
==