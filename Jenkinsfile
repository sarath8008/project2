@Library('java_demo_pipeline@main') _
pipeline {
    agent { label 'slave2' }

    parameters {
        string(name: 'command1', description: 'Give build the command')
        choice(choices: ['package', 'compile', 'install'], name: 'command2')
    }

    stages {
        stage('Checkout') {             
            steps {
               // sh "rm -rf hello-world-war"
               // sh "git clone https://github.com/Dev86-git/hello-world-war.git"
                checkoutcode()
            }
        }

        stage('Build') {
            steps {
               // sh "cd hello-world-war"
                // sh "mvn clean package"
                buildproject()
                        }
        }
stage('download') {
            steps {             
            
withCredentials([string(credentialsId: 'jfrog-token', variable: 'JFROG_API_TOKEN')]) {
                        sh '''
                        curl -L -u  "saratkumarpaluri@gmail.com:\${JFROG_API_TOKEN}" -o "sarath kumar-1.0.0.war" "https://trial3e0k8c.jfrog.io/artifactory/hello-world-war-libs-release/com/efsavage/hello-world-war/3.1.1/hello-world-war-3.1.1.war"
                        '''
}
            }
        }
        stage('Deploy') {
            steps {
                sh "sudo cp target/*.war /opt/apache-tomcat-10.1.35/webapps/"
            }
        }
    }
}
