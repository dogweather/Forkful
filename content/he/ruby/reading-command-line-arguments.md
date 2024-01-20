---
title:                "קריאה של ארגומנטים משורת הפקודה"
html_title:           "C#: קריאה של ארגומנטים משורת הפקודה"
simple_title:         "קריאה של ארגומנטים משורת הפקודה"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/ruby/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## מה זה ולמה? 

קריאת ארגומנטים משורת הפקודה היא היכולת לקבל מידע מהמשתמש בתחילת ביצוע התוכנית שלך. מתכנתים משתמשים בזה באופן נרחב כדי להעניק למשתמשים שלהם אופציות גמישות לשליטה בביצועים של התוכנית.

## איך זה מתבצע: 

שימו לב לקוד הבא:

```Ruby
ARGV.each do |arg|
  puts "Arg value: #{arg}"
end
```

בהרצת התוכנית עם כמה ארגומנטים (לדוגמה, ruby my_script.rb arg1 arg2), תוצאת הפלט תהיה:

```
Arg value: arg1
Arg value: arg2
```

## צלילה עמוקה: 

קריאת ארגומנטים משורת הפקודה היא יכולת שנמצאת ברוב תָּכנוּת שפות, וRuby לא שונה. מבחינה היסטורית, היא הייתה חלק משפות התכנות המוקדמות ביותר. אלטרנטיבה הנפוצה היא שימוש בגרפיקאי ממשק משתמש, אך התכנת בשורת הפקודה מאפשרת תוכנית גמישה וחזקה יותר.

## ראה גם:

ישנם מגוון משאבים וחומרי למידה אוויר-ליין שמתמקדים בנושא הקריאה של ארגומנטים משורת הפקודה.

- [דוקומנטציה הרשמית של Ruby](https://ruby-doc.org/core-2.7.0/ARGV.html)
- [ראיון טכני Ruby - קריאה של ארגומנטים משורת הפקודה](https://www.interviewbit.com/ruby-interview-questions/)
- [הדרכה של W3Schools על ארגומנטים שורת הפקודה ב-Ruby](https://www.w3schools.com/ruby/ruby_command_line.asp)

עבודה מהנה ומרתקת!