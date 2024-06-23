---
title: "Publish to Maven Central"
date: 2018-07-18T20:09:30+02:00
draft: true
params:
    author: Christoph
---

We already publish [openfasttrace](https://github.com/itsallcode/openfasttrace/) to [JCenter](https://bintray.com/bintray/jcenter), see [openfasttrace distribution](https://bintray.com/itsallcode/itsallcode/openfasttrace). Using libraries from JCenter in a Gradle build only requires adding `repositories { jcenter() }` to your `build.gradle`.

You can do the same with maven by adding the following to your `pom.xml`:

```xml
<repositories>
  <repository>
    <id>central</id>
    <name>bintray</name>
    <url>http://jcenter.bintray.com</url>
  </repository>
</repositories>
```

But we want to make it even easier for maven users by publishing our artifacts to the [Maven Central repository](https://search.maven.org/) which maven uses by default.

The easiest way to publish to Maven Central is [synchronization via bintray](https://blog.bintray.com/2014/02/11/bintray-as-pain-free-gateway-to-maven-central/). The setup process is not trivial, so I want to share my experience.

1. [Apply for a repository](https://central.sonatype.org/pages/ossrh-guide.html) for your organisation (in our case: `org.itsallcode`)
2. Optionally generate a gpg key **without password** and upload it to bintray. As an alternative you can also use bintray’s key.
3. Configure your bintray maven repository to [automatically sign uploaded files](https://www.jfrog.com/confluence/display/BT/Managing+Uploaded+Content#ManagingUploadedContent-GPGSigning)
4. Make sure your project conforms to Maven Central’s quality requirements:
    1. Your `pom.xml` must contain information about the project license and developers (elements `<licenses>` and `<developers>`)
    2. Publish the source code by adding this to your `pom.xml`:
        ```xml
        <plugin>
          <groupId>org.apache.maven.plugins</groupId>
          <artifactId>maven-source-plugin</artifactId>
          <version>3.0.1</version>
          <executions>
            <execution>
              <id>attach-sources</id>
              <goals>
                <goal>jar</goal>
              </goals>
            </execution>
          </executions>
        </plugin>
        ```
    3. Publish javadoc by adding this to `pom.xml`:
        ```xml
        <plugin>
          <groupId>org.apache.maven.plugins</groupId>
          <artifactId>maven-javadoc-plugin</artifactId>
          <version>3.0.1</version>
          <executions>
            <execution>
              <id>attach-javadocs</id>
              <goals>
                <goal>jar</goal>
              </goals>
            </execution>
          </executions>
        </plugin>
        ```
5. Now you can publish your artifacts to JCenter as usual via mvn deploy. Don’t forget to increment your version number in `pom.xml`.
6. The last step is to synchronize the artifacts by clicking the “Sync” button in the “Maven Central” tab in bintray. If everything was OK after some time you should see the message “Successfully synced and closed repo”.

Then it will take some time (in my case around 40 minutes) until your packages are shown in [Maven Central](https://repo1.maven.org/maven2/org/itsallcode/openfasttrace/) and you can search for it. And then it will take up to two hours until you can [find](https://search.maven.org/#search%7Cga%7C1%7Copenfasttrace) them at [search.maven.org](https://search.maven.org/).