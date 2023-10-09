# CSR&#x20;

CSR是[Certificate](Certificate_w6tWgKGaAmrQ5VQWWkTemq.md "Certificate") [Signing](Signing_jTmffdT2LxcyJ9gsej5ob.md "Signing") [Request](Request_3ENYnzsenSqwTt2gjRVaN3.md "Request")

即证书请求文件，也就是证书申请者在申请数字证书时由CSP(加密服务提供者)在生成私钥的同时也生成证书请求文件，证书申请者只要把CSR文件提交给证书颁发机构后，证书颁发机构使用其根证书私钥签名就生成了证书公钥文件，也就是颁发给用户的证书。

## 用途

通常CSR文件是在拿到参考码、授权码进行证书签发和下载时，通过网页提交给CA的（也可以由浏览器自动生成）。
