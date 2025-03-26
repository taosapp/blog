---
title: vscode 自定义代码片段
date: 2019-08-05 17:15:00
---

# 1.添加“用户代码片段”的菜单位置：
文件-> 首选项 -> 用户代码片段
![文件-首选项-用户代码片段](/media/vscode-snippet.png)

## 代码片段文件存储的路径：
C:\Users\your-user-name\AppData\Roaming\Code\User\snippets\taosapp.code-snippets


# 2.示例：增加三个片段
* 1) sclink 输出HTML

```HTML
<script src="assets/x.js"></script>
```

* 2) csslink 输出HTML

```HTML
<link rel="stylesheet" href="assets/x.css">
```

* 3) for5 输出javascript

```javascript
for (var i = 0; i < array.length; i++) {
    var item = array[i];

};
```

## "taosapp.code-snippets"里的内容

```json
{
    "scLink": {
        "prefix": "sclink",
        "body": [
            "<script src=\"assets/$1.js\"></script>",
            "\t$2"
        ],
        "description": "script link"
    },
    "cssLink": {
        "prefix": "csslink",
        "body": [
            "<link rel=\"stylesheet\" href=\"assets/$1.css\">",
            "\t$2"
        ],
        "description": "css link"
    },
    "for loop ES5": {
        "prefix": "for5",
        "body": [
            "for (var i = 0; i < array.length; i++) {\n        var item = array[i];\n        $1\n};"
        ],
        "description": "ES5 for code"
    }
}
```