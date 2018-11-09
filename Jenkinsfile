pipeline {
  agent any
  stages {
    stage('fetch') {
      steps {
        git(url: 'https://github.com/hzhaosh/simple-java-maven-app', branch: 'master')
      }
    }
    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage('publish') {
      steps {
        sh '''cp target/*.jar /home/tomcat/demo
java -jar /home/tomcat/demo/my-app-1.0-SNAPSHOT.jar

'''
      }
    }
  }
}