## Participant Onboarding Data Contract

This is the data contract for what data will be provided to any onboarding scripts. The data will be provided via a 
`participants.json` file.


Version: `1.1.0`
```
{
  "participants": [
    {
      "firstName": "name1",
      "email": "email1",
    }
  ],
  "services": {
    "slack": {
      "defaultChannels": [
        "channel1",
        "channel2"
      ]
    },
    "github": {
      "defaultGroups": [
        "groups1",
        "groups2"
      ]
    },
    "googleDrive": {
      "defaultFolders": [
        "folder1",
        "folder2"
      ]
    }
  },
  "numberOfTeams": 15
}
```