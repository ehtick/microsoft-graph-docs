---
title: "ediscoveryCustodian: removeHold"
description: "**TODO: Add Description**"
author: "SeunginLyu"
ms.localizationpriority: medium
ms.prod: "ediscovery"
doc_type: apiPageType
---

# ediscoveryCustodian: removeHold
Namespace: microsoft.graph.security

Start the process of removing hold from [eDiscovery custodians](../resources/security-ediscoverycustodian.md). After the operation is created, you can get the status by retrieving the `Location` parameter from the response headers. The location provides a URL that will return an [eDiscoveryHoldOperation](../resources/security-ediscoveryholdoperation.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|eDiscovery.Read.All, eDiscovery.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /security/cases/ediscoveryCases/{ediscoveryCaseId}/custodians/removeHold
POST /security/cases/ediscoveryCases/{ediscoveryCaseId}/custodians/{eDiscoveryCustodianId}/removeHold
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the parameters.

The following table shows the parameters that can be used with this action.

|Parameter|Type|Description|
|:---|:---|:---|
|ids|String collection|The IDs of custodians to apply hold. Optional.|


## Response

If successful, this action returns a `202 Accepted` response code.

## Examples
### Example 1: Remove hold from multiple custodians
#### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "ediscoverycustodianthis.removehold"
}
-->
``` http
POST https://graph.microsoft.com/v1.0/security/cases/eDiscoverycases/b0073e4e-4184-41c6-9eb7-8c8cc3e2288b/custodians/removeHold
Content-Type: application/json

{
  "ids": [
    "7f697316-43ed-48e1-977f-261be050db93", "b26888b3-e1f5-47c5-bdf2-33d1b90cb2e8"
  ]
}
```


#### Response
The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 202 Accepted
```

### Example 2: Remove hold from a single custodian
#### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "ediscoverycustodianthis.removehold"
}
-->
``` http
POST https://graph.microsoft.com/v1.0/security/cases/eDiscoverycases/b0073e4e-4184-41c6-9eb7-8c8cc3e2288b/custodians/c25c3914f9f743ee9cbaa25377e0cec6/removeHold
```


#### Response
The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 202 Accepted
```