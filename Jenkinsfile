pipeline {
agent any
stages {
stage('unit Tests') {
steps {
sh 'ant -f build.xml -v'
}
}
steps {
sh 'ant -f test.xml -v'
junit 'reports/result.xml'
}
}
}
post {
always {
archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
}
}
}
