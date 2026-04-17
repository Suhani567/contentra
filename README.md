# Contentra (Content Management System)

## Overview
A lightweight, MVC-based Content Management System (CMS) built with Node.js. Features an admin panel for managing pages, blog posts, users, templates, files, comments, and zones. Designed for simplicity and extensibility.

**Version:** 2.0.0  
**Author:** David Pirek (http://www.davidpirek.com)  
**Repository:** https://github.com/dpirek/nodejs-mvc-cms.git

## Features
- **Admin Panel**: Full-featured dashboard at `/admin` for CRUD operations on:
  - Pages
  - Blog posts
  - Users
  - Templates
  - Files (with upload)
  - Comments
  - Zones (custom content areas)
- **Frontend**: Dynamic page rendering with blog and page support.
- **JSON APIs**: REST-like endpoints under `/json` for admin operations.
- **Rich Text Editing**: TinyMCE integration.
- **Code Editor**: Ace editor for templates.
- **Responsive Design**: Bootstrap-based UI.
- **File Uploads**: Formidable-powered uploads.
- **MongoDB Backend**: Via Mongolian driver.
- **Templating**: jQuery Templates (jqtpl).

## Tech Stack
- **Runtime**: Node.js (>=0.6.2)
- **Web Framework**: Custom lightnode (embedded file server/routing)
- **Database**: MongoDB
- **Frontend**: jQuery, Bootstrap, TinyMCE, Ace Editor
- **Dependencies**:
  ```
  mongolian: MongoDB driver
  jqtpl: jQuery Templates
  formidable: Form handling/uploads
  lightnode: Routing/server
  ```

## Quick Start

### Prerequisites
- Node.js >=0.6.2
- MongoDB (running locally or remote)

### Installation
1. Clone the repo:
   ```
   git clone https://github.com/dpirek/nodejs-mvc-cms.git
   cd nodejs-mvc-cms
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Configure MongoDB in `config.js`:
   ```js
   exports.config = {
     // ...
     dbConnection: 'mongodb://localhost:27017',
     dbName: 'your_db_name',
     dbUserName: '', // if auth required
     dbPassword: '',
     portNumber: 8080
   };
   ```

4. Run the server:
   ```
   npm start
   ```
   Or:
   ```
   node app/server.js
   ```

5. Open http://localhost:8080/

### Initial Setup
- Visit http://localhost:8080/admin/install.html to run the installer.
- Login at http://localhost:8080/admin/login.html (default credentials set during install).

## Project Structure
```
.
├── app/
│   ├── server.js          # Entry point (HTTP server)
│   ├── admin/             # Admin panel (HTML/JS/CSS)
│   ├── controllers/       # MVC controllers (Blog, Page, User, etc.)
│   ├── views/             # MVC views (HTML templates)
│   ├── models/            # Data models
│   ├── lib/               # Utilities (routing, DB access, etc.)
│   └── content/           # Static assets (Bootstrap, jQuery, etc.)
├── config.js              # App configuration
├── package.json           # Dependencies & scripts
└── README.md              # This file
```

## Usage
- **Public Site**: Browse pages and blog at root (e.g., /blog, /page).
- **Admin**: Manage content via `/admin`.
  - Dash: Dashboard overview.
  - Blog/Page/User/etc.: List/Create/Edit/View.
- **APIs**: `/json/blog`, `/json/page`, etc. for AJAX operations.
- **Uploads**: POST to `/upload`.

## Development
- Edit controllers/views in `app/admin/controllers/` and `app/admin/views/`.
- Custom templates in admin Templates section.
- Extend routes in `app/lib/routes.js` and `app/lib/json.routes.js`.
