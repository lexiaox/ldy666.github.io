`sprintf` 函数是C语言中的一个标准库函数，用于将格式化的数据写入字符串中。

**函数原型：**
```c
int sprintf(char *str, const char *format, ...);
```

**参数说明：**
- `str`：指向目标字符串的指针（字符数组）
- `format`：格式化字符串，包含普通字符和格式说明符
- `...`：可变参数列表，根据格式说明符提供相应的数据

**常用格式说明符：**
- `%d`：整数
- `%f`：浮点数
- `%c`：字符
- `%s`：字符串
- `%x`：十六进制整数

**使用示例：**

```c
#include <stdio.h>

int main() {
    char buffer[50];
    int a = 10;
    float b = 3.14;
    char c = 'A';
    char name[] = "John";
    
    // 将多个数据格式化到字符串中
    sprintf(buffer, "整数:%d, 浮点数:%.2f, 字符:%c, 名字:%s", a, b, c, name);
    // buffer中的内容："整数:10, 浮点数:3.14, 字符:A, 名字:John"
    
    // 只转换整数
    char num_str[20];
    sprintf(num_str, "%d", 12345);
    // num_str中的内容："12345"
    
    // 组合不同类型数据
    char info[100];
    sprintf(info, "年龄:%d, 成绩:%.1f", 18, 95.5);
    // info中的内容："年龄:18, 成绩:95.5"
    
    return 0;
}
```

**返回值：**
- 成功时返回写入的字符总数（不包括结尾的null字符）
- 失败时返回负值

**注意事项：**
- 要确保目标字符串有足够的空间存储结果
- 会自动在结果字符串末尾添加null终止符（`\0`）
- 比`printf`更安全的是`snprintf`，可以指定最大写入长度