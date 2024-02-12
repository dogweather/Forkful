---
title:                "הגדלת אותיות במחרוזת"
aliases:
- /he/cpp/capitalizing-a-string/
date:                  2024-02-03T19:05:36.786957-07:00
model:                 gpt-4-0125-preview
simple_title:         "הגדלת אותיות במחרוזת"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/cpp/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## מה ולמה?
הגדלת אות ראשונה במחרוזת מערבת המרת התו הראשון של כל מילה במחרוזת לאות גדולה אם הוא באות קטנה, תוך שמירה על שאר התווים ללא שינוי. מתכנתים לעיתים קרובות מבצעים משימה זו עבור עיצוב פלטים, קלטים של משתמשים או עיבוד נתונים כדי להבטיח עקביות באופן שבו הטקסט מוצג או מעובד, במיוחד בממשקי משתמש או משימות נרמול נתונים.

## איך לעשות:
ב-C++, ניתן להגדיל אות ראשונה במחרוזת באמצעות הספרייה הסטנדרטית ללא צורך בספריות צד שלישי. עם זאת, עבור התנהגויות הגדלה מורכבות או ספציפיות יותר, ספריות כמו Boost יכולות להיות מועילות מאוד. להלן דוגמאות הממחישות את שתי הגישות.

### באמצעות ספריית C++ סטנדרטית:

```cpp
#include <iostream>
#include <cctype> // עבור std::tolower ו-std::toupper
#include <string>

std::string capitalizeString(const std::string& input) {
    std::string result;
    bool capitalizeNext = true;

    for (char ch : input) {
        if (std::isspace(ch)) {
            capitalizeNext = true;
        } else if (capitalizeNext) {
            ch = std::toupper(ch);
            capitalizeNext = false;
        }
        result += ch;
    }

    return result;
}

int main() {
    std::string text = "hello world from c++";
    std::string capitalizedText = capitalizeString(text);
    std::cout << capitalizedText << std::endl; // פלט: "Hello World From C++"
}
```

### באמצעות ספריית Boost:

למניפולציה מתקדמת של מחרוזות, כולל הגדלת אות ראשונה תוך התחשבות באזור, ייתכן שתרצה להשתמש בספריית Boost String Algo.

ראשית, הבטח שהספרייה של Boost מותקנת ומוגדרת בפרויקט שלך. לאחר מכן תוכל לכלול את הכותרות הנדרשות ולהשתמש בתכונות שלה כפי שמוצג למטה.

```cpp
#include <boost/algorithm/string.hpp>
#include <iostream>
#include <string>

int main() {
    std::string text = "hello world from c++";
    std::string capitalizedText = text;

    // הגדלת אות ראשונה של כל מילה
    boost::algorithm::to_lower(capitalizedText); // הבטחת שהמחרוזת באותיות קטנות
    capitalizedText[0] = std::toupper(capitalizedText[0]); // הגדלת התו הראשון

    for (std::size_t i = 1; i < capitalizedText.length(); ++i) {
        if (isspace(capitalizedText[i - 1])) { // הגדלה לאחר רווח
            capitalizedText[i] = std::toupper(capitalizedText[i]);
        }
    }

    std::cout << capitalizedText << std::endl; // פלט: "Hello World From C++"
}
```

במקרה זה, Boost מפשטת חלק ממשימות מניפולציית המחרוזת אך עדיין דורשת גישה מותאמת אישית להגדלה אמיתית מכיוון שהיא בעיקר מציעה פונקציונליות להמרה והעברה בין רישיות.
