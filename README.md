
node {
    echo "The job name is ${env.JOB_NAME}"
    def mavenHome = tool name: 'maven3.9.5'
    stage('CheckOutCode') { 
        git 'https://github.com/ChandruMurugan100/maven-web-application.git'
    }
    stage('Build') {
        sh "${mavenHome}/bin/mvn clean package"
    }
}

