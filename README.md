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

## (2) Voeg drizzle module toe aan resource module