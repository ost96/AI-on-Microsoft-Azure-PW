# foodQuestion dialog

```javascript
{
  "$kind": "Microsoft.AdaptiveDialog",
  "$designer": {
    "id": "2IJDDq",
    "name": "foodQuestion",
    "description": "Ask generic question about calories/vitamins in your food to get answer from API."
  },
  "autoEndDialog": true,
  "defaultResultProperty": "dialog.result",
  "triggers": [
    {
      "$kind": "Microsoft.OnBeginDialog",
      "$designer": {
        "name": "BeginDialog",
        "description": "",
        "id": "Edg1y9"
      },
      "actions": [
        {
          "$kind": "Microsoft.SendActivity",
          "$designer": {
            "id": "jH00nk"
          },
          "activity": "${SendActivity_jH00nk()}"
        },
        {
          "$kind": "Microsoft.TextInput",
          "$designer": {
            "id": "8elGxA"
          },
          "disabled": false,
          "maxTurnCount": 3,
          "alwaysPrompt": false,
          "allowInterruptions": false,
          "prompt": "${TextInput_Prompt_8elGxA()}",
          "unrecognizedPrompt": "",
          "invalidPrompt": "",
          "defaultValueResponse": "",
          "property": "user.question",
          "outputFormat": "=trim(this.value)"
        },
        {
          "$kind": "Microsoft.HttpRequest",
          "$designer": {
            "id": "Z5EXlF"
          },
          "method": "GET",
          "headers": {
            "x-rapidapi-key": ""
          },
          "url": "https://spoonacular-recipe-food-nutrition-v1.p.rapidapi.com/recipes/quickAnswer?q=${user.question}",
          "resultProperty": "dialog.api_response"
        },
        {
          "$kind": "Microsoft.IfCondition",
          "$designer": {
            "id": "nZkOee"
          },
          "condition": "=dialog.api_response.statusCode == 200",
          "actions": [
            {
              "$kind": "Microsoft.SetProperty",
              "$designer": {
                "id": "98LH31"
              },
              "property": "dialog.answer",
              "value": "=dialog.api_response.content"
            },
            {
              "$kind": "Microsoft.SendActivity",
              "$designer": {
                "id": "t3gvEG"
              },
              "activity": "${SendActivity_t3gvEG()}"
            }
          ],
          "elseActions": [
            {
              "$kind": "Microsoft.SendActivity",
              "$designer": {
                "id": "JoYzcn"
              },
              "activity": "${SendActivity_JoYzcn()}"
            },
            {
              "$kind": "Microsoft.DeleteProperties",
              "$designer": {
                "id": "v4nuz7"
              },
              "properties": [
                "user.question"
              ]
            }
          ]
        }
      ]
    }
  ],
  "generator": "foodQuestion.lg",
  "recognizer": "foodQuestion.lu.qna",
  "id": "foodQuestion"
}
```