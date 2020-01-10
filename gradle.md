# Gradle

## How to customize JUnit reports

``build.gradle.kts
tasks {
  test {
    useJUnitPlatform()
    reports {
      junitXml.isEnabled = true
      junitXml.destination = file("target/junitreports/")
      html.isEnabled = false
    }
  }
}
```
