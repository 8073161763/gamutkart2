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
//				sh 'cp target/gamutkart.war /opt/apache-tomcat-8.5.38/webapps'
//				sh '"JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64" "/opt/apache-tomcat-8.5.38/bin/startup.sh"'
	    	}
		}
    }
}
