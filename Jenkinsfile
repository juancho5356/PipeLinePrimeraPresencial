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
                    // Aquí puedes añadir comandos para instalar dependencias
                    sh 'pip install -r requirements.txt' // Ejemplo
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo 'Ejecutando pruebas...'
                    // Añade aquí los comandos para ejecutar pruebas
                    sh 'pytest' // Ejemplo si usas pytest
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo 'Levantando contenedor de base de datos...'
                    // Aquí no necesitas usar docker run; podrías usar un contenedor en el contexto de Jenkins.
                    sh 'docker run -d --name mydb -e MYSQL_ROOT_PASSWORD=root mysql:latest'
                    echo 'Contenedor de base de datos levantado.'
                }
            }
        }
    }
}

