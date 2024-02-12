---
title:                "日付を比較する"
aliases:
- ja/cpp/comparing-two-dates.md
date:                  2024-01-20T17:32:41.018397-07:00
model:                 gpt-4-1106-preview
simple_title:         "日付を比較する"

tag:                  "Dates and Times"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/cpp/comparing-two-dates.md"
---

{{< edit_this_page >}}

## What & Why? (何となぜ？)
比較する二つの日付とは、単純にそれらが同じか、どちらが先かを判断することです。これは、期限の管理、予約システム、履歴データ分析など、プログラミングでよく出くわす作業。

## How to: (やり方)
```C++
#include <iostream>
#include <chrono>
#include <ctime>

int main() {
    // 現在のシステムの日時を取得
    auto now = std::chrono::system_clock::now();

    // tm構造体に変換
    std::time_t now_c = std::chrono::system_clock::to_time_t(now - std::chrono::hours(24));
    std::tm* now_tm = std::localtime(&now_c);
    
    // 昨日の日付を作成
    std::tm yesterday_tm = *now_tm;

    // 今日の日付を作成
    std::tm today_tm = *std::localtime(&now_c);
    today_tm.tm_hour = 0;
    today_tm.tm_min = 0;
    today_tm.tm_sec = 0;
    
    // tm構造体をtime_tに変換
    std::time_t yesterday = std::mktime(&yesterday_tm);
    std::time_t today = std::mktime(&today_tm);

    // 日付を比較
    if (std::difftime(today, yesterday) > 0) {
        std::cout << "Today is after Yesterday.\n";
    } else {
        std::cout << "Yesterday is not after Today.\n";
    }

    return 0;
}
```
サンプル出力:
```
Today is after Yesterday.
```

## Deep Dive (深掘り)
歴史的背景では、C++には長い間`<ctime>`ライブラリが日時を扱う主流でしたが、C++11から`<chrono>`ライブラリが導入され、より精確で扱いやすいAPIが提供されています。また、Boost.Date_Timeライブラリのような他の選択肢もありますが、標準ライブラリの機能拡張が進むにつれて、より稀なニーズに対処するためのものとなりつつあります。実装の詳細では、`<chrono>`は時間のポイントを`time_point`オブジェクトとして表現し、時間の間隔や期間を`duration`オブジェクトとして扱います。これにより、日付の比較は異なる時間ポイント間の`duration`を計算することで行えます。

## See Also (関連情報)
- [std::chrono](https://en.cppreference.com/w/cpp/chrono)
- [std::ctime](https://en.cppreference.com/w/cpp/header/ctime)
- [Boost.Date_Time](https://www.boost.org/doc/libs/1_75_0/doc/html/date_time.html)
