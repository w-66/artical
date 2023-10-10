# \[En]Kibana

-   \[报错]**Failed to **[retrieve](retrieve_7Zytr5KtY9nWk5bCv5aWFc.md "retrieve")** lists **：[exception](exception_oH8TTJi7SVrJYUT25ZL5PN.md "exception"): Security must be explicitly enabled when using a \[basic] license. Enable security by setting \[xpack.security.enabled] to \[true] in the elasticsearch.yml file and restart the node. (500)

    ![](../image/image_pAftEtVoNm.png)

    `xpack.security.enabled:true`
        {
          "name": "Error",
          "body": {
            "message": "exception: Security must be explicitly enabled when using a [basic] license. Enable security by setting [xpack.security.enabled] to [true] in the elasticsearch.yml file and restart the node.",
            "status_code": 500
          },
          "message": "Internal Server Error",
          "stack": "http_fetch_error_HttpFetchError@http://10.43.1.51:5601/46307/bundles/core/core.entry.js:8:52683\nfetchResponse@http://10.43.1.51:5601/46307/bundles/core/core.entry.js:8:56906\n"
        }
-   \[Dev Tools] welcome to console
    ## Welcome to Console
    #### Quick [intro](intro_dcbYv1aKxChvsVxsmHw9RC.md "intro") to the UI&#xA;用户界面快速介绍
    The Console UI is [split](split_o6STQYpB6cDFM3Qan5MbeY.md "split") into two panes: an [editor](editor_gX8gm9Wt6cv9Q6ez2M57Zd.md "editor") pane (left) and a [response](response_hFjiQzNdFoT6CjVg7f9Cew.md "response") pane (right). Use the editor to type requests and [submit](submit_6JfwTeqVCzvsmyQL6qbU5W.md "submit") them to Elasticsearch. The results will be displayed in the response pane on the right side.
    Console UI 分为两个窗格：编辑器窗格（左）和响应窗格（右）。使用编辑器键入请求并将它们提交到 Elasticsearch。结果将显示在右侧的响应窗格中

    Console understands requests in a compact format, similar to cURL:
    Console 理解紧凑格式的请求，类似于 cURL：
    ```javascript
    # index a doc
    PUT index/_doc/1
    {
      "body": "here"
    }

    # and get it ...
    GET index/_doc/1
    ```
    Dev Tools Console editor example
    开发工具控制台编辑器示例

    [while](while_jCBSJx9dMeDsis1aKFXpPT.md "while") typing a request, Console will makesuggestions [which](which_2Z8rHRsSCfSMVCCXNHhHpc.md "which") you can [then](then_s6jZQuAE6vjTzwQbQEG3YP.md "then") accept by [hitting](hitting_eELLR6cxEMZiakPXDJu5f.md "hitting") Enter/Tab. These suggestions are [made](made_kKDbsYM1z8nKZV21BamXuY.md "made")**(构成) **[based](based_wmX8rCGCw97Z4adnTeuUdv.md "based") on the request [structure](structure_Wv9fsgJmwjPrUMmiUHWsx.md "structure") as well as your indices and types.
    键入请求时，控制台将提供建议，您可以通过按 Enter/Tab 键来接受建议。这些建议基于请求结构以及索引和类型进行提供。


    #### A few [quick](quick_eoQTSJkVkeAtnvQ3av2iNY.md "quick") tips, while I have your [attention](attention_tb3XZvfpNVYAsiudQdoc3D.md "attention")
    -   [submit](submit_6JfwTeqVCzvsmyQL6qbU5W.md "submit") requests to ES using the green [triangle](triangle_64EBNuKejH8NATEU8wc7aP.md "triangle") [button](button_kNKDegsG4uk3h6y3ajSx2p.md "button").
        使用绿色三角按钮将请求提交到 ES。
    -   Use the [wrench](wrench_w9KyYkZpfj9pgc91gYQ6S3.md "wrench") menu for other [useful](useful_ksZ9GndAZNNWngNgxzrEVB.md "useful") things.
        使用扳手菜单执行其他有用的操作。
    -   You can [paste](paste_v2i21WGNCw3jbHxLDA6UAa.md "paste") requests in cURL [format](format_8KAh4zaA1bzipVJpEK3BGK.md "format") and they will be translated to the Console [syntax](syntax_3t74ta2sZmkBU2neBHiVtt.md "syntax").
        您可以粘贴 cURL 格式的请求，这些请求将转换成 Console 语法格式。
    -   You can [resize](resize_eHkpg7JTDw3DzumzSeSngT.md "resize") the editor and output panes by dragging the separator between them.
    -   Study the keyboard shortcuts under the Help button. Good stuff in there!
-   Setting the time to "now" means that on every refresh this time will be set to the time of the refresh.

    ![](../image/image_RaYSKV66Ft.png)

[kibana.yml](kibana.yml_bEoRwiLaM8NDPthpZ26AR8.md "kibana.yml")

## Secure saved objects

[https://www.elastic.co/guide/en/kibana/current/xpack-security-secure-saved-objects.html#xpack-security-secure-saved-objects](https://www.elastic.co/guide/en/kibana/current/xpack-security-secure-saved-objects.html#xpack-security-secure-saved-objects "https://www.elastic.co/guide/en/kibana/current/xpack-security-secure-saved-objects.html#xpack-security-secure-saved-objects")

Kibana stores entities such as dashboards, visualizations, alerts, actions, and advanced settings as saved objects, which are kept in a dedicated, internal Elasticsearch index. If such an object includes sensitive information, for example a PagerDuty integration key or email server credentials used by the alert action, Kibana encrypts it and makes sure it cannot be accidentally leaked or tampered with.

