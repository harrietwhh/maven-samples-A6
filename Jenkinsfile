pipeline {
  agent any
  tools { 
      maven 'maven_3.9.9' 
      jdk 'JavaVirtualMachines_zulu8' 
  }
  stages {
    stage('Find Buggy Commit') {
      steps {
        script {
          sh 'git bisect start 198644632661c67b6c32f59e9047c11a70685e15 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5'
          sh 'git bisect run mvn clean test'
        }  
      }
    }
  }
}
