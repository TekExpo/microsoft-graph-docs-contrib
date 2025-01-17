---
title: "Create cloudPcUserSetting"
description: "Create a new cloudPcUserSetting ."
author: "AshleyYangSZ"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: apiPageType
---

# Create cloudPcUserSetting

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new [cloudPcUserSetting](../resources/cloudpcusersetting.md) object.

[!INCLUDE [national-cloud-support](../../includes/global-us.md)]

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "virtualendpoint_post_usersettings" } -->
[!INCLUDE [permissions-table](../includes/permissions/virtualendpoint-post-usersettings-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
POST /deviceManagement/virtualEndpoint/userSettings
```

## Request headers

| Name          | Description                |
| :------------ | :------------------------  |
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
| Content-Type  | application/json. Required.|

## Request body

In the request body, supply a JSON representation of the [cloudPcUserSetting](../resources/cloudpcusersetting.md) object.

The following table lists the properties that are required when you create the [cloudPcUserSetting](../resources/cloudpcusersetting.md).

|Property|Type|Description|
|:---|:---|:---|
|displayName|String|The setting name as it appears in the UI. |
|lastModifiedDateTime|DateTimeOffset|The last date and time the setting was modified. The timestamp type represents the date and time information using ISO 8601 format and is always in UTC. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. |
|localAdminEnabled|Boolean|To turn on the local admin option, change this setting to `true`.  |
|restorePointSetting|[cloudPcRestorePointSetting](../resources/cloudpcrestorepointsetting.md)|Defines how frequently a restore point is created (that is, a snapshot is taken) for users' provisioned Cloud PCs (default is 12 hours), and whether the user is allowed to restore their own Cloud PCs to a backup made at a specific point in time.|
|selfServiceEnabled (deprecated)|Boolean|To turn on the self service option, change this setting to `true`. The **selfServiceEnabled** property is deprecated and will stop returning data on December 1, 2023.|

## Response

If successful, this method returns a `201 Created` response code and a [cloudPcUserSetting](../resources/cloudpcusersetting.md) object in the response body.

## Examples

### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "create_cloudpcusersetting_from_"
}
-->
``` http
POST https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/userSettings
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.cloudPcUserSetting",
  "displayName": "Example",
  "selfServiceEnabled": false,
  "localAdminEnabled": true,
  "restorePointSetting": {
    "frequencyInHours": 16,
    "frequencyType": "sixteenHours",
    "userRestoreEnabled": true
  }
}
```

### Response
The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.cloudPcUserSetting"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.cloudPcUserSetting",
  "id": "556092f8-92f8-5560-f892-6055f8926055",
  "displayName": "Example",
  "selfServiceEnabled": false,
  "localAdminEnabled": true,
  "restorePointSetting": {
    "frequencyInHours": 16,
    "frequencyType": "sixteenHours",
    "userRestoreEnabled": true
  },
  "lastModifiedDateTime": "2021-02-01T10:29:57Z"  
}
```
