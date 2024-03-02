Below is the body text of the HTML step.

```json
{
  "embeds": [
    {
      "author": {
        "icon_url": "https://seeklogo.com/images/M/microsoft-sentinel-azure-logo-28FA1B44A7-seeklogo.com.png",
        "name": "@{items('For_each')?['properties']?['productName']} - (@{triggerBody()?['workspaceInfo']?['WorkspaceName']})",
        "url": "ADD LINK TO YOUR SENTINEL WORKSPACE"
      },
      "color": @{variables('MessageColour')},
      "description": "@{triggerBody()?['object']?['properties']?['description']}",
      "fields": [
        {
          "inline": true,
          "name": "Incident Id",
          "value": "@{triggerBody()?['object']?['properties']?['incidentNumber']}"
        },
        {
          "inline": true,
          "name": "Time Generated (GMT+10)",
          "value": "@{body('Convert_Incident_Creation_time_to_BNE')}"
        },
        {
          "name": "Link to Incident",
          "value": "@{triggerBody()?['object']?['properties']?['incidentUrl']}"
        }
      ],
      "footer": {
        "text": "Sent with 💖 by LOGIC APP TITLE <@{workflow().run.name}>"
      },
      "title": "@{triggerBody()?['object']?['properties']?['title']}"
    }
  ],
  "username": "Microsoft Sentinel"
}
```