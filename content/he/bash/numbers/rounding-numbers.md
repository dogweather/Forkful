---
date: 2024-01-26 03:45:37.482349-07:00
description: "\u05E2\u05D9\u05D2\u05D5\u05DC \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD\
  \ \u05E4\u05D9\u05E8\u05D5\u05E9\u05D5 \u05D7\u05D9\u05EA\u05D5\u05DA \u05D4\u05E1\
  \u05E4\u05E8\u05D5\u05EA \u05D0\u05D7\u05E8\u05D9 \u05D4\u05E0\u05E7\u05D5\u05D3\
  \u05D4 \u05D4\u05E2\u05E9\u05E8\u05D5\u05E0\u05D9\u05EA \u05DC\u05E2\u05E8\u05DA\
  \ \u05E4\u05E9\u05D5\u05D8 \u05D9\u05D5\u05EA\u05E8 \u05E9\u05DE\u05E1\u05E4\u05D9\
  \u05E7 \u05D8\u05D5\u05D1 \u05DC\u05D4\u05E7\u05E9\u05E8 \u05E0\u05EA\u05D5\u05DF\
  . \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05D2\u05DC\u05D9\u05DD\
  \ \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05E2\u05DC \u05DE\u05E0\u05EA \u05DC\u05E4\
  \u05E9\u05D8 \u05EA\u05D5\u05E6\u05D0\u05D5\u05EA, \u05DC\u05D7\u05E1\u05D5\u05DA\
  \ \u05D1\u05DE\u05E7\u05D5\u05DD, \u05D0\u05D5\u2026"
lastmod: '2024-03-13T22:44:39.612163-06:00'
model: gpt-4-0125-preview
summary: "\u05E2\u05D9\u05D2\u05D5\u05DC \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05E4\
  \u05D9\u05E8\u05D5\u05E9\u05D5 \u05D7\u05D9\u05EA\u05D5\u05DA \u05D4\u05E1\u05E4\
  \u05E8\u05D5\u05EA \u05D0\u05D7\u05E8\u05D9 \u05D4\u05E0\u05E7\u05D5\u05D3\u05D4\
  \ \u05D4\u05E2\u05E9\u05E8\u05D5\u05E0\u05D9\u05EA \u05DC\u05E2\u05E8\u05DA \u05E4\
  \u05E9\u05D5\u05D8 \u05D9\u05D5\u05EA\u05E8 \u05E9\u05DE\u05E1\u05E4\u05D9\u05E7\
  \ \u05D8\u05D5\u05D1 \u05DC\u05D4\u05E7\u05E9\u05E8 \u05E0\u05EA\u05D5\u05DF."
title: "\u05E2\u05D9\u05D2\u05D5\u05DC \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD"
weight: 13
---

## איך לעשות את זה:
הנה המדריך לעיגול ב-Bash:

```Bash
# עיגול למטה בעזרת 'floor' עם bc
echo "scale=0; 3.49/1" | bc

# עיגול למעלה בעזרת 'ceiling' עם bc
echo "scale=0; 3.01/1" | bc -l

# עיגול לשלם הקרוב באמצעות printf
printf "%.0f\n" 3.49

# טריק לעיגול לשלם הקרוב בעזרת bc
echo "(3.49+0.5)/1" | bc
```

דוגמאות לפלטים—ישירות מפי הטרמינל:

```
3  # עוגל למטה (floor)
4  # עוגל למעלה (ceiling)
3  # עוגל לשלם הקרוב (עם printf)
3  # עוגל לשלם הקרוב (עם bc)
```

## צלילה עמוקה
בימים ההם, לא היו `bc` או `printf` בסקריפטים של Bash לעשות את קסמי המתמטיקה. הותיקים נאלצו להסתמך על כלים חיצוניים או פתרונות יצירתיים. כעת, `bc` מאפשרת לך לבצע חישובים מדויקים. זכרו, `bc` לא מעגלת כברירת מחדל—היא מורידה. חלק ה-scale מגדיר את פעולת נקודת העשרון.

אלטרנטיבות? אפשר להשתמש ב-`awk` לעיגול בלי לעבור ל-`bc` או להתאמץ עם `perl` לצורכי מתמטיקה כבדים יותר. למזוכיסטים בינינו, תוכלו ללכת על Bash טהור עם, בואו נאמר, מניפולציה איטרטיבית של מחרוזות - אבל למה?

לגבי פרטים, `bc` לא רק מעגלת, היא עושה המון דברים במתמטיקה—תוכלו לשנות סקאל, לעשות סינוס, שורש ריבועי, מה שתרצו. עם `printf`, זה יותר על עיצוב טקסט, אבל היי, זה מעגל מספרים, אז אנחנו לא מתלוננים.

## ראו גם
למי שרוצה עוד:

- מדריך GNU `bc`: https://www.gnu.org/software/bc/manual/html_mono/bc.html
- פקודת Bash `printf`: https://www.gnu.org/software/bash/manual/html_node/Bash-Builtins.html#index-printf
- מדריך למשתמש של AWK (לעיגול ועיבוד טקסט נוסף): https://www.gnu.org/software/gawk/manual/gawk.html
- עוד מתמטיקה, סקריפטים, וטריקים במספרים ב-Bash: https://mywiki.wooledge.org/BashFAQ/022
