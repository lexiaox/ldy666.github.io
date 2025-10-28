# 🧩 C语言 `getchar()` 与 `putchar()` 用法简明笔记

## 📘 1. 函数简介

| 函数 | 功能 | 头文件 | 返回类型 |
|------|------|---------|-----------|
| `getchar()` | 从键盘读取一个字符 | `<stdio.h>` | `int`（返回字符的 ASCII 值） |
| `putchar()` | 向屏幕输出一个字符 | `<stdio.h>` | `int`（返回输出的字符） |

---

## ⚙️ 2. 基本语法

```c
int getchar(void);
int putchar(int c);
```

---

## 🧠 3. 示例一：读取并输出字符

```c
#include <stdio.h>

int main() {
    int ch;
    printf("请输入一个字符：");
    ch = getchar();      // 从键盘读入一个字符
    printf("你输入的是：");
    putchar(ch);         // 输出该字符
    putchar('\n');
    return 0;
}
```

---

## 💡 4. 示例二：连续读取并回显

```c
#include <stdio.h>

int main() {
    int c;
    printf("请输入一行文字（回车结束）：\n");
    while ((c = getchar()) != '\n') {  // 逐字符读取直到换行
        putchar(c);                    // 立即输出
    }
    return 0;
}
```

---

## ⚠️ 5. 注意事项

- `getchar()` **会读取空格和换行符**。  
- `putchar()` 只输出一个字符，若要换行需显式使用 `putchar('\n');`。  
- 返回类型为 `int`，不是 `char`，是为了能返回 `EOF`（-1）。  
