pipeline{
    agent any
    stages{
        stage("Build ECS Docker images"){
            steps{
                script {
                  def ecs_services = sh(returnStdout: true, script: 'ls artifacts/ecs')
                  ecs_services.tokenize().each { service ->
                    dir ("artifacts/ecs/${service}") {
                      sh "cat Dockerfile"
                    }
                  }
                }
            }
        }
    }
}