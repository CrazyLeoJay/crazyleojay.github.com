# java 数据库连接 JDBC
-

- 步骤

> - 加载驱动

```java
	 Class.forName("com.mysql.jdbc.Driver");
```

> - 获得数据库连接

```java
	Connection conn = DriverManager.getConnection(URL, USER, PASSWORD);
```

> - 操作数据库，实现增删改查

```java
	 Statement stmt = conn.createStatement();
```

其他详见文档

### java.sql Package 包含的内容

java.sql 包中包含用于以下方面的 API：

- 通过 DriverManager 实用程序建立与数据库的连接
    - DriverManager 类：建立与驱动程序的连接
    - SQLPermission 类：当代码在 Security Manager（比如 applet）中运行时提供权限，试图通过 DriverManager 设置一个记录流
    - Driver 接口：提供用来注册和连接基于 JDBC 技术（“JDBC 驱动程序”）的驱动程序的 API，通常仅由 DriverManager 类使用
    - DriverPropertyInfo 类：提供 JDBC 驱动程序的属性，不是供一般用户使用的
- 向数据库发送 SQL 语句
    - Statement：用于发送基本 SQL 语句
    - PreparedStatement：用于发送准备好的语句或基本 SQL 语句（派生自 Statement）
    - CallableStatement：用于调用数据库存储过程（派生自 PreparedStatement）
    - Connection 接口：提供创建语句以及管理连接及其属性的方法
    - Savepoint：在事务中提供保存点
- 获取和更新查询的结果
    - ResultSet 接口
- SQL 类型到 Java 编程语言中的类和接口的标准映射关系
    - Array 接口：SQL ARRAY 的映射关系
    - Blob 接口：SQL BLOB 的映射关系
    - Clob 接口：SQL CLOB 的映射关系
    - Date 类：SQL DATE 的映射关系
    - NClob 接口：SQL NCLOB 的映射关系
    - Ref 接口：SQL REF 的映射关系
    - RowId 接口：SQL ROWID 的映射关系
    - Struct 接口：SQL STRUCT 的映射关系
    - SQLXML 接口：SQL XML 的映射关系
    - Time 类：SQL TIME 的映射关系
    - Timestamp 类：SQL TIMESTAMP 的映射关系
    - Types 类：提供用于 SQL 类型的常量
- 自定义映射 SQL 用户定义类型 (UDT) 到 Java 编程语言中的类
    - SQLData 接口：指定 UDT 到此类的一个实例的映射关系
    - SQLInput 接口：提供用来从流中读取 UDT 属性的方法
    - SQLOutput 接口：提供用来将 UDT 属性写回流中的方法
- 元数据
    - DatabaseMetaData 接口：提供有关数据库的信息
    - ResultSetMetaData 接口：提供有关 ResultSet 对象的列的信息
    - ParameterMetaData 接口：提供有关 PreparedStatement 命令的参数的信息
- 异常
    - SQLException：由大多数方法在访问数据出问题时抛出，以及因为其他原因由其他一些方法抛出
    - SQLWarning：为了指示一个警告而抛出
    - DataTruncation：为了指示数据可能已经被截断而抛出
    - BatchUpdateException：为了指示并不是批量更新中的所有命令都成功执行而抛出