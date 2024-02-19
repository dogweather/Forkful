---
aliases:
- /he/elm/generating-random-numbers/
date: 2024-01-27 20:34:52.446136-07:00
description: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD\
  \ \u05D0\u05E7\u05E8\u05D0\u05D9\u05D9\u05DD \u05D1-Elm \u05DB\u05D5\u05DC\u05DC\
  \u05EA \u05D9\u05E6\u05D9\u05E8\u05EA \u05E2\u05E8\u05DB\u05D9\u05DD \u05DE\u05E1\
  \u05E4\u05E8\u05D9\u05D9\u05DD \u05D1\u05DC\u05EA\u05D9 \u05E6\u05E4\u05D5\u05D9\
  \u05D9\u05DD \u05D4\u05D7\u05D9\u05D5\u05E0\u05D9\u05D9\u05DD \u05DC\u05D9\u05D9\
  \u05E9\u05D5\u05DE\u05D9\u05DD \u05DB\u05DE\u05D5 \u05DE\u05E9\u05D7\u05E7\u05D9\
  \u05DD, \u05E1\u05D9\u05DE\u05D5\u05DC\u05E6\u05D9\u05D5\u05EA \u05D5\u05D0\u05DC\
  \u05D2\u05D5\u05E8\u05D9\u05EA\u05DE\u05D9\u05DD \u05E9\u05DC \u05D0\u05D1\u05D8\
  \u05D7\u05D4. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05DE\u05E9\u05EA\u05DE\
  \u05E9\u05D9\u05DD \u05D1\u05D0\u05E7\u05E8\u05D0\u05D9\u05D5\u05EA\u2026"
lastmod: 2024-02-18 23:08:52.748913
model: gpt-4-0125-preview
summary: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05D0\
  \u05E7\u05E8\u05D0\u05D9\u05D9\u05DD \u05D1-Elm \u05DB\u05D5\u05DC\u05DC\u05EA \u05D9\
  \u05E6\u05D9\u05E8\u05EA \u05E2\u05E8\u05DB\u05D9\u05DD \u05DE\u05E1\u05E4\u05E8\
  \u05D9\u05D9\u05DD \u05D1\u05DC\u05EA\u05D9 \u05E6\u05E4\u05D5\u05D9\u05D9\u05DD\
  \ \u05D4\u05D7\u05D9\u05D5\u05E0\u05D9\u05D9\u05DD \u05DC\u05D9\u05D9\u05E9\u05D5\
  \u05DE\u05D9\u05DD \u05DB\u05DE\u05D5 \u05DE\u05E9\u05D7\u05E7\u05D9\u05DD, \u05E1\
  \u05D9\u05DE\u05D5\u05DC\u05E6\u05D9\u05D5\u05EA \u05D5\u05D0\u05DC\u05D2\u05D5\u05E8\
  \u05D9\u05EA\u05DE\u05D9\u05DD \u05E9\u05DC \u05D0\u05D1\u05D8\u05D7\u05D4. \u05DE\
  \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05DE\u05E9\u05EA\u05DE\u05E9\u05D9\u05DD\
  \ \u05D1\u05D0\u05E7\u05E8\u05D0\u05D9\u05D5\u05EA\u2026"
title: "\u05D2\u05D9\u05DC\u05D5\u05D9 \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05D0\
  \u05E7\u05E8\u05D0\u05D9\u05D9\u05DD"
---

{{< edit_this_page >}}

## מה ולמה?
יצירת מספרים אקראיים ב-Elm כוללת יצירת ערכים מספריים בלתי צפויים החיוניים ליישומים כמו משחקים, סימולציות ואלגוריתמים של אבטחה. מתכנתים משתמשים באקראיות כדי לחקות גיוון בעולם האמיתי, לשפר את חוויית המשתמש או להבטיח נתונים באמצעות טכניקות הצפנה.

## איך לעשות:
Elm מטפל באקראיות באופן שונה משפות תכנות רבות אחרות, תוך שימוש במערכת ששומרת על פונקציות טהורות. כדי ליצור מספרים אקראיים, עליך לעבוד עם מודול `Random` של Elm. הנה דוגמה בסיסית ליצירת מספר אקראי בין 1 ל-100:

```Elm
import Html exposing (Html, text)
import Random

main : Html msg
main =
    Random.generate NewRandomNumber (Random.int 1 100)
    |> Html.map (text << toString)

type Msg = NewRandomNumber Int
```

קטע קוד זה משתמש ב-`Random.generate` כדי ליצור פקודה שכאשר היא מתבצעת, מייצרת מספר אקראי בטווח המצוין. דקלרציית ה-`type Msg` משמשת לטיפול במספר שנוצר בפונקציית העדכון של יישומך ב-Elm.

לדוגמה יותר אינטראקטיבית, בואו נסתכל על תרחיש בו משתמשים מפעילים יצירת מספר אקראי דרך לחיצה:

```Elm
import Html exposing (Html, button, div, text)
import Html.Events exposing (onClick)
import Random

type alias Model = Int

type Msg = Generate

update : Msg -> Model -> (Model, Cmd Msg)
update msg model =
    case msg of
        Generate ->
            (model, Random.generate NewRandomNumber (Random.int 1 100))

view : Model -> Html Msg
view model =
    div []
        [ text ("Generated number: " ++ String.fromInt model)
        , button [ onClick Generate ] [ text "Generate new number" ]
        ]

type Msg = NewRandomNumber Int
```

יישום Elm זה מציג אינטראקטיביות, עודכן להצגה עם מספר אקראי חדש בכל פעם שהמשתמש לוחץ על הכפתור.

## עיון מעמיק
עיצוב מערכת יצירת המספרים האקראיים של Elm נובע מהתחייבות השפה לטוהר ולניתוח. במקום פונקציות ישירות ולא טהורות שמחזירות ערכים שונים בכל קריאה, Elm מכילה את האקראיות במבנה `Cmd`, בהתאם לארכיטקטורה שלה המפרידה בין תופעות לוואי לבין פונקציות טהורות.

למרות שגישה זו מבטיחה עקביות בהתנהגות היישום ומקלה על ניפוי באגים, היא מציגה מורכבות ראשונית בפני אלה שרגילים ליצירת מספרים אקראיים באופן פקודתי. עם זאת, יתרונות שמירת טוהר היישום והקלות בבדיקות לרוב מפצים על המורכבות ההתחלתית.

שיטת Elm מנוגדת גם לשפות המציעות מחוללי מספרים אקראיים גלובליים, אשר עלולים להוביל לבאגים עדינים עקב מצב משותף. על ידי דרישת טיפול מפורש ביצירת מספרים אקראיים והשפעותיה, Elm מעודדת מפתחים לחשוב באופן יותר ביקורתי על היכן ואיך אקראיות משפיעה על היישומים שלהם, מה שמוביל לקוד יותר מוצק וניתן לחיזוי.

לחלופין, שפות פונקציונליות אחרות מציעות פונקציונליות דומות אך עשויות ליישם זאת באופן שונה. האסקל, לדוגמה, גם כן שומרת על טוהר ביצירת מספרים אקראיים אך דרך שימוש במונדים, מושג ש-Elm בחרה במודע להימנע ממנו כדי לפשט את המודל שלה. לעומת זאת, הגישה של Elm נגישה יותר למתחילים ומדגישה ארכיטקטורת יישום ישירה ללא להקריב את עוצמת עקרונות התכנות הפונקציונליים.
