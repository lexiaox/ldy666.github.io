# strcmp函数用法

## 函数原型
```c
int strcmp(const char *s1, const char *s2);
```

## 参数说明
- `s1`：待比较的第一个字符串
- `s2`：待比较的第二个字符串

## 返回值
- **0**：两个字符串相等
- **负值**：`s1` 字典序小于 `s2`
- **正值**：`s1` 字典序大于 `s2`

## 示例代码
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "Hello";
    char str2[] = "hello";
    int result = strcmp(str1, str2);
    
    if(result == 0) {
        printf("字符串相等
");
    } else if(result < 0) {
        printf("str1 小于 str2
");
    } else {
        printf("str1 大于 str2
");
    }
    return 0;
}
```

## 注意事项
1. 严格区分大小写（'A' != 'a'）
2. 遇到` `即终止比较
3. 缓冲区必须以` `结尾
4. 禁止直接比较指针地址
以上内容由文心人工智能生成合成
