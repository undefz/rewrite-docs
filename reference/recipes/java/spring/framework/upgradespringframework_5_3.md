# Upgrade to Spring Framework 5.3

** org.openrewrite.java.spring.framework.UpgradeSpringFramework\_5\_3**
_Upgrade to Spring Framework to 5.3 from any prior version._

## Source

[Github](https://github.com/openrewrite/rewrite-spring), [Issue Tracker](https://github.com/openrewrite/rewrite-spring/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-spring/4.25.1/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-spring
* version: 4.25.1


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-spring:4.25.1 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.27.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.spring.framework.UpgradeSpringFramework_5_3")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-spring:4.25.1")
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
            <recipe>org.openrewrite.java.spring.framework.UpgradeSpringFramework_5_3</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-spring</artifactId>
            <version>4.25.1</version>
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

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.java.spring.framework.UpgradeSpringFramework_5_3`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Upgrade spring-framework Maven dependencies](../../../java/spring/framework/upgradespringframeworkdependencies.md)
  * newVersion: `5.3.x`
* [Use `ObjectUtils#isEmpty(Object)`](../../../java/spring/framework/useobjectutilsisempty.md)
* [Convert `InstantiationAwareBeanPostProcessorAdapter` to `SmartInstantiationAwareBeanPostProcessor`](../../../java/spring/framework/migrateinstantiationawarebeanpostprocessoradapter.md)
* [Use varargs equivalents for deprecated JdbcTemplate signatures](../../../java/spring/framework/jdbctemplateobjectarrayargtovarargs.md)
* [Upgrade Maven dependency version](../../../maven/upgradedependencyversion.md)
  * groupId: `org.hibernate`
  * artifactId: `hibernate-search-orm`
  * newVersion: `5.11.x`
  * overrideManagedVersion: `true`
* [Remove Maven dependency](../../../maven/removedependency.md)
  * groupId: `org.aspectj`
  * artifactId: `aspectjrt`
* [Remove Maven dependency](../../../maven/removedependency.md)
  * groupId: `org.aspectj`
  * artifactId: `aspectjweaver`
* [Remove Maven dependency](../../../maven/removedependency.md)
  * groupId: `aopalliance`
  * artifactId: `aopalliance`
* [Remove Maven dependency](../../../maven/removedependency.md)
  * groupId: `cglib`
  * artifactId: `cglib`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.spring.framework.UpgradeSpringFramework_5_3
displayName: Upgrade to Spring Framework 5.3
description: Upgrade to Spring Framework to 5.3 from any prior version.
recipeList:
  - org.openrewrite.java.spring.framework.UpgradeSpringFrameworkDependencies:
      newVersion: 5.3.x
  - org.openrewrite.java.spring.framework.UseObjectUtilsIsEmpty
  - org.openrewrite.java.spring.framework.MigrateInstantiationAwareBeanPostProcessorAdapter
  - org.openrewrite.java.spring.framework.JdbcTemplateObjectArrayArgToVarArgs
  - org.openrewrite.maven.UpgradeDependencyVersion:
      groupId: org.hibernate
      artifactId: hibernate-search-orm
      newVersion: 5.11.x
      overrideManagedVersion: true
  - org.openrewrite.maven.RemoveDependency:
      groupId: org.aspectj
      artifactId: aspectjrt
  - org.openrewrite.maven.RemoveDependency:
      groupId: org.aspectj
      artifactId: aspectjweaver
  - org.openrewrite.maven.RemoveDependency:
      groupId: aopalliance
      artifactId: aopalliance
  - org.openrewrite.maven.RemoveDependency:
      groupId: cglib
      artifactId: cglib

```
{% endtab %}
{% endtabs %}
