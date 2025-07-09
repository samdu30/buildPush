node {
   
   def PROJECT="quenec"
   def IMAGE="$PROJECT/form_jenkins:8.6"
   
    stage('Clone') {
          checkout scm
    }

    def img = stage('Build') {
          docker.build("$IMAGE",  '.')
          }

    stage('Run') {
          img.withRun("--name run-$BUILD_ID") { c ->
       
          }
    }

    stage('Push') {
       docker.withRegistry('https://registry.hub.docker.com/' , 'dockerhub_id') {
              img.push()
          }
    }
}
