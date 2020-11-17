# diet dialog
```javascript
{
  "$kind": "Microsoft.AdaptiveDialog",
  "$designer": {
    "id": "j6k5qC",
    "name": "diet",
    "description": "Example diet on request."
  },
  "autoEndDialog": true,
  "defaultResultProperty": "dialog.result",
  "triggers": [
    {
      "$kind": "Microsoft.OnBeginDialog",
      "$designer": {
        "name": "BeginDialog",
        "description": "",
        "id": "DUdV20"
      },
      "actions": [
        {
          "$kind": "Microsoft.SendActivity",
          "$designer": {
            "id": "K95Otc"
          },
          "activity": "${SendActivity_K95Otc()}"
        },
        {
          "$kind": "Microsoft.TextInput",
          "$designer": {
            "id": "13KRGP"
          },
          "disabled": false,
          "maxTurnCount": 3,
          "alwaysPrompt": false,
          "allowInterruptions": false,
          "prompt": "${TextInput_Prompt_13KRGP()}",
          "unrecognizedPrompt": "",
          "invalidPrompt": "",
          "defaultValueResponse": "",
          "property": "user.isMeat",
          "outputFormat": "=trim(this.value)"
        },
        {
          "$kind": "Microsoft.IfCondition",
          "$designer": {
            "id": "bMbTOK"
          },
          "condition": "=user.isMeat==\"yes\"||user.isMeat==\"y\"",
          "elseActions": [
            {
              "$kind": "Microsoft.TextInput",
              "$designer": {
                "id": "9T5qua"
              },
              "disabled": false,
              "maxTurnCount": 3,
              "alwaysPrompt": false,
              "allowInterruptions": false,
              "prompt": "${TextInput_Prompt_9T5qua()}",
              "unrecognizedPrompt": "",
              "invalidPrompt": "",
              "defaultValueResponse": "",
              "property": "user.isVegan"
            },
            {
              "$kind": "Microsoft.IfCondition",
              "$designer": {
                "id": "yiRp6A"
              },
              "condition": "=user.isVegan==\"yes\"||user.isVegan==\"y\"",
              "actions": [
                {
                  "$kind": "Microsoft.SetProperty",
                  "$designer": {
                    "id": "ZjlhGo"
                  },
                  "property": "user.dietType",
                  "value": "'vegan'"
                },
                {
                  "$kind": "Microsoft.SendActivity",
                  "$designer": {
                    "id": "I3OuYm"
                  },
                  "activity": "${SendActivity_I3OuYm()}"
                }
              ],
              "elseActions": [
                {
                  "$kind": "Microsoft.SetProperty",
                  "$designer": {
                    "id": "EjrMsz"
                  },
                  "property": "user.dietType",
                  "value": "'vegetarian'"
                },
                {
                  "$kind": "Microsoft.SendActivity",
                  "$designer": {
                    "id": "I0T38v"
                  },
                  "activity": "${SendActivity_I0T38v()}"
                }
              ]
            }
          ],
          "actions": [
            {
              "$kind": "Microsoft.SetProperty",
              "$designer": {
                "id": "z3f3jc"
              },
              "property": "user.dietType",
              "value": "'carnivore'"
            },
            {
              "$kind": "Microsoft.SendActivity",
              "$designer": {
                "id": "7zwJko"
              },
              "activity": "${SendActivity_7zwJko()}"
            }
          ]
        },
        {
          "$kind": "Microsoft.NumberInput",
          "$designer": {
            "id": "jrxW1S"
          },
          "defaultLocale": "en-us",
          "disabled": false,
          "maxTurnCount": 3,
          "alwaysPrompt": false,
          "allowInterruptions": false,
          "prompt": "${NumberInput_Prompt_jrxW1S()}",
          "unrecognizedPrompt": "",
          "invalidPrompt": "",
          "defaultValueResponse": "",
          "property": "user.calories"
        },
        {
          "$kind": "Microsoft.SendActivity",
          "$designer": {
            "id": "Mesiwa"
          },
          "activity": "${SendActivity_Mesiwa()}"
        },
        {
          "$kind": "Microsoft.HttpRequest",
          "$designer": {
            "id": "B4bscu"
          },
          "method": "GET",
          "url": "https://spoonacular-recipe-food-nutrition-v1.p.rapidapi.com/recipes/mealplans/generate?timeFrame=\"day\"&targetCalories=${user.calories}&diet=${user.dietType}",
          "headers": {
            "x-rapidapi-key": "",
            "x-rapidapi-host": "spoonacular-recipe-food-nutrition-v1.p.rapidapi.com"
          },
          "resultProperty": "dialog.api_response"
        },
        {
          "$kind": "Microsoft.IfCondition",
          "$designer": {
            "id": "DSPaDE"
          },
          "condition": "=dialog.api_response.statusCode == 200",
          "elseActions": [
            {
              "$kind": "Microsoft.SendActivity",
              "$designer": {
                "id": "OAKLVv"
              },
              "activity": "${SendActivity_OAKLVv()}"
            },
            {
              "$kind": "Microsoft.DeleteProperties",
              "$designer": {
                "id": "e4WsK8"
              },
              "properties": [
                "user.isMeat",
                "user.isVegan",
                "user.dietType",
                "user.calories"
              ]
            }
          ],
          "actions": [
            {
              "$kind": "Microsoft.SetProperty",
              "$designer": {
                "id": "KwZIrq"
              },
              "property": "dialog.diet",
              "value": "=dialog.api_response.content"
            },
            {
              "$kind": "Microsoft.SendActivity",
              "$designer": {
                "id": "CVMVyb"
              },
              "activity": "${SendActivity_CVMVyb()}"
            },
            {
              "$kind": "Microsoft.SendActivity",
              "$designer": {
                "id": "Je8FcW"
              },
              "activity": "${SendActivity_Je8FcW()}"
            },
            {
              "$kind": "Microsoft.SendActivity",
              "$designer": {
                "id": "9yXiNb"
              },
              "activity": "${SendActivity_9yXiNb()}"
            }
          ]
        }
      ]
    }
  ],
  "generator": "diet.lg",
  "recognizer": "diet.lu.qna",
  "id": "diet"
}
```