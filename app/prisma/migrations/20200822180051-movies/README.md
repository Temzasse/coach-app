# Migration `20200822180051-movies`

This migration has been generated at 8/22/2020, 6:00:51 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE TABLE "public"."Movie" (
"id" SERIAL,
"director" text   NOT NULL ,
"movieName" text   NOT NULL ,
"yearReleased" integer   NOT NULL ,
PRIMARY KEY ("id")
)
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200822180051-movies
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,18 @@
+// This is your Prisma schema file,
+// learn more about it in the docs: https://pris.ly/d/prisma-schema
+
+datasource db {
+  provider = "postgresql"
+  url = "***"
+}
+
+generator client {
+  provider = "prisma-client-js"
+}
+
+model Movie {
+  id           Int    @default(autoincrement()) @id
+  director     String
+  movieName    String
+  yearReleased Int
+}
```


