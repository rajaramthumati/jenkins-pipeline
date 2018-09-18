pipeline {
    agent any
    tools {
        maven "maven354"
    }
    stages {
        stage("echo") {
            steps {
               
                    sh "echo hi"
              
            }
           
        }
        stage("git clone") {
            steps {
                git branch: 'master',
    credentialsId: '',
    url: 'https://github.com/rajaramthumati/di-demo.git'
            }
        }
        stage("maven build") {
            steps {
                sh "mvn clean install"
            }
        }
        stage("invoke ansible script") {
            steps {
                sh "ansible-playbook -vvvv /tmp/test.yml"
            }
            
        }
    }
}
