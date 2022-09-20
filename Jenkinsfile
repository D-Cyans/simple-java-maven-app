pipeline {
    script { 
        System.setProperty("org.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL", "86400"); 
    }
    agent {
        docker {
            image 'maven:3.5.3-alpine'
            // args '-v /root/.m2:/root/.m2'
            // args '-v $HOåME/.m2:/root/.m2'
            args '-v /tmp/jenkins/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
