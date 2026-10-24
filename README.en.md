# LiteratureRecommendationSystem

[简体中文](README.md) | **English**

Django literature-recommendation coursework with user and article pages and a PyTorch/FAISS vector recommendation prototype. Configuration work is required before running in a new environment.

## Requirements

Python and MySQL. requirements.txt lists only Django 4.2.9 and Pillow. The recommendation module also needs compatible PyTorch/FAISS packages and complete article metadata.

## Get the repository

```bash
git clone https://github.com/RoxyXu151/LiteratureRecommendationSystem.git
cd LiteratureRecommendationSystem
```

Private repositories require GitHub authentication. Relative paths and steps below start from this repository.

## Setup and entry point

```bash
python -m venv .venv
# Activate the virtual environment.
python -m pip install -r requirements.txt
```

Activate with `.venv\Scripts\Activate.ps1` in PowerShell or `source .venv/bin/activate` on Linux/macOS.

## Configuration and preparation

manage.py, system/settings.py, and WSGI configuration still reference day16, while the current settings package is system. Align those module paths and configure MySQL plus its driver before running. This README update does not fix those source-code issues.

## Usage and outputs

After fixing configuration, run python manage.py migrate, python manage.py createsuperuser, and python manage.py runserver, then visit local port 8000. deploy/deploy.py reads article CSV and two embedding files by relative path; use the matching working directory and consistent article/vector IDs.

## Repository map

- [manage.py](manage.py)
- [system](system)
- [app01](app01)
- [deploy](deploy)
- [requirements.txt](requirements.txt)
- [Original detailed material](README.reference.md): historical design, screenshots, and notes are retained; use the checked setup guidance above where it differs.

## Verification and troubleshooting

After configuration, run python manage.py check and manually verify login, article pages, and recommendation loading. No comprehensive test result is claimed. Missing articles.csv or optional dependencies prevents the recommendation module from starting.

## Maintenance and contributions

Keep both READMEs in sync when functionality or usage changes. Report reproducible steps, environment versions, and sanitized logs. Describe the verification actually performed with each change.

## License and attribution

See [LICENSE](LICENSE) for repository terms. Third-party code, data, models, papers, and artwork retain their own licenses and attribution.
