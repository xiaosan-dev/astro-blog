---
title: Android String.format 异常
description: "Android String.format 转换异常"
publishDate: "2024/10/17"
tags: ["bug"]
---

这是最近修改代码时，发现的bug。

```java
String.format("1~19%test")
```

上述代码中的`%t`会被`String.format`所识别为格式化字符串。

在不修改API返回的情况下，使用下述的`StringUtil.format`替换系统的`String.format`。

```java
    class StringUtil {
        /*
        * Returns a formatted string using the specified format string and arguments.
        * In order to avoid call String.format causes an ConvertException (25%ア)
        * eg: StringUtil.format("test%arg0test%arg1test", "AAA", "BBB") // testAAAtestBBBtest
        * */
        public static String format(String format, Object... args) {
            for (int i = 0; i < args.length; i++) {
                format = format.replace("%arg" + i, args[i].toString());
            }
            return format;
        }
    }
```