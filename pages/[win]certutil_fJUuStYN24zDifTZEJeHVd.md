# \[win]certutil





##

## 示例

-   示例：下载了MySQL安装包进行完整性验证
    ```纯文本
    >certutil -hashfile mysql-5.7.38-linux-glibc2.12-i686.tar.gz md5
    MD5 hash of mysql-5.7.38-linux-glibc2.12-i686.tar.gz:
    cb984e0d2b3fb552381aabfa64380b9e
    CertUtil: -hashfile command completed successfully.

    C:\Users\wq\Downloads>cb984e0d2b3fb552381aabfa64380b9e
    ```
    ![](../image/image_oa1VmXELgd.png)
-   示例3：sha256校验
    ```html
    certutil -hashfile filename SHA256 
    ```
-   示例2：sha1校验
    ```html
    certutil -hashfile filename SHA1
    ```
-   示例1：文件md5校验
    ```html
    certutil -hashfile filename MD5
    ```

## 碎片

-   [md5sum](md5sum_VwXAJvNQQYMGiC39jKG14.md "md5sum")
