# Git setup

1. `git clone https://github.com/Matt-Murungi/Mrembo.git`
2. `cd mrembo`


# Server Installation

1. Install pipenv `pip install pipenv`
1. Set up the pipenv `pipenv install --dev` to install dependencies
1. `pipenv shell` to active the virtual environment
1. Run database migrations `python manage.py migrate`
1. Create a superuser with `python manage.py createsuperuser`
1. Run dev server `python manage.py runserver 0.0.0.0:8000`
1. Browse to http://localhost:8000/
1. Confirm that you can log in to the admin at http://localhost:8000/admin


# Frontend Installation

1. Install nodejs - tested on v8.1.2
2. Install yarn
3. `cd frontend/dashboard`
4. `yarn`

### Commands

 * `yarn start` - To start development server

# Resetting local postgres db (MacOS)

* psql postgres
    * DROP SCHEMA public CASCADE;
    * CREATE SCHEMA public;
    * GRANT ALL ON SCHEMA public TO postgres;
    * GRANT ALL ON SCHEMA public TO public;

* DJANGO_USE_POSTGRES=1 ./manage.py dbshell < backup.sql

# Commit message format

## Template

<type>(<scope>): <subject>

Motivation
<why this change is needed and expected results>

Implementation
<how the change was achieved>


Closes #<issue # if appropriate>

## Key

type: 
  - feat (feature)
    - new or modified functionality due to new or changed spec
  - fix (bug fix)
    - only for fixes to code that previously didn't meet the spec, not a changed spec
  - docs (documentation)
  - style (formatting, missing semicolons, …)
  - refactor
  - test (when adding missing tests)
  - chore (maintain)

scope:
  - for backend, the main app name that is being modified
  - for frontend the main container name, duck name, saga or middleware being modified, or your discretion
  set this as your commit template: `git config --local commit.template "pull_request_template.txt"`
