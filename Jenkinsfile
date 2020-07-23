pipeline {
    agent any

    stages {
        
        stage('Hello') {
            steps {
                git 'https://github.com/SalmanIsha/test-project.git'
                sh label: '', script: 'pwd'
                sh label: '', script: 'mvn clean package'
            }
        }
        stage('deploy') {
            steps {
                sh label: '', script: 'ansible-playbook deployment.yml -i stage'
            }
        }
        
    }
    post {
        always {
            archiveArtifacts artifacts: 'webapp/target/webapp.war', fingerprint: true
            
        }
    }
}
