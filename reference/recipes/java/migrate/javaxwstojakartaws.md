# Migrate deprecated `javax.ws` packages to `jakarta.ws`

** org.openrewrite.java.migrate.JavaxWsToJakartaWs**
_Java EE has been rebranded to Jakarta EE, necessitating a package relocation._

## Source

[Github](https://github.com/openrewrite/rewrite-migrate-java), [Issue Tracker](https://github.com/openrewrite/rewrite-migrate-java/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-migrate-java/1.9.1/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-migrate-java
* version: 1.9.1


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-migrate-java:1.9.1 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.27.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.migrate.JavaxWsToJakartaWs")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-migrate-java:1.9.1")
}
```
{% endcode %}
{% endtab %}

{% tab title="Maven" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>4.32.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.migrate.JavaxWsToJakartaWs</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-migrate-java</artifactId>
            <version>1.9.1</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.java.migrate.JavaxWsToJakartaWs`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Add Maven dependency](../../maven/adddependency.md)
  * groupId: `jakarta.ws.rs`
  * artifactId: `jakarta.ws.rs-api`
  * version: `3.x`
  * onlyIfUsing: `javax.ws.+`
* [Upgrade Maven dependency version](../../maven/upgradedependencyversion.md)
  * groupId: `jakarta.ws.rs`
  * artifactId: `jakarta.ws.rs-api`
  * newVersion: `3.x`
* [Rename package name](../../java/changepackage.md)
  * oldPackageName: `javax.ws`
  * newPackageName: `jakarta.ws`
  * recursive: `true`
* [Remove Maven dependency](../../maven/removedependency.md)
  * groupId: `javax.ws.rs`
  * artifactId: `javax.ws.rs-api`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.migrate.JavaxWsToJakartaWs
displayName: Migrate deprecated `javax.ws` packages to `jakarta.ws`
description: Java EE has been rebranded to Jakarta EE, necessitating a package relocation.
recipeList:
  - org.openrewrite.maven.AddDependency:
      groupId: jakarta.ws.rs
      artifactId: jakarta.ws.rs-api
      version: 3.x
      onlyIfUsing: javax.ws.+
  - org.openrewrite.maven.UpgradeDependencyVersion:
      groupId: jakarta.ws.rs
      artifactId: jakarta.ws.rs-api
      newVersion: 3.x
  - org.openrewrite.java.ChangePackage:
      oldPackageName: javax.ws
      newPackageName: jakarta.ws
      recursive: true
  - org.openrewrite.maven.RemoveDependency:
      groupId: javax.ws.rs
      artifactId: javax.ws.rs-api

```
{% endtab %}
{% endtabs %}
