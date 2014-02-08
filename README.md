androidInject
=============

###使用注解来简化android开发  <br/>(Use annotations inject to simplify the development of android)<br/>

###注解(Annotations): <br/>
###
        @AINoTitle: 类注解, 只适用于Activity(需继承于AIActivity), 设置Activity不显示Title

        @AIFullScreen: 类注解, 只适用于Activity(需继承于AIActivity), 设置Activity全屏

        @AILayout: 类注解
            value[int]: 用于设置该Activity的布局 ---- setContentView(resId);


        @AIView: 属性注解
            id[int]: 用于绑定控件 ---- findViewById(resId);(default identifier[R.id.{field name}] if did not set id)
            clickMethod[String]: 用于设置控件点击事件的回调方法, 可选, 方法名称任意, 参数必须为(View view)
            longClickMethod[String]: 用于设置控件长按的回调方法, 可选, 方法名任意, 参数必须为(View view)
            itemClickMethod[String]: 用于设置控件item点击的回调方法, 可选, 方法名任意, 参数必须为(AdapterView, View, int, long)
            itemLongClickMethod[String]: 用于设置控件item长按的回调方法, 可选, 方法名任意, 参数必须为(AdapterView, View, int, long)

        @AIBean: 属性注解, 为该属性生成一个对象并注入, 该对象必须有个默认的不带参数的构造方法

        @AISystemService: 属性注解，为该属性注入系统服务对象


        @AIClick: 方法注解
            value[int[], 所要绑定控件的id]: 用于绑定控件点击事件的回调方法, 方法名称任意, 参数必须为(View view)

        @AIItemClick: 方法注解
            value[int[], 所要绑定控件的id]: 用于绑定控件item点击事件的回调方法, 方法名称任意, 参数必须为(AdapterView, View, int, long)

        @AILongClick: 方法注解
            value[int[], 所要绑定控件的id]: 用于绑定控件长按事件的回调方法, 方法名称任意, 参数必须为(View view)

        @AIItemLongClick: 方法注解
            value[int[], 所要绑定控件的id]: 用于绑定控件item长按事件的回调方法, 方法名称任意, 参数必须为(AdapterView, View, int, long)

        @AIScreenSize: 属性注解
            用于注入当前设备的屏幕大小（宽高）

        @AIGet: 方法注解
            value[String, 所要请求的url]：表示以GET来请求url

        @AIPost: 方法注解
            value[String, 所要请求的url]：表示以Post来请求url

        @AIParam: 方法参数注解
            value[String, 请求的参数别名]：注入@AIGet或@AIPost注解方法的请求参数

        @AINetWorker: 属性注解
            注入网络请求服务


###提交日志(Commit Logs): <br/>
###
        2014-2-8:
        1. 增加@AIScreenSize注解，作用于属性，用于注入当前设备的屏幕大小（宽高）
        2. 增加对网络请求的支持，使用动态代理实现：@AIGet注解，作用于接口方法，表示以GET来请求url；@AIPost注解，作用于接口方法，表示以POST来请求url；@AIParam，用于注入请求参数
        3. 增加@AINetWorker注解，作用于属性，用于注入网络请求服务
        4. 重构代码

        2013-12-17:
        1. refactor source

        2013-12-5:
        1. build androidInject_1.0.jar

        2013-12-5:
        1. add fragment support(need android-support-v4.jar)

        2013-12-4:
        1. add type annotations: @AINoTitle, @AIFullScreen
        2. modify field annotation ---- @AIView: default identifier[R.id.{field name}] if did not set id

        2013-12-2:
        1. add field annotations: @AIBean, @AISystemService

        2013-12-1:
        1. add method annotations: @AIItemLongClick
        2. add annotations(itemLongClickMethod) of @AIView

        2013-12-1:
        1. RENAME @InitLayout, @InitView TO @AILayout, @AIView
        2. ADD method annotations: @AIClick, @AILongClick, @AIItemClick
        3. refactor source











