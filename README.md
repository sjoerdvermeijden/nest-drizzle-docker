# Drizzle + NestJS setup

Stappenplan om Drizzle ORM te koppelen aan een NestJS resource.

## 1. Maak een `.env` bestand aan met de database gegevens

```env
DATABASE_URL=postgres://postgres:local@localhost:5432/postgres
```

## 2. Voeg imports toe aan de resource

```ts
import { NodePgDatabase } from 'drizzle-orm/node-postgres';
import * as schema from '../drizzle/schema';
import { DrizzleAsyncProvider } from '../drizzle/drizzle.provider';
```

## 3. Voeg een constructor toe aan de class

```ts
constructor(
  @Inject(DrizzleAsyncProvider)
  private db: NodePgDatabase<typeof schema>,
) {}
```

## 4. Fetch data van de resource

```ts
async findAll() {
  const allCars = await this.db.select().from(schema.cars);
  return allCars;
}
```

## 5. Voeg de Drizzle module toe aan de resource module

> _Nog aan te vullen: voorbeeld van de module-configuratie._
