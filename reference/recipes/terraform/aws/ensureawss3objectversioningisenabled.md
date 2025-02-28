# Ensure AWS S3 object versioning is enabled

** org.openrewrite.terraform.aws.EnsureAWSS3ObjectVersioningIsEnabled**
_Ensure AWS S3 object versioning is enabled._

### Tags

* CKV_AWS_21
* terraform
* AWS

## Source

[Github](https://github.com/openrewrite/rewrite-terraform), [Issue Tracker](https://github.com/openrewrite/rewrite-terraform/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-terraform/1.9.1/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-terraform
* version: 1.9.1


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-terraform:1.9.1 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.27.0")
}

rewrite {
    activeRecipe("org.openrewrite.terraform.aws.EnsureAWSS3ObjectVersioningIsEnabled")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-terraform:1.9.1")
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
            <recipe>org.openrewrite.terraform.aws.EnsureAWSS3ObjectVersioningIsEnabled</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-terraform</artifactId>
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

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.terraform.aws.EnsureAWSS3ObjectVersioningIsEnabled`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Add Terraform configuration](../../terraform/addconfiguration.md)
  * resourceName: `aws_s3_bucket`
  * content: `versioning {
  enabled = true
}`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.terraform.aws.EnsureAWSS3ObjectVersioningIsEnabled
displayName: Ensure AWS S3 object versioning is enabled
description: Ensure AWS S3 object versioning is enabled.
tags:
  - CKV_AWS_21
  - terraform
  - AWS
recipeList:
  - org.openrewrite.terraform.AddConfiguration:
      resourceName: aws_s3_bucket
      content: versioning {
  enabled = true
}

```
{% endtab %}
{% endtabs %}
