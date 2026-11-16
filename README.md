# Bank REST API in Django

A Django project with 4 models and a REST API (Django REST Framework).

## Tech stack

- Python 3
- Django
- Django REST Framework
- psycopg2 (PostgreSQL)
- Pillow
- Database: PostgreSQL

## Project structure

- `bank_rest_api/`: project settings and root URLs
- `account_app/`: Django app
- `transaction_app/`: Django app
- Tests: `account_app/tests.py`, `transaction_app/tests.py`

## Data model

| Model | App | Fields |
|---|---|---|
| `Client` | `account_app` | cin, name, familyName, email, photo, client_documents |
| `Bank` | `account_app` | name, address, creationDate, website |
| `Account` | `account_app` | rib, balance, client, creation_date, accountType, bank |
| `Transaction` | `transaction_app` | amount, date, transactionType, account, transfer_to_account |

## URL routes

Declared in `urls.py`:

- `/accounts/ (router)`
- `/banks/ (router)`
- `/clients/ (router)`
- `/blog/`
- `/account_app/`
- `/transaction_app/`
- `/transactions/ (router)`

## How to run

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

`settings.py` is configured for PostgreSQL: create the database and use your own credentials before running `migrate`.

Then open `http://127.0.0.1:8000/`.

---

Author: [Chaouki Bayoudhi](https://github.com/ChaoukiBayoudhi)
