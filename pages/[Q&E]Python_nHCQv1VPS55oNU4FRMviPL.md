# \[Q\&E]Python

### 问题

-   \[Q]Python判断字典是否为空 \[[\[Py\]字典dict](\[Py]字典dict_mooKYVeHS7ytgK761kAmeR.md "\[Py]字典dict")]

    在 Python 中，可以使用多种方法来判断一个字典是否为空。下面是几种常见的方法：
    1.  使用逻辑判断：
    ```python
    my_dict = {}

    if my_dict:
        print("字典不为空")
    else:
        print("字典为空")
    ```
    在 Python 中，空字典被视为 False，非空字典被视为 True。因此，通过直接在条件语句中对字典进行判断，可以确定它是否为空。
    1.  使用 len() 函数：
    ```python
    my_dict = {}

    if len(my_dict) == 0:
        print("字典为空")
    else:
        print("字典不为空")
    ```
    使用 len() 函数可以获取字典的键值对数量，如果数量为 0，则表示字典为空。
    1.  检查所有键：
    ```python
    my_dict = {}

    if not any(my_dict):
        print("字典为空")
    else:
        print("字典不为空")
    ```
    使用 `any()` 函数可以检查字典中的所有键，如果没有键存在，则表示字典为空。

    这些方法可以根据你的具体需求来选择使用，以确定字典是否为空。请根据实际情况选择最适合的方法。
-   \[Q]Python 判断字符串是否为空 \[[\[Py\]字符串str](\[Py]字符串str_pTHvmwuesWwMHJLwG7ZbLY.md "\[Py]字符串str")]

    在 Python 中，可以使用多种方法来判断一个字符串是否为空。下面是几种常见的方法：
    1.  使用逻辑判断：
    ```python
    my_string = "Hello, World!"

    if my_string:
        print("字符串不为空")
    else:
        print("字符串为空")
    ```
    在 Python 中，空字符串被视为 False，非空字符串被视为 True。因此，通过直接在条件语句中对字符串进行判断，可以确定它是否为空。
    1.  使用 len() 函数：
    ```python
    my_string = "Hello, World!"

    if len(my_string) == 0:
        print("字符串为空")
    else:
        print("字符串不为空")
    ```
    使用 len() 函数可以获取字符串的长度，如果长度为 0，则表示字符串为空。
    1.  使用 strip() 方法：
    ```python
    my_string = "   "

    if my_string.strip():
        print("字符串不为空")
    else:
        print("字符串为空")
    ```
    strip() 方法用于移除字符串两端的空格和换行符等字符。如果移除两端空格后的字符串非空，则表示原始字符串不为空。

    这些方法可以根据你的具体需求来选择使用，以确定字符串是否为空。请根据实际情况选择最适合的方法。
-   如何查看 Django 源码在你系统的哪个位置 \[-c]
    ```python
    python -c "import django; print(django.__path__)"
    ```

### 报错

-   \[E]UnicodeEncodeError: 'latin-1' codec can't encode character '\u2026' in position 512: ordinal not in range(256)
    ```react&#x20;jsx
    Traceback (most recent call last):
      File "f:\Code\Python\Python\py_crawler\bilibili\get_follow_video_list\get_follow_video_list.py", line 282, in <module>
        get_up_videos_list(data_dict, 'sub_videos.json')
      File "f:\Code\Python\Python\py_crawler\bilibili\get_follow_video_list\get_follow_video_list.py", line 212, in get_up_videos_list
        data_json = get_response_json(mid, up_url)
      File "f:\Code\Python\Python\py_crawler\bilibili\get_follow_video_list\get_follow_video_list.py", line 124, in get_response_json
        response = requests.get(url, headers=headers)
      File "F:\Program Files\Python310\lib\site-packages\requests\api.py", line 73, in get
        return request("get", url, params=params, **kwargs)
      File "F:\Program Files\Python310\lib\site-packages\requests\api.py", line 59, in request
        return session.request(method=method, url=url, **kwargs)
      File "F:\Program Files\Python310\lib\site-packages\requests\sessions.py", line 587, in request
        resp = self.send(prep, **send_kwargs)
      File "F:\Program Files\Python310\lib\site-packages\requests\sessions.py", line 701, in send
        r = adapter.send(request, **kwargs)
      File "F:\Program Files\Python310\lib\site-packages\requests\adapters.py", line 489, in send
        resp = conn.urlopen(
      File "F:\Program Files\Python310\lib\site-packages\urllib3\connectionpool.py", line 703, in urlopen
        httplib_response = self._make_request(
      File "F:\Program Files\Python310\lib\site-packages\urllib3\connectionpool.py", line 398, in _make_request
        conn.request(method, url, **httplib_request_kw)
      File "F:\Program Files\Python310\lib\site-packages\urllib3\connection.py", line 239, in request
        super(HTTPConnection, self).request(method, url, body=body, headers=headers)
      File "F:\Program Files\Python310\lib\http\client.py", line 1282, in request
        self._send_request(method, url, body, headers, encode_chunked)
      File "F:\Program Files\Python310\lib\http\client.py", line 1323, in _send_request
        self.putheader(hdr, value)
      File "F:\Program Files\Python310\lib\site-packages\urllib3\connection.py", line 224, in putheader
        _HTTPConnection.putheader(self, header, *values)
      File "F:\Program Files\Python310\lib\http\client.py", line 1255, in putheader
        values[i] = one_value.encode('latin-1')
    UnicodeEncodeError: 'latin-1' codec can't encode character '\u2026' in position 512: ordinal not in range(256)
    ```
    你遇到的错误是UnicodeEncodeError，它是由于尝试在'latin-1'字符集中编码不在范围内的字符所导致的。通常这个问题发生在尝试在HTTP头部中包含非ASCII字符时。

    要解决这个错误，你需要确保用于请求的头部只包含ASCII字符。一种处理方法是在发送请求前使用Python的`encode`方法，使用'utf-8'编码，它支持更广泛的字符范围。

    为了实现这一点，修改`get_response_json`函数，在发送请求前对头部进行编码。以下是更新后的函数版本：
    ```python
    def get_response_json(mid, url):
        headers = {
            # 在这里放入你的头部（不需要更改）
        }

        # 使用utf-8对头部进行编码
        encoded_headers = {k: v.encode('utf-8') for k, v in headers.items()}

        response = requests.get(url, headers=encoded_headers)

        # 函数的其余部分（无需更改）
        if response.status_code == 200:
            # 在这里放入你的代码（无需更改）
        else:
            # 在这里放入你的代码（无需更改）
    ```
    通过使用'utf-8'编码头部，你可以处理更广泛的字符范围，包括导致UnicodeEncodeError的字符。

    请记得将这个更改应用到你代码中使用头部的其他地方。

    另外，注意你代码中的特定头部值包含了大量的cookie和其他数据。请注意在代码中使用硬编码的cookie和敏感信息可能不是最佳实践。建议根据你的具体使用情况，以更安全和适当的方式处理认证和cookie。
-   \[E]`'unicodeescape' codec can't decode bytes in position 2-3: truncated \UXXXXXXXX escape`

    原因：在文件夹中复制地址时，文件夹中的地址是用 \ 来分隔不同文件夹的，而Python识别地址时只能识别用 / 分隔的地址。
-   \[Error]TypeError: diGua.jiaTiaoLiao() takes 1 [positional](positional_cdRreeLGcFF6Xu7L7g3y8N.md "positional") argument but 2 [were](were_987eXhy9ZSi18sjCxMMzu6.md "were") [given](given_r4abA78rxpMTa8u95tjzK7.md "given")

    翻译：类型错误： diGua.jiaTiaoLiao()取了一个位置参数，但是给出了两个参数位置

    问题：调用类的方法，但是类的方法没有写self，所以报错
    ```python
    def jiaTiaoLiao( self , flavour):
    ```
-   cookie : The term 'cookie' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spell <文件名不能有括号>...

    ing of the name, or if a path was included, verify that the path is correct and try again.

    At line:1 char:118
    -   ... n.exe f:/Code/Python/demo\_basics/demo.crawler\_rullib\_weibo(cookie).py
    -   \~\~\~\~\~\~
        -   CategoryInfo          : ObjectNotFound: (cookie:String) \[], CommandNotFoundException
        -   FullyQualifiedErrorId : CommandNotFoundException
    ![](../image/image_sVwRA-xUfA.png)

## 提示

-   [Expected](Expected_hbBogJvHhExMJsgQ9BfdqV.md "Expected") [indented](indented_4aokkcK9HWexTMq5ytzK5m.md "indented") [block](block_vHhqtkod19YEjrGDypRVEv.md "block")

    ![](../image/image_emDsVS55sc.png)
-   [statements](statements_puvHN9h5JqEs3Q5BYd8Bds.md "statements") must be [separated](separated_wNz9WDCB5J8DKUzmhUKZdv.md "separated") by [newlines](newlines_59iTokRDufQB84WuSTu8Yy.md "newlines") or [semicolons](semicolons_nuFaG2zbi3R2ZPPjQpTDVE.md "semicolons") Pylance

    ![](../image/image_eHzSgwbHYJ.png)
-   Return a copy of the [string](string_sGJHjyxUcxRJeHL7fpJUes.md "string")[^注释1] with leading and trailing [whitespace](whitespace_cjyWSXyuUKjvR7j5KextUn.md "whitespace") [removed](removed_89nDQtP4PTVTpEvAHZrNw6.md "removed"). If chars [^注释2]is [given](given_r4abA78rxpMTa8u95tjzK7.md "given") and not None, remove [characters](characters_38AYE588xwJkUjCQky39JY.md "characters") in chars instead. \[`.strip`] <ʷ[leading](leading_bFMpQXhDrxq8pobnumFmLQ.md "leading")adj.首位的，居前的；[trailing](trailing_gw6yu924myyaAuSho2ppfG.md "trailing")adj.后面的；>&#x20;

    ![](../image/image_nx1VW88Puy.png)

    返回字符串的副本，删除前导和尾部的空白。如果给定的是chars而不是None，则删除chars中的字符。&#x20;
-   Return a list of the words in the string, using sep as the  [delimiter string](<delimiter string_uPYvHgE497Czip8uyw79dS.md> "delimiter string") \[`.split`]

    sep

    The delimiter [according](according_ipinW38QxmKVBnQDoNUTLe.md "according") [which](which_2Z8rHRsSCfSMVCCXNHhHpc.md "which") to [split](split_o6STQYpB6cDFM3Qan5MbeY.md "split") the string. None (the default value) means split according to any whitespace, and discard empty strings from the result. &#x20;
    maxsplit &#x20;

    Maximum number of splits to do. -1 (the default value) means no limit.

    ![](../image/image_T8P_p93XWP.png)



[^注释1]: 字符串

[^注释2]: 字符
