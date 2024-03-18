---
title:                "একটি ওয়েবপেজ ডাউনলোড করা"
date:                  2024-03-17T17:47:32.878665-06:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## কি এবং কেন?
ওয়েব পেজ ডাউনলোড করা মানে ইন্টারনেট থেকে HTML কন্টেন্ট আনা। প্রোগ্রামাররা ডেটা পার্স করা, তথ্য স্ক্রেপ করা, বা প্রোগ্রাম্যাটিকভাবে পরিবর্তনগুলি পর্যবেক্ষণ করার জন্য এটি করে থাকেন।

## কিভাবে:
`net/http` এবং `open-uri` মতো লাইব্রেরি এবং জেমস দ্বারা Ruby এ ওয়েব পেজ ডাউনলোড করা সহজ। `net/http` ব্যবহার করে এখানে কিভাবে করবেন তা নিচে দেওয়া হল:

```Ruby
require 'net/http'
require 'uri'

url = URI.parse('http://example.com') 
response = Net::HTTP.get_response(url)

puts response.body if response.is_a?(Net::HTTPSuccess)
```

আপনি `http://example.com` এর HTML কন্টেন্ট প্রিন্ট করে দেখতে পাবেন।

`open-uri` ব্যবহার করা আরও সহজ:

```Ruby
require 'open-uri'

downloaded_page = URI.open('http://example.com').read
puts downloaded_page
```

আবার, ওয়েব পেজের কন্টেন্ট আপনার টার্মিনালে দেখানো হবে।

## গভীর ডুব
ওয়েবের প্রাথমিক দিনগুলিতে, একটি পৃষ্ঠা ডাউনলোড করা আরও বেশি শ্রম-প্রবণ ছিল, যার মধ্যে ম্যানুয়াল HTTP অনুরোধ তৈরি করা অন্তর্ভুক্ত। আজ, Ruby অনেকটা জটিলতা দূর করে দেয়।

`net/http` এবং `open-uri` এর বিকল্প হিসেবে উচ্চ পর্যায়ের জেমস যেমন `HTTParty` এবং `RestClient` রয়েছে। এগুলি আরও বেশি ফিচার এবং একটি অবজেক্ট-ওরিয়েন্টেড প্রোচেস অফার করে। ভারী দায়িত্বের ওয়েব স্ক্র্যাপিংয়ের জন্য, অনেক Rubyist এরা `Nokogiri` ব্যবহার করে HTML পার্স করার জন্য বা `Mechanize` যা একটি ওয়েব ব্রাউজারের মত কাজ করে।

বাস্তবায়ন সম্পর্কে বিবেচনা করার সময়, মনে রাখবেন `open-uri` হচ্ছে `net/http`-এর জন্য একটি র‍্যাপার, তাই এটি খুব সুবিধাজনক তবে কিছু লো-লেভেল নিয়ন্ত্রণের অভাব থাকতে পারে। `net/http` আপনাকে অনুরোধের উপর আরও নিয়ন্ত্রণ দেয় তবে সাধারণ কাজের জন্য হয়তো বাচ্যবাহুল্য হতে পারে।

## আরও দেখুন
আরও পঠন এবং অতিরিক্ত সম্পদের জন্য, দেখুন:

- Ruby's Net::HTTP ডক: [https://ruby-doc.org/stdlib-3.0.0/libdoc/net/http/rdoc/Net/HTTP.html](https://ruby-doc.org/stdlib-3.0.0/libdoc/net/http/rdoc/Net/HTTP.html)
- Open-URI ডক: [https://ruby-doc.org/stdlib-3.0.0/libdoc/open-uri/rdoc/OpenURI.html](https://ruby-doc.org/stdlib-3.0.0/libdoc/open-uri/rdoc/OpenURI.html)
- Nokogiri's ওয়েবপেজ: [https://nokogiri.org/](https://nokogiri.org/)
- Mechanize জেম রিপোজিটরি: [https://github.com/sparklemotion/mechanize](https://github.com/sparklemotion/mechanize)
- HTTParty জেম গিটহাবে: [https://github.com/jnunemaker/httparty](https://github.com/jnunemaker/httparty)
- RestClient জেম: [https://github.com/rest-client/rest-client](https://github.com/rest-client/rest-client)
