---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := msgraphsdk.NewTeam()
displayName := "My Sample Team"
requestBody.SetDisplayName(&displayName)
description := "My Sample Team’s Description"
requestBody.SetDescription(&description)
requestBody.SetAdditionalData(map[string]interface{}{
	"template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
}
result, err := graphClient.Teams().Post(requestBody)


```