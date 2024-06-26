---
title: cms
date: 2024-04-15T12:29:42+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1711291817956-30c8fc8f9663?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MTMxNTUyOTR8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1711291817956-30c8fc8f9663?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MTMxNTUyOTR8&ixlib=rb-4.0.3
---

# [code100x/cms](https://github.com/code100x/cms)

<h1 align='center'>CMS</h1>

## Setup Procedure

* Docker

    OR

* Copy .env.example to .env
* Get a postgres db from https://neon.tech/ (or any other provider)
* Replace the DATABASE_URL in .env
* Run ```npx prisma migrate dev``` to setup schema
## Steps to run locally
With Docker

* ```docker compose up```

Without Docker
* ```npm install```
* ```npm run db:seed``` to seed the database
* ```npm run dev```
* Login using any userid and password 123456
* You should be able to see some test courses

Make sure to lint and format your code before creating a PR
* ```npm run lint:check``` to check for lint errors
* ```npm run lint:fix``` to fix lint errors
* ```npm run format:check``` to format the code
* ```npm run format:fix``` to fix the formatting
* If the code is not formatted properly, the CI will fail

---

Read [contributing guidelines](./CONTRIBUTING.md) to start making contributions
