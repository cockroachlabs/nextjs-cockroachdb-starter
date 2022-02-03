# CockroachDB Next.js Starter App

[![Netlify Status](https://api.netlify.com/api/v1/badges/e73ba2a6-89e0-4c06-954d-16096c00202e/deploy-status)](https://app.netlify.com/sites/nextjs-cockroachdb-starter/deploys)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

## Overview

This is a [Next.js](https://nextjs.org/) v12 project bootstrapped with `create-next-app` and set up to be instantly deployed to [Netlify](https://netlify.com/).

## Stack

- Framework - [Next.js v12](https://nextjs.org)
- Auth - [NextAuth.js](https://next-auth.js.org/)
- Database - [CockroachDB](https://cockroachlabs.com)
- ORM - [Prisma](https://prisma.io)
- Hosting - [Netlify](https://netlify.com)

## Getting Started

### CockroachDB Serverless Configuration

- [Create a free serverless cluster](https://www.cockroachlabs.com/docs/cockroachcloud/quickstart.html)
- Execute the [provided script](./prisma/init_database.sql) using the SQL client to create the database and tables;
  ```
  cockroach sql --url [Connection string] --file ./prisma/init_database.sql
  ```
- Save the connection string to the `DATABASE_URL` environment variable

### Installation options

**Option one:** One-click deploy

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/cockroachlabs/nextjs-cockroachdb-starter)

Clicking this button will create a new repo for you that looks like this one, and sets that repo up immediately for deployment on Netlify. You will be prompted for a repo name and to provide the values for the following environment variables:

- Postgres Connection String (`DATABASE_URL`), **required** You can find this in the Connect model in the Cockroach Labs Cloud Console
- NextAuth URL (`NEXTAUTH_URL`), **required for production** The canonical URL of your site.
- NextAuth Secret (`NEXTAUTH_SECRET`), **required for production** A random string is used to hash tokens, sign/encrypt cookies and generate cryptographic keys. Can be generated using the `openssl` command:

  ```shell
  openssl rand -base64 32
  ```

Additonal Environment variables:

This example is set up to use the [GitHub NextAuth Provider](https://next-auth.js.org/providers/github). Follow the instructions provided in that documentation to add variables for `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET`.

You may also choose to update this application to use [one or more of the many authentication providers](https://next-auth.js.org/providers/overview).

**Option two:** Manual clone

You will need to [install the Netlify CLI](https://docs.netlify.com/cli/get-started/) and connect it to your Netlify site to run locally.

1. Clone this repo: `git clone https://github.com/cockroachlabs/nextjs-cockroachdb-starter.git`
2. Navigate to the directory and run `ntl init` to connect to Netlify
3. Add the above environment variables using `ntl env:set [env var] [value]`
4. Run the app locally using `ntl dev`
5. Make any changes and push to your repo to deploy.
