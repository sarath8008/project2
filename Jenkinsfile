pipeline {
    agent { label 'slave1' }
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
                sh "cp target/*.war /opt/apache-tomcat-11.0.3/webapps/"
            }
        }
    }
}
