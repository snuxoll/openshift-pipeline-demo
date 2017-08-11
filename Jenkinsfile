node('maven') {
    def mvnCmd = "mvn"

    stage('build') {
        checkout scm
        sh "${mvnCmd} -B clean install -DskipTests=true"
    }
    stage('test') {
        sh "${mvnCmd} test"
    }
    stage('image') {
        openshiftBuild(buildConfig: 'demo')
    }
    stage('deploy') {
        input message: 'Deploy to production?', ok: 'Deploy'
    }
}