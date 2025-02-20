pipeline {
    agent { label 'slave2' }
    stages {
        stage('checkout') {
            steps {
                sh "rm -rf project2"
                sh "git clone https://github.com/sarath8008/project2.git"
            }
        }
         stage('build') {
            steps {
                sh "cd project2"
                sh "mvn clean package" 
            }
        }
        stage('deploy') {
            steps {
                sh "sudo cp target/*.war /opt/apache-tomcat-10.1.35/webapps/"
            }
        }
    }
}
