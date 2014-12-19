compiler-eclipse
================

Maven Compiler Plug-in for Java 1.8

This project will be removed as soon as:<br>
1. JDK-8059511 and relative bugs solved, see http://stackoverflow.com/questions/26972192 . Or<br>
2. plexus-compiler-eclipse supports Java 1.8 .

Some codes with Java 1.8 features can be run properly under Eclipse but fail to be built by maven
default compiler (javac). Use xqbase-compiler-eclipse as a workaround to pass maven compilation:

```xml
<build>
    <plugins>
        <plugin>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.2</version>
            <configuration>
                <compilerId>eclipse</compilerId>
                <optimize>true</optimize>
            </configuration>
            <dependencies>
                <dependency>
                    <groupId>com.xqbase</groupId>
                    <artifactId>xqbase-compiler-eclipse</artifactId>
                    <version>0.1.0</version>
                </dependency>
            </dependencies>
        </plugin>
    </plugins>
</build>
```