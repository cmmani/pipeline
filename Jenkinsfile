pipeline {
agent any
stages {
   stage('build') {
         steps { 
            sh 'ant -f build.xml -v'
              }	
          }
   stage('unit Tests') {
         steps {
            sh 'ant -f test.xml -v'
            junit 'reports/result.xml'
               }
          }
    stage('deployment') {
         steps {
            sh "cp dist/rectangle_${env.BUILD_NUMBER}.jar /var/www/html/rectangles/all/"
               }
          }
    }
    post {
     always {
         archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
            }
         }
    }
