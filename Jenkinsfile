pipeline {
    agent any
    tools { 
        maven 'Maven'  
    }

    stages {
        stage('SCM') {
            steps {
                echo 'Hello Clone staage'
                git credentialsId: '97919fd9-d38c-4bba-991f-b0ac60e42a8b', url: 'https://github.com/polarapu/Batch110.git'
                }
        }
        stage('Build') {
            steps {
                echo 'Hello Build'
                sh 'mvn clean install'
            }
        }
        stage('Dev-Deploy') {
            steps {
                echo 'Hello Docker Deploy'
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'deefa649-04e9-4b56-b227-c98536c42fc7', path: '', url: 'http://192.168.254.128:8081/')], contextPath: 'devops110.war', war: '**/*.war'
                  }
        }
}
}
