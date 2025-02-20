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

        stage('Deploy') {
            steps {
                sh "sudo cp target/*.war /opt/apache-tomcat-10.1.35/webapps/"
            }
        }
    }
}
