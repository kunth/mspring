mspring
=======

abandon these ways

[http://stackoverflow.com/questions/129207/getting-spring-application-context](http://stackoverflow.com/questions/129207/getting-spring-application-context)

[http://sujitpal.blogspot.hk/2007/03/accessing-spring-beans-from-legacy-code.html](http://sujitpal.blogspot.hk/2007/03/accessing-spring-beans-from-legacy-code.html)

create an applicationContext in /config
update web.xml and create http-servlet.xml

``` java
//this way would create beans again

ApplicationContext ctx = new ClassPathXmlApplicationContext("applicationContext.xml");  
Bean myBean = ctx.getBean("testBean");  
```

``` java
//load current beans

ApplicationContext ctx = ContextLoader.getCurrentWebApplicationContext();  
ctx.getBean("testBean"); 
```

It could create beans by implementing the applicationContextAware.
