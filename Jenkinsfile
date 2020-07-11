/* import shared library */
@Library('jenkins-shared-library')_

pipeline {
    agent none
    stages {
        stage('Check css syntax') {
            agent { docker { image 'eeacms/csslint' } }
            steps {
                sh 'csslint  \${WORKSPACE}/battleboat/css/styles.css'
            }
        }
    }
    post {
    always {
       script {
         /* Use slackNotifier.groovy from shared library and provide current build result as parameter */
         clean
         slackNotifier currentBuild.result
     }
    }
    }
}
