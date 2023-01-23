pipeline{
    agent any
    stages{
        stage("Build ECS Docker images"){
            steps{
                script {
                  def ecs_services = sh(returnStdout: true, script: 'ls -d artifacts/ecs').trim()
                  println ecs_services
                  ecs_services.tokenize().each { service ->
                    sh "ls service"
                  }
                }
            }
        }
    }
}