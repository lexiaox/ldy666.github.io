# strcpy函数用法

## 函数原型
```c
char *strcpy(char *dest, const char *src);
```

## 参数说明
- `dest`：目标缓冲区（必须足够大）
- `src`：源字符串（必须以` `结尾）

## 返回值
- 目标字符串`dest`的指针

## 示例代码
```c
#include <stdio.h>
#include <string.h>

int main() {
    char src[] = "Secure Copy";
    char dest[20];
    
    // 安全复制方式
    strncpy(dest, src, sizeof(dest)-1);
    dest[sizeof(dest)-1] = '\0'; // 手动添加终止符
    
    printf("复制结果: %s
", dest);
    return 0;
}
```

## 注意事项
1. 必须确保目标缓冲区足够大
2. 目标与源不能重叠（否则用memmove）
3. 源字符串不能为NULL
4. 推荐使用`strncpy`+手动添加终止符
以上内容由文心人工智能生成合成
