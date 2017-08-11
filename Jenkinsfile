node('maven') {
    stage 'build'
    openshiftBuild(buildConfig: 'demo')
    stage 'test'
    stage 'deploy'
}