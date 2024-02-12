---
title:                "पाठ खोजना और बदलना"
aliases:
- hi/fish-shell/searching-and-replacing-text.md
date:                  2024-01-20T17:58:24.730163-07:00
model:                 gpt-4-1106-preview
simple_title:         "पाठ खोजना और बदलना"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/fish-shell/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## क्या और क्यों? (What & Why?)

टेक्स्ट खोजना और बदलना (search and replace) कंप्यूटर में शब्दों या वाक्यों की तलाश करके उन्हें नए से बदलने की प्रक्रिया है। प्रोग्रामर्स इसे बग्स ठीक करने, कोड अपडेट करने या डेटा संशोधन के लिए करते हैं।

## कैसे करें? (How to:)

Fish Shell में टेक्स्ट खोजने और बदलने के लिए `string` कमांड का इस्तेमाल होता है:

```Fish Shell
# मूल स्ट्रिंग बनाएँ.
set original "मैं Fish Shell सीख रहा हूँ।"

# 'सीख' को 'इस्तेमाल' से बदलें.
echo $original | string replace "सीख" "इस्तेमाल"

# आउटपुट: मैं Fish Shell इस्तेमाल रहा हूँ।
```

आगे, आपको एक फाइल में टेक्स्ट बदलने की जरूरत हो सकती है:

```Fish Shell
# 'example.txt' फाइल में हर 'Fish' को 'हिंदी Fish' से बदलें.
string replace -a "Fish" "हिंदी Fish" < example.txt > temp.txt; and mv temp.txt example.txt
```

## गहरी जानकारी (Deep Dive)

Fish Shell की `string` कमांड 2015 में रिलीज Fish 2.3.0 में आई थी। पहले, टेक्स्ट खोजने/बदलने के लिए `sed` और `awk` जैसे यूनिक्स उपकरणों पर निर्भर थे। `string` इस्तेमाल करने का फायदा इसकी सादगी और स्पष्टता में है। इसमें नियमित अभिव्यक्तियों (regexes) का समर्थन भी है जो कि जटिल पैटर्न के साथ भी खोजने/बदलने को सक्षम बनाता है।

## संबंधित स्रोत (See Also)

- Fish Shell डॉक्यूमेंटेशन: [https://fishshell.com/docs/current/index.html](https://fishshell.com/docs/current/index.html)
- RegEx testing: [https://regex101.com/](https://regex101.com/)
- स्ट्रिंग ऑपरेशंस ट्यूटोरियल: [https://fishshell.com/docs/current/commands.html#string](https://fishshell.com/docs/current/commands.html#string)
