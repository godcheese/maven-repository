# maven-repository
自己的 Maven Repository

将以下代码添加到项目的 pom.xml 中即可获取本仓库的依赖包：
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
或者直接使用
```
  <repositories>
        <repository>
            <id>godcheese-github-maven-repository</id>
            <url>https://raw.githubusercontent.com/godcheese/maven-repository/master/repository</url>
        </repository>
    </repositories>
```

国内镜像地址（解决无法连接 GitHub 的问题）

```
  <repositories>
        <repository>
            <id>godcheese-github-maven-repository</id>
            <url>https://cdn.jsdelivr.net/gh/godcheese/maven-repository</url>
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
```

deploy.sh 代码：
```
#!/usr/bin/env bash
echo "author godcheese"
CURRENT_DIR=$(pwd)
echo ${CURRENT_DIR}
SCRIPTS_DIR=$(cd "$(dirname $0)" || exit; pwd)
cd "${SCRIPTS_DIR}" || exit
cd ..
rm -rf maven-repository
git clone https://github.com/godcheese/maven-repository.git
mvn clean deploy -Dmaven.test.skip -DaltDeploymentRepository="godcheese-github-maven-repository::default::file:`pwd`/maven-repository/repository"
cd maven-repository
echo "Add file..."
git add -A
git commit -m "deploy release package."
echo "Submit code..."
git push origin master
echo "Submit complete,close..."
cd "${CURRENT_DIR}"
cd ..
rm -rf maven-repository

```
