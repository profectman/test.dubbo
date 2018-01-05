# Dubbo-Zookeeper-Netty-SpringMVC

1. dubbo-common 提供公共接口；
2. dubbo-provide是服务提供者（接口的实现）；
3. dubbo-consumer是服务器消费者（接口的调用）；
4. zookeeper管理注册中心（负载均衡，资源同步-当然前提是集群）；
5. springmvc写restful接口；
6. netty提供服务器，客户端的请求由spring的DispatcherServlet处理；


如何创建一个dubbo-zookeeper-Netty-SptingMVC项目
   1.总pom.xml的配置
         添加jcl - over - slf4j - 1.7.25
                 junit - 4.12
                 spring-context(exclusion common-logging)
                 spring-webmvc
                 spring-test
                 dubbo-2.5.8(exclusion org.springframework)
                 zkclient-0.1
                 netty(netty-transport netty-handler netty-codec-http)
                 geronimo-servlet-3.0_spec -1.0
                 aspectjrt-1.8.2
                 cglib-2.2
    2.创建DubboCommon(dubbo.common)          
                 创建接口  并写入一个抽象方法
    3.创建DubboProduer
           1.pom.xml中引入DubboCommon
           2.创建包并创建一个接口实现类
           3.在dubbo-provider.xml文件中去配置参数
    4.创建DubboConsumer
           1.创建springMVC和consumer配置文件,配置文件
            ........     