
app：
          ● 相当于boot，只用路由组织各个模块的fragment。
          ARouter.getInstance().build(item.getPath()).navigation();
          ● @Route(path = “/xx/main”)前缀xx不能相同。
              

sdk：
           ● BaseApp              
           ● BaseActivity        
           ● BaseFragment    
           ● 引入第三方的时候需要gradle
              ○ api ：相当于public
              ○ implementation  : 相当于private
          ● Eventbus3.0 
              ○ 全局只有一个地方接受处理消息，增加粘性事件。
          ● Widget 
              ○ ProgressDialog，只有转圈dialog
          ● android 组件化 butterknife gradle 3.0
              ○ moudle R
              ○ Library  将所有的R->R2
              ❖ 废除使用  butterknife，base加入组件初始化规范。



各组件规范以及注意：
         ●  各个模块间命名规则，都是以模块名命名
              ○ api：retrofit定义的接口
              ○ bean
              ○ dagger
              ○ event：事件传递是全局base都会接收到，在页面生命周期里面控制接受生命周期，一          定要用tag去区分接受事件。（各个模块间是相互独立隔离的，如果需要交互，在SDK里面定义Event，用EventBus去交互。）
              ○ presenter：网络请求逻辑
              ○ ui
              ○ view
              App
              Constant
          ●  bean定义
              net -> response(bean)
              dao-> entity(bean)
              ui   -> model(bean)
          ● 与Presenter交互的数据层
             presenter -> repository -> dao
                                                          net
          

用户模块的设计：
        因为组件之间相互的隔离，但是因为需求会出现交叉业务。
        模块需要提供接口供外部模块调用provider



