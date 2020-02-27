pipeline {
    agent {
        label "master"
	}
    stages {
        stage("Export Porject") {
            steps {
             echo '**** mvn Build****'
			}
        }
        stage("Zip Project") {
            steps {
                echo '**** mvn Build****'    
            }
        }
        stage("Publish to Nexus") {
            steps {
			  echo "*** nexusVersion*****"       
			}
		}
	}		
    post { 
		always { 
			echo '----------Sending Build Notification to CDD--------------'
		}
		success { 
			sendNotificationToCDD appName: 'AR-Server', 
					appVersion:  "${env.BRANCH_NAME}", 
					gitCommit: "${env.GIT_COMMIT}",
					gitPrevSuccessfulCommit: "${env.GIT_PREVIOUS_SUCCESSFUL_COMMIT}",
					overrideCDDConfig: [
							customApiKey: 'eyJhbGciOiJIUzUxMiJ9.eyJ1c2VybmFtZSI6ImFzc2FmLnNobG9taUBicm9hZGNvbS5jb20iLCJ0ZW5hbnRJZCI6IjAwMDAwMDAwLTAwMDAtMDAwMC0wMDAwLTAwMDAwMDAwMDAwMCIsInVzZXJJZCI6NCwianRpIjoiMWY3Zjk1ZDYtMGM0Yi00YzA3LThhZDQtZjQ0Zjc3MzgyYjk3IiwiZXhwIjoxNTkwNjA3NDI5fQ.2epCq8HIEvgGlo5azCW1_V1RSgfyhCx5q71VUBlt29yWdo7plLe9t1wfxIvVhaiv4Xo_gLrizMSbVyIe1rH-tg',
							customProxyPassword: '',
                            				customProxyUrl: '',
                           				customProxyUsername: '',
                            				customServerName: '35.185.100.184',
                            				customServerPort: 8080,
                            				customTenantId: '00000000-0000-0000-0000-000000000000',
                            				customUseSSL: false
                    			],
					releaseTokens: '{}'
		}
	}
}
