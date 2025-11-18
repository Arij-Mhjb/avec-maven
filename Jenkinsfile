pipeline {
    agent any

    stages {
        stage('Hello World') {
            steps {
                echo 'Hello World !'
            }
        }

        stage('Checkout Git') {
            steps {
                git(
                    url: 'https://github.com/Arij-Mhjb/avec-maven.git', 
                    branch: 'main',
                    credentialsId: 'github-token' // si le repo est privé
                )
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Build réussi !'
        }
        failure {
            echo 'Le build a échoué.'
        }
    }
}
