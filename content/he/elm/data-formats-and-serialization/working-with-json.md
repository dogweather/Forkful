---
title:                "עבודה עם JSON"
aliases:
- /he/elm/working-with-json/
date:                  2024-02-03T19:23:25.517296-07:00
model:                 gpt-4-0125-preview
simple_title:         "עבודה עם JSON"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/elm/working-with-json.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## מה ולמה?
עבודה עם JSON ב-Elm מדוברת על פענוח נתוני JSON לסוגים ב-Elm וקידוד ערכים מ-Elm חזרה ל-JS‪ON. תהליך זה קריטי לאינטרקציות של אפליקציות אינטרנט עם API-ים ומקורות נתונים חיצוניים, מאפשר החלפה חלקה של נתונים בין הלקוח (Elm) לשרתים או שירותים אחרים.

## איך לעשות:

Elm מתייחס לטיפול ב-JSO‪N עם מפורשות ובטיחות, בעיקר באמצעות המודולים `Json.Decode` ו`Json.Encode`. כדי להתחיל לעבוד עם JS‪ON, תצטרך להגדיר פענח לסוג הנתונים שלך. בואו נניח שאנו עוסקים באובייקט פרופיל משתמש פשוט.

ראשית, הגדר את סוג ה-Elm שלך:

```elm
type alias UserProfile = 
    { id : Int
    , name : String
    , email : String
    }
```

### פענוח JS‪ON ל-Elm

כדי לפענח מחרוזת JS‪ON לסוג `UserProfile`, צור פענח:

```elm
import Json.Decode exposing (Decoder, int, string, field, map3)

userProfileDecoder : Decoder UserProfile
userProfileDecoder =
    map3 UserProfile
        (field "id" int)
        (field "name" string)
        (field "email" string)
```

כדי לפענח אובייקט JS‪ON:

```elm
import Json.Decode exposing (decodeString)

jsonString : String
jsonString = 
    """{"id": 1, "name": "John Doe", "email": "john@example.com"}"""

decoded : Result String UserProfile
decoded =
    decodeString userProfileDecoder jsonString

{- פלט לדוגמא:
Result.Ok { id = 1, name = "John Doe", email = "john@example.com" }
-}
```

### קידוד Elm ל-JS‪ON

כדי לקודד ערך מ-Elm חזרה ל-JS‪ON, השתמש במודול `Json.Encode`.

```elm
import Json.Encode exposing (object, int, string)

encodeUserProfile : UserProfile -> String
encodeUserProfile userProfile =
    object
        [ ("id", int userProfile.id)
        , ("name", string userProfile.name)
        , ("email", string userProfile.email)
        ]
        |> Json.Encode.encode 0

{-
שימוש:
encodeUserProfile { id = 1, name = "John Doe", email = "john@example.com" }

פלט לדוגמא:
"{"id":1,"name":"John Doe","email":"john@example.com"}"
-}
```

### ספריות צד שלישי

חבילות Elm כמו `elm-json-decode-pipeline` יכולות לפשט את יצירת הפענחים באמצעות סגנון צינור, שמאוד נוח לפענוח אובייקטים מורכבים.

ראשית, הוסף את הספריה לפרויקט שלך:

```shell
elm install NoRedInk/elm-json-decode-pipeline
```

אז, אתה יכול לפשט את הגדרת הפענח כך:

```elm
import Json.Decode exposing (int, string, succeed)
import Json.Decode.Pipeline exposing (required, decode)

userProfileDecoder : Decoder UserProfile
userProfileDecoder =
    decode UserProfile
        |> required "id" int
        |> required "name" string
        |> required "email" string

{- השתמש בפענח הזה כמו קודם עם decodeString לפענוח מחרוזות JS‪ON. -}
```

גישה זו מפשטת את הפענח, הופכת את הקוד לנקי יותר וקל יותר לתחזוקה, במיוחד ככל שמבני הנתונים הופכים למורכבים יותר.
