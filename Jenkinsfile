pipeline {
    agent none
    stages {
        stage('Build & Deploy') {
            agent {
                docker {
                    image 'maven:3-alpine'
                    args '-v $HOME/.m2:/root/.m2'
                }
            }
            steps {
                /* withMaven(options: [artifactsPublisher(disabled: true)]){
                    sh 'mvn test surefire-report:report'
                 }*/
                
                echo "DELOY "
                 withMaven(mavenSettingsConfig: 'my-maven-settings'){
                    sh 'mvn deploy -Dmaven.test.skip=true'
                 }
            }
        }
        
    }
}
