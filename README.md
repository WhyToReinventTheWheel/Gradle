# Gradle

gradle build

java -cp build\classes\java\main\ com.pluralsight.Hello


apply plugin: 'java'

task wrapper(type: Wrapper) {
    gradleVersion = '2.6'
}

gradlew build


# Task
	- lifecycle
	- properties
	- actions
	- dependencies
	
gradle is groovy, means jvm and have top level object = project

project.task("Task1")
task("Task2")
task "Task3"
task Task4
gradle tasks // list all task




##############################


ext.projectVersion = "3.0"

project.task("Task1")

task("Task2")

task "Task3"

task Task4

Task4.description = "Task 4 Description"

Task4.doLast {println "This is Task 4"}

Task3 << {println "This is task 3"}

task Task5 << {println "this is task 5"}

Task5 << {println "Another closure"}

task Task6 {
  description "This is task 6"
  dependsOn Task5
  doFirst {
    println "Task 6 - First"
  }
  doLast {
    println "This is task 6 - version $projectVersion"
  }
}

Task6.doFirst {
  println "Another first"
}

Task6.dependsOn Task3
Task5.dependsOn Task4


##################