@Library('techED-app') _
@Library('techED-landscape') __

node() {

  stage('prepare') {

      checkout scm

      setupCommonPipelineEnvironment script:this, customDefaults: 'landscape.yml'

      checkChangeInDevelopment script: this
  }

  stage('build') {
      mtaBuild script: this
  }

  stage('neoDeploy') {
      neoDeploy script: this
  }

  stage('solmanUpload') {
      transportRequestUploadFile script:this
  }
}
