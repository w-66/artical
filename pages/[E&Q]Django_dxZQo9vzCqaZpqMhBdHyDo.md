# \[E\&Q]Django

-   \[Q]` 'blog.apps.BlogConfig'`与`'blog'`的区别 `INSTALLED_APPS`[¶](https://docs.djangoproject.com/zh-hans/3.2/ref/applications/#module-django.apps "¶")注册app

    **You:**

    INSTALLED\_APPS = \[ 'blog.apps.BlogConfig', ] 与 INSTALLED\_APPS = \[ 'blog', ] 的区别

    **ChatGPT:**

    这两个 `INSTALLED_APPS` 的设置的区别在于：
    1.  `'blog.apps.BlogConfig'` vs `'blog'`：

        `'blog.apps.BlogConfig'` 是指定了 `blog` 应用的配置类 `BlogConfig`，而 `'blog'` 则是指定了 `blog` 应用的名称。
    2.  前者需要在 `blog` 应用的 `apps.py` 文件中定义 `BlogConfig` 类，如下所示：
        ```python
        # blog/apps.py

        from django.apps import AppConfig

        class BlogConfig(AppConfig):
            default_auto_field = 'django.db.models.BigAutoField'
            name = 'blog'
        ```
        这种方式可以让你在应用的配置类中进行一些自定义的配置，比如默认使用的数据库类型，以及应用的名称等。
    3.  后者不需要在 `blog` 应用中定义任何配置类，Django 默认会使用应用的名称 `blog` 来配置应用。
    总之，使用 `'blog.apps.BlogConfig'` 方式可以为应用提供更多的自定义配置选项，而使用 `'blog'` 则更加简洁明了。如果不需要在应用中进行额外的自定义配置，建议使用后者。
-   \[E]delete\_queryset在搜索的之后的结果集中进行删除会报错Cannot call delete() after .distinct().


-   \[Q]search\_fields = \['pub\_date', 'content','tags\_\_tag']    其中tags\_\_tag是什么意思?关联查询

    `tags__tag`表示使用Django ORM中的关联查询（related lookup）来搜索`Tag`模型中的`tag`字段。在这里，`tags`是`Lifelog`模型中的`ManyToManyField`字段，而`tag`是`Tag`模型中的`CharField`字段。因此，如果您想搜索与`Lifelog`模型相关的`Tag`模型中的`tag`字段，就需要使用关联查询语法。

    在这里，`tags__tag`中的双下划线`__`表示关联查询，它告诉Django ORM搜索`tags`字段的相关(相关联的)模型（即`Tag`模型），并使用`tag`字段进行搜索。因此，`search_fields = ['pub_date', 'content','tags__tag']`表示您可以在`Lifelog`模型中搜索`pub_date`和`content`字段，同时也可以搜索相关的`Tag`模型中的`tag`字段。
-   \[Q]如何设计使添加多个标签
    ```javascript

    class Tag(models.Model):
        tag = models.CharField(verbose_name='标签名', unique=True, max_length=200)
        def __str__(self):
            return self.tag

    class Lifelog(models.Model):
        # now = timezone.now().strftime('%Y-%m-%d %H:%M:%S')
        pub_date = models.DateTimeField(verbose_name='发布时间',default=timezone.now)
        content = models.TextField(verbose_name='内容', null=True)
        location_choices = (
            (0, '无')
        )
        location = models.PositiveSmallIntegerField(verbose_name='位置',choices=location_choices, default=2)

        # tag_choices = [(tag.id, tag.tag) for tag in Tag.objects.all()]  
        # tag = models.SmallIntegerField(null=True, blank=True,verbose_name='标签',help_text='一个tag')
        tag = models.ForeignKey(Tag, null=True, blank=True, on_delete=models.SET_NULL, verbose_name='标签')
        
        # def __str__(self):
        #     return self.tag
    ```
    为了使Lifelog可以添加多个标签，您可以使用ManyToManyField。这将创建一个新的关系表，将Lifelog与Tag相关联，并允许您为每个Lifelog添加多个标签。以下是您可以更新Lifelog模型的示例代码：
    ```javascript
    class Lifelog(models.Model):
        pub_date = models.DateTimeField(verbose_name='发布时间', default=timezone.now)
        content = models.TextField(verbose_name='内容', null=True)
        location_choices = (
            (0, '无')
        )
        location = models.PositiveSmallIntegerField(verbose_name='位置', choices=location_choices, default=2)
        tags = models.ManyToManyField(Tag, verbose_name='标签')

        def __str__(self):
            return self.content

    ```
    在此模型中，您可以看到我们使用了ManyToManyField来创建Lifelog与Tag之间的多对多关系。这个字段名为“tags”，并将“Tag”模型作为参数传递。我们还将verbose\_name设置为“标签”，以便在管理界面中更清楚地显示。

    现在，您可以为每个Lifelog添加多个标签，并通过以下方式访问它们：
    ```javascript
    lifelog = Lifelog.objects.get(id=1)
    tags = lifelog.tags.all()

    ```
    这将返回与给定Lifelog相关联的所有标签。您还可以添加或删除标签，例如：
    ```javascript
    # 添加标签
    tag1 = Tag.objects.get(tag='标签1')
    tag2 = Tag.objects.get(tag='标签2')
    lifelog.tags.add(tag1, tag2)

    # 删除标签
    lifelog.tags.remove(tag1)

    ```

    -   \[Q]怎么在模板中访问标签
        ```javascript
        {% for item in queryset %}
        <div class="d-flex text-muted pt-3 ">
            <img src="{% static 'img/site_logo_small.svg' %}" class="bd-placeholder-img flex-shrink-0 me-2 rounded"
                width="32" height="32" alt="">
            <p class="pb-3 mb-0 small lh-sm border-bottom text-truncate">
                <strong class="d-block text-dark">
                    <font style="vertical-align: inherit;" class="me-3">
                        {% for tag in item.tags.all %}
                        <span class="badge bg-secondary">{{ tag.tag }}</span>
                        {% endfor %}
                    </font>
                </strong>
                <span class="">
                    <font style="vertical-align: inherit;">
                        {{item.content}}
                    </font>
                </span>

            </p>
        </div>
        {% endfor %}

        ```

-   \[Q]Django 的models设计两个表，tag表，person表，只允许tag表中tag列根据person中的tag列进行增加修改，person表中的tag当最后一个被删除，tag.tag中的数据也删除，当person.tag相同的标签大于1时，tag表不改动，tag.tag中的标签不重复

    您可以使用 Django 中的信号（signals）来实现该需求。

    首先，在您的 [models.py](http://models.py "models.py") 文件中定义两个模型：Tag 和 Person。Tag 模型应该具有一个 CharField 字段来存储标签名称。Person 模型应该具有一个 ManyToManyField 字段来存储与该人物相关的标签。
    ```javascript
    from django.db import models

    class Tag(models.Model):
        name = models.CharField(max_length=255, unique=True)

    class Person(models.Model):
        name = models.CharField(max_length=255)
        tags = models.ManyToManyField(Tag, related_name='people')

    ```
    然后，您可以使用 Django 的 post\_save 和 post\_delete 信号来处理标签的创建、修改和删除。
    ```javascript
    from django.db.models.signals import post_save, post_delete
    from django.dispatch import receiver

    @receiver(post_save, sender=Person)
    @receiver(post_delete, sender=Person)
    def update_tags(sender, instance, **kwargs):
        # 获取该 person 对应的所有标签
        tags = instance.tags.all()

        # 如果该 person 没有标签，则删除所有与该 person 相关的标签
        if not tags:
            Tag.objects.filter(people=instance).delete()
            return

        # 获取该 person 对应的第一个标签
        first_tag = tags.first()

        # 如果该 person 只有一个标签，则将该标签的名称修改为该 person 的标签名称
        if tags.count() == 1:
            first_tag.name = instance.tags.first().name
            first_tag.save()
            return

        # 如果该 person 有多个标签，则不进行任何操作
        # 确保所有与该 person 相关的标签的名称都是唯一的
        for tag in tags:
            if tag.name != first_tag.name:
                tag.delete()

    ```
    该信号接收两个参数：sender 和 instance。sender 是发送信号的模型类，instance 是发送信号的模型实例。在上面的代码中，我们使用 @receiver 装饰器将 update\_tags 函数连接到 Person 模型的 post\_save 和 post\_delete 信号。

    在 update\_tags 函数中，我们首先获取与该 person 相关的所有标签。如果该 person 没有标签，则删除所有与该 person 相关的标签。如果该 person 只有一个标签，则将该标签的名称修改为该 person 的标签名称。最后，如果该 person 有多个标签，则不进行任何操作。

    通过这种方式，我们可以确保标签的名称始终与与该标签相关的最后一个 person 的标签名称相同，并且在最后一个 person 被删除时，该标签也将被删除。
-   \[Q]python3 manage.py migrate 不生效; django-关于manage.py migrate无效的问题 `migrate`

    曾经做过一下操作：
    -   直接删除了app，然后又重新生成了新的同名app
    -   删除过app/migrations里面的文件
    解决方案：

    直接进入数据库找到Django生成的django\_migrations，从里面删除你的对应的app的名称的数据
-   \[Q]表单中显示内存地址(object(13)怎么显示对应的数据? \[`learning_app\models.py`,`__str__()`]
    1.  `__str__()`打印时，会打印从这个方法中return数据
        -   当使用print对象的时候，默认打印对象的内存地址
    ![](../image/image_1nlSopSuQP.png)
    ```python
    class Admin(models.Model):
        '''管理员表'''
        username = models.CharField(verbose_name='用户名', max_length=32, unique=True)
        password = models.CharField(verbose_name='密码', max_length=64)
        def __str__(self):
            return self.username
    ```

-   \[Q]怎么在Django中直接使用SQL查询

    Django有两种方法可以使用原生SQL查询数据库。
    1.  使用django.db.connection

        您可以使用django.db.connection直接访问数据库连接，并执行SQL查询。例如：
        ```python
        from django.db import connection

        cursor = connection.cursor()
        cursor.execute("SELECT * FROM myapp_mymodel")
        rows = cursor.fetchall()

        ```
    2.  使用django.db.models.RawSQL

        您也可以使用django.db.models.RawSQL类直接执行原生SQL查询，并将结果视为模型实例。例如：
        ```python
        from django.db.models import RawSQL

        result = MyModel.objects.raw("SELECT * FROM myapp_mymodel")
        for row in result:
            print(row.column_name)

        ```
    3.  请注意，使用原生SQL查询的方法不是Django的核心功能，应该只在必要时使用。最好使用Django的ORM功能，以便获得更好的可维护性和更高的安全性。
-   \[Q]Django中 怎么使用orm查询数据库中的条目总数

    Django使用ORM（Object-Relational Mapping）对数据库进行操作。在Django中，可以使用如下代码查询数据库中的条目总数：
    ```python
    from django.db.models import Count

    entry_count = YourModel.objects.aggregate(Count('id'))['id__count']

    ```
    其中，`YourModel`是您要查询的数据库模型，`id`是模型中的一个字段。

    如果您要查询所有模型中的所有字段的总数，则可以使用如下代码：
    ```python
     entry_count = YourModel.objects.count()

    ```
-   \[Q]在使用组件ModelForm时，调用`.save()`方法怎么存入指定数据库，而不是默认数据库中?


-   \[Q] 怎么获取多个数据库中的数据 \[.object.using()]
    -   题详细描述
        ```python
        以下是view.py的部份内容:
        from app01.models import Favormusic
        from app01.models import Lifelog

        def lifelog(request):
            if request.method == "GET":
                lifelog = Lifelog.objects.all().order_by("-addtime")[:40]
                return render(request, 'lifelog.html', {'lifelog':lifelog})
        def lifelog_edit(request,global_id):
            if request.method == "GET":
                one_row = Lifelog.objects.filter(global_id=global_id).first()
                return render(request, 'lifelog_edit.html', {'onerow':one_row,'global_id':global_id})
            else:
                pass

        以下是models.py的部份内容:
        class Favormusic(models.Model):
            song = models.CharField(max_length=128)
            songer = models.CharField(max_length=128)
            addtime = models.DateTimeField()
            album = models.CharField(max_length=100, blank=True, null=True)
            info_from = models.IntegerField()
            duration = models.TimeField()
            global_id = models.PositiveBigIntegerField(unique=True)
            native_id = models.CharField(primary_key=True, max_length=18)
            tag = models.CharField(max_length=1024, blank=True, null=True)

            class Meta:
                managed = False
                db_table = 'favormusic'
                unique_together = (('native_id', 'info_from'), ('native_id', 'info_from'),)
                db_tablespace = 'second_db'


        class Lifelog(models.Model):
            global_id = models.PositiveBigIntegerField(primary_key=True)
            addtime = models.DateTimeField()
            tag = models.CharField(max_length=128, blank=True, null=True)
            content = models.TextField()
            weather = models.CharField(max_length=64)
            location_id = models.IntegerField(db_column='location_Id')  # Field name made lowercase.

            class Meta:
                managed = False
                db_table = 'lifelog'
                db_tablespace = 'second_db'


        以下是setting.py的部份内容:
        DATABASES = {
            'default': {
                'ENGINE': 'django.db.backends.mysql',
                'NAME': 'blog_django',
                'USER': 'django',
                'PASSWORD': 'asdf;1111',
                'HOST': '172.29.0.2',
                'PORT': 3306,
            },
            'second_db':{
                'ENGINE': 'django.db.backends.mysql',
                'NAME': 'person',
                'USER': 'person',
                'PASSWORD': 'asdf;11111',
                'HOST': 'mysql5.7.39',
                'PORT': 3306,
            }
        }


        问题是：读取的数据还是来自默认数据库?
        ```
    -   AI回答
        ```python
        从你提供的代码来看，你在models.py中对Favormusic和Lifelog设置了db_tablespace='second_db'，表示这两个模型的数据存储在second_db数据库中。

        而在views.py中调用的时候，你并没有明确的指定使用哪个数据库，所以Django会使用默认的数据库来查询数据。

        如果你想读取来自second_db数据库的数据，那么你需要在views.py中使用using() 方法来明确指定使用哪个数据库，例如:

        lifelog = Lifelog.objects.using('second_db').all().order_by("-addtime")[:40]

        one_row = Lifelog.

        ```
-   \[Q]设置静态资源时，STATIC\_URL 参数无效，无法 加载|访问 资源? \[`STATICFILES_DIRS`[¶](https://docs.djangoproject.com/zh-hans/3.2/ref/settings/#staticfiles-dirs "¶")[¶](https://docs.djangoproject.com/zh-hans/3.2/howto/static-files/#configuring-static-files "¶")通用的查找静态资源路径，优先于`STATIC_URL`] \[] 答案:`TEMPLATES`需要配置
    > 隔天我再看，发现两者参数都生效了...，难道是因为需要重启一下吗?但是我也没有重启啊，我的服务器...奇怪，但是现在才是正常的情况...
    ***
    环境：Linux 中
    > 但是在window环境不需要加决方案1：就可以访问
    ```javascript
    setting.py文件 
      # 配置static_url ， 但是在app中创建的static文件夹中的资源无法访问，为什么这个不生效
      STATIC_URL = '/static/'

    ```
    -   &#x20;决方案2：
        ```javascript
          # 需要再配置下面这个参数才能生效，可以放在app文件夹中，也可以访问django项目根目录中，都能生效...
          STATICFILES_DIRS = [ BASE_DIR / "static" ]
        ```
    -   决方案1：

        [参考](https://cloud.tencent.com/developer/article/1741335 "参考")

        原问题的答案：1、INSTALLED\_APPS 中，加入 ‘django.contrib.staticfiles’2、TEMPLATES 中，context\_processors中，加入django.template.context\_processors.static \[`django.template.context_processors.static`如果启用了这个处理器，每个 `RequestContext` 都会包含一个变量 `STATIC_URL`，提供 [STATIC\_URL](https://docs.djangoproject.com/zh-hans/3.2/ref/settings/#std:setting-STATIC_URL "STATIC_URL") 配置的值。]
        ```javascript
        INSTALLED_APPS  = [
            'django.contrib.admin',
            'django.contrib.auth',
            'django.contrib.contenttypes',
            'django.contrib.sessions',
            'django.contrib.messages', 
            'django.contrib.staticfiles',
             'app01',
        ] 
        ...
        TEMPLATES = [
            {
                 'BACKEND': 'django.template.backends.django.DjangoTemplates',
                'DIRS': [],
                'APP_DIRS': True,
                'OPTIONS': {
                    'context_processors': [
                        'django.template.context_processors.debug',
                        'django.template.context_processors.request',
                        'django.contrib.auth.context_processors.auth',
                        'django.contrib.messages.context_processors.messages', 
                        'django.template.context_processors.static',
                    ],
                },
            },
        ]
        ```



# 添加标签

tag1 = Tag.objects.get(tag='标签1')

tag2 = Tag.objects.get(tag='标签2')

lifelog.tags.add(tag1, tag2)

# 删除标签

lifelog.tags.remove(tag1)
