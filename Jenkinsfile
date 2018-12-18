pipeline {
    agent any
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    stages {
        stage('Build') {
            steps {
                echo 'Build'
            }
        }
        stage('Deploy to Test') {
            steps {
                echo 'Deploy to Test'
            }
        }
        stage('Smoke Test') {
            steps {
                echo 'Smoke Test'
            }
        }
        stage('Integration Test') {
            steps {
                echo 'Integration Test'
                error 'Failed test!'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Production'
            }
        }
        stage('Production Smoke Tests') {
            steps {
                echo 'Production Smoke Tests'
            }
        }
    }
    post {
        failure {
        		script {
	            	def ticket = IncidentTicket shortDescription:'Build failed!',callerId:'Beth Anglin',impact:'3 - Low',urgency:'3 - Low'
		    		def requestId = createIncidentTicket incidentTicket: ticket
		    	}
        }

    }

}