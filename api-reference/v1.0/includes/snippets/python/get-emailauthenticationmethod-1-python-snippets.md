---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)


result = await graph_client.me.authentication.email_methods.by_email_authentication_method_id('emailAuthenticationMethod-id').get()


```