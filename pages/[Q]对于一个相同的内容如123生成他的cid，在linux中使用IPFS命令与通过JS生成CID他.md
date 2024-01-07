# \[Q]对于一个相同的内容如123生成他的cid，在linux中使用IPFS命令与通过JS生成CID他们之间的CID不一样

\[A]答案：linux中的echo默认末尾带有换行符，JS生成的则只是字符串的哈希，所以通过ipfs block stat可以看到他们字节相差一个，也就是那个换行符造成的，只要取消换行符得到CID就相同。 \[[\[Linux\]echo](https://www.wolai.com/ru54t3YUTsZYFSXo4edTYi "\[Linux]echo")`-n`; CID inspector,`ipfs block put`, `ipfs block stat`, \[JS]TextEncoder]

```json
bash-5.1# echo -n 123 | ipfs block put
bafkreifgmwsfsiccf6ouc7sim7x5yt5yubfb6p77d6qh5gmoq337pit24m
```

-   Linux中
    ```json
    bash-5.1# echo '123' | ipfs block put
    bafkreiayciipr6ohphbg3iozwidvxxqbe4yc5yhd7sryzgud6wy53ds5hm
    bash-5.1# echo 123 | ipfs block put
    bafkreiayciipr6ohphbg3iozwidvxxqbe4yc5yhd7sryzgud6wy53ds5hm
    ```
-   JS中
    ```json
    /**
     * 通过字符生成CIDv1; 
     * @Multicodec 0x55 raw ipld permanent binary
     * @param {string} value 
     * @returns 
     */
    export async function genCID_0x55(data) {  
        // 将字符串转换为二进制数据
        const textEncoder = new TextEncoder()
        const binaryData = textEncoder.encode(data)
        const block = await Block.encode({ value: binaryData, codec: raw, hasher: sha256 })
        return block.cid.toString()
    }

    console.log(1702643106, await genCID_0x55(value)); // bafkreifgmwsfsiccf6ouc7sim7x5yt5yubfb6p77d6qh5gmoq337pit24m

    ```
-   通过cid inspector发现digest (base32 multibase)与digest (hex)不相同
    ```json

    Human readable CID

    base32 - cidv1 - raw - (sha2-256 : 256 : A665A45920422F9D417E4867EFDC4FB8A04A1F3FFF1FA07E998E86F7F7A27AE3)

    multibase - version - multicodec - multihash (name : size : digest in hex)
    Multibase

    prefix:
        b
    name:
        base32

    Multicodec

    code:
        0x55
    name:
        raw
    description:
        raw binary

    Multihash

    code:
        0x12
    name:
        sha2-256
    bits:
        256
    digest (base32 multibase):
        bciqkmzneleqeel45if7eqz7p3rh3rickd4776h5ap2my5bxx66rhvyy
    digest (hex):
        A665A45920422F9D417E4867EFDC4FB8A04A1F3FFF1FA07E998E86F7F7A27AE3

    CID Byte length
    As base32 string (Bytes)
        59
    Binary (Bytes)
        36
    CIDv1 (Base32)
    bafkreifgmwsfsiccf6ouc7sim7x5yt5yubfb6p77d6qh5gmoq337pit24m

    ```
    ```json

    Human readable CID

    base32 - cidv1 - raw - (sha2-256 : 256 : 181210F8F9C779C26DA1D9B2075BDE0127302EE0E3FCA38C9A83F5B1DD8E5D3B)

    multibase - version - multicodec - multihash (name : size : digest in hex)
    Multibase

    prefix:
        b
    name:
        base32

    Multicodec

    code:
        0x55
    name:
        raw
    description:
        raw binary

    Multihash

    code:
        0x12
    name:
        sha2-256
    bits:
        256
    digest (base32 multibase):
        bciqbqeqq7d44o6ocnwq5tmqhlppacjzqf3qoh7fdrsnih5nr3whf2oy
    digest (hex):
        181210F8F9C779C26DA1D9B2075BDE0127302EE0E3FCA38C9A83F5B1DD8E5D3B

    CID Byte length
    As base32 string (Bytes)
        59
    Binary (Bytes)
        36
    CIDv1 (Base32)
    bafkreiayciipr6ohphbg3iozwidvxxqbe4yc5yhd7sryzgud6wy53ds5hm

    ```
-   通过ipfs block stat，大小也不相同，多一个字节
    ```json
    bash-5.1# ipfs block stat bafkreifgmwsfsiccf6ouc7sim7x5yt5yubfb6p77d6qh5gmoq337pit24m
    Key: bafkreifgmwsfsiccf6ouc7sim7x5yt5yubfb6p77d6qh5gmoq337pit24m
    Size: 3
    bash-5.1# ipfs block stat bafkreiayciipr6ohphbg3iozwidvxxqbe4yc5yhd7sryzgud6wy53ds5hm
    Key: bafkreiayciipr6ohphbg3iozwidvxxqbe4yc5yhd7sryzgud6wy53ds5hm
    Size: 4
    ```
-   在通过ipfs cat找到了原因：JS生成的时内容中不带换行|回车，Linux IPFS命令中则有，具体来说是`echo`默认带换行需要取消&#x20;
    ```json
    bash-5.1# ipfs cat bafkreiayciipr6ohphbg3iozwidvxxqbe4yc5yhd7sryzgud6wy53ds5hm
    123
    bash-5.1# ipfs cat bafkreifgmwsfsiccf6ouc7sim7x5yt5yubfb6p77d6qh5gmoq337pit24m
    123bash-5.1# 
    ```
