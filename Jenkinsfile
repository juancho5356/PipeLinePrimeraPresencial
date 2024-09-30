pipeline {
    agent any
   
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Construyendo...'
                    // Aquí puedes añadir comandos para instalar dependencias
                    sh 'apt install pip'
                    sh 'pip install -r requirements.txt' // Ejemplo
                    sh 'pip install pytest'
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

