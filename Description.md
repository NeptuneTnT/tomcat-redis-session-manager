### Session共享



目的 :  
> 实现两个以上tomcat之间的session共享

基于 :

- [x] tomcat-redis-session-manager
- [x] Redis



用法 :
1.准备一个新的tomcat
2.将jar包放入tomcat/lib目录下
![jar.png-10.5kB][1]
  [1]: http://static.zybuluo.com/Liuxiansen/zlk69mvlowodv353t8etz8c5/jar.png
3.修改conf/context.xml配置文件
```
<Valve className="com.orangefunction.tomcat.redissessions.RedisSessionHandlerValve" />        
<Manager className="com.orangefunction.tomcat.redissessions.RedisSessionManager" 
        host="127.0.0.1"       
        port="6379"           
   	  maxInactiveInterval="60" />

```
4.启动tomcat,session已经存到Redis中,SESSIONID为key
