# \[E\&Q]CSS选择器

-   \[Q]怎么选择最后一个元素
    -   例：CSS选择器:对最后一行输入框修改成占100%\[`:nth-last-child(n)`]
        ```css
          <style>
              #form_add>.row>div:nth-last-child(1) {
                  width: 100%;
              }
          </style>
        ```
        -   HTML
            ```css
            <div class="container">
                <div class="row">
                    <form action="" id="form_add">
                        <div class="row">
                            
                            <div class="col-6">
                                <div class="form-group">
                                    <label for="">标题</label>
                                    <input type="text" name="title" maxlength="120" class="form-control" required="" id="id_title">
                                </div>
                            </div>
                            
                            <div class="col-6">
                                <div class="form-group">
                                    <label for="">负责人</label>
                                    <select name="user" class="form-control" required="" id="id_user">
              <option value="" selected="">---------</option>

              <option value="13">qusay</option>

              <option value="14">1</option>

            </select>
                                </div>
                            </div>
                            
                            <div class="col-6">
                                <div class="form-group">
                                    <label for="">紧急程度</label>
                                    <select name="urgency" class="form-control" id="id_urgency">
              <option value="3">紧急</option>

              <option value="2">一般</option>

              <option value="1" selected="">松弛</option>

            </select>
                                </div>
                            </div>
                            
                            <div class="col-6">
                                <div class="form-group">
                                    <label for="">重要程度</label>
                                    <select name="importance" class="form-control" id="id_importance">
              <option value="3">重要</option>

              <option value="2">一般</option>

              <option value="1" selected="">次要</option>

            </select>
                                </div>
                            </div>
                            
                            <div class="col-6">
                                <div class="form-group">
                                    <label for="">详细信息</label>
                                    <input type="text" name="detail" class="form-control" required="" id="id_detail">
                                </div>
                            </div>
                            
                        </div>
                        <button form="but_add" class="btn btn-primary mt-4">Submit</button>
                    </form>
                </div>
            </div>
            ```
-   \[Q]\[CSS]`:nth-child(n)`选择前几个元素 \[[伪选择器](伪选择器_5aTEw3tguuXcfFnhADnqd6.md "伪选择器")]
    -   &#x20;示例：前3个元素 \[`:nth-last-child(n)`]
        ```纯文本
        :nth-child(-n+3){
             margin-top: 12px;
         }
        ```
    -   示例：【正方向范围】选择从第6个开始`:nth-child(an+b)`
        ```纯文本
        :nth-child(n+6){}
        ```
    -   示例：选择某一个范围：从第2个到第6个元素`:nth-child(an+b)`
        ```纯文本
        :nth-child(n+2):nth-child(-n+6){}
        ```

