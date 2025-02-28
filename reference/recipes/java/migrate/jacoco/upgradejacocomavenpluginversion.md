# Upgrade JaCoCo Maven plugin version

** org.openrewrite.java.migrate.jacoco.UpgradeJaCoCoMavenPluginVersion**
_This recipe will upgrade the JaCoCo Maven plugin to a more recent version compatible with Java 11._

### Tags

* jacoco
* java11

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
    activeRecipe("org.openrewrite.java.migrate.jacoco.UpgradeJaCoCoMavenPluginVersion")
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
            <recipe>org.openrewrite.java.migrate.jacoco.UpgradeJaCoCoMavenPluginVersion</recipe>
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

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.java.migrate.jacoco.UpgradeJaCoCoMavenPluginVersion`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Upgrade Maven plugin version](../../../maven/upgradepluginversion.md)
  * groupId: `org.jacoco`
  * artifactId: `jacoco-maven-plugin`
  * newVersion: `0.8.8`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.migrate.jacoco.UpgradeJaCoCoMavenPluginVersion
displayName: Upgrade JaCoCo Maven plugin version
description: This recipe will upgrade the JaCoCo Maven plugin to a more recent version compatible with Java 11.
tags:
  - jacoco
  - java11
recipeList:
  - org.openrewrite.maven.UpgradePluginVersion:
      groupId: org.jacoco
      artifactId: jacoco-maven-plugin
      newVersion: 0.8.8

```
{% endtab %}
{% endtabs %}
