pipeline{
    agent any
    stages{
        stage("Build ECS Docker images"){
            steps{
                def ecs_services = sh(returnStdout: true, script: 'ls artifacts/ecs')
                echo $ecs_services
            }
        }
    }
}