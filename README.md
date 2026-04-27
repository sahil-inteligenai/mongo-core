# mongo-core — Public Maven Repository

Public, no-auth Maven repository hosting `mongo-core`. Two GAVs are served — pick whichever you prefer.

> **Note:** The package shown on GitHub Packages (`com.github.sahil-inteligenai:mongo-core:1.0.0`) requires a GitHub PAT to install. **This raw repo serves the same artifact with no auth.**

## Usage

Add the repository to your `pom.xml`:

```xml
<repositories>
  <repository>
    <id>mongo-core-repo</id>
    <url>https://raw.githubusercontent.com/sahil-inteligenai/mongo-core/main/</url>
  </repository>
</repositories>
```

Then pick **one** of the GAVs below:

### Option A — `com.github.sahil-inteligenai:mongo-core:1.0.0` (matches GitHub Packages)

```xml
<dependency>
  <groupId>com.github.sahil-inteligenai</groupId>
  <artifactId>mongo-core</artifactId>
  <version>1.0.0</version>
</dependency>
```

### Option B — `com.sixsprints:mongo-core:1.0` (original POM coordinates)

```xml
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
    implementation 'com.github.sahil-inteligenai:mongo-core:1.0.0'
    // or: implementation 'com.sixsprints:mongo-core:1.0'
}
```
