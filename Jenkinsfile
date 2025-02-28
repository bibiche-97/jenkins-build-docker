node{
    def app 
    
    stage('Clone repository'){
        checkout scm
    }
    stage('Build image'){
        app=docker.build("jenkins/nginx")
    }
    stage('Run image'){
        docker.image('jenkins/nginx').run('-p 80:80'){
            sh 'docker ps'
            sh 'sleep 10'
            sh 'curl http://localhost'
        }
    }
    stage('test'){
        sh 'echo "test stage success"'
    }
}