---
title:                "חיבור מחרוזות"
html_title:           "C++: חיבור מחרוזות"
simple_title:         "חיבור מחרוזות"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/ruby/concatenating-strings.md"
---

{{< edit_this_page >}}

## מה ולמה?

מילול של מחרוזות הוא התהליך שבו מעבירים שני או יותר מחרוזות למחרוזת אחת. מתכנתים עושים את זה או בעת שמרות טקסט, או כאשר הם רוצים ליצור טקסט במבנה מסוים.

## איך לעשות:

קוד סדרתי:
```Ruby
str1 = "shalom"
str2 = "olechem"
message = str1 + " " + str2
puts message
```
הפלט:
```Ruby
"shalom olechem"
```
בעזרת המתודה `concat`:
```Ruby
str1 = "shalom"
str2 = "olechem"
str1.concat(" ", str2)
puts str1
```
הפלט:
```Ruby
"shalom olechem"
```
## צלילה עמוקה:

כאשר אנחנו מדביקים מחרוזות ב - Ruby, יש לנו למעשה כמה אפשרויות. ניתן לבחור להשתמש באופרטור `+` או במתודה `concat`, או אף אפשר להשתמש באופרטור `<<`. האופרטור `+` יוצר מחרוזת חדשה, בעוד `concat` רק משנה את המחרוזת המקורית. 

## ראה גם:

1. [חיבור מחרוזות | תכנות ברובי](https://he.wikibooks.org/wiki/%D7%AA%D7%9B%D7%A0%D7%95%D7%AA_%D7%91%D7%A8%D7%95%D7%91%D7%99/%D7%97%D7%99%D7%91%D7%95%D7%A8_%D7%9E%D7%97%D7%A8%D7%95%D7%96%D7%95%D7%AA)
2. [Concatenation - The Ruby Way](https://www.rubyguides.com/2018/06/ruby-string-concatenation/)
3. [Why use two string concatenation techniques?](https://stackoverflow.com/questions/4684446/why-does-ruby-have-both-and-for-concatenation)