# Assignments (100xDevs Cohort 2)

Weekly coding assignments for the 100xDevs Cohort 2 full-stack web development course, covering JavaScript fundamentals, Node.js/Express, MongoDB, JWT auth, React, SQL/Postgres, Prisma, Cloudflare Workers and Next.js.

This repository is a fork of [100xdevs-cohort-2/assignments](https://github.com/100xdevs-cohort-2/assignments).

## Repository structure

Each week lives in its own folder. Most folders contain their own `README.md` with the exact problem statements, and many include a `solution`/`solutions` folder.

| Folder | Topic | What's inside |
| --- | --- | --- |
| `01-js/` | JavaScript basics | Easy / medium / hard exercises (anagram, palindrome, calculator, todo list, ...) with Jest tests in `tests/` |
| `week-1/offline-class-1/` | JS built-ins | Example scripts for String, Number, Array, Class, Date, JSON, Math, Object |
| `week-2/01-async-js/` | Async JavaScript | Counters, file read/write, file cleaner, clock (task descriptions in `.md` files) and promise exercises (`setTimeout`, sleep, `Promise.all`, chaining) with Jest tests |
| `week-2/02-nodejs/` | Node.js | File server and todo server with Express (Jest + Supertest tests) |
| `week-3/` | Express & auth | `01-middlewares` (request count, rate limiter, error count), `02-jwt` (jsonwebtoken + zod), `03-mongo` and `04-mongo-with-jwt-auth` (Mongoose), plus `solutions/` |
| `week-4/` | DOM / React internals | Plain HTML todo app where you implement DOM diffing (`index.html`), plus `react-basics/` |
| `week-5/` | React components | Business card component (`level-1/`), with a solution in `solutions/` |
| `week-6/` | React hooks | `useMemo`, `useCallback`, `useRef` exercises (Vite + React apps), with `solutions/` |
| `week-10/` | SQL & ORMs | `1-postgres-simple` (raw SQL with `pg`) and `2-prisma-simple` (Prisma), both TypeScript with Jest tests |
| `week-11/` | Serverless | Blogging-platform backend on Cloudflare Workers; `solution/` uses Hono, Prisma (Accelerate) and Wrangler |
| `week-12/12.1 Relations/` | Prisma relations | Survey/poll app with Express and Prisma |
| `week-14/` | Next.js | Next.js App Router assignment (routing, layouts, static vs client rendering), with `solution/` |

## Prerequisites

- [Node.js](https://nodejs.org/) and npm
- Depending on the week: a MongoDB instance (week 3), a Postgres database URL (weeks 10-12), a Cloudflare account and Wrangler (week 11)

## Running and testing

There is no root `package.json`; work inside the individual assignment folder. Commands below come from the `package.json`/`README.md` files in those folders.

```sh
# JavaScript basics (01-js)
cd 01-js
npx jest ./tests/

# Async JS (week-2/01-async-js)
cd week-2/01-async-js
npm install
npm run all            # or e.g. npm run 1-promisify-setTimeout

# Node.js servers (week-2/02-nodejs)
cd week-2/02-nodejs
npm install
npm run test-fileServer
npm run test-todoServer

# Express middlewares / JWT (week-3/01-middlewares, week-3/02-jwt)
cd week-3/01-middlewares   # or 02-jwt
npm install
npx jest ./tests

# Course-selling app with MongoDB (week-3/03-mongo, week-3/04-mongo-with-jwt-auth)
cd week-3/03-mongo         # or 04-mongo-with-jwt-auth
npm install                # set your MongoDB connection string in db/index.js first
node index.js

# React hooks (week-6/*)
cd week-6/1-use-memo       # or 2-use-callback, 3-use-ref
npm install
npm run dev

# SQL / Prisma (week-10/*)
cd week-10/1-postgres-simple   # or 2-prisma-simple
npm install
npm test

# Cloudflare Workers solution (week-11/solution)
cd week-11/solution
npm install
npm run dev            # npm run deploy to publish with Wrangler
```

See each folder's `README.md` for the full instructions of that assignment.

## Configuration / environment variables

Some assignments need a database connection. Variable names used in the repo:

- `week-3/03-mongo`, `week-3/04-mongo-with-jwt-auth`: the MongoDB connection string is set in `db/index.js`.
- `week-10/1-postgres-simple`: the Postgres connection URL is set as `DB_URL` in `src/config.ts` (see the folder's README).
- `week-10/2-prisma-simple`: the database URL is set as `url` in the `datasource db` block of `prisma/schema.prisma`.
- `week-11/solution` (`.env.example`): `DATABASE_URL`, `DIRECT_URL`
- `week-12/12.1 Relations/solution`: `DATABASE_URL`, `PORT`, `SECRET_KEY`

Do not commit real credentials; keep them in a local `.env` file.

## License

No license file is included in this repository (needs confirmation).
