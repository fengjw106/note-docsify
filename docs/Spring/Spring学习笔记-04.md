# Spring学习笔记 - 04

## 1. Spring 中的事务控制

### 1.1 基本介绍

- 在上一篇笔记中，为了实现业务层的事务管理，我们自己创建了连接工具类 `ConnectionUtils` 和事务管理器 `TransactionManager`。但是其实 Spring 已经给我们提供了事务管理相关的接口，我们只需要在配置文件中声明使用即可。
- JavaEE 体系进行分层开发，**事务处理位于业务层**，Spring 提供了分层设计业务层的事务处理解决方案。
- Spring 框架为我们提供了一组事务控制的接口，这组接口是在 `spring-tx-5.0.2.RELEASE.jar` 中，因此我们需要导入相关依赖

```xml
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-tx</artifactId>
    <version>5.0.2.RELEASE</version>
</dependency>
```

- **Spring 的事务控制都是基于 AOP 的**，它既可以使用编程的方式实现，也可以使用配置的方式实现。由于编程式事务比较繁琐并且耦合度高，所以这里不作介绍，只介绍**声明式事务**。

### 1.2 Spring 中事务控制的 API 介绍

#### 1.2.1 PlatformTransactionManager 接口

- `PlatformTransactionManager` 接口是 Spring 的事务管理器，它里面提供了我们常用的操作事务的方法，见下表

| 常用方法                                                     | 作用             |
| ------------------------------------------------------------ | ---------------- |
| `TransactionStatus getTransaction(@Nullable TransactionDefinition definition)` | 获取事务状态信息 |
| `void commit(TransactionStatus status)`                      | 提交事务         |
| `void rollback(TransactionStatus status)`                    | 回滚事务         |

- 在开发我们一般使用以下实现类

| 实现类                                                       | 作用                                                  |
| ------------------------------------------------------------ | ----------------------------------------------------- |
| `org.springframework.jdbc.datasource.DataSourceTransactionManager` | **使用Spring JDBC 或者 Mybatis 进行持久化数据时使用** |
| `org.springframework.orm.hibernate5.HibernateTransactionManager` | 使用 HIbernate 进行持久化数据时使用                   |

#### 1.2.2 TransactionDefinition 接口

- `TransactionDefinition` 接口是事务的定义信息对象，提供以下方法：

| 常用方法                     | 作用               |
| ---------------------------- | ------------------ |
| `String getName()`           | 获取事务的名称     |
| `int getIsolationLevel()`    | 获取事务的隔离级别 |
| `int getPropagationBehavior` | 获取事务的传播行为 |
| `int getTimeout()`           | 获取事务的超时时间 |
| `boolean isReadOnly()`       | 获取事务是否只读   |

> - 事务的隔离级别反映了事务提交并发访问时的处理态度，在`TransactionDefinition`中定义了以下几种级别
>   - `ISOLATION_DEFAULT` ： 使用数据库默认的隔离级别，为以下四种的其中之一
>   - `ISOLATION_READ_UNCOMMITTED` ： 可以读取未提交数据
>   - `ISOLATION_READ_COMMITTED` ： 只能读取已提交数据，解决脏读问题 **（Oracle 默认级别）**
>   - `ISOLATION_REPEATABLE_READ` ： 只有当前事务提交后才可以看到其他事务提交的修改 **（MySQL 默认级别）**
>   - `ISOLATION_SERIALIZABLE` ： 事务串行执行，一个时刻只能有一个事务执行
> - 事务的传播行为反映了事务的控制范围，在`TransactionDefinition`中定义了以下几种级别
>   - **`REQUIRED`：默认的 Spring 事务传播行为，能满足大部分应用场景**。如果当前没有事务，就新建一个事务；如果已经存在一个事务，那么加入到这个事务中。
>   - **`SUPPORTS`**：支持当前事务，如果没有事务，就以非事务方式执行
>   - `MANDATORY`：使用当前的事务，如果没有事务就抛出异常
>   - `REQUIRES_NEW` ：新建事务，如果当前处于事务中，就把当前事务挂起
>   - `NOT_SUPPORTED`：以非事务方式执行操作，如果当前存在事务，就把当前事务挂起
>   - `NEVER`：以非事务方式执行操作，如果当前存在事务就抛出异常
>   - `NESTED`：如果当前存在事务，则在嵌套事务中执行；如果当前没有事务，则执行 `REQUIRED` 类似的操作
> - 事务的超时时间
>   - **默认值是 -1 ，没有超时限制**。设置的时候以秒为单位进行设置
> - 事务是否为只读事务
>   - 一般把查询操作设置为只读事务
> - 了解隔离级别和传播行为可以看这里：[Spring五个事务隔离级别和七个事务传播行为](https://yq.aliyun.com/articles/48893)

#### 1.2.3 TransactionStatus 接口

- `TransactionStatus` 接口描述了某个时间点上事务对象具体的运行状态，提供以下方法：

| 常用方法                     | 作用                   |
| ---------------------------- | ---------------------- |
| `void flush()`               | 刷新事务               |
| `boolean hasSavepoint()`     | 获取是否存在存储点     |
| `boolean isCompleted()`      | 获取事务是否完成       |
| `boolean isNewTransaction()` | 获取事务是否为新的事务 |
| `boolean isRollbackOnly()`   | 获取事务是否回滚       |
| `void setRollbackOnly()`     | 设置回滚               |

### 1.3 基于 XML 的声明式事务控制

- 这里使用上一篇笔记的账户案例，在此基础上修改
- 导入相关依赖

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-context</artifactId>
        <version>5.0.2.RELEASE</version>
    </dependency>
    <!-- 使用JdbcTemplate -->
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-jdbc</artifactId>
        <version>5.0.2.RELEASE</version>
    </dependency>
    <!-- 事务 -->
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-tx</artifactId>
        <version>5.0.2.RELEASE</version>
    </dependency>

    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-test</artifactId>
        <version>5.0.2.RELEASE</version>
    </dependency>

    <dependency>
        <groupId>org.aspectj</groupId>
        <artifactId>aspectjweaver</artifactId>
        <version>1.8.7</version>
    </dependency>

    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>5.1.6</version>
    </dependency>

    <dependency>
        <groupId>junit</groupId>
        <artifactId>junit</artifactId>
        <version>4.12</version>
        <scope>test</scope>
    </dependency>
</dependencies>
```

- 持久层使用 `JdbcTemplate`，同时继承 `JdbcDaoSupport` 完成数据源注入，不了解 `JbdcTemplate` 的可以看这里：[Spring 的 JdbcTemplate 的入门使用](http://note.youdao.com/noteshare?id=67713bcc3b2b9ea82c84d7808a80def9&sub=BD84A6)

```java
public class AccountDaoImpl extends JdbcDaoSupport implements IAccountDao {

    @Override
    public Account getAccountById(Integer accountId) {
        return super.getJdbcTemplate().queryForObject("SELECT * FROM account WHERE id = ?",new BeanPropertyRowMapper<Account>(Account.class));
    }

    @Override
    public Account getAccountByName(String accountName) {
        List<Account> accounts = super.getJdbcTemplate().query("SELECT * FROM account WHERE name = ?", new BeanPropertyRowMapper<Account>(Account.class), accountName);
        if (accounts.isEmpty()) {
            return null;
        }
        if (accounts.size() > 1) {
            throw new RuntimeException("结果集不唯一！");
        }
        return accounts.get(0);
    }

    @Override
    public int updateAccount(Account account) {
        return super.getJdbcTemplate().update("UPDATE account SET name = ?, balance = ? WHERE id = ?", account.getName(), account.getBalance(), account.getId());
    }
}
```

- 编写配置文件，注意要导入 `aop` 和 `tx` 的名称空间

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xmlns:tx="http://www.springframework.org/schema/tx"
       xsi:schemaLocation="
        http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/tx
        http://www.springframework.org/schema/tx/spring-tx.xsd
        http://www.springframework.org/schema/aop
        http://www.springframework.org/schema/aop/spring-aop.xsd">

    <!-- 配置service -->
    <bean id="accountService" class="cn.ykf.service.impl.AccountServiceImpl">
        <property name="accountDao" ref="accountDao"/>
    </bean>

    <!-- 配置dao -->
    <bean id="accountDao" class="cn.ykf.dao.impl.AccountDaoImpl">
        <!-- 注入数据源 -->
        <property name="dataSource" ref="dataSource"/>
    </bean>

    <!-- 配置数据源，这里使用的是 Spring 内置连接池 -->
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName" value="com.mysql.jdbc.Driver"/>
        <property name="url" value="jdbc:mysql://localhost:3306/db_demo"/>
        <property name="username" value="root"/>
        <property name="password" value="123456"/>
    </bean>

    <!-- 配置事务管理器 -->
    <bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
        <property name="dataSource" ref="dataSource"/>
    </bean>

    <!-- 配置事务的通知 -->
    <tx:advice id="txAdvice" transaction-manager="transactionManager">
        <!-- 配置事务的属性 -->
        <tx:attributes>
            <!-- 所有方法都有事务控制，但是优先级低于 "get*" -->
            <tx:method name="*" propagation="REQUIRED" read-only="false"/>
            <!-- 所有查询方法都为只读事务，传播行为：支持事务 -->
            <tx:method name="get*" propagation="SUPPORTS" read-only="true"/>
        </tx:attributes>
    </tx:advice>
    
    <!-- 配置aop -->
    <aop:config>
        <!-- 配置切入点表达式 -->
        <aop:pointcut id="pt1" expression="execution(* cn.ykf.service.impl.*.*(..))"/>
        <!-- 建立切入点表达式和事务通知的关系 -->
        <aop:advisor advice-ref="txAdvice" pointcut-ref="pt1"></aop:advisor>
    </aop:config>
</beans>
```

#### 1.3.1 声明式事务的配置步骤

1. 使用 `<bean>` 标签配置一个事务管理器 `DataSourceTransactionManager`
2. 使用 `<tx:advice>` 标签配置事务的通知并且引用事务管理器

> - `id` 属性用于给事务通知提供一个唯一标识， `ref` 属性用于引用配置好的事务管理器 Bean

1. 在 `<tx:advice>` 标签内部使用 `<tx:attributes>` 标签和 `<tx:method>` 标签配置事务的属性

> - `<tx:method>`标签用于配置事务的属性，有以下属性：
>   - `name` 属性：指定要控制的方法，可以使用通配符 `*`
>   - `propagation` 属性：指定事务的传播行为，增删改使用 `REQUIRED`（默认值），查询使用 `SUPPORTS`
>   - `isolation` 属性：指定事务的隔离级别，默认值是 `DEFAULT`，表示使用数据库的默认隔离级别
>   - `read-only` 属性：指定事务是否只读，默认值为 `false`，表示读写，只有查询方法才需要设置为 `true`
>   - `timeout` 属性：指定事务的超时时间
>   - `rollback-for` 属性：用于指定一个异常，当产生该异常时，事务回滚；产生其它异常时，事务不回滚。没有默认值，表示任何事务都回滚
>   - `no-rollback-for` 属性：用于指定一个异常，当产生该异常时，事务不回滚；产生其它异常时，事务回滚。没有默认值，表示任何事务都回滚

1. 使用 `<aop:config>` 标签和 `<aop:pointcut>` 标签配置 AOP 切入点表达式
2. 在 `<aop:config>` 标签内部使用 `<aop:advisor>` 标签配置切入点表达式和事务通知的关系

> `advice-ref` 属性用于指定通知的引用，`pointcut-ref` 属性用于指定切入点表达式的引用

### 1.4 基于半注解（XML + 注解） 的声明式事务控制

- 修改业务层和持久层代码， 使用 `@Transactional` 注解开启业务层方法的事务配置

```java
// 业务层
@Service("accountService")
// 开启事务配置
@Transactional(propagation = Propagation.SUPPORTS, readOnly = true)
public class AccountServiceImpl implements IAccountService {

    @Autowired
    private IAccountDao accountDao;

    @Override
    public Account getAccountById(Integer accountId) {
        return accountDao.getAccountById(accountId);
    }

    @Override
    // 单独配置非查询方法
    @Transactional(propagation = Propagation.REQUIRED, readOnly = false)
    public void transfer(String sourceName, String targetName, Double money) {
        // 1. 获取转出账户和转入账户
        Account source = accountDao.getAccountByName(sourceName);
        Account target = accountDao.getAccountByName(targetName);
        // 2 转账
        source.setBalance(source.getBalance() - money);
        target.setBalance(target.getBalance() + money);
        // 3. 更新账户
        accountDao.updateAccount(source);
        // 模拟异常
        int i = 1 / 0;
        accountDao.updateAccount(target);
    }
}

// 持久层
@Repository("accountDao")
public class AccountDaoImpl implements IAccountDao {
    @Autowired
    private JdbcTemplate jdbcTemplate;
    // ...
}
```

> - 关于`@Transactional`注解：
>   - 该注解的属性和 XML 中的属性含义一致。该注解可以出现在接口上，类上和方法上。
>   - 出现接口上，表示该接口的所有实现类都有事务支持。
>   - 出现在类上，表示类中所有方法有事务支持
>   - 出现在方法上，表示方法有事务支持。
>   - **以上三个位置的优先级：方法>类>接口**
> - 使用注解不需要配置 AOP 的原因是在业务层配置了 `@Transactional` 注解的地方就相当于是切入点

- 编写配置文件，注意在配置文件中一样要配置事务管理器，同时还要开启对注解事务的支持

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:tx="http://www.springframework.org/schema/tx"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="
        http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/tx
        http://www.springframework.org/schema/tx/spring-tx.xsd
        http://www.springframework.org/schema/context
        http://www.springframework.org/schema/context/spring-context.xsd">


    <!-- 配置要扫描的包 -->
    <context:component-scan base-package="cn.ykf"/>

    <!-- 配置 JdbcTemplate -->
    <bean id="jdbcTemplate" class="org.springframework.jdbc.core.JdbcTemplate">
        <property name="dataSource" ref="dataSource"/>
    </bean>

    <!-- 配置数据源，这里使用的是 Spring 内置连接池 -->
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName" value="com.mysql.jdbc.Driver"/>
        <property name="url" value="jdbc:mysql://localhost:3306/db_demo"/>
        <property name="username" value="root"/>
        <property name="password" value="123456"/>
    </bean>

    <!-- 配置事务管理器 -->
    <bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
        <property name="dataSource" ref="dataSource"/>
    </bean>

    <!-- 开启注解事务的支持 -->
    <tx:annotation-driven transaction-manager="transactionManager"></tx:annotation-driven>
</beans>
```

### 1.5 基于纯注解的声明式事务控制

- 如果想使用纯注解的方式，那么需要使用 `@EnableTransactionManagement` 注解开启事务（这里被我写在 `TransactionConfiguration` 中）

```java
/**
 * Spring 的主配置类，相当于bean.xml
 *
 * @author yukaifan
 * @ClassName SpringConfiguration
 * @date 2020-02-24 10:52
 */
@Configuration
@ComponentScan("cn.ykf")
@Import({JdbcConfiguration.class, TransactionConfiguration.class})
public class SpringConfiguration {
}
```

- Jdbc 配置类

```java
/**
 * 数据库连接相关的配置类
 *
 * @author yukaifan
 * @ClassName JdbcConfiguration
 * @date 2020-02-24 10:53
 */
@PropertySource("classpath:jdbcConfig.properties")
public class JdbcConfiguration {

    @Value("${jdbc.driver}")
    private String driver;

    @Value("${jdbc.url}")
    private String url;

    @Value("${jdbc.username}")
    private String username;

    @Value("${jdbc.password}")
    private String password;

    /**
     * 创建一个JdbcTemplate对象
     *
     * @param dataSource
     * @return
     */
    @Bean(name = "jdbcTemplate")
    @Scope("prototype")
    public JdbcTemplate createJdbcTemplate(DataSource dataSource) {
        return new JdbcTemplate(dataSource);
    }

    /**
     * 创建一个数据源对象
     *
     * @return
     */
    @Bean(name = "dataSource")
    public DataSource createDateSource() {
        DriverManagerDataSource dataSource = new DriverManagerDataSource();
        dataSource.setDriverClassName(driver);
        dataSource.setUrl(url);
        dataSource.setUsername(username);
        dataSource.setPassword(password);

        return dataSource;
    }
}
```

- 事务配置类

```java
/**
 * 事务相关配置类
 *
 * @author yukaifan
 * @ClassName TransactionConfiguration
 * @date 2020-02-24 11:00
 */
@EnableTransactionManagement
public class TransactionConfiguration {
    /**
     * 创建事务管理器
     * @param dataSource
     * @return
     */
    @Bean(name = "transactionManager")
    public PlatformTransactionManager createTransactionManager(DataSource dataSource) {
        return new DataSourceTransactionManager(dataSource);
    }
}
```

## 2. 扩展知识（ 事务）

- 事务的四大特性
  - 原子性（Atomicity）：**一个事务必须视为一个不可分割的最小单元**，整个事务中的所有操作要么全部提交成功，要么全部失败回滚。对于一个事务来说，不可能只执行成功其中的一部分操作，这就是事务的原子性。
  - 一致性（Consistency）：**数据总是从一个一致性的状态转换到另一个一致性的状态**。比如在账户案例的转账中，转帐前后两账户的总金额是不变的。
  - 隔离性（Isolation）：**一个事务所做的修改在最终提交以前，对其他事务是不可见的**，多个并发事务之间是相互隔离的。
  - 持久性（Durability）：**一旦事务提交，所做的修改会永久保存到数据库中**。即使系统崩溃，修改的数据也不会丢失
- 事务的隔离级别
  - `Read-uncommitted` (读未提交) ：一个事务修改了数据，即使没有提交事务，其他的并发事务也可以看到修改。这是最低的隔离级别，会导致脏读、不可重复读、幻读等问题。
  - `Rad-committed` (读已提交)：事务只能读取到其他并发事务已经提交的修改。可以避免脏读，但是存在不可重复读、幻读等问题。
  - `Repeatable-read` (可重复读)：只有当前事务提交后才可以看到其他事务提交的修改。可以避免脏读、不可重复读，但是存在幻读。
  - `Serializable` (串行化)：一个时刻只能有一个事务执行，可以避免脏读、不可重复读、幻读等问题
- 事务的安全隐患
  - 脏读：指在一个事务处理过程中读取了另一个未提交的事务中的数据。
  - 不可重复读：指对于数据库中的某个数据，一个事务内多次查询却返回了不同的数据值，这是由于在事务执行过程中，数据被另一个事务修改并提交了。
  - 幻读：是事务非独立执行时发生的一种现象。例如，事务T1对一个表中所有的行的某个字段做了从“1”修改为“2”的操作，这时事务T2又插入了一条新的记录，而该字段的值为“1”并且提交给数据库。这时，操作事务T1的用户如果再查看刚刚修改的数据，会发现还有一行没有修改，其实这行是从事务T2中添加的，就好像产生幻觉一样，这就是产生了幻读。