---
title:                "עבודה עם XML"
date:                  2024-01-26T04:35:53.675120-07:00
model:                 gpt-4-0125-preview
simple_title:         "עבודה עם XML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/ruby/working-with-xml.md"
---

{{< edit_this_page >}}

## מה ולמה?
עבודה עם XML כוללת ניתוח, יצירה ושינוי של מסמכי XML (שפת סימון נרחבת) באמצעות קוד. תכנתים עושים זאת כדי להתקשר עם מגוון שירותי אינטרנט, קובצי קונפיגורציה, ותסדירי החלפת נתונים שבהם XML היא שפת הממשק הפופולרית.

## כיצד לעשות זאת:
בואו נשתמש ב-REXML, המצורף עם Ruby, כדי לנתח קטע XML:
```Ruby
require 'rexml/document'
include REXML

xml_data = <<-XML
<fruits>
  <fruit name="apple" color="green"/>
  <fruit name="banana" color="yellow"/>
</fruits>
XML

document = Document.new(xml_data)
document.elements.each('fruits/fruit') do |element|
  puts "Name: #{element.attributes['name']}, Color: #{element.attributes['color']}"
end
```
פלט:
```
Name: apple, Color: green
Name: banana, Color: yellow
```

יצירת XML גם היא פשוטה:
```Ruby
doc = Document.new
doc.add_element 'fruits'
apple = doc.root.add_element 'fruit', {'name' => 'apple', 'color' => 'green'}
banana = doc.root.add_element 'fruit', {'name' => 'banana', 'color' => 'yellow'}
puts doc
```
פלט XML:
```XML
<fruits>
  <fruit name="apple" color="green"/>
  <fruit name="banana" color="yellow"/>
</fruits>
```

## צלילה עמוקה:
שורשי ה-XML חוזרים לשנות ה-90 כתת-קבוצה מפושטת של SGML למסמכי אינטרנט. הוא מסורבל אך מאוד מבני, וזו הסיבה לכך שהוא נשאר בשימוש. הוא לא הדבר היחידי בעיר—JSON ו-YAML הפכו לפופולריים בשל פשטותם—אך ה-XML מחזיק מעמד במערכות רבות ארגוניות ומורשת.

Ruby מספקת מספר דרכים להתמודד עם XML. REXML הוא ספרייה כולה ב-Ruby שקל לזנק אליה. Nokogiri הוא ג'ם המעטפת ספריות C מהירות יותר, ומציע מהירות ותכונות נוספות. לבחור ביניהם? התחל עם REXML למשימות קטנות ועבור ל-Nokogiri אם אתה זקוק לכוח נוסף.

מאחורי הקלעים, ניתוח XML הוא אודות המרת מחרוזות למודלים DOM או SAX. DOM יוצר עץ בזיכרון, בעוד SAX מזרים את המסמך ושולח אירועים כשהוא מנתח. REXML מציע שני המודלים, אך בדרך כלל הוא איטי יותר מהרחבות C כמו אלו שמשתמש בהם Nokogiri.

## ראה גם:
- תיעוד Ruby REXML: https://www.rubydoc.info/stdlib/rexml
- ג'ם Nokogiri: https://nokogiri.org/
- מפרט ה-XML: https://www.w3.org/XML/
- הקדמה ל-SAX: https://www.saxproject.org/
- השוואה בין YAML ל-JSON ל-XML: https://www.upwork.com/resources/json-vs-xml-vs-yaml
