pipeline {
    agent { 
        node {
            label 'kcs-jenkins-agent'
        }
    }
    triggers {
        pollSCM 'H/5 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                sudo apt install -y python3-fire
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                |
                cd myapp
		python3 hello.py
		python3 hello.py --name=Sreedhar
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
