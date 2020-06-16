# thin-demo
this is a demo for [spring-boot-thin-launcher](https://github.com/spring-projects-experimental/spring-boot-thin-launcher)

test step:
```
1.$ mvn clean deploy
$ ll reporoot/repository/thin/demo/thin-lib/1.0-SNAPSHOT/
-rw-r--r-- 1 yong 197121 2647  6月 17 00:01 thin-lib-1.0-SNAPSHOT.jar

2.$ rm thin-lib/src/main/java/thin/demo/lib/ClassB.java
$ rm thin-lib/src/main/java/thin/demo/lib/ClassC.java

3.$ mvn clean install
$ ll reporoot/repository/thin/demo/thin-lib/1.0-SNAPSHOT/
-rw-r--r-- 1 yong 197121 2647  6月 17 00:04 thin-lib-1.0-SNAPSHOT.jar

```

after step 3 , the thin-lib-1.0-SNAPSHOT.jar is 1987 bytes in my local repo, but 2647 bytes in thin resolved dependency.
if i use `mvn clean deploy`, the thin-lib-1.0-SNAPSHOT.jar will be deployed to my private nexus repo, and it works well.