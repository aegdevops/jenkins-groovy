pipeline{
    agent any
    stages{
        stage("Build ECS Docker images"){
            steps{
                script {
                  def ecs_services = sh(returnStdout: true, script: 'ls artifacts/ecs | cut -f 1 -d "."').trim()
                  println ecs_services
                  ecs_services.tokenize().each { service ->
                    sh "ls artifacts/ecs/${service}"
                  }
                }
            }
        }
    }
}