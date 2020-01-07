# Vue JSON Tree View
##  依赖源码项目
下载源码  https://github.com/onlySparrow/vue-json-view/upload/master
安装  npm install   
运行  npm run dev
打包  npm run build


##  依赖安装
```shell
npm install edp-vue-json -S  
```

Then, in your Application JavaScript, add:
```javascript
import TreeView from "edp-vue-json"
Vue.use(TreeView)
```

## 使用插件

Put the `tree-view` element into your  HTML where you want the Tree View to appear.
```html
<div>
  <tree-view :data="jsonSource" :options="{rootObjectKey: '日志',maxDepth: 2,errorword: 'ERROR'}"></tree-view>
</div>

jsonSource: [{
	"requestParameter": null,
	"requestHeader": null,
	"traceId": "df0641d38c786e0c",
	"任务耗时": 105,
	"节点名称【a_1】": {
		"耗时": 72,
		"节点输入": "null",
		"日志编号": 52,
		"任务编号": 17427,
		"节点类型": "JsInput",
		"节点日志": {
			"2020-01-03 16:00:33.878": "ERROR JsInputException: JavaScript执行 错误 请检查 !\n[Ljava.lang.Object; cannot be cast to java.util.HashMap\n  com.datahub.steps.share.core.api.exception.step.JsInputException: JavaScript执行 错误 请检查 !\n[Ljava.lang.Object; cannot be cast to java.util.HashMap\n\n\tat com.datahub.steps.share.core.service.steps.input.impl.JsInputServiceImpl.perform(JsInputServiceImpl.java:160)\n\tat com.datahub.steps.share.core.service.steps.input.impl.JsInputServiceImpl.perform(JsInputServiceImpl.java:49)\n\tat com.datahub.steps.share.base.api.service.impl.BaseConvertServiceImpl.execute(BaseConvertServiceImpl.java:43)\n\tat com.datahub.steps.center.api.controller.input.JsInputController.execute(JsInputController.java:38)\n\tat com.datahub.steps.center.api.controller.input.JsInputController.execute(JsInputController.java:27)\n\tat com.datahub.steps.center.api.controller.input.JsInputController$$FastClassBySpringCGLIB$$757c0a1d.invoke(<generated>)\n\tat org.springframework.cglib.proxy.MethodProxy.invoke(MethodProxy.java:204)\n\tat org.springframework.aop.framework.CglibAopProxy$CglibMethodInvocation.invokeJoinpoint(CglibAopProxy.java:746)\n\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:163)\n\tat org.springframework.aop.aspectj.MethodInvocationProceedingJoinPoint.proceed(MethodInvocationProceedingJoinPoint.java:88)\n\tat com.datahub.steps.share.base.service.service.impl.AopServiceImpl.proceed(AopServiceImpl.java:181)\n\tat com.datahub.steps.center.base.aop.StepsControllerAop.around(StepsControllerAop.java:46)\n\tat sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)\n\tat sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)\n\tat sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)\n\tat java.lang.reflect.Method.invoke(Method.java:498)\n\tat org.springframework.aop.aspectj.AbstractAspectJAdvice.invokeAdviceMethodWithGivenArgs(AbstractAspectJAdvice.java:644)\n\tat org.springframework.aop.aspectj.AbstractAspectJAdvice.invokeAdviceMethod(AbstractAspectJAdvice.java:633)\n\tat org.springframework.aop.aspectj.AspectJAroundAdvice.invoke(AspectJAroundAdvice.java:70)\n\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)\n\tat org.springframework.aop.interceptor.ExposeInvocationInterceptor.invoke(ExposeInvocationInterceptor.java:92)\n\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)\n\tat org.springframework.aop.framework.CglibAopProxy$DynamicAdvisedInterceptor.intercept(CglibAopProxy.java:688)\n\tat com.datahub.steps.center.api.controller.input.JsInputController$$EnhancerBySpringCGLIB$$bfc2025d.execute(<generated>)\n\tat com.datahub.steps.share.base.service.service.impl.ExecuteStepsServiceImpl.executeSteps(ExecuteStepsServiceImpl.java:64)\n\tat com.datahub.steps.share.base.service.listener.ApiListener.recursiveImplementation(ApiListener.java:212)\n\tat com.datahub.steps.share.base.service.listener.ApiListener.proceed(ApiListener.java:134)\n\tat com.datahub.steps.share.base.service.listener.ApiListener$$FastClassBySpringCGLIB$$56f867c4.invoke(<generated>)\n\tat org.springframework.cglib.proxy.MethodProxy.invoke(MethodProxy.java:204)\n\tat org.springframework.aop.framework.CglibAopProxy$CglibMethodInvocation.invokeJoinpoint(CglibAopProxy.java:746)\n\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:163)\n\tat org.springframework.aop.interceptor.ExposeInvocationInterceptor.invoke(ExposeInvocationInterceptor.java:92)\n\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)\n\tat org.springframework.aop.framework.CglibAopProxy$DynamicAdvisedInterceptor.intercept(CglibAopProxy.java:688)\n\tat com.datahub.steps.share.base.service.listener.ApiListener$$EnhancerBySpringCGLIB$$7ccf5bb2.proceed(<generated>)\n\tat com.datahub.steps.center.api.controller.BaseStepsController.synchronous(BaseStepsController.java:83)\n\tat com.datahub.steps.center.api.controller.BaseStepsController.executorSteps(BaseStepsController.java:69)\n\tat com.datahub.steps.center.base.web.StepsStartController.perform(StepsStartController.java:77)\n\tat com.datahub.steps.center.base.web.StepsStartController.execute(StepsStartController.java:72)\n\tat com.datahub.steps.center.base.web.StepsStartController$$FastClassBySpringCGLIB$$9e3e9f4c.invoke(<generated>)\n\tat org.springframework.cglib.proxy.MethodProxy.invoke(MethodProxy.java:204)\n\tat org.springframework.aop.framework.CglibAopProxy$CglibMethodInvocation.invokeJoinpoint(CglibAopProxy.java:746)\n\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:163)\n\tat org.springframework.aop.aspectj.MethodInvocationProceedingJoinPoint.proceed(MethodInvocationProceedingJoinPoint.java:88)\n\tat com.datahub.steps.center.base.aop.StepsControllerAop.around(StepsControllerAop.java:43)\n\tat sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)\n\tat sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)\n\tat sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)\n\tat java.lang.reflect.Method.invoke(Method.java:498)\n\tat org.springframework.aop.aspectj.AbstractAspectJAdvice.invokeAdviceMethodWithGivenArgs(AbstractAspectJAdvice.java:644)\n\tat org.springframework.aop.aspectj.AbstractAspectJAdvice.invokeAdviceMethod(AbstractAspectJAdvice.java:633)\n\tat org.springframework.aop.aspectj.AspectJAroundAdvice.invoke(AspectJAroundAdvice.java:70)\n\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)\n\tat org.springframework.aop.interceptor.ExposeInvocationInterceptor.invoke(ExposeInvocationInterceptor.java:92)\n\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)\n\tat org.springframework.aop.framework.CglibAopProxy$DynamicAdvisedInterceptor.intercept(CglibAopProxy.java:688)\n\tat com.datahub.steps.center.base.web.StepsStartController$$EnhancerBySpringCGLIB$$e35cf74a.execute(<generated>)\n\tat sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)\n\tat sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)\n\tat sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)\n\tat java.lang.reflect.Method.invoke(Method.java:498)\n\tat org.springframework.web.method.support.InvocableHandlerMethod.doInvoke(InvocableHandlerMethod.java:209)\n\tat org.springframework.web.method.support.InvocableHandlerMethod.invokeForRequest(InvocableHandlerMethod.java:136)\n\tat org.springframework.web.servlet.mvc.method.annotation.ServletInvocableHandlerMethod.invokeAndHandle(ServletInvocableHandlerMethod.java:102)\n\tat org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.invokeHandlerMethod(RequestMappingHandlerAdapter.java:877)\n\tat org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.handleInternal(RequestMappingHandlerAdapter.java:783)\n\tat org.springframework.web.servlet.mvc.method.AbstractHandlerMethodAdapter.handle(AbstractHandlerMethodAdapter.java:87)\n\tat org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:991)\n\tat org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:925)\n\tat org.springframework.web.servlet.FrameworkServlet.processRequest(FrameworkServlet.java:974)\n\tat org.springframework.web.servlet.FrameworkServlet.doPost(FrameworkServlet.java:877)\n\tat javax.servlet.http.HttpServlet.service(HttpServlet.java:661)\n\tat org.springframework.web.servlet.FrameworkServlet.service(FrameworkServlet.java:851)\n\tat javax.servlet.http.HttpServlet.service(HttpServlet.java:742)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:231)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166)\n\tat org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:52)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166)\n\tat org.springframework.web.filter.CorsFilter.doFilterInternal(CorsFilter.java:96)\n\tat org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166)\n\tat org.springframework.boot.actuate.web.trace.servlet.HttpTraceFilter.doFilterInternal(HttpTraceFilter.java:90)\n\tat org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166)\n\tat org.springframework.cloud.sleuth.instrument.web.ExceptionLoggingFilter.doFilter(ExceptionLoggingFilter.java:48)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166)\n\tat brave.servlet.TracingFilter.doFilter(TracingFilter.java:86)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166)\n\tat org.springframework.boot.actuate.metrics.web.servlet.WebMvcMetricsFilter.filterAndRecordMetrics(WebMvcMetricsFilter.java:155)\n\tat org.springframework.boot.actuate.metrics.web.servlet.WebMvcMetricsFilter.filterAndRecordMetrics(WebMvcMetricsFilter.java:123)\n\tat org.springframework.boot.actuate.metrics.web.servlet.WebMvcMetricsFilter.doFilterInternal(WebMvcMetricsFilter.java:108)\n\tat org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166)\n\tat org.springframework.web.filter.CharacterEncodingFilter.doFilterInternal(CharacterEncodingFilter.java:200)\n\tat org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166)\n\tat org.apache.catalina.core.StandardWrapperValve.invoke(StandardWrapperValve.java:198)\n\tat org.apache.catalina.core.StandardContextValve.invoke(StandardContextValve.java:96)\n\tat org.apache.catalina.authenticator.AuthenticatorBase.invoke(AuthenticatorBase.java:493)\n\tat org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:140)\n\tat org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:81)\n\tat org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:87)\n\tat org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:342)\n\tat org.apache.coyote.http11.Http11Processor.service(Http11Processor.java:800)\n\tat org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:66)\n\tat org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:800)\n\tat org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1471)\n\tat org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:49)\n\tat java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)\n\tat java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)\n\tat org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)\n\tat java.lang.Thread.run(Thread.java:748)\nCaused by: java.lang.ClassCastException: [Ljava.lang.Object; cannot be cast to java.util.HashMap\n\tat com.datahub.steps.center.base.aop.HttpLoadAop.httpAop(HttpLoadAop.java:93)\n\tat com.datahub.steps.center.base.aop.HttpLoadAop.around(HttpLoadAop.java:61)\n\tat sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)\n\tat sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)\n\tat sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)\n\tat java.lang.reflect.Method.invoke(Method.java:498)\n\tat org.springframework.aop.aspectj.AbstractAspectJAdvice.invokeAdviceMethodWithGivenArgs(AbstractAspectJAdvice.java:644)\n\tat org.springframework.aop.aspectj.AbstractAspectJAdvice.invokeAdviceMethod(AbstractAspectJAdvice.java:633)\n\tat org.springframework.aop.aspectj.AspectJAroundAdvice.invoke(AspectJAroundAdvice.java:70)\n\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:174)\n\tat org.springframework.aop.interceptor.ExposeInvocationInterceptor.invoke(ExposeInvocationInterceptor.java:92)\n\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)\n\tat org.springframework.aop.framework.CglibAopProxy$DynamicAdvisedInterceptor.intercept(CglibAopProxy.java:688)\n\tat com.datahub.steps.share.base.service.service.impl.HttpRestTemplateServiceImpl$$EnhancerBySpringCGLIB$$96ca6fb4.getSynchronous(<generated>)\n\tat jdk.nashorn.internal.scripts.Script$4$\\^eval\\_.:program(<eval>:4)\n\tat jdk.nashorn.internal.runtime.ScriptFunctionData.invoke(ScriptFunctionData.java:637)\n\tat jdk.nashorn.internal.runtime.ScriptFunction.invoke(ScriptFunction.java:494)\n\tat jdk.nashorn.internal.runtime.ScriptRuntime.apply(ScriptRuntime.java:393)\n\tat jdk.nashorn.api.scripting.NashornScriptEngine.evalImpl(NashornScriptEngine.java:449)\n\tat jdk.nashorn.api.scripting.NashornScriptEngine.access$200(NashornScriptEngine.java:73)\n\tat jdk.nashorn.api.scripting.NashornScriptEngine$3.eval(NashornScriptEngine.java:510)\n\tat javax.script.CompiledScript.eval(CompiledScript.java:106)\n\tat com.datahub.steps.share.core.service.steps.input.impl.JsInputServiceImpl.evalJs(JsInputServiceImpl.java:325)\n\tat com.datahub.steps.share.core.service.steps.input.impl.JsInputServiceImpl.performJs(JsInputServiceImpl.java:280)\n\tat com.datahub.steps.share.core.service.steps.input.impl.JsInputServiceImpl.perform(JsInputServiceImpl.java:158)\n\t... 118 more\n"
		},
	}
}]
```

## 参数说明

参数  | 说明  | 默认值
------------- | ------------- | -------------
maxDepth  | 默认情况下应该展开的JSON树的最大级别数。从0到∞的整数  | 4
rootObjectKey  | 根对象的名称  | "root"
modifiable  | 修改json值  | false
link  | URL字符串将显示为可单击链接(modifiable= "true")  | false
errorWord  | 根据json值内容修改展示的颜色  | ' '


#### updated json data
If `modifiable` is true and you want to take the updated json data, you must register event handler as `v-on:change-data=...`. Only one argument is passed that is updated data - `data`.
```html
<div>
  <tree-view :data="jsonSource" :options="{modifiable: true}" @change-data="onChangeData"></tree-view>
</div>

// in your vue code
  ...
  methods: {
    onChangeData: function(data) {
      console.log(JSON.stringify(data))
    }
  },
  ...

```
## Custom Styling

All leaves will have their type indicated as a CSS class, like `tree-view-item-value-string`. Supported types: String, Number, Function, Boolean and Null Values.

Keys can also be styled. For instance to make labels red:
```
.tree-view-item-key {
    color: red;
}
.errorColor {
		color: red
}
```



### 引用 Blockquotes

> 本插件是二次开发 原作者：<https://github.com/michaelfitzhavey/vue-json-tree-view>


