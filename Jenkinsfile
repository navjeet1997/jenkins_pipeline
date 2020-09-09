pipeline {
    agent any
    stages {
        stage('Test'){
            steps {
                sh '''python3 -m venv myenv
                 source myenv/bin/activate
                 pip3 install requests
                 python3 main.py'''
                
            }
        }
    }
    post {
        always {
          xunit(
              //thresholds: [ skipped(failureThreshold: '0'), failed(failureThreshold: '0') ],
              tools : [Custom(pattern: 'data.xml', customXSL: 'input.xsl')]
              )
        }
      }  
 }
