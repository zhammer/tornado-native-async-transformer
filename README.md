# Tornado Async Transformer

A [libcst](https://github.com/Instagram/LibCST) transformer for updating tornado @gen.coroutine syntax to python3.5+ native async/await.

[Check out the demo.](https://tornado-async-transformer.zhammer.now.sh/)

#### Example
```diff
 """
 A simple coroutine.
 """
 from tornado import gen
 
 
-@gen.coroutine
-def call_api():
-    response = yield fetch()
+async def call_api():
+    response = await fetch()
     if response.status != 200:
         raise BadStatusError()
-    raise gen.Return(response.data)
+    return response.data
```
