pipeline {
    agent {
        docker {
            image 'python:3.9'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Construyendo...'
                    // Aquí puedes añadir comandos para instalar dependencias si es necesario
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo 'Ejecutando pruebas...'
                    // Añade aquí los comandos para ejecutar pruebas
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh 'docker run -d --name mydb -e MYSQL_ROOT_PASSWORD=root mysql:latest'
                    echo 'Contenedor levantado.'
                }
            }
        }
    }
}
