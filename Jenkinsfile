//omments
pipeline { 
    agent any
    tools {
        maven 'maven' 
    }  
    
    stages {
        stage('clone') {
            steps {
                git  branch: "main", url: 'https://github.com/Raghusadhu/Employe.git'
                sh 'echo hello1'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('code_review') {
            steps {
                sh 'mvn -P metrics pmd:pmd'
            }
        }
        stage('unit_test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('package') {
            steps{
                sh 'mvn package'
            }
        }
    }
}
