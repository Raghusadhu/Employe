// added comment new add
pipeline { 
    agent any
    tools {
        maven 'maven' 
    }  
    parameters {
    gitParameter branchFilter: 'origin/(.*)', defaultValue: 'main', name: 'BRANCH', type: 'main'
  }
    
    stages {
        stage('clone') {
            steps {
                git  branch "${params.BRANCH}", url: 'https://github.com/Raghusadhu/Employe.git'
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
