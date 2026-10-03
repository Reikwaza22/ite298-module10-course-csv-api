# Course Enrollment CSV API

FastAPI service for student, course, and enrollment data, with a per-course student-count CSV report.

## CSV endpoint

`GET /courses/export/csv` returns `courses_summary.csv` with `course_code`, `course_title`, and `total_students`. The query counts distinct students per course and includes courses with no enrollments.

## Database configuration

Set `DB_USER`, `DB_PASSWORD`, `DB_HOST`, `DB_PORT`, and `DB_NAME` as environment variables. For local development, copy `.env.example` to `api/.env` and fill in your database connection values. Never commit `.env`. In Vercel, add the same variables under Project Settings > Environment Variables.

## Run locally

Install dependencies with `pip install -r requirements.txt`, then run `uvicorn api.main:app --reload`. Visit `/docs` for interactive API documentation.

## Deploy

Push this project to a public GitHub repository, import that repository into Vercel, add the database environment variables, and deploy. The CSV URL will be `https://YOUR-VERCEL-DOMAIN/courses/export/csv`.

## GitHub and Vercel submission

1. Create a new **public** GitHub repository for this course API. Do not reuse the BaryoBenta API repository.
2. In this project folder, initialize Git, commit the files, and push the `main` branch to that new repository. Check that no `.env` file is staged or committed.
3. Import the new repository into Vercel. Add the five database variables in the Vercel project settings, deploy, and open `/courses/export/csv` on the deployed domain.
4. Submit the public GitHub URL and the deployed CSV endpoint URL in Google Classroom.
