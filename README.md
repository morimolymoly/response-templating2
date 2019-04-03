# dockerfile
```
FROM rodolpheche/wiremock:2.21.0-alpine
COPY ./stubs /home/wiremock
COPY ./extentions /var/wiremock/extensions
CMD [ "--local-response-templating", "--extensions", "test.maven_test.ResponseTemplateTransformer"]
```
# build
build with openjdk-1.8

```
mvn package
```

# error
```
HTTP/1.1 500 Server Error
Content-Type: text/html; charset=ISO-8859-1
Cache-Control: must-revalidate,no-cache,no-store
Content-Length: 7646
Connection: close
Server: Jetty(9.2.z-SNAPSHOT)

<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
<title>Error 500 Server Error</title>
</head>
<body><h2>HTTP ERROR 500</h2>
<p>Problem accessing /salesPromotion/reporting/v1/campaigns. Reason:
<pre>    Server Error</pre></p><h3>Caused by:</h3><pre>com.github.jknack.handlebars.HandlebarsException: inline@59e4d51f:9:35: java.lang.IllegalArgumentException: Illegal pattern character &apos;e&apos;
    inline@59e4d51f:9:35
	at java.text.SimpleDateFormat.compile(SimpleDateFormat.java:826)
	at java.text.SimpleDateFormat.initialize(SimpleDateFormat.java:634)
	at java.text.SimpleDateFormat.&lt;init&gt;(SimpleDateFormat.java:605)
	at com.github.jknack.handlebars.helper.StringHelpers$19.safeApply(StringHelpers.java:544)
	at com.github.jknack.handlebars.helper.StringHelpers$21.safeApply(StringHelpers.java:700)
	at com.github.jknack.handlebars.helper.StringHelpers.apply(StringHelpers.java:711)
	at com.github.jknack.handlebars.internal.Variable.value(Variable.java:181)
	at com.github.jknack.handlebars.internal.Variable.merge(Variable.java:160)
	at com.github.jknack.handlebars.internal.BaseTemplate.apply(BaseTemplate.java:130)
	at com.github.jknack.handlebars.internal.TemplateList.merge(TemplateList.java:95)
	at com.github.jknack.handlebars.internal.BaseTemplate.apply(BaseTemplate.java:130)
	at com.github.jknack.handlebars.internal.BaseTemplate.apply(BaseTemplate.java:118)
	at com.github.jknack.handlebars.internal.ForwardingTemplate.apply(ForwardingTemplate.java:72)
	at test.maven_test.ResponseTemplateTransformer.uncheckedApplyTemplate(ResponseTemplateTransformer.java:169)
	at test.maven_test.ResponseTemplateTransformer.applyTemplatedResponseBody(ResponseTemplateTransformer.java:163)
`` test.maven_test.ResponseTemplateTransformer.transform(ResponseTemplateTransformer.java:126)
	at com.github.tomakehurst.wiremock.stubbing.InMemoryStubMappings.applyTransformations(InMemoryStubMappings.java:91)
	at com.github.tomakehurst.wiremock.stubbing.InMemoryStubMappings.serveFor(InMemoryStubMappings.java:72)
	at com.github.tomakehurst.wiremock.core.WireMockApp.serveStubFor(WireMockApp.java:172)
	at com.github.tomakehurst.wiremock.http.StubRequestHandler.handleRequest(StubRequestHandler.java:50)
	at com.github.tomakehurst.wiremock.http.AbstractRequestHandler.handle(AbstractRequestHandler.java:47)
	at com.github.tomakehurst.wiremock.servlet.WireMockHandlerDispatchingServlet.service(WireMockHandlerDispatchingServlet.java:111)
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:790)
	at wiremock.org.eclipse.jetty.servlet.ServletHolder.handle(ServletHolder.java:812)
	at wiremock.org.eclipse.jetty.servlet.ServletHandler.doHandle(ServletHandler.java:587)
	at wiremock.org.eclipse.jetty.server.handler.ContextHandler.doHandle(ContextHandler.java:1127)
	at wiremock.org.eclipse.jetty.servlet.ServletHandler.doScope(ServletHandler.java:515)
	at wiremock.org.eclipse.jetty.server.handler.ContextHandler.doScope(ContextHandler.java:1061)
	at wiremock.org.eclipse.jetty.server.handler.ScopedHandler.handle(ScopedHandler.java:141)
	at wiremock.org.eclipse.jetty.servlets.gzip.GzipHandler.handle(GzipHandler.java:529)
	at wiremock.org.eclipse.jetty.server.handler.HandlerCollection.handle(HandlerCollection.java:110)
	at wiremock.org.eclipse.jetty.server.handler.HandlerWrapper.handle(HandlerWrapper.java:97)
	at wiremock.org.eclipse.jetty.server.Server.handle(Server.java:499)
	at wiremock.org.eclipse.jetty.server.HttpChannel.handle(HttpChannel.java:311)
	at wiremock.org.eclipse.jetty.server.HttpConnection.onFillable(HttpConnection.java:258)
	at wiremock.org.eclipse.jetty.io.AbstractConnection$2.run(AbstractConnection.java:544)
	at wiremock.org.eclipse.jetty.util.thread.QueuedThreadPool.runJob(QueuedThreadPool.java:635)
	at wiremock.org.eclipse.jetty.util.thread.QueuedThreadPool$3.run(QueuedThreadPool.java:555)
	at java.lang.Thread.run(Thread.java:748)
Caused by: java.lang.IllegalArgumentException: Illegal pattern character &apos;e&apos;
	... 39 more
</pre>
<h3>Caused by:</h3><pre>java.lang.IllegalArgumentException: Illegal pattern character &apos;e&apos;
	at java.text.SimpleDateFormat.compile(SimpleDateFormat.java:826)
	at java.text.SimpleDateFormat.initialize(SimpleDateFormat.java:634)
	at java.text.SimpleDateFormat.&lt;init&gt;(SimpleDateFormat.java:605)
	at com.github.jknack.handlebars.helper.StringHelpers$19.safeApply(StringHelpers.java:544)
	at com.github.jknack.handlebars.helper.StringHelpers$21.safeApply(StringHelpers.java:700)
	at com.github.jknack.handlebars.helper.StringHelpers.apply(StringHelpers.java:711)
	at com.github.jknack.handlebars.internal.Variable.value(Variable.java:181)
	at com.github.jknack.handlebars.internal.Variable.merge(Variable.java:160)
	at com.github.jknack.handlebars.internal.BaseTemplate.apply(BaseTemplate.java:130)
	at com.github.jknack.handlebars.internal.TemplateList.merge(TemplateList.java:95)
	at com.github.jknack.handlebars.internal.BaseTemplate.apply(BaseTemplate.java:130)
	at com.github.jknack.handlebars.internal.BaseTemplate.apply(BaseTemplate.java:118)
	at com.github.jknack.handlebars.internal.ForwardingTemplate.apply(ForwardingTemplate.java:72)
	at test.maven_test.ResponseTemplateTransformer.uncheckedApplyTemplate(ResponseTemplateTransformer.java:169)
	at test.maven_test.ResponseTemplateTransformer.applyTemplatedResponseBody(ResponseTemplateTransformer.java:163)
	at test.maven_test.ResponseTemplateTransformer.transform(ResponseTemplateTransformer.java:126)
	at com.github.tomakehurst.wiremock.stubbing.InMemoryStubMappings.applyTransformations(InMemoryStubMappings.java:91)
	at com.github.tomakehurst.wiremock.stubbing.InMemoryStubMappings.serveFor(InMemoryStubMappings.java:72)
	at com.github.tomakehurst.wiremock.core.WireMockApp.serveStubFor(WireMockApp.java:172)
	at com.github.tomakehurst.wiremock.http.StubRequestHandler.handleRequest(StubRequestHandler.java:50)
	at com.github.tomakehurst.wiremock.http.AbstractRequestHandler.handle(AbstractRequestHandler.java:47)
	at com.github.tomakehurst.wiremock.servlet.WireMockHandlerDispatchingServlet.service(WireMockHandlerDispatchingServlet.java:111)
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:790)
	at wiremock.org.eclipse.jetty.servlet.ServletHolder.handle(ServletHolder.java:812)
	at wiremock.org.eclipse.jetty.servlet.ServletHandler.doHandle(ServletHandler.java:587)
	at wiremock.org.eclipse.jetty.server.handler.ContextHandler.doHandle(ContextHandler.java:1127)
	at wiremock.org.eclipse.jetty.servlet.ServletHandler.doScope(ServletHandler.java:515)
	at wiremock.org.eclipse.jetty.server.handler.ContextHandler.doScope(ContextHandler.java:1061)
	at wiremock.org.eclipse.jetty.server.handler.ScopedHandler.handle(ScopedHandler.java:141)
	at wiremock.org.eclipse.jetty.servlets.gzip.GzipHandler.handle(GzipHandler.java:529)
	at wiremock.org.eclipse.jetty.server.handler.HandlerCollection.handle(HandlerCollection.java:110)
	at wiremock.org.eclipse.jetty.server.handler.HandlerWrapper.handle(HandlerWrapper.java:97)
	at wiremock.org.eclipse.jetty.server.Server.handle(Server.java:499)
	at wiremock.org.eclipse.jetty.server.HttpChannel.handle(HttpChannel.java:311)
	at wiremock.org.eclipse.jetty.server.HttpConnection.onFillable(HttpConnection.java:258)
	at wiremock.org.eclipse.jetty.io.AbstractConnection$2.run(AbstractConnection.java:544)
	at wiremock.org.eclipse.jetty.util.thread.QueuedThreadPool.runJob(QueuedThreadPool.java:635)
	at wiremock.org.eclipse.jetty.util.thread.QueuedThreadPool$3.run(QueuedThreadPool.java:555)
	at java.lang.Thread.run(Thread.java:748)
</pre>
<hr><i><small>Powered by Jetty://</small></i><hr/>

</body>
</html>
`````
