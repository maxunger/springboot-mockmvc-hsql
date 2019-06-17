pipeline {
    agent { label 'docker1' }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'docker run --rm --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.3-jdk-8 mvn --version'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'docker run --rm --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.3-jdk-8 mvn clean test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}