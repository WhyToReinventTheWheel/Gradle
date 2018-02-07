# Gradle

gradle build

java -cp build\classes\java\main\ com.pluralsight.Hello


apply plugin: 'java'

task wrapper(type: Wrapper) {
    gradleVersion = '2.6'
}

gradlew build