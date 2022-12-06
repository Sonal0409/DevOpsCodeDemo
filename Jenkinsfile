pipeline{
 
    tools{
        maven 'mymaven'
    }
    agent any
    stages
    {
        stage('Clone A Repo')
        {
            steps{
                git 'https://github.com/Sonal0409/DevOpsClassCodes.git'
            }
        }
        stage('Compile the Code')
        {
            steps{
                sh 'mvn compile'
            }
        }
        stage('Code Review')
        {
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage('Unit Test')
        {
            steps{
                sh 'mvn test'
            }
        }
        post{
            success {
                junit 'target/surefire-reports/*.xml'
            }
        }
        stage('Package')
        {
            steps{
                sh 'mvn package'
            }
        }
        post{
            success {
                jacoco()
            }
        }
    } 
}
