pipeline{
    agent any
    stages{
        stage("Build ECS Docker Images"){
            when {
              expression { GIT_BRANCH == "origin/main"}
              changeset "artifacts/ecs/**/*"
            }
            steps{
                script {
                  def ecs_services = sh(returnStdout: true, script: 'ls artifacts/ecs').trim()
                  ecs_services.tokenize().each { service ->
                    dir ("artifacts/ecs/${service}"){
                      sh "pwd"
                      sh "cat Dockerfile"
                    }
                  }
                }
            }
        }
    }
}