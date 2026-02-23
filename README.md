# 🚂 Railway Management System

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-2.3.3-000000?style=for-the-badge&logo=flask&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

### 🎯 A Complete End-to-End Railway Ticket Booking & Management System

*Built with Flask, MySQL, and modern web technologies to provide seamless railway reservation experience*

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Documentation](#-detailed-documentation)

</div>

---

## 📋 Table of Contents

- [About the Project](#-about-the-project)
- [Features](#-features)
- [Technology Stack](#️-technology-stack)
- [Project Architecture](#️-project-architecture)
- [File Structure](#-file-structure)
- [Installation](#-installation)
- [Database Setup](#-database-setup)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [Quick Start Commands](#-quick-start-commands)

---

## 📖 About the Project

The **Railway Management System** is a full-stack web application that replicates the functionality of real-world railway reservation systems like IRCTC. It provides a complete booking experience from user registration to ticket generation, including features like PNR status checking, train running status, ticket cancellation, and administrative controls.

### 🎯 Project Objectives

- **Simplify Ticket Booking**: Intuitive interface for searching and booking train tickets
- **Real-time Information**: Live seat availability and train running status
- **Automated Notifications**: Email confirmations and ticket delivery
- **Administrative Control**: Ticket release management and system monitoring
- **Scalable Architecture**: Modular Flask application with MySQL backend

---

## ✨ Features

### 👥 Passenger Features

| Feature | Description |
|---------|-------------|
| 🔐 **User Registration** | 3-step registration with personal details, security questions |
| 🔑 **Secure Login** | Session-based authentication with password recovery |
| 🔍 **Train Search** | Search by source station, destination, date, and category |
| 🎫 **Ticket Booking** | Book General/Tatkal tickets with multiple passengers |
| 🍽️ **Food Service** | Choose veg/non-veg meals with smart pricing |
| 📧 **Email Tickets** | Automatic ticket delivery to registered email |
| 🔢 **PNR Status** | Check booking status using PNR number |
| ❌ **Cancellation** | Cancel General tickets (Tatkal non-cancellable) |
| 🚄 **Running Status** | Track train location in real-time |
| 📄 **PDF Tickets** | Download tickets as PDF documents |

### 👨‍💼 Admin Features

| Feature | Description |
|---------|-------------|
| 🔐 **Admin Login** | Secure administrative access portal |
| 🎟️ **Release General Tickets** | Open booking for specific dates |
| ⚡ **Release Tatkal Tickets** | Enable Tatkal booking for dates |
| 📊 **Seat Management** | Control availability across classes |
| 🗓️ **Date Controls** | Validate train running days |

### 🛠️ System Features

- ✅ **Multiple Train Classes**: Sleeper (SL), 3AC, 2AC, 1AC, Chair Car (CC)
- ✅ **Dynamic Fare Calculation**: Automatic pricing based on distance and class
- ✅ **Real-time Seat Tracking**: Live availability updates
- ✅ **Waitlist Management**: Queue system when seats are full
- ✅ **Session Management**: Secure user sessions with Flask
- ✅ **Form Validation**: Client and server-side validation
- ✅ **Responsive UI**: Works on all devices and screen sizes
- ✅ **Modern Design**: Clean interface with Font Awesome icons

---

## 🛠️ Technology Stack

### Backend Technologies

```
Python 3.8+          → Core programming language
Flask 2.3.3          → Lightweight web framework
MySQL 8.0            → Relational database management
Flask-MySQLdb        → MySQL database adapter for Flask
mysql-connector      → Python MySQL database driver
Flask-Mail 0.9.1     → Email sending functionality
```

### Frontend Technologies

```
HTML5                → Structure and semantic markup
CSS3                 → Styling with gradients, animations, flexbox
JavaScript (Vanilla) → Client-side interactivity and validation
Font Awesome 6.5     → Icon library (1000+ icons)
Google Fonts         → Poppins font family
```

### Development Tools

```
MySQL Workbench      → Database design and E-R modeling
VS Code / PyCharm    → Code editor
Git                  → Version control
pip                  → Python package manager
Virtual Environment  → Isolated Python environment
```

---

## 🏗️ Project Architecture

```
┌─────────────────────────────────────────────────────┐
│                   User Browser                       │
│        (HTML/CSS/JavaScript Frontend)                │
└──────────────────┬──────────────────────────────────┘
                   │ HTTP Requests (GET/POST)
                   ▼
┌─────────────────────────────────────────────────────┐
│              Flask Application (web.py)              │
│  ┌─────────────────────────────────────────────┐   │
│  │         Routes & Controllers (27)            │   │
│  │  /login, /register, /search, /book, etc.    │   │
│  └─────────────────┬───────────────────────────┘   │
│                    │                                 │
│  ┌─────────────────▼───────────────────────────┐   │
│  │          Session Management                  │   │
│  │      (Flask Session, User State)             │   │
│  └─────────────────┬───────────────────────────┘   │
│                    │                                 │
│  ┌─────────────────▼───────────────────────────┐   │
│  │       Flask-Mail (Email Service)             │   │
│  │    SMTP Configuration & Notifications        │   │
│  └──────────────────────────────────────────────┘   │
└──────────────────┬──────────────────────────────────┘
                   │ SQL Queries
                   ▼
┌─────────────────────────────────────────────────────┐
│            MySQL Database (Railway)                  │
│  ┌──────────────────────────────────────────────┐  │
│  │  13 Tables: Userdetails, Traindetails,       │  │
│  │  Route, Ticket, Station, Admin, etc.         │  │
│  └──────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────┘
```


---

## 📁 File Structure

### 📂 Complete Directory Layout

```
Railway-Management-System-main/
│
├── 📁 Templates/                     # HTML Template Files (19 files)
│   ├── 🏠 home.html                  # Landing page with PNR search
│   ├── 🔑 login.html                 # User login page
│   ├── 📝 registration1.html         # Registration: Credentials step
│   ├── 📝 registration2.html         # Registration: Personal details step
│   ├── 📝 registration3.html         # Registration: Confirmation page
│   ├── 🔍 search.html                # Train search & results display
│   ├── 🔢 passengers.html            # Passenger quantity selection
│   ├── 👤 npass.html                 # Passenger details entry form
│   ├── 🎫 ticket.html                # Ticket display after booking
│   ├── 🔢 pnr.html                   # PNR status enquiry page
│   ├── ❌ cancel.html                # Ticket cancellation page
│   ├── 🚄 runningstatus.html         # Train running status tracker
│   ├── 🔐 adminlogin.html            # Admin login portal
│   ├── ⚙️ adminrights.html           # Admin dashboard/control panel
│   ├── 🎟️ releaseg.html              # Release general tickets
│   ├── ⚡ releaset.html              # Release Tatkal tickets
│   ├── 📰 travelupdates.html         # Travel news and updates
│   ├── 🔒 privacypolicy.html         # Privacy policy page
│   └── 📜 t&c.html                   # Terms and conditions
│
├── 📁 screenshots/                   # Application screenshots for README
│   ├── 📷 homepage.png               # Main landing page
│   ├── 📷 login.png                  # Login interface
│   ├── 📷 registration.png           # Registration process
│   ├── 📷 search.png                 # Train search page
│   ├── 📷 search_results.png         # Search results display
│   ├── 📷 passenger_details.png      # Passenger form
│   ├── 📷 ticket.png                 # Generated ticket
│   ├── 📷 pnr_status.png             # PNR checking
│   ├── 📷 running_status.png         # Train tracking
│   ├── 📷 admin_login.png            # Admin portal
│   ├── 📷 admin_dashboard.png        # Admin controls
│
├── 🐍 web.py                         # Main Flask application (826 lines)
├── 🗄️ Railway database.sql           # MySQL database schema & data
├── 📊 Railway.mwb                    # MySQL Workbench model file
├── 📦 requirements.txt               # Python dependencies
└── 📖 README.md                      # This documentation file
```

### 📂 Folder Details & Contents

#### 1. 📁 `Templates/` Folder
**Purpose**: Contains all HTML template files for the Flask application  
**File Count**: 19 HTML files  
**Technology**: HTML5 with Jinja2 templating engine

<details>
<summary>📄 Detailed File Descriptions (Click to expand)</summary>

| File Name | Route | Description |
|-----------|-------|-------------|
| `home.html` | `/` | Landing page with hero slider, navigation menu, PNR quick search |
| `login.html` | `/login` | User authentication form with username/password |
| `registration1.html` | `/register1` | First step: Username, password, security question |
| `registration2.html` | `/register2` | Second step: Personal details (name, DOB, occupation) |
| `registration3.html` | `/register3` | Confirmation page after successful registration |
| `search.html` | `/search` | Main search interface: station selection, date picker, category |
| `passengers.html` | `/passengers` | Select number of passengers for booking |
| `npass.html` | `/npass` | Enter passenger details: name, age, gender, food |
| `ticket.html` | `/ticket` | Display confirmed ticket with PNR and details |
| `pnr.html` | `/pnr` | PNR enquiry form and status display |
| `cancel.html` | `/cancel` | Cancel booked tickets (General only) |
| `runningstatus.html` | `/runningstatus` | Track train location and running status |
| `adminlogin.html` | `/adminlogin` | Administrative portal login page |
| `adminrights.html` | `/adminrights` | Admin dashboard with ticket release options |
| `releaseg.html` | `/releaseg` | Release general tickets for specific dates |
| `releaset.html` | `/releaset` | Release Tatkal tickets for specific dates |
| `travelupdates.html` | `/travelupdates` | Latest travel news and announcements |
| `privacypolicy.html` | `/privacypolicy` | Privacy policy and data handling |
| `t&c.html` | `/t&c` | Terms and conditions of service |

</details>

#### 2. 📁 `screenshots/` Folder
**Purpose**: Stores application screenshots for documentation  
**Usage**: Referenced in README.md to showcase features  
**Format**: PNG images (recommended 1366x768px or 1920x1080px)

#### 3. 🐍 `web.py` File
**Purpose**: Main Flask application backend  
**Lines of Code**: 826 lines  
**Key Components**:
- Flask routes (27 endpoints)
- Database connections (MySQL)
- Email configuration (Flask-Mail)
- Session management
- Business logic for booking, search, cancellation
- Admin controls

#### 4. 🗄️ `Railway database.sql` File
**Purpose**: Complete MySQL database schema with sample data  
**Contains**:
- CREATE TABLE statements for 13 tables
- INSERT statements for stations, trains, routes
- Initial admin credentials
- Sample pricing data

#### 5. 📊 `Railway.mwb` File
**Purpose**: MySQL Workbench model for E-R diagram  
**Usage**: Visual database design and relationship mapping  
**Tool**: Opens with MySQL Workbench 8.0+

#### 6. 📦 `requirements.txt` File
**Purpose**: Python package dependencies  
**Usage**: `pip install -r requirements.txt`  
**Contains**:
```
Flask==2.3.3
flask-mysqldb==1.0.1
mysql-connector-python==8.1.0
flask-mail==0.9.1
```
- **JavaScript** - Interactive functionality
- **Font Awesome 6.5** - Icons
- **Google Fonts (Poppins)** - Typography

### Database
- **MySQL 8.0** - Relational database management

##  Installation

### Prerequisites
```bash
- Python 3.8 or higher
- MySQL 8.0 or higher  
- pip (Python package manager)
- Web browser (Chrome, Firefox, Edge, Safari)
```

### Step-by-Step Installation

1. **Clone the Repository**
```bash
git clone https://github.com/yourusername/Railway-Management-System.git
cd Railway-Management-System
```

2. **Create Virtual Environment (Recommended)**
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/Mac
python3 -m venv venv
source venv/bin/activate
```

3. **Install Dependencies**
```bash
pip install -r requirements.txt
```

**Required Packages:**
- Flask==2.3.3
- flask-mysqldb==1.0.1
- mysql-connector-python==8.1.0
- flask-mail==0.9.1


##  Database Setup

### Create & Import Database

1. **Start MySQL Server**
```bash
# Windows: Start MySQL service from Services app
# Linux: sudo service mysql start
# Mac: mysql.server start
```

2. **Create Database**
```sql
CREATE DATABASE Railway;
```

3. **Import Schema**
```bash
mysql -u root -p Railway < "Railway database.sql"
```

**Database Tables (13 total):**
- `Userdetails` - User accounts
- `Admin` - Admin credentials
- `Station` - Available stations
- `Traindetails` - Train information
- `Route` - Train routes
- `Generalseatavailability` - General ticket seats
- `Tatkalseatavailability` - Tatkal ticket seats
- `Generalrouteprices` - General pricing
- `Tatkalrouteprices` - Tatkal pricing
- `Passengerdetails` - Passenger info
- `Ticket` - Booking records
- `Traincategory` - Train categories
- `Foodservice` - Meal options

##  Configuration

### 1. Database Connection
Edit `web.py` (lines 24-26):
```python
connection = mysql.connector.connect(
    host="localhost",
    user="root",
    password="YOUR_MYSQL_PASSWORD",  #  Change this
    database="Railway"
)
```

### 2. Email Configuration
Edit `web.py` (lines 15-21):
```python
app.config['MAIL_SERVER'] = 'smtp.gmail.com'
app.config['MAIL_PORT'] = 465
app.config['MAIL_USERNAME'] = 'your-email@gmail.com'      #  Change this
app.config['MAIL_PASSWORD'] = 'your-app-password'          #  Change this
app.config['MAIL_USE_TLS'] = False
app.config['MAIL_USE_SSL'] = True
```

##  Usage

### Start Application
```bash
python web.py
```
Application runs at: **http://localhost:5000**

### Initial Setup (IMPORTANT!)

**Admin Login Required First:**
- Username: `Ram`
- Password: `1234`

1. Go to http://localhost:5000/adminlogin
2. Release General Tickets for dates
3. Release Tatkal Tickets for dates
4. Then users can start booking

### User Journey
1. **Register**  Create account (3 steps)
2. **Login**  Access system
3. **Search**  Find trains
4. **Book**  Select seats & enter details
5. **Confirm**  Get ticket & email
6. **PNR**  Check status
7. **Cancel**  Cancel tickets (General only)




##  Quick Start Commands

```bash
# 1. Clone & Navigate
git clone <repo-url>
cd Railway-Management-System

# 2. Setup Database
mysql -u root -p
CREATE DATABASE Railway;
USE Railway;
SOURCE Railway\ database.sql;

# 3. Install & Run
pip install -r requirements.txt
python web.py

# 4. Access Application
# Browser: http://localhost:5000
```

---



 

