---
title: "Add password credential"
description: "Add a password to an application."
localization_priority: Normal
author: "davidmu1"
ms.prod: "microsoft-identity-platform"
---

# Add password credential 

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update an existing [application](../resources/application.md) object to add a password.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](../../../concepts/permissions_reference.md).

| Permission type | Permissions (from least to most privileged) |
|:-------------- |:------------------------------------------- |
| Delegated (work or school account) | Directory.AccessAsUser.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application | Application.ReadWrite.OwnedBy, Application.ReadWrite.All, Directory.Read.All |

## HTTP request

<!-- { "blockType": "ignored" } -->
```http
POST /applications/{id}/addPassword

```
## Request headers

| Name | Description|
|:---------------|:----------|
| Authorization  | Bearer {token} |
| Content-type   | application/json |

## Request body

In the request body, supply a JSON representation of a [passwordCredential](../resources/passwordcredential.md) object.

## Response

If successful, this method returns a `200 Ok` response code and a [passwordCredential](../resources/passwordcredential.md) object.

## Example

The following example shows how to call this API.

### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "create_directoryobject_from_application"
}-->
```http
POST https://graph.microsoft.com/beta/applications/{id}/addPassword
Content-type: application/json
Content-length: 30

{
  "passwordCredential": {}
}
```

### Response

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.passwordCredential"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 51

{
  "passwordCredential": {
    "customKeyIdentifier": "fsdna389aaa==",
    "startDateTime": "2017-06-12T07:15:32.45Z",
    "endDateTime": "2019-06-12T07:15:32.45Z",
    "keyId": "24ddd58e-81b3-49f1-aea1-89cabf662386",
    "secretText": "autogenerated password value"
  }
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Create owner",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->