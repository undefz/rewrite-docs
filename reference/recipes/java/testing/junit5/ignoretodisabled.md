# Use JUnit Jupiter `@Disabled`

** org.openrewrite.java.testing.junit5.IgnoreToDisabled**
_Migrates JUnit 4.x `@Ignore` to JUnit Jupiter `@Disabled`._

### Tags

* junit
* testing

## Source

[Github](https://github.com/openrewrite/rewrite-testing-frameworks), [Issue Tracker](https://github.com/openrewrite/rewrite-testing-frameworks/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-testing-frameworks/1.26.1/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-testing-frameworks
* version: 1.26.1


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-testing-frameworks:1.26.1 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.27.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.testing.junit5.IgnoreToDisabled")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-testing-frameworks:1.26.1")
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
            <recipe>org.openrewrite.java.testing.junit5.IgnoreToDisabled</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-testing-frameworks</artifactId>
            <version>1.26.1</version>
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

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.java.testing.junit5.IgnoreToDisabled`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `org.junit.Ignore`
  * newFullyQualifiedTypeName: `org.junit.jupiter.api.Disabled`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.testing.junit5.IgnoreToDisabled
displayName: Use JUnit Jupiter `@Disabled`
description: Migrates JUnit 4.x `@Ignore` to JUnit Jupiter `@Disabled`.
tags:
  - junit
  - testing
recipeList:
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: org.junit.Ignore
      newFullyQualifiedTypeName: org.junit.jupiter.api.Disabled

```
{% endtab %}
{% endtabs %}
