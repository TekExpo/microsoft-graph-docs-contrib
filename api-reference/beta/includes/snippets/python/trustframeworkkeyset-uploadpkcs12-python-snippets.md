---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = UploadPkcs12PostRequestBody(
	key = "Base64-encoded-pfx-content",
	password = "password-value",
)

result = await graph_client.trust_framework.key_sets.by_trust_framework_key_set_id('trustFrameworkKeySet-id').upload_pkcs12.post(request_body)


```