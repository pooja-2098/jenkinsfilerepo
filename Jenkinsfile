pipeline{
    tools{
        jdk "myjava"
        maven "mymaven"
    }
    agent any
    stages{
        stage('clone repository')
        {
            steps{
                git 'https://github.com/pooja-2098/DevOpsCodeDemo.git'
            }
        }
        stage('compile')
        {
            steps{
                  sh 'mvn compile'
            }
        }
         stage('Unit Test')
        {
            steps
            {
            sh 'mvn test'
            }
            post{
                 success{
                      junit 'target/surefire-reports/*.xml'
                 }
            }
        }
        stage('Code Review')
        {
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage('Package')
        {
        steps{
            sh 'mvn package'
        }
        }
        
    }
}
