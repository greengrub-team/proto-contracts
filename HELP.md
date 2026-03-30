# Read Me First
The following was discovered as part of building this project:

* The original package name 'com.greengrub.proto-contracts' is invalid and this project uses 'com.greengrub.proto_contracts' instead.

# Getting Started

### Reference Documentation
For further reference, please consider the following sections:

* [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)
* [Spring Boot Maven Plugin Reference Guide](https://docs.spring.io/spring-boot/4.0.3/maven-plugin)
* [Create an OCI image](https://docs.spring.io/spring-boot/4.0.3/maven-plugin/build-image.html)

### Maven Parent overrides

Due to Maven's design, elements are inherited from the parent POM to the project POM.
While most of the inheritance is fine, it also inherits unwanted elements like `<license>` and `<developers>` from the parent.
To prevent this, the project POM contains empty overrides for these elements.
If you manually switch to a different parent and actually want the inheritance, you need to remove those overrides.


### For this project we are using a Project-Level setting.xml file 

Add a setting.xml file at project level (where you have your pom file)
content:

    <servers>
        <server>
            <id>github</id>
            <username>${env.GITHUB_USERNAME}</username>
            <password>${env.GITHUB_TOKEN}</password>
        </server>
    </servers>

To Deploy the changes run below three commands :
export GITHUB_USERNAME=your_username \
export GITHUB_TOKEN=your_token \
mvn clean deploy -s settings.xml

