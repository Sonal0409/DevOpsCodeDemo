pipeline {
    
    tools{
        maven 'mymaven'
    }
    agent any
    stages {
        stage('Clone a repository'){
            steps {
                git 'https://github.com/srinivas0902/DevOpsCodeDemo.git'
            }
        }
        stage('Compile'){
            steps {
                sh 'mvn compile'
            }
        }
        
        stage('Code Review'){
            steps {
                sh 'mvn pmd:pmd'
            }
        }
        stage ('Unit Test'){
            steps {
                sh 'mvn test'
            }
        }
        stage ('Build code'){
            steps {
                sh 'mvn package'
            }
        }
    }
}
