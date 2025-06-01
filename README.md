# Monorepo Template

This template combines [Turborepo with Shadcn](https://github.com/shadcn-ui/ui/tree/main/templates/monorepo-next) and [Turborepo with Prisma](https://github.com/vercel/turborepo/tree/main/examples/with-prisma) templates together.

## Prerequisite
Download [pnpm](https://pnpm.io/installation)
POSIX (Mac, Linux)
```bash
curl -fsSL https://get.pnpm.io/install.sh | sh -
```
Windows
```powershell
Invoke-WebRequest https://get.pnpm.io/install.ps1 -UseBasicParsing | Invoke-Expression
```

Download [Docker](https://www.docker.com/products/docker-desktop/])
- Optional
- Feel free to integrate with database like Neon/Supabase

Start db
```bash
docker-compose up
```

Setup env (DATABASE_URL)
```bash
cp .env.example ./packages/database/.env
cp .env.example ./apps/web/.env
```

## Usage
Install packages
```bash
pnpm i
```

Seed db (either start docker container or connect to external db)
```bash
pnpm db:seed
```

Start dev!
```bash
pnpm dev
```

## Optional: Using [Turborepo](https://turborepo.com/docs/getting-started/installation)
```bash
pnpm install turbo --global
```
Login
```bash
npx turbo login
```
Link it to remote cache
```bash
npx turbo link
```

## Adding Shadcn components
To add components to your app, run the following command at the root of your `web` app:
```bash
pnpm dlx shadcn@latest add button -c apps/web
```

This will place the ui components in the `packages/ui/src/components` directory.
