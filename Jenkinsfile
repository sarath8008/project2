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
                sh "scp target/*.war root@172.31.16.119:/opt/apache-tomcat-10.1.34/webapps/"
            }
        }
    }
}
