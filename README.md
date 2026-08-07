## (1) Maak een .env bestand aan met de database gegevens
```
DATABASE_URL=postgres://postgres:local@localhost:5432/postgres
```

## (1) Imports toe te voegen aan resource
```
import { NodePgDatabase } from 'drizzle-orm/node-postgres';
import * as schema from '../drizzle/schema';
import { DrizzleAsyncProvider } from '../drizzle/drizzle.provider';
```

## (2) Voeg constructor toe aan class
```
constructor(
    @Inject(DrizzleAsyncProvider)
    private db: NodePgDatabase<typeof schema>,
  ) { }

```

## (3) Fetch data van resource
```
  async findAll() {
    const allCars = await this.db.select().from(schema.cars);
    return allCars;
  }

```

## (4) Voeg drizzle module toe aan resource module