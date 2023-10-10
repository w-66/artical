# \[E\&Q]Selenium

-   \[E]报错1：`(The process started from chrome location /usr/bin/google-chrome is no longer running, so ChromeDriver is assuming that Chrome has crashed.)`  解决方案：\[`'--no-sandbox'`]

    参考：[https://blog.csdn.net/blueheart20/article/details/81566903](https://blog.csdn.net/blueheart20/article/details/81566903 "https://blog.csdn.net/blueheart20/article/details/81566903")

    [参考快照](参考快照_91RntjssUftcYa8aNpCEwZ.md "参考快照")
    -   报错详情
        ```纯文本
        # xvfb-run python3 text-xvfb.py                     
        Traceback (most recent call last):
          File "text-xvfb.py", line 7, in <module>
            driver = Chrome(service=s)
          File "/usr/local/lib/python3.8/dist-packages/selenium/webdriver/chrome/webdriver.py", line 81, in __init__
            super().__init__(
          File "/usr/local/lib/python3.8/dist-packages/selenium/webdriver/chromium/webdriver.py", line 106, in __init__
            super().__init__(
          File "/usr/local/lib/python3.8/dist-packages/selenium/webdriver/remote/webdriver.py", line 288, in __init__
            self.start_session(capabilities, browser_profile)
          File "/usr/local/lib/python3.8/dist-packages/selenium/webdriver/remote/webdriver.py", line 381, in start_session
            response = self.execute(Command.NEW_SESSION, parameters)
          File "/usr/local/lib/python3.8/dist-packages/selenium/webdriver/remote/webdriver.py", line 444, in execute
            self.error_handler.check_response(response)
          File "/usr/local/lib/python3.8/dist-packages/selenium/webdriver/remote/errorhandler.py", line 249, in check_response
            raise exception_class(message, screen, stacktrace)
        selenium.common.exceptions.WebDriverException: Message: unknown error: Chrome failed to start: exited abnormally.
          (unknown error: DevToolsActivePort file doesn't exist)
          (The process started from chrome location /usr/bin/google-chrome is no longer running, so ChromeDriver is assuming that Chrome has crashed.)
        Stacktrace:
        #0 0x562b0df57013 <unknown>
        #1 0x562b0dd1d8f8 <unknown>
        #2 0x562b0dd45b80 <unknown>
        #3 0x562b0dd40c25 <unknown>
        #4 0x562b0dd847f2 <unknown>
        #5 0x562b0dd8429f <unknown>
        #6 0x562b0dd7c433 <unknown>
        #7 0x562b0dd4d3d5 <unknown>
        #8 0x562b0dd4e541 <unknown>
        #9 0x562b0dfa8eae <unknown>
        #10 0x562b0dfac3e5 <unknown>
        #11 0x562b0df8d9ee <unknown>
        #12 0x562b0dfad173 <unknown>
        #13 0x562b0df80e45 <unknown>
        #14 0x562b0dfcd968 <unknown>
        #15 0x562b0dfcdaf9 <unknown>
        #16 0x562b0dfe8f62 <unknown>
        #17 0x7f35356dc609 start_thread
        ```
    解决方案：
    ```纯文本
    chrome_options = webdriver.ChromeOptions()
    # chrome_options.add_argument('--headless')
    chrome_options.add_argument('--no-sandbox')
    chrome_options.add_argument('--disable-gpu')
    chrome_options.add_argument('--disable-dev-shm-usage')

    ```
-   \[E]运行时1048 Failed to read descriptor from node connection: 连到系统上的设备没有发挥作用。 (0x1F) >>忽略无用日志\[`.add_experimental_option`]
    ```javascript
    # 忽略无用的日志
    options.add_experimental_option("excludeSwitches", ['enable-automation', 'enable-logging'])
    ```
-   \[E]获取网易用户歌单标题时，只能到`html>body>div.g-bd>div.g-wrap`这一层，在往下，就报错了 | 重要信息1：[\[JS\]document](\[JS]document_rmn21mqHBYoFCmcAN3xwXW.md "\[JS]document")`.domain`
    ```python
    DevTools listening on ws://127.0.0.1:12989/devtools/browser/3896ab7b-9856-4f54-87c1-09ab509df89f
    [1127/195025.962:INFO:CONSOLE(103)] "Uncaught SecurityError: Blocked a frame with origin "https://music.163.com" from accessing a frame with origin "https://music.163.com". The frame requesting access set "document.domain" to "music.163.com", but the frame being accessed did not. Both must set "document.domain" to the same value to allow access.", source: https://s3.music.126.net/web/s/core_c837a71e03dca33da0921812acdefe31.js?c837a71e03dca33da0921812acdefe31 (103)
    ```
-   \[E]
    -   报错详情


        ```html
        root@360cfe754588:/www/django_www# python3 /www/django_www/crawler/get_wangyiyun_musicList.py 
        1.检测歌单ing：https://music.163.com/#/playlist?id=7624041147
        Traceback (most recent call last):
          File "/www/django_www/crawler/get_wangyiyun_musicList.py", line 259, in <module>
            songList = get_html_selenium(playList_id_list=playList_id_list)
          File "/www/django_www/crawler/get_wangyiyun_musicList.py", line 73, in get_html_selenium
            browser.get(url_cooked)
          File "/usr/local/lib/python3.8/dist-packages/selenium/webdriver/remote/webdriver.py", line 455, in get
            self.execute(Command.GET, {"url": url})
          File "/usr/local/lib/python3.8/dist-packages/selenium/webdriver/remote/webdriver.py", line 444, in execute
            self.error_handler.check_response(response)
          File "/usr/local/lib/python3.8/dist-packages/selenium/webdriver/remote/errorhandler.py", line 249, in check_response
            raise exception_class(message, screen, stacktrace)
        selenium.common.exceptions.WebDriverException: Message: unknown error: session deleted because of page crash
        from unknown error: cannot determine loading status
        from tab crashed
          (Session info: headless chrome=107.0.5304.110)
        Stacktrace:
        #0 0x563fc3ccb013 <unknown>
        #1 0x563fc3a9177a <unknown>
        #2 0x563fc3a7d3a6 <unknown>
        #3 0x563fc3a7cae6 <unknown>
        #4 0x563fc3a7bd1f <unknown>
        #5 0x563fc3a7bb30 <unknown>
        #6 0x563fc3a7a714 <unknown>
        #7 0x563fc3a7ac6c <unknown>
        #8 0x563fc3a87ebd <unknown>
        #9 0x563fc3a88bb2 <unknown>
        #10 0x563fc3a99c60 <unknown>
        #11 0x563fc3a9e294 <unknown>
        #12 0x563fc3a7b239 <unknown>
        #13 0x563fc3a997ff <unknown>
        #14 0x563fc3b09792 <unknown>
        #15 0x563fc3af0433 <unknown>
        #16 0x563fc3ac13d5 <unknown>
        #17 0x563fc3ac2541 <unknown>
        #18 0x563fc3d1ceae <unknown>
        #19 0x563fc3d203e5 <unknown>
        #20 0x563fc3d019ee <unknown>
        #21 0x563fc3d21173 <unknown>
        #22 0x563fc3cf4e45 <unknown>
        #23 0x563fc3d41968 <unknown>
        #24 0x563fc3d41af9 <unknown>
        #25 0x563fc3d5cf62 <unknown>
        #26 0x7f0023335609 start_thread

        ```
    -   解决方案
        ```html
        chrome_option.add_argument('--disable-dev-shm-usage')
        ```

