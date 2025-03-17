pipeline {
    agent any  // Usa cualquier máquina disponible en Jenkins

    stages {
        stage('Clonar Repositorio') {
            steps {
                git 'https://github.com/kevinqm020/clase-jenkins.git'
            }
        }

        stage('Instalar Dependencias') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Entrenar Modelo') {
            steps {
                sh 'python main.py train'
            }
        }

        stage('Desplegar API') {
            steps {
                sh 'uvicorn main:app --host 0.0.0.0 --port 8000 &'
            }
        }
    }
}