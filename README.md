# maven-generate-bom

This is an example project to demonstrate how to generate a BOM (Bill of Materials) using the Maven Flatten Plugin.

## Explanation

I've created 3 modules in this project:
- abelaneiros-common
- abelaneiros-secretsmanager
- abelaneiros-ssm

And a BOM module that only contains the pom.xml file with the dependencies of the other modules:
- abelaneiros-bom

## Usage

1. Clone this project:
```bash
git clone https://github.com/abelaneiros/maven-generate-bom.git
```
2. Build this project:
```bash
mvn clean install
```

3. In your project pom.xml add first the BOM as a dependency management:

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>example</groupId>
            <artifactId>abelaneiros-bom</artifactId>
            <version>1.0.0-SNAPSHOT</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>  
```

4. Then the required artifacts as dependencies:

```xml
<dependencies>
      <dependency>
        <groupId>example</groupId>
        <artifactId>abelaneiros-common</artifactId>
        <version>1.0.0-SNAPSHOT</version>
      </dependency>
      <dependency>
        <groupId>example</groupId>
        <artifactId>abelaneiros-secretsmanager</artifactId>
        <version>1.0.0-SNAPSHOT</version>
      </dependency>
</dependencies>    
```

## See more:
https://www.mojohaus.org/flatten-maven-plugin/flatten-mojo.html
https://github.com/mojohaus/flatten-maven-plugin/blob/master/src/main/java/org/codehaus/mojo/flatten/ElementHandling.java



