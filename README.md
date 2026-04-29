<<<<<<< HEAD
# SJB Institute of Technology Bangalore – 560060 Elective Opt-In System

> **Professional Elective Management System for SJB Institute of Technology**
>
> A production-ready, comprehensive academic allocation platform with CSV import, PDF generation, and professional design.

---

## ✨ Key Features

- **Professional Design**: Times New Roman typography with white/blue institutional theme
- **Smart Allocation**: First-come-first-served allocation based on submission time
- **CSV Import System**: Bulk data import for departments, students, courses, and admin users
- **PDF Generation**: Professional allocation certificates and summary reports
- **Real-time Updates**: Live seat availability tracking via AJAX
- **Student Portal**: Browse courses, submit preferences, view allocations, download PDFs
- **Admin Dashboard**: Run allocation, manual overrides, export reports, system diagnostics
- **Waitlist Management**: Automatic promotion when seats become available
- **Mobile Responsive**: Works perfectly on desktop, tablet, and mobile devices
- **Production Ready**: Secure configuration, logging, and error handling

---

## 🚀 Quick Start

### 1. Setup Environment

```bash
# Create and activate virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Apply migrations
python manage.py migrate
```

### 2. Import Your Data

**CSV Import (Use Your Own Data)**
```bash
# Import departments
python manage.py import_csv departments your_departments.csv

# Import admin users
python manage.py import_csv admins your_admins.csv

# Import students
python manage.py import_csv students your_students.csv

# Import courses
python manage.py import_csv courses your_courses.csv
```

**Note**: Create your CSV files following the format specifications in `CSV_IMPORT_FORMAT.md`

### 3. Run Server

```bash
python manage.py runserver
```

Open → **http://127.0.0.1:8000**

---

## 🔐 User Credentials

| Role    | Username      | Password   |
|---------|---------------|------------|
| Admin   | Use your imported admin credentials | |
| Student | Use your imported student credentials | |

---

## 📚 Documentation

- **[SETUP_INSTRUCTIONS.md](SETUP_INSTRUCTIONS.md)** - Complete setup guide
- **[DATA_IMPORT_GUIDE.md](DATA_IMPORT_GUIDE.md)** - How to import your data
- **[CSV_IMPORT_FORMAT.md](CSV_IMPORT_FORMAT.md)** - CSV file format specifications

---

## 📁 Project Structure

```
elective_optin/
├── sjbit_elective/                  # Django project settings
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── electives/                       # Main application
│   ├── models.py                   # Database models
│   ├── views.py                    # Application logic
│   ├── forms.py                    # Forms
│   ├── utils.py                    # Allocation engine
│   ├── urls.py                     # URL routing
│   ├── admin.py                    # Django admin
│   └── management/commands/
│       └── import_csv.py           # CSV import command
├── templates/electives/             # HTML templates
│   ├── base.html
│   ├── home.html
│   ├── catalog.html
│   ├── course_detail.html
│   ├── dashboard.html
│   ├── preferences.html
│   ├── admin_panel.html
│   ├── login.html
│   └── register.html
├── static/
│   ├── css/styles.css              # Professional UI theme
│   └── js/ajax_seats.js            # Real-time AJAX updates
├── your_data/                       # Your CSV data files
│   ├── your_departments.csv
│   ├── your_students.csv
│   ├── your_courses.csv
│   └── your_admins.csv
├── media/                           # Uploaded files
├── requirements.txt
├── README.md
├── SETUP_INSTRUCTIONS.md
├── DATA_IMPORT_GUIDE.md
└── CSV_IMPORT_FORMAT.md
```

---

## 🎨 Professional Design

Institutional design featuring:
- **Typography**: Times New Roman for professional appearance
- **Header**: "SJB Institute of Technology Bangalore – 560060 Elective Opt-In System"
- **Color Scheme**: Professional white background with blue accents (#1e3a8a, #3b82f6)
- **Layout**: Clean card-based design with proper spacing and shadows
- **Navigation**: Collapsible sidebar with hamburger menu for mobile
- **Responsive**: Fully responsive design that works on all devices
- **Accessibility**: High contrast colors and proper font sizes

---

## 📊 CSV Data Import

The system uses CSV files for data management:

### Import Order:
1. **Departments** - Department codes and names
2. **Admins** - Admin user accounts
3. **Students** - Student records with CGPA, semester
4. **Courses** - Course catalog with seats, prerequisites

### CSV Templates:
Create your CSV files following the format specifications in `CSV_IMPORT_FORMAT.md`.

### Import Commands:
```bash
# Import departments
python manage.py import_csv departments your_departments.csv

# Import admin users
python manage.py import_csv admins your_admins.csv

# Import students
python manage.py import_csv students your_students.csv

# Import courses
python manage.py import_csv courses your_courses.csv
```

See **[CSV_IMPORT_FORMAT.md](CSV_IMPORT_FORMAT.md)** for detailed format specifications.

---

## 🎯 How It Works

### For Students:
1. **Browse** course catalog with real-time seat availability
2. **Add** courses to preferences (max 5)
3. **Rank** preferences by dragging and dropping
4. **Submit** preferences before deadline
5. **View** allocation results and waitlist position

### For Administrators:
1. **Import** student/course data via CSV
2. **Monitor** preference submissions
3. **Run** allocation algorithm
4. **View** occupancy dashboard
5. **Export** reports in CSV format
6. **Override** allocations manually if needed

### Allocation Algorithm:

**First-Come-First-Served (FCFS)**

The allocation system is based purely on submission timing:

- **Submission Time**: Students who submit preferences earlier get priority
- **Fair and Simple**: No complex scoring - just chronological order
- Preferences allocated in order of rank (1st choice first, then 2nd, etc.)
- Automatic waitlist for full courses
- Auto-promotion when seats become available

**How it works:**
1. For each course, gather all pending preferences
2. Sort by submission timestamp (earliest first)
3. Allocate seats in chronological order
4. Remaining students go to waitlist
5. Students already allocated to a higher-ranked preference are skipped

---

## ✅ Core Features

| Feature | Status |
|---|---|
| Professional Times New Roman design | ✅ |
| SJB Institute branding and header | ✅ |
| Department course catalog with filters | ✅ |
| College-wide open elective publishing | ✅ |
| Constraint-based elective opting | ✅ |
| Real-time AJAX seat counter | ✅ |
| CSV import/export system | ✅ |
| PDF generation for certificates | ✅ |
| Responsive Bootstrap UI | ✅ |
| Drag-and-drop preferences | ✅ |
| Waitlist management | ✅ |
| Admin override functionality | ✅ |
| System diagnostics page | ✅ |
| Production-ready configuration | ✅ |

---

## 🛠️ Technology Stack

- **Backend**: Django 5.1.4
- **Database**: SQLite (development) / PostgreSQL (production)
- **Frontend**: HTML, CSS, JavaScript
- **UI Framework**: Bootstrap 5.3.2
- **Icons**: Bootstrap Icons 1.11.3
- **Fonts**: Inter, Syne (Google Fonts)

---

## 🔧 Management Commands

```bash
# Import data from CSV
python manage.py import_csv <model> <file.csv>

# Example:
python manage.py import_csv departments your_departments.csv
python manage.py import_csv students your_students.csv
python manage.py import_csv courses your_courses.csv
python manage.py import_csv admins your_admins.csv
```

---

## 🧪 Verification Checklist

```
✓ Server runs at http://127.0.0.1:8000
✓ Course catalog displays with filters
✓ Student can submit preferences for eligible courses
✓ Eligibility validation prevents invalid selections
✓ AJAX seat counter updates live (every 20s)
✓ Add-to-preference via AJAX (no page reload)
✓ Drag-and-drop preference reorder works
✓ Allocation algorithm runs successfully
✓ Waitlist students get position numbers
✓ Admin can override allocations
✓ CSV export works with filters
✓ CSV import works for all data types
✓ Mobile responsive design works
✓ Professional UI theme applied
```

---

## 📝 Production Deployment

For production deployment:

1. Change `DEBUG = False` in settings.py
2. Set `SECRET_KEY` from environment variable
3. Configure `ALLOWED_HOSTS`
4. Use PostgreSQL/MySQL instead of SQLite
5. Set up static file serving (`collectstatic`)
6. Configure email backend
7. Set up HTTPS/SSL
8. Import real data via CSV
9. Change all default passwords
10. Set up regular database backups

---

## 📧 Contact

**Institution**: SJBIT (Sri Jayachamarajendra College of Engineering)  
**System**: Elective Option App  
**Version**: 2.0  
**Last Updated**: April 2026

For support or questions, refer to the documentation files or contact the system administrator.

---

## 📄 License

Developed for SJBIT educational purposes.

---

## 🤝 Contributing

This is an educational project for SJBIT. For modifications or improvements, contact the system administrator.

## Data Import Instructions

To import your data from CSV files, run the following commands **one by one** (not with `>>`):

```bash
python manage.py import_csv departments your_departments.csv
python manage.py import_csv admins your_admins.csv
python manage.py import_csv students your_students.csv
python manage.py import_csv courses your_courses.csv
```

Or run the batch file:
```bash
setup_data.bat
```

## CSV File Format

1. **your_departments.csv** - Department codes and names
2. **your_admins.csv** - Admin users with superuser privileges
3. **your_students.csv** - Student data with department codes
4. **your_courses.csv** - Course data with department codes

**Note**: The courses CSV file has `[Upload Faculty Name]` placeholders for instructor names. Replace these with actual faculty names when uploading your data.
=======
# Django-semihack-starter
Starter template for semi-hackathon
# 🚀 Django Semi-Hackathon: [Team Name]

## 📋 Project Details
- **Theme**: [e.g., TH-03: Elective Choice System]
- **Team Members**: @student1, @student2, @student3, @student4
- **Live URL**: [To be filled after deployment]

## ✅ Submission Checklist
- [ ] Code runs with `pip install -r requirements.txt`
- [ ] `DEBUG=False` in production settings
- [ ] Working AJAX endpoint (tested live)
- [ ] CSV/PDF export functional
- [ ] CO-SDG mapping table completed below
- [ ] 150-word SDG justification included

## 🎯 CO-SDG Mapping Table
| Course Outcome | How This Project Demonstrates It | SDG Target Addressed |
|---------------|----------------------------------|---------------------|
| CO1: MVT Architecture | [Brief explanation] | SDG 4.5 |
| CO2: Models & Forms | [Brief explanation] | SDG 9.5 |
| ... | ... | ... |

## 📦 Setup Instructions
```bash
git clone [your-repo-url]
cd [repo-name]
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```
### ✅ Pre-Deploy Checklist
- [ ] `DEBUG = False` in `settings.py`
- [ ] `STATIC_ROOT` configured
- [ ] `ALLOWED_HOSTS` includes cloud domain
- [ ] `gunicorn` in `requirements.txt`
- [ ] Local `python manage.py collectstatic` ran successfully
## 🚀 Deployment Guide (Free Tier: Render)
*Follow these steps on Event Day to make your app publicly accessible for judging.*

1. **Sign Up & Connect**
   - Go to [render.com](https://render.com) → Sign up with GitHub
   - Authorize Render to access your repos

2. **Create Web Service**
   - Click `New +` → `Web Service` → Connect this repo
   - Fill in:
     - **Name**: `team-xyz-app`
     - **Region**: `Oregon` or `Frankfurt` (closest to India)
     - **Branch**: `main`
     - **Build Command**: `pip install -r requirements.txt && python manage.py collectstatic --noinput`
     - **Start Command**: `gunicorn project_name.wsgi` *(replace `project_name` with your actual Django folder)*

3. **Environment Variables (Critical)**
   Click `Advanced` → `Add Environment Variable`:
   | Key | Value |
   |-----|-------|
   | `SECRET_KEY` | Generate at [miniwebtool.com/django-secret-key-generator](https://miniwebtool.com/django-secret-key-generator/) |
   | `DEBUG` | `False` |
   | `ALLOWED_HOSTS` | `*.onrender.com, localhost, 127.0.0.1` |

4. **Deploy & Verify**
   - Click `Create Web Service` → Wait 2–4 mins for build
   - Once live, copy the `https://...onrender.com` URL
   - ✅ Test: Open URL, check CSS/JS loads, test AJAX endpoint, download CSV/PDF
   - 📝 Update this `README.md` with your live URL

### 🚨 Troubleshooting Quick Fixes
| Issue | Fix |
|-------|-----|
| `Application Error` | Ensure `gunicorn` is in `requirements.txt` & `wsgi` path matches your project folder |
| Broken CSS/JS | Add `STATIC_ROOT = BASE_DIR / "staticfiles"` to `settings.py` |
| `DisallowedHost` | Verify `ALLOWED_HOSTS` env var or `settings.py` matches your Render domain |
| DB locked/migrations fail | Free tier uses SQLite by default. It's fine for hackathon demos. No extra config needed. |

> 💡 **Note:** After deployment, every `git push` to `main` auto-triggers a rebuild. No manual server restarts needed.
>>>>>>> 2a55c0b7423e0e5327e885164cfe16ed0f77dc77
