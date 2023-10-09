# 自定义代码片段

C:\Users\wq\AppData\Roaming\Code\User\snippets

-   \[Q]vscode 中怎么添加自定义的快捷指令，比如，输入一个c1 可以选择输出 12356

    在 VS Code 中，可以通过自定义代码片段（snippet）来实现快捷指令的功能。以下是一个简单的例子，将 c1 定义为输出数字 1、2、3、5、6：
    1.  打开 VS Code，进入命令面板（快捷键 Ctrl/Cmd + Shift + P）。
    2.  输入 "Configure User Snippets" 并选择 "Preferences: Configure User Snippets"。
    3.  选择 "New Global Snippets File"。
    4.  输入一个名称（比如 "my-snippets"），保存。
    5.  在新创建的代码片段文件中，输入以下代码：
    ```python
    {
      "c1": {
        "prefix": "c1",
        "body": [
          "12356"
        ],
        "description": "Output numbers 1, 2, 3, 5, 6"
      }
    }

    ```
-   \[Q]输入之后怎么让光标处在2的后面
    ```python
    {
        "c1": {
            "prefix": "c1",
            "body": [
                "12$0356"
            ],
            "description": "Custom command"
        }
    }

    ```

