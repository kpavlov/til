[Home](../README.md)

Swagger Stuff
=============

## Docker image for local swagger editor

For local swagger editor: 

    docker run --rm -p 8085:8080 swaggerapi/swagger-editor & open http://localhost:8085

## `pom.xml` for swagger-generated java API

~~~xml pom.xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>swagger-api</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <swagger.codegen.version>2.3.1</swagger.codegen.version>
        <swagger.version>1.5.17</swagger.version>
    </properties>

    <dependencies>
        <dependency>
            <groupId>io.swagger</groupId>
            <artifactId>swagger-annotations</artifactId>
            <version>${swagger.version}</version>
        </dependency>
    </dependencies>
    
    <build>
        <plugins>
            <plugin>
                <groupId>io.swagger</groupId>
                <artifactId>swagger-codegen-maven-plugin</artifactId>
                <version>${swagger.codegen.version}</version>
                <executions>
                    <execution>
                        <id>generate-payment-api</id>
                        <phase>generate-sources</phase>
                        <goals>
                            <goal>generate</goal>
                        </goals>
                        <configuration>
                            <inputSpec>${project.basedir}/swagger/swagger.yaml</inputSpec>
                            <apiPackage>com.example.api.v1</apiPackage>
                            <modelPackage>com.example.api.v1.model</modelPackage>
                            <verbose>false</verbose>
                            <configHelp>false</configHelp>
                            <language>spring</language>
                            <generateApiDocumentation>false</generateApiDocumentation>
                            <generateApis>true</generateApis>
                            <generateModels>true</generateModels>
                            <generateSupportingFiles>false</generateSupportingFiles>
                            <configOptions>
                                <useBeanValidation>true</useBeanValidation>
                                <java8>true</java8>
                                <dateLibrary>java8</dateLibrary>
                            </configOptions>
                        </configuration>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
</project>
~~~
