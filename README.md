****Jenkins global shared library****

This project will guide us how to create a shared gloabl library

Configure Jenkins using above project..

Steps to configure shared library

** Manage Jenkins -->  Configure System --> Global shared Pipeline


Configure Library 

Name should be as your shared library name
Default version can be branch,commit sha,Git Tag etc .. example master..
Check Modern SCM Option..

Click on Git 
Add Git Url and Credentials

Our Jenkins shared pipeline set up is ready..


now use the following pipeline to run shared library


********************************************************************************

@Library('cicd_sample')_

stage('checkout') {
    Checkout()
}
stage('Build') { 
   Build()
} 
stage('SonarAnalysis'){
    SonarAnalysis()
}
stage('CreateArtifact') {
    CreateArtifact()
}
stage('SMSNotification'){
    SMSNotification()
}
stage('UploadArtifact'){
    UploadArtifact()
}

***********************************************************************************

------------Just Run Jenkins Job-------------