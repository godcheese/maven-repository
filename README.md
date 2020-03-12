# maven-repository
自己的 Maven Repository

将以下代码添加到项目的 pom.xml 中即可获取本仓库的依赖包。
```
<repositories>
    <repository>
        <id>godcheese-maven-repository-snapshot</id>
        <url>https://raw.githubusercontent.com/godcheese/maven-repository/snapshot/repository</url>
    </repository>
    <repository>
        <id>godcheese-maven-repository-release</id>
        <url>https://raw.githubusercontent.com/godcheese/maven-repository/release/repository</url>
    </repository>
</repositories>
```

pom.xml 文件中依赖包添加方式，如下：
```
 <dependency>
    <groupId>com.gioov</groupId>
    <artifactId>tile</artifactId>
    <version>1.0.0</version>
 </dependency>
```# maven-repository
自己的 Maven Repository
