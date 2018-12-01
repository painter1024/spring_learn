# spring_learn
spring learn demo

# Spring boot 热加载
## 第一种：适合Idea自动装载的Run或Debug
1. 打开自动编译
- mac:IDE->preferences->Build project automatically
- win:Settings->Build project automatically
2. CMD+Shift+A ( win：Ctrl+Shift+A ) ->搜索registry，找到Registry...，注意是后面有三个点的那个，然后找到compiler.automake.allow.when.app.running，勾选

## 第二种：这种方式不支持idea自动装载的run和debug
Spring boot提供了devtools，添加依赖，同时在settings里设置Build project automatically
```
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-devtools</artifactId>
    <optional>true</optional>
</dependency>
<build>
    <plugins>
        <plugin>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
            <configuration>
                <fork>true</fork>
            </configuration>
        </plugin>
    </plugins>
</build>
```
配置好后使用命令启动 mvn `spring-boot:run`

推荐使用第一种方法