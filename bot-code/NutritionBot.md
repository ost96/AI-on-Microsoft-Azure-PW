# NutritionBot
```javascript
{
  "$kind": "Microsoft.AdaptiveDialog",
  "$designer": {
    "$designer": {
      "name": "NutritionBot",
      "description": "Have a nutrition related question? Want to get a diet? Ask NutritionBot!",
      "id": "eJ7OTI"
    }
  },
  "autoEndDialog": true,
  "defaultResultProperty": "dialog.result",
  "triggers": [
    {
      "$kind": "Microsoft.OnConversationUpdateActivity",
      "$designer": {
        "id": "376720"
      },
      "actions": [
        {
          "$kind": "Microsoft.Foreach",
          "$designer": {
            "id": "518944",
            "name": "Loop: for each item"
          },
          "itemsProperty": "turn.Activity.membersAdded",
          "actions": [
            {
              "$kind": "Microsoft.IfCondition",
              "$designer": {
                "id": "641773",
                "name": "Branch: if/else"
              },
              "condition": "string(dialog.foreach.value.id) != string(turn.Activity.Recipient.id)",
              "actions": [
                {
                  "$kind": "Microsoft.SendActivity",
                  "$designer": {
                    "id": "859266",
                    "name": "Send a response"
                  },
                  "activity": "${SendActivity_Welcome()}"
                }
              ]
            }
          ]
        }
      ]
    },
    {
      "$kind": "Microsoft.OnIntent",
      "$designer": {
        "id": "MIGyt7",
        "name": "Question"
      },
      "intent": "Question",
      "actions": [
        {
          "$kind": "Microsoft.BeginDialog",
          "$designer": {
            "id": "JJ5H8s"
          },
          "activityProcessed": true,
          "dialog": "foodQuestion"
        }
      ],
      "condition": "#Question.Score >= 0.8"
    },
    {
      "$kind": "Microsoft.OnIntent",
      "$designer": {
        "id": "KWANQe",
        "name": "Diet"
      },
      "intent": "Diet",
      "actions": [
        {
          "$kind": "Microsoft.BeginDialog",
          "$designer": {
            "id": "pOjKh5"
          },
          "activityProcessed": true,
          "dialog": "diet"
        }
      ],
      "condition": "#Diet.Score >= 0.8"
    },
    {
      "$kind": "Microsoft.OnIntent",
      "$designer": {
        "id": "P5bRip",
        "name": "Cancel"
      },
      "intent": "Cancel",
      "actions": [
        {
          "$kind": "Microsoft.BeginDialog",
          "$designer": {
            "id": "7gOvrM"
          },
          "activityProcessed": true,
          "dialog": "cancel"
        }
      ],
      "condition": "#Cancel.Score >= 0.8"
    }
  ],
  "$schema": "https://raw.githubusercontent.com/microsoft/BotFramework-Composer/stable/Composer/packages/server/schemas/sdk.schema",
  "generator": "NutritionBot.lg",
  "id": "NutritionBot",
  "recognizer": "NutritionBot.lu.qna"
}
```