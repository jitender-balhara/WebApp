
/*node {
    // Get Artifactory server instance, defined in the Artifactory Plugin administration page.
    //def server = Artifactory.server "artifactory"
    // Create an Artifactory Maven instance.
    //def rtMaven = Artifactory.newMavenBuild()
    //def buildInfo
    
 //rtMaven.tool = "maven"

    stage('Clone sources') {
        git url: 'https://github.com/jitender-balhara/webapp.git'
    }

    stage('Compile Code') {
        // Tool name from Jenkins configuration
        //rtMaven.tool = "maven"
        // Set Artifactory repositories for dependencies resolution and artifacts deployment.
        //rtMaven.deployer releaseRepo:'libs-release-local', snapshotRepo:'libs-snapshot-local', server: server
        //rtMaven.resolver releaseRepo:'libs-release', snapshotRepo:'libs-snapshot', server: server
	    build 'compile-web-app'
    }

    stage('Deploy to QA') {
        //buildInfo = rtMaven.run pom: 'pom.xml', goals: 'clean install'
	    build 'deploy-to-qa'
    }

    }
    }
    */
pipeline {				//indicate the job is written in Declarative Pipeline 
	agent any
    stages {
        stage ("Compile Web App") 
        {		//an arbitrary stage name
            steps 
            {
                build 'compile-web-app'	//this is where we specify which job to invoke.
            }
            
        }
        stage ("Deploy To QA") 
        {		//an arbitrary stage name
        steps 
            {
                build 'deploy-to-qa'	//this is where we specify which job to invoke.
            }
        }
        stage ("Functional Testing") 
        {		//an arbitrary stage name
        steps 
            {
                build 'functional-testing'	//this is where we specify which job to invoke.
            }
        }
        stage ("Performance Testing") 
        {		//an arbitrary stage name
        steps 
            {
                build 'performance-testing'	//this is where we specify which job to invoke.
            }
        }
        stage ("Deployment to Production") 
        {		//an arbitrary stage name
        steps 
            {
                build  'deploy-to-prod'	//this is where we specify which job to invoke.
            }
        }
        stage ("Production Sanity Testing") 
        {		//an arbitrary stage name
        steps 
            {
                build  'Sanity-test-prod'	//this is where we specify which job to invoke.
            }
        }
    }
}
