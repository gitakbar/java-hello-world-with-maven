node {
    def mvnHome //to declare variable 
    stage('scm') { 
        git 'https://github.com/gitakbar/JenkinsWar.git'
        mvnHome = tool 'm386'
    }
    stage('Build') {
                withEnv(["MVN_HOME=$mvnHome"]) {
            if (isUnix()) {
                sh '"$MVN_HOME/bin/mvn" clean install  package'
            } else {
                bat(/"%MVN_HOME%\bin\mvn" clean install package/)
            }
        }
    }
}
