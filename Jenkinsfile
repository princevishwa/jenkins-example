pipeline {
    notify('started')
    agent any
  
    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    bat 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    bat 'mvn deploy'
                }
            }
        }
    }
    
    def notify(status){
    emailext(
       to: "manee2k6@gmail.com",
        subject: "${status}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
        body: """<p> ${status}: Job '${env.JOBE_NAME} [${env.BUILD_NUMBER}]':</p>
           <p>Check console Output at <a href ='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a></p>
    )    
    
    }
}
