# Migration `20200310180738-create-posts`

This migration has been generated by Cedricium at 3/10/2020, 6:07:38 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE TABLE "quaint"."Post" (
    "body" TEXT NOT NULL DEFAULT '' ,
    "createdAt" DATE NOT NULL DEFAULT '1970-01-01 00:00:00' ,
    "id" INTEGER NOT NULL  PRIMARY KEY AUTOINCREMENT,
    "title" TEXT NOT NULL DEFAULT '' 
) 
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200310180738-create-posts
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,18 @@
+datasource DS {
+  provider = "sqlite"
+  url = env("DB_HOST")
+}
+
+generator photonjs {
+  provider = "prisma-client-js"
+  binaryTargets = ["native", "rhel-openssl-1.0.x"]
+}
+
+// Define your own datamodels here and run `yarn redwood db save` to create
+// migrations for them.
+model Post {
+  id          Int @id @default(autoincrement())
+  title       String
+  body        String
+  createdAt   DateTime @default(now())
+}
```


