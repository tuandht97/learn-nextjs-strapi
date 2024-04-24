
<div align="center">
<p align="center">
  <img src="https://user-images.githubusercontent.com/44535256/180598361-505e938a-dff5-4845-9fb7-6f0a7b8d0682.png" alt="Logo"/>
</p>

<p style="margin-top: 0;">Dockerize your Strapi v4 backend with Next.js and Nginx Support 🚀</p>
	</div>

## Table of Contents <!-- omit in toc -->

- [Current Status](#current-status)
- [What for?](#what-for)
- [Features & Stacks](#features--stacks)
    - [Backend](#backend)
    - [Frontend](#frontend)
    - [Database](#database)
    - [Reverse Proxy](#reverse-proxy)
    - [Containerization](#containerization)
    - [Environment Variables Management](#environment-variables-management)
- [Installation and Usage](#installation-and-usage)
    - [Installation](#installation)
    - [Usage](#usage)
- [Security for Endpoints](#security-for-endpoints)

## Current Status

This package is currently under development and should be consider **BETA** in terms of state. We are currently accepting contributions to help develop and maintain this package.

For more information on contributing please see [the contrib message below](#contributing).

##  What for?

- Easy development & production environment
- Easy frontend adoption (just delete frontend folder and create your best)
- Creating full-stack applications for small or medium size projects

## Features & Stacks

#### Backend
- Strapi v4
- Node.js v16 for Docker Image
- Node Package Manager
#### Frontend
- Next.js
- React.js
- Node.js-alpine for Docker Image
- Node Package Manager
#### Database
- Postgres v12-alpine
#### Reverse Proxy
- Nginx Latest
- Fastcgi support
- Mime-types
- Security configs
#### Containerization
- Docker-compose v3 for container orchestration 🐳
- Seperated Dockerfiles for development and production
#### Environment Variables Management
- One file for backend + frontend + database + nginx


## Installation
#### Installation manual
- Run frontend:
```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```
- Run backend:
```bash
npm run develop
# or
yarn develop
```

#### Instalation with docker
You have to currently exist Docker and Docker Compose on your system:
- [Docker & Docker Compose](https://docs.docker.com/get-docker/)
- Change credentials with secure and strong ones in `.env`
- If you are on development, be sure `ENVIRONMENT=development` on .env file
- If you are on production or want to production build, change with `ENVIRONMENT=production`
- Be sure `localhost:80` is accesible and not using from another process (Nginx runs on 80)
- Pull necessary images:
```bash
docker-compose pull
```
- Build and up your docker-compose file if everything is ok:
```bash
docker-compose build
docker-compose up -d
```
## Use
- Now you can access to Next.js frontend on `http://localhost` and Strapi backend (admin) on `http://localhost/strapi/admin`
- Register with your e-mail and password.
- Go to `Content-Type Builder`, It has sample content type as `Article` and this content type has three field as `title` `body` and `cover`.
- For creating new `Article`, go to `Content Manager`and click `Article`on left pane, click `Create new entry`and fill the blanks > click Publish!
- For testing API endpoint you need to give public access to the `Article` so
	- Go to `Settings`>`User & Permissions Plugin`>`Roles`>`Public`>`Article`and select `find` `findOne`, If you need more, select what you want and save!
	- Go to the `http://localhost/strapi/api/articles`

## Security for Endpoints
Secure all your Strapi related endpoints in Nginx, make sure to use API tokens to connect to the backend and keep this information private. The Nginx config that on the repo is for development, not production ⛔️
