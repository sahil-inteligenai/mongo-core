# mongo-core — Public Maven Repository

Public, no-auth Maven repository hosting `com.sixsprints:mongo-core`.

## Usage

Add this repository and dependency to your `pom.xml`:

```xml
<repositories>
  <repository>
    <id>mongo-core-repo</id>
    <url>https://raw.githubusercontent.com/sahil-inteligenai/mongo-core/main/</url>
  </repository>
</repositories>

<dependency>
  <groupId>com.sixsprints</groupId>
  <artifactId>mongo-core</artifactId>
  <version>1.0</version>
</dependency>
```

That's it — `mvn install` / `mvn package` will pull it. No login, no token.

### Gradle

```groovy
repositories {
    maven { url 'https://raw.githubusercontent.com/sahil-inteligenai/mongo-core/main/' }
}

dependencies {
    implementation 'com.sixsprints:mongo-core:1.0'
}
```
