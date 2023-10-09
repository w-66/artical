# 中英混输

参考：

<https://10101.io/2019/01/30/rime-configuration>

关于英文输入

增加一个英文词库，来满足中文模式下方便地输入一些常见的英文单词的需求。

1.  在用户文件夹下放入两个文件：easy\_en.schema.yaml、easy\_en.dict.yaml（文件可去 GitHub 查找）
2.  在double\_pinyin\_flypy.custom.yaml（其他方案找到对应文件）加入以下内容：

    \# 加載 easy\_en 依賴  "schema/dependencies/@1": easy\_en  "engine/translators/@4": table\_translator\@english # 載入翻譯英文的碼表翻譯器，取名爲 english  english: # english 翻譯器的設定項    dictionary: easy\_en    spelling\_hints: 9    enable\_completion: false # 是否启用英文输入联想补全    enable\_sentence: false    initial\_quality: 0 # 调整英文候选词的位置，如 -3 会更靠后

