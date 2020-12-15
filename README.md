# Next Crud

[![NPM Version](https://img.shields.io/npm/v/@premieroctet/next-crud/latest)](https://www.npmjs.com/package/@premieroctet/next-crud)
[![NPM License](https://img.shields.io/npm/l/all-contributors.svg?style=flat)](https://github.com/premieroctet/next-crud/blob/master/LICENSE)
[![Github Actions](https://github.com/premieroctet/next-crud/workflows/next-crud/badge.svg)](https://github.com/premieroctet/next-crud/actions?query=workflow%3Anext-crud)

`next-crud` is a helper library that creates CRUD API routes with one simple function based on a Prisma model for Next.js.

# Documentation

The documentation is available [here](https://next-crud.js.org/)

# Overview

`yarn add @premieroctet/next-crud`

Given the following Prisma schema:

```sql
model User {
  id              Int        @id @default(autoincrement())
  name            String?
  email           String?
}
```

Create the file `/pages/api/users/[[...users]].ts.` with:

```javascript
import NextCrud, { PrismaAdapter } from '@premieroctet/next-crud'

const handler = NextCrud({
  resourceName: 'users', // Same as your folder name
  adapter: new PrismaAdapter({
    modelName: 'User', // Prisma model name
  }),
})

export default handler
```

And get your full featured CRUD routes!

|              | Endpoint                | Description               |
| ------------ | ----------------------- | ------------------------- |
| List         | GET `/api/users`        | Get all the users         |
| Get          | GET `/api/users/[id]`   | Get one user              |
| Add          | POST `/api/users`       | Create one user           |
| Edit         | PUT `/api/users/[id]`   | Update one user           |
| Partial edit | PATCH `/api/users`      | Update one user (partial) |
| Delete       | DELETE`/api/users/[id]` | Delete one user           |

# Example

See the example folder
