# \[Win]SSH

known\_hosts

```bash
usage: ssh [-46AaCfGgKkMNnqsTtVvXxYy] 
           [-B bind_interface]
           [-b bind_address] 
           [-c cipher_spec] 
           [-D [bind_address:]port]
           [-E log_file] 
           [-e escape_char] 
           [-F configfile] 
           [-I pkcs11]
           [-i identity_file] 
            [-J [user@]host[:port]] 
           [-L address]
           [-l login_name]
           [-m mac_spec]
           [-O ctl_cmd]
           [-o option] 
            [-p port] 
           [-Q query_option] 
           [-R address] 
           [-S ctl_path] 
           [-W host:port]
           [-w local_tun[:remote_tun]] destination [command]
```





示例： `ssh wq@192.168.1.105 -p 29611`





-   \[E]ssh无法登录 known\_hosts
    -   详情
        ```powershell
        [00:44:53.283] Log Level: 2
        [00:44:53.291] SSH Resolver called for "ssh-remote+101.34.109.107", attempt 1
        [00:44:53.292] "remote.SSH.useLocalServer": false
        [00:44:53.292] "remote.SSH.useExecServer": false
        [00:44:53.292] "remote.SSH.showLoginTerminal": false
        [00:44:53.292] "remote.SSH.remotePlatform": {"qwertyui.vip-django":"linux","qwertyui.vip-djangoBlog":"linux","qwertyui.vip-mydjango":"linux","qwertyui.vip":"linux","qwertyui.vip_django_drf":"linux"}
        [00:44:53.292] "remote.SSH.path": undefined
        [00:44:53.292] "remote.SSH.configFile": undefined
        [00:44:53.292] "remote.SSH.useFlock": true
        [00:44:53.293] "remote.SSH.lockfilesInTmp": false
        [00:44:53.293] "remote.SSH.localServerDownload": auto
        [00:44:53.293] "remote.SSH.remoteServerListenOnSocket": false
        [00:44:53.294] "remote.SSH.showLoginTerminal": false
        [00:44:53.294] "remote.SSH.defaultExtensions": []
        [00:44:53.295] "remote.SSH.loglevel": 2
        [00:44:53.295] "remote.SSH.enableDynamicForwarding": true
        [00:44:53.295] "remote.SSH.enableRemoteCommand": false
        [00:44:53.295] "remote.SSH.serverPickPortsFromRange": {}
        [00:44:53.295] "remote.SSH.serverInstallPath": {}
        [00:44:53.298] VS Code version: 1.82.2
        [00:44:53.298] Remote-SSH version: remote-ssh@0.106.4
        [00:44:53.298] win32 x64
        [00:44:53.299] SSH Resolver called for host: 101.34.109.107
        [00:44:53.299] Setting up SSH remote "101.34.109.107"
        [00:44:53.302] Using commit id "abd2f3db4bdb28f9e95536dfa84d8479f1eb312d" and quality "stable" for server
        [00:44:53.304] Install and start server if needed
        [00:44:54.538] Checking ssh with "F:\Program Files\Python310\Scripts\ssh.exe -V"
        [00:44:54.540] Got error from ssh: spawn F:\Program Files\Python310\Scripts\ssh.exe ENOENT
        [00:44:54.541] Checking ssh with "F:\Program Files\Python310\ssh.exe -V"
        [00:44:54.541] Got error from ssh: spawn F:\Program Files\Python310\ssh.exe ENOENT
        [00:44:54.542] Checking ssh with "C:\Users\wq\AppData\Local\Microsoft\WindowsApps\ssh.exe -V"
        [00:44:54.542] Got error from ssh: spawn C:\Users\wq\AppData\Local\Microsoft\WindowsApps\ssh.exe ENOENT
        [00:44:54.543] Checking ssh with "C:\Users\wq\AppData\Local\Programs\EmEditor\ssh.exe -V"
        [00:44:54.543] Got error from ssh: spawn C:\Users\wq\AppData\Local\Programs\EmEditor\ssh.exe ENOENT
        [00:44:54.543] Checking ssh with "F:\aid sofware\Microsoft VS Code\bin\ssh.exe -V"
        [00:44:54.545] Got error from ssh: spawn F:\aid sofware\Microsoft VS Code\bin\ssh.exe ENOENT
        [00:44:54.546] Checking ssh with "C:\windows\system32\ssh.exe -V"
        [00:44:54.583] > OpenSSH_for_Windows_8.1p1, LibreSSL 3.0.2

        [00:44:54.589] Running script with connection command: "C:\windows\system32\ssh.exe" -T -D 10240 "101.34.109.107" bash
        [00:44:54.590] Terminal shell path: C:\Windows\System32\cmd.exe
        [00:44:54.939] > @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
        > ]0;C:\Windows\System32\cmd.exe
        [00:44:54.939] Got some output, clearing connection timeout
        [00:44:54.953] > @    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
        > @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
        > IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
        > Someone could be eavesdropping on you right now (man-in-the-middle attack)!     
        > It is also possible that a host key has just been changed.
        > The fingerprint for the ECDSA key sent by the remote host is
        > SHA256:9vbPSZYIywkdkuqKPu/qtGdUn7n3Wd6Epb9xqxx0ZfE.
        > Please contact your system administrator.
        > Add correct host key in C:\\Users\\wq/.ssh/known_hosts to get rid of this messag
        > e.
        > Offending ECDSA key in C:\\Users\\wq/.ssh/known_hosts:19
        > ECDSA host key for [101.34.109.107]:19980 has changed and you have requested str
        > ict checking.
        > Host key verification failed.
        > The process tried to write to a nonexistent pipe.
        > 
        [00:44:56.221] "install" terminal command done
        [00:44:56.221] Install terminal quit with output: Host key verification failed.
        [00:44:56.221] Received install output: Host key verification failed.
        [00:44:56.222] Failed to parse remote port from server output
        [00:44:56.223] Resolver error: Error: 
          at g.Create (c:\Users\wq\.vscode\extensions\ms-vscode-remote.remote-ssh-0.106.4\out\extension.js:2:637879)
          at t.handleInstallOutput (c:\Users\wq\.vscode\extensions\ms-vscode-remote.remote-ssh-0.106.4\out\extension.js:2:635279)
          at t.tryInstall (c:\Users\wq\.vscode\extensions\ms-vscode-remote.remote-ssh-0.106.4\out\extension.js:2:756878)
          at async c:\Users\wq\.vscode\extensions\ms-vscode-remote.remote-ssh-0.106.4\out\extension.js:2:717470
          at async t.withShowDetailsEvent (c:\Users\wq\.vscode\extensions\ms-vscode-remote.remote-ssh-0.106.4\out\extension.js:2:720723)
          at async C (c:\Users\wq\.vscode\extensions\ms-vscode-remote.remote-ssh-0.106.4\out\extension.js:2:714384)
          at async t.resolve (c:\Users\wq\.vscode\extensions\ms-vscode-remote.remote-ssh-0.106.4\out\extension.js:2:718119)
          at async c:\Users\wq\.vscode\extensions\ms-vscode-remote.remote-ssh-0.106.4\out\extension.js:2:901789
        [00:44:56.226] ------

        ```
    根据提供的日志信息，出现了 "Host key verification failed" 错误，这是因为SSH连接中远程主机的主机密钥发生了变化，而你的计算机在已知主机密钥文件（`known_hosts`）中找不到新的主机密钥，因此连接失败。

    要解决这个问题，你可以执行以下步骤：
    1.  打开Windows资源管理器，导航到你的用户目录（通常是`C:\Users\<你的用户名>`）。
    2.  在用户目录下查找名为`.ssh`的隐藏文件夹。如果没有该文件夹，可以创建一个。
    3.  在`.ssh`文件夹中，找到名为`known_hosts`的文件，并用文本编辑器打开它。
    4.  在`known_hosts`文件中，找到与远程主机IP地址（`101.34.109.107`）相关的行。这是之前连接时记录的主机密钥。
    5.  删除与远程主机IP地址相关的行，保存文件并关闭编辑器。
    6.  然后重新尝试SSH连接。
    重新尝试连接后，SSH将会重新获取新的主机密钥并将其保存在`known_hosts`文件中。请注意，删除`known_hosts`文件中的行将删除之前记录的所有主机密钥，这可能会带来一定的安全风险。确保你信任远程主机的真实性，以防止中间人攻击。
