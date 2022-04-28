# http4k-webgoat

http4k-webgoat is a deliberately-vulnerable application written with the `http4k` web framework.

## Build/test locally

```shell script
./gradlew test distZip
unzip build/distributions/Example.zip
Example/bin/Example
```

then:
```shell script
curl -v http://localhost:8080/
```

## Build/run in Docker

```shell script
./build_and_run.sh
```

then:
```shell script
curl -v http://localhost:8080/
```

## Vulnerabilities

The project contains the following vulnerabilities:

- Remote Code Execution
- Directory Traversal
- SQL Injection
- Open Redirect
- Sensitive Data Leak
- XSS

```
$ grep vulnerability . -R -n | grep -v README
./src/main/kotlin/com/example/HelloWorld.kt:50:                // vulnerability: Sensitive Data Leak
./src/main/kotlin/com/example/HelloWorld.kt:41:              // vulnerability: Remote Code Execution
./src/main/kotlin/com/example/HelloWorld.kt:60:            // vulnerability: Directory Traversal
./src/main/kotlin/com/example/HelloWorld.kt:69:                // vulnerability: SQL Injection
./src/main/kotlin/com/example/HelloWorld.kt:79:            // vulnerability: Open Redirect
./src/main/kotlin/com/example/HelloWorld.kt:113:                    // vulnerability: XSS
```

