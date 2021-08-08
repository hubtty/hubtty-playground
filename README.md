# hubtty-playground

A very useful playground for testing [hubtty](https://github.com/hubtty/hubtty).

Adding a line.

Here too.

You may want to modify hubtty to use this repo when starting from a fresh database:
```
+++ w/hubtty/sync.py
@@ -218,15 +218,15 @@ class SyncProjectListTask(Task):
         app = sync.app

         page = 1
-        remote = set()
-        remote_keys = set()
-        remote_desc = dict()
-        while page == 1 or len(remote) > 0:
-            remote = sync.get('user/repos?page=%d&per_page=100' % page)
-            for r in remote:
-                remote_keys.add(r['full_name'])
-                remote_desc[r['full_name']] = r.get('description', '')
-            page = page + 1
+        # remote = set()
+        remote_keys = set(['hubtty/hubtty-playground'])
+        remote_desc = {'hubtty/hubtty-playground':''}
+        # while page == 1 or len(remote) > 0:
+        #     remote = sync.get('user/repos?page=%d&per_page=100' % page)
+        #     for r in remote:
+        #         remote_keys.add(r['full_name'])
+        #         remote_desc[r['full_name']] = r.get('description', '')
+        #     page = page + 1

         with app.db.getSession() as session:
             local = {}
```
