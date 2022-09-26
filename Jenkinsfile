// script { 
//     System.setProperty("org.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL", "86400"); 
// }
// pipeline {
//     // agent { dockerfile true }
//     agent {
//         docker {
//             image 'maven:3.5.4-alpine'
//             // args '-v /root/.m2:/root/.m2'
//             // args '-v $HOåME/.m2:/root/.m2'
//             args '-v /tmp/jenkins/.m2:/root/.m2'
//         }
//     }
//     stages {
//         stage('Build') {
//             steps {
//                 sh 'mvn -v  && sleep 3'
//                 // sh 'env'
//                 // sh 'mvn -B -DskipTests clean package'
//             }
//         }
//         stage('Test') {
//             steps {
//                 sh 'mvn test'
//             }
//             post {
//                 always {
//                     junit 'target/surefire-reports/*.xml'
//                 }
//             }
//         }
//         stage('Deliver') {
//             steps {
//                 sh './jenkins/scripts/deliver.sh'
//             }
//         }
//     }
// }


// pipeline {
//     agent {
//         docker {
//             image 'maven:3.5.4-alpine'
//             // args '-v /root/.m2:/root/.m2'
//             // args '-v $HOåME/.m2:/root/.m2'
//             args '-v /tmp/jenkins/.m2:/root/.m2'
//         }
//     }
//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building..'
//                 sh 'mvn -v  && sleep 3'
//             }
//         }
//         stage('Test') {
//             steps {
//                 echo 'Testing..'
//             }
//         }
//         stage('Deploy') {
//             steps {
//                 echo 'Deploying....'
//             }
//         }
//     }
// }

pipeline {
    agent {
        docker { image 'node:7-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}