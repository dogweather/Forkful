---
aliases:
- /hi/ruby/writing-tests/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:33:02.327205-07:00
description: "Ruby \u092E\u0947\u0902 \u092A\u0930\u0940\u0915\u094D\u0937\u0923 \u0906\
  \u092A\u0915\u0947 \u0915\u094B\u0921 \u0915\u0947 \u0935\u093F\u092D\u093F\u0928\
  \u094D\u0928 \u092A\u0930\u093F\u0938\u094D\u0925\u093F\u0924\u093F\u092F\u094B\u0902\
  \ \u092E\u0947\u0902 \u0905\u092A\u0947\u0915\u094D\u0937\u093F\u0924 \u0935\u094D\
  \u092F\u0935\u0939\u093E\u0930 \u0915\u094B \u0938\u0924\u094D\u092F\u093E\u092A\
  \u093F\u0924 \u0915\u0930\u0928\u0947 \u0915\u0947 \u092C\u093E\u0930\u0947 \u092E\
  \u0947\u0902 \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\
  \u092E\u0930 \u0938\u0939\u0940\u092A\u0928 \u0915\u0940 \u091C\u093E\u0902\u091A\
  , \u092A\u093F\u091B\u0921\u093C\u0947\u092A\u0928 \u0915\u094B \u0930\u094B\u0915\
  \u0928\u0947 \u0914\u0930\u2026"
lastmod: 2024-02-18 23:09:04.303151
model: gpt-4-0125-preview
summary: "Ruby \u092E\u0947\u0902 \u092A\u0930\u0940\u0915\u094D\u0937\u0923 \u0906\
  \u092A\u0915\u0947 \u0915\u094B\u0921 \u0915\u0947 \u0935\u093F\u092D\u093F\u0928\
  \u094D\u0928 \u092A\u0930\u093F\u0938\u094D\u0925\u093F\u0924\u093F\u092F\u094B\u0902\
  \ \u092E\u0947\u0902 \u0905\u092A\u0947\u0915\u094D\u0937\u093F\u0924 \u0935\u094D\
  \u092F\u0935\u0939\u093E\u0930 \u0915\u094B \u0938\u0924\u094D\u092F\u093E\u092A\
  \u093F\u0924 \u0915\u0930\u0928\u0947 \u0915\u0947 \u092C\u093E\u0930\u0947 \u092E\
  \u0947\u0902 \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\
  \u092E\u0930 \u0938\u0939\u0940\u092A\u0928 \u0915\u0940 \u091C\u093E\u0902\u091A\
  , \u092A\u093F\u091B\u0921\u093C\u0947\u092A\u0928 \u0915\u094B \u0930\u094B\u0915\
  \u0928\u0947 \u0914\u0930\u2026"
title: "\u091F\u0947\u0938\u094D\u091F \u0932\u093F\u0916\u0928\u093E"
---

{{< edit_this_page >}}

## क्या और क्यों?
Ruby में परीक्षण आपके कोड के विभिन्न परिस्थितियों में अपेक्षित व्यवहार को सत्यापित करने के बारे में है। प्रोग्रामर सहीपन की जांच, पिछड़ेपन को रोकने और पुनर्गठन की सुविधा के लिए परीक्षण लिखते हैं, मजबूत और बनाए रखने योग्य अनुप्रयोगों के लिए लक्ष्य के साथ।

## कैसे:
Ruby में `Test::Unit` नामक एक निर्मित पुस्तकालय है जो इकाई परीक्षणों को लिखने के लिए है, जो सरल संरचनाओं के भीतर परीक्षण प्रथाओं को समाहित करती है। हालांकि, Ruby समुदाय अक्सर उनकी उन्नत अभिव्यक्ति और लचीलापन के कारण RSpec और Minitest जैसी तृतीय-पक्ष पुस्तकालयों की ओर झुकाव रखता है।

### `Test::Unit` का उपयोग करते हुए:
```ruby
require 'test/unit'

class CalculatorTest < Test::Unit::TestCase
  def test_addition
    result = 2 + 2
    assert_equal 4, result
  end
end
```
अपनी परीक्षण फ़ाइल को टर्मिनल से चलाएं, और आपको एक आउटपुट मिलना चाहिए जो परीक्षणों की सफलता या विफलता को इंगित करता है:
```
Loaded suite test_calculator
Started
.
Finished in 0.001288 seconds.
1 tests, 1 assertions, 0 failures, 0 errors, 0 pendings, 0 omissions, 0 notifications
100% passed
```

### RSpec का उपयोग करते हुए:
RSpec Ruby के लिए एक लोकप्रिय BDD (Behavior-Driven Development) ढांचा है। `gem install rspec` के साथ इसे स्थापित करें, फिर इसे अपने प्रोजेक्ट में `rspec --init` के साथ प्रारंभ करें।

```ruby
# calculator_spec.rb
require_relative '../calculator'

describe Calculator do
  it 'सही तरीके से दो संख्याओं को जोड़ती है' do
    expect(Calculator.add(2, 2)).to eq(4)
  end
end
```
`rspec` कमांड के साथ परीक्षण चलाएं। उदाहरण आउटपुट:
```
.

Finished in 0.002 seconds (files took 0.1 seconds to load)
1 example, 0 failures
```

### Minitest का उपयोग करते हुए:
Minitest TDD, BDD, मॉकिंग, और बेंचमार्किंग का समर्थन करने वाली परीक्षण सुविधाओं का एक पूरा सेट प्रदान करता है। इसे `gem install minitest` के साथ स्थापित करें और इस प्रकार इसका उपयोग करें:

```ruby
# test_calculator.rb
require 'minitest/autorun'
require_relative '../calculator'

class CalculatorTest < Minitest::Test
  def test_addition
    assert_equal 4, Calculator.add(2, 2)
  end
end
```

अपनी परीक्षण फ़ाइल को सीधे या minitest के लिए सेट किए गए `rake` टास्क के माध्यम से चलाएं। नमूना आउटपुट:
```
Run options: --seed 33407

# Running:

.

Finished in 0.001027s, 974.5922 runs/s, 974.5922 assertions/s.
1 runs, 1 assertions, 0 failures, 0 errors, 0 skips
```

इन पुस्तकालयों का उपयोग करके अपने Ruby परियोजनाओं में परीक्षण को लागू करके, आप इससे अधिक विश्वसनीय और बनाए रखने योग्य कोड आधारों की ओर ले जाते हैं।
