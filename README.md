# WebShield Analyzer (Django Starter)

Student-level Django starter for:
- Landing page
- Login / Register
- Profile
- User dashboard and scan workflow
- Admin analytics + governance + operations
- OWASP ZAP integration

## 1) Setup
```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate

pip install -r requirements.txt
```

## 2) Configure environment
Copy `.env.example` to `.env` and adjust values:
```bash
cp .env.example .env
```

Important values:
- `SECRET_KEY`
- `DEBUG`
- `ALLOWED_HOSTS`
- `ZAP_BASE_URL`
- `ZAP_API_KEY`
- `ZAP_VERIFY_SSL`

## 3) Run migrations
```bash
python manage.py migrate
```

## 4) Create bootstrap admin (one-time)
```bash
python manage.py bootstrap_admin
```

Optional overrides:
```bash
python manage.py bootstrap_admin --username admin --email admin@webshield.local --password Admin@12345 --reset-password
```

## 5) Run server
```bash
python manage.py runserver
```
Open: http://127.0.0.1:8000/

## Main routes
- User dashboard: `http://127.0.0.1:8000/dashboard/`
- Start scan: `http://127.0.0.1:8000/scan/new/`
- All scans: `http://127.0.0.1:8000/scans/`

Admin (staff):
- Analytics: `http://127.0.0.1:8000/admin-analytics/`
- User management: `http://127.0.0.1:8000/admin-users/`
- Governance: `http://127.0.0.1:8000/admin-governance/`
- System ops: `http://127.0.0.1:8000/admin-system/`
- Django admin: `http://127.0.0.1:8000/admin/`

## Notes
- Tailwind, Alpine.js, and Chart.js are CDN-based.
- ZAP API endpoints used:
  - `/JSON/ascan/action/scan/`
  - `/JSON/ascan/view/status/`
  - `/JSON/core/view/alerts/`
