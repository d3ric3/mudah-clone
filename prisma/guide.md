# Guide after running npx prisma init

Command: npx prisma init

✔ Your Prisma schema was created at prisma/schema.prisma
You can now open it in your favorite editor.

**warn** You already have a .gitignore file. Don't forget to add `.env` in it to not commit any private information.

Next steps:

1. Set the **DATABASE_URL** in the **.env** file to point to your existing database. If your database has no tables yet, read https://pris.ly/d/getting-started
2. Set the **provider** of the **datasource** block in **schema.prisma** to match your database: **postgresql, mysql, sqlite, sqlserver, mongodb or cockroachdb.**
3. Run **prisma db pull** to turn your database schema into a Prisma schema.
4. Run **prisma generate** to generate the Prisma Client. You can then start querying your database.

More information in our documentation:
https://pris.ly/d/getting-started

# Guide for creating db schema and push to Planet-Scale

1. Create db schema, ref: https://www.prisma.io/docs/concepts/components/prisma-schema
2. Push your schema to PlanetScale: **npx prisma db push**
3. Using the Prisma client (src/index.js)

```javascript
import { PrismaClient } from "@prisma/client";

const prisma = new PrismaClient();

async function main() {
  // ... you will write your Prisma Client queries here
}

main()
  .then(async () => {
    await prisma.$disconnect();
  })
  .catch(async (e) => {
    console.error(e);
    await prisma.$disconnect();
    process.exit(1);
  });
```
