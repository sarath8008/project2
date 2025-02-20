pipeline {
    agent { label 'slave3' }
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
                sh "scp target/*.war root@172.31.29.198:/opt/apache-tomcat-11.0.3/webapps/"
            }
        }
    }
}
