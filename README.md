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

---

## Alternative — install from GitHub Packages (requires PAT)

The same artifact is also published to GitHub Packages at
`https://maven.pkg.github.com/sahil-inteligenai/mongo-core`.

> **GitHub limitation:** `maven.pkg.github.com` requires authentication for **all** reads, even on public packages. There is no way to make this URL anonymous. If you want zero-auth, use the raw repo URL above.

### 1. Create a GitHub Personal Access Token (Classic)

Go to https://github.com/settings/tokens and generate a token with the
**`read:packages`** scope. (For publishing, also add `write:packages`.)

### 2. Add credentials to `~/.m2/settings.xml`

```xml
<settings>
  <servers>
    <server>
      <id>github</id>
      <username>YOUR_GITHUB_USERNAME</username>
      <password>YOUR_PAT</password>
    </server>
  </servers>
</settings>
```

### 3. Add the repository and dependency to your `pom.xml`

```xml
<repositories>
  <repository>
    <id>github</id>
    <url>https://maven.pkg.github.com/sahil-inteligenai/mongo-core</url>
  </repository>
</repositories>

<dependency>
  <groupId>com.github.sahil-inteligenai</groupId>
  <artifactId>mongo-core</artifactId>
  <version>1.0.0</version>
</dependency>
```

### Publishing a new version (maintainer only)

```bash
mvn deploy:deploy-file \
  -DgroupId=com.github.sahil-inteligenai \
  -DartifactId=mongo-core \
  -Dversion=1.0.0 \
  -Dpackaging=jar \
  -Dfile=mongo-core-2.2.6_5-279d4ecc66-1.jar \
  -DrepositoryId=github \
  -Durl=https://maven.pkg.github.com/sahil-inteligenai/mongo-core
```

The `repositoryId=github` must match the `<server><id>github</id></server>`
entry in `~/.m2/settings.xml` so the PAT is picked up.
