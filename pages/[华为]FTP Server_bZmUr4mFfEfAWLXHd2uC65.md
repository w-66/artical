# \[华为]FTP Server

# 开启FTP

```html
ftp server enable

aaa
 local-user user_name password cipher %$%$Lq,5!k^7zS5+iY-s{EA$y0bl%$%$
 local-user user_name privilege level 3
 local-user user_name ftp-directory flash:/test
 local-user user_name service-type ftp

```

```纯文本
There was a problem using the initial local directory C:\Users\Administrator\Documents: The system cannot find the path specified. 
Attempting to fall back to default initial path.

Press Ctrl+C to cancel or Enter to reconnect immediately.
Reconnecting in 4 seconds...

```



# client登录操作

[FTP命令](FTP命令_cm57xziDNxrmTmSfbF7LGz.md "FTP命令")



```html
ftp> put C:\Users\Downloads\AR509C-V200R010C10SPC700.cc
200 Port command okay.
150 Opening BINARY mode data connection for AR509C-V200R010C10SPC700.cc.
226 Transfer complete.
ftp: 发送 91889408 字节，用时 177.88秒 516.60千字节/秒。
```



```html
C:\Documents and Settings\Administrator> d:
D:\> cd ftp
D:\ftp> ftp 10.164.30.20
Connected to 10.164.30.20. 
220 FTP service ready. 
User(10.164.30.20:(none)):AR  # 输入用户名
331 Password required for AR.
Password:  # 输入密码huawei@123,回车，密码不显示在屏幕。
230 User logged in. 
ftp> binary
200 Type set to I. 
ftp> get AR509C-V200R010C10SPC600.cc
200 PORT command okay 
150 "D:\FTP\ AR509C-V200R010C10SPC600.cc" file ready to send (61464320 bytes) in ASCII mode
226 Transfer finished successfully.
ftp: 收到 91070080 字节，用时 91.42秒 1000.67千字节/秒。
```

