---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:11:01.339167-07:00
description: "\u9023\u60F3\u914D\u5217\u3001\u307E\u305F\u306F\u30CF\u30C3\u30B7\u30E5\
  \u30DE\u30C3\u30D7\u306F\u3001\u30C7\u30FC\u30BF\u3092\u30AD\u30FC\u3068\u5024\u306E\
  \u30DA\u30A2\u3068\u3057\u3066\u4FDD\u5B58\u3067\u304D\u308B\u305F\u3081\u3001\u30AD\
  \u30FC\u3067\u60C5\u5831\u3092\u6574\u7406\u3057\u3066\u53D6\u5F97\u3057\u3084\u3059\
  \u304F\u306A\u308A\u307E\u3059\u3002\u7279\u306B\u8A2D\u5B9A\u3084\u3055\u307E\u3056\
  \u307E\u306A\u5C5E\u6027\u3092\u6271\u3046\u5834\u5408\u306A\u3069\u3001\u30EA\u30B9\
  \u30C8\u3060\u3051\u3067\u306F\u4E0D\u5341\u5206\u306A\u30C7\u30FC\u30BF\u51E6\u7406\
  \u3092\u3088\u308A\u69CB\u9020\u5316\u3057\u305F\u65B9\u6CD5\u3067\u6271\u3044\u305F\
  \u3044\u3068\u304D\u306B\u4FBF\u5229\u3067\u3059\u3002"
lastmod: '2024-03-13T22:44:42.721666-06:00'
model: gpt-4-0125-preview
summary: "\u9023\u60F3\u914D\u5217\u3001\u307E\u305F\u306F\u30CF\u30C3\u30B7\u30E5\
  \u30DE\u30C3\u30D7\u306F\u3001\u30C7\u30FC\u30BF\u3092\u30AD\u30FC\u3068\u5024\u306E\
  \u30DA\u30A2\u3068\u3057\u3066\u4FDD\u5B58\u3067\u304D\u308B\u305F\u3081\u3001\u30AD\
  \u30FC\u3067\u60C5\u5831\u3092\u6574\u7406\u3057\u3066\u53D6\u5F97\u3057\u3084\u3059\
  \u304F\u306A\u308A\u307E\u3059\u3002\u7279\u306B\u8A2D\u5B9A\u3084\u3055\u307E\u3056\
  \u307E\u306A\u5C5E\u6027\u3092\u6271\u3046\u5834\u5408\u306A\u3069\u3001\u30EA\u30B9\
  \u30C8\u3060\u3051\u3067\u306F\u4E0D\u5341\u5206\u306A\u30C7\u30FC\u30BF\u51E6\u7406\
  \u3092\u3088\u308A\u69CB\u9020\u5316\u3057\u305F\u65B9\u6CD5\u3067\u6271\u3044\u305F\
  \u3044\u3068\u304D\u306B\u4FBF\u5229\u3067\u3059\u3002."
title: "\u9023\u60F3\u914D\u5217\u306E\u4F7F\u7528"
weight: 15
---

## 方法:
FishはBash 4+のようにネイティブに連想配列をサポートしていませんが、リストと文字列操作の組み合わせを使用することで、同様の機能を実現できます。こちらがそれらの模倣方法です：

まず、「連想配列」要素を別々に設定します：

```Fish Shell
set food_color_apple "red"
set food_color_banana "yellow"
```

要素にアクセスするには、直接参照します：

```Fish Shell
echo $food_color_apple
# 出力: red
```

それらを繰り返し処理する必要がある場合は、命名規則を考えたforループを使用します：

```Fish Shell
for food in apple banana
    echo $food_color_$food
end
# 出力:
# red
# yellow
```

Bashの`${!array[@]}`で全てのキーを取得する機能が恋しい場合は、キーを別のリストに保存できます：

```Fish Shell
set food_keys apple banana

for key in $food_keys
    echo $key 'is' $food_color_$key
end
# 出力:
# apple is red
# banana is yellow
```

## 詳細解説
他のスクリプト言語のような本物の連想配列は、まだFishのアプローチの一部ではありません。ここで示された回避策は、Fishの文字列操作とリスト機能を活用して、擬似的な連想配列構造を作成します。この方法は機能しますが、組み込みの連想配列サポートがあればもっとクリーンでエラーが少なくなるはずです。BashやZshなどの他のシェルは組み込みの連想配列機能を提供しており、より直接的で読みやすいコードになります。しかし、Fishの設計哲学はシンプルさとユーザーフレンドリーさを目指しており、そのような機能が犠牲になることもあります。この回避策はほとんどのニーズを満たしますが、Fish Shellの進化に注目してください。開発者はコミュニティのフィードバックに基づいて積極的に機能の改善と追加を行っています。
