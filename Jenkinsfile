  node {
      stage('Register Build Artifact') {
          script {
              env.CBP_ARTIFACT_ID = registerBuildArtifactMetadata(
                  name: "my-artifact",
                  url: "https://example.com",
                  version: "1.0.0.${BUILD_NUMBER}",
                  componentId: "fffd876f-1cac-4d03-ba2f-ab813ad583d6"
              )
              echo "Registered artifact: ${env.CBP_ARTIFACT_ID}"
          }
      }

      stage('Deploy') {
          script {
              sleep 5
              registerDeployedArtifactMetadata(
                  id: env.CBP_ARTIFACT_ID,
                  targetEnvironment: "GregsSuborgEnv"
              )
              echo "Deploying"
              if (Math.random() < 0.5) {
                  error "Deployment failed"
              }
              echo "Deployment succeeded"
          }
      }
  }
