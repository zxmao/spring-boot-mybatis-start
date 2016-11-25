# spring 3.0 相关

##  自动检测 Bean
 -   使用<context:cmponent-scan> 拥有 <context:annotation-config> 开启注解功能
 -   1.为了配置Spring自动检车，需要使用<context:cmponent-scan>元素來代替<context:annotation-config>元素
 
> <context:cmponent-scan>:
-    查找使用构造型stereotype注解所标注的类
>-  @Component
>-  @Controller
>-  @Repository
>-  @Service
>-  使用@Component標注的任意自定義注解

> <context:include-filter/>告知哪些类需要被spring注册为bean<br/>
> <context:exclude-filter/>告知哪些类不需要被spring注册为bean<br/>

> <context:include-filter type="assignable" expression="xx.xx.xx.xx"/><br/>
> 暂不详解/type分 
>- annotation
>- assignable
>- aspectj
>- custom
>- regex

> 清除xml配置spring<br/>
> @Configuration注解的java类,等价于XML配置中的<beans>元素
- @Bean 作用于方法是上面，创建bean
- id默认为方法名字 
- 使用该注解的方法在创建实例的时候，并不会直接创建对象实例，而是会由Spirng拦截，检查spring容器是否有该对象实例，有就引用Spirng容器里面的实例，没有才会创建一个实例

## AOP
- AspectJ (http://eclipse.org/aspectj);
- JBoss AOP (http://www.jboss.org/jbossaop);
- Spring AOP (http://www.springframework.org).

> springAOP
- 基于代理的经典AOP
- @AspectJ注解驱动的切面
- 纯POJO切面
- 注入式AspectJ切面（适合Spring各版本）
- 前三种是spring基于代理的AOP变体。Spring对AOP的支持局限于方法拦截。
- spring只支持方法连接点（限制）

学习AspectJ书籍 ： Rammniva Laddad <<AspectJ in Action,Second Edition>>

AspectJ 指示器 / 描述
- arg() 限制
- @arg() 限制
- execution() 执行
- this() 限制
- target() 限制
- @target() 限制
- within() 限制
- @within() 限制
- @annotation() 限制

### execution(* com.springinaction.springidol.Instrument.play(..))
### execution(返回类型 方法所属类型.方法(参数))

> ### execution(* com.springinaction.springidol.Instrument.play(..) && within(com.springinaction.springidol)) and !bean(eddie) <br/> 
  ### 使用within()指示器来限制匹配  并且 除了指定ID的Bean应用通知
  - XML         and     or      not
  - annotation  &&      ||      !
  
  
 ## AOP配置元素
 - <aop:advisor> 
 - <aop:config> 
 - <aop:pointcut>
 - <aop:after>
 - <aop:after-returning>
 - <aop:after-throwing>
 - <aop:before>
 - <aop:around>
 - <aop:aspect>
 - <aop:aspect-autoproxy> 啓用@AspectJ注解驅動的切麵
 - <aop:declare-parents> 引入別的接口實現

> 环绕通知<aop:around> 

`
try{

    //前置通知
    joinpoint.proceed()
    //後置通知
}catche(Throwable t){

    //異常通知
}

//138

`









































