pipeline {
    agent any

	tools {
		maven 'Maven3.3.9'
	}
//
//	environment {
//		M2_INSTALL = "/usr/share/maven"
//	}

    stages {
		stage('Clone-Repo') {
			steps {
				checkout scm
			}
		}
		stage('Build') {
	    	steps {
				sh 'mvn install -DskipTests'
			}
	    }
		stage('Unit Tests') {
			steps {
				sh 'mvn surefire:test'
			}
		}
		stage('Deployment') {
	    	steps {
				print "Deployment is done!"
                                script{
				sh 'cp /root/.jenkins/workspace/pipeline-demo/target/gamutkart.war /opt/apache-tomcat-8.5.38/webapps'
				sh 'sh /opt/apache-tomcat-8.5.38/bin/shutdown.sh'
                                sh 'sh /opt/apache-tomcat-8.5.38/bin/startup.sh'
                                }
	    	}
		}
    }
}
