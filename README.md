# maven-repository
自己的 Maven Repository

## 添加仓库镜像
- 将以下代码添加到项目的 pom.xml 中即可获取本仓库的依赖包：

```
<repositories>
    <repository>
        <id>godcheese-github-maven-repository</id>
        <url>https://raw.githubusercontent.com/godcheese/maven-repository/master/repository</url>
    </repository>
</repositories>
```

- 国内无法连接 raw.githubusercontent.com 的问题，在 etc 中指定可以 PING 通的 IP 地址：
```
199.232.28.133 raw.githubusercontent.com
```

- 或者使用
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

## 添加项目依赖
pom.xml 文件中依赖包添加方式，如下：
```
 <dependency>
    <groupId>com.gioov</groupId>
    <artifactId>tile</artifactId>
    <version>1.0.0</version>
 </dependency>
```

## 部署代码
- [deploy.sh](https://github.com/godcheese/maven-repository/blob/master/scripts/deploy.sh)
- [deploy.bat](https://github.com/godcheese/maven-repository/blob/master/scripts/deploy.bat)
