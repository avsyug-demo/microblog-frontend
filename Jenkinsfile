  pipeline {
      agent any
      stages {
          stage('Register build artifact') {
              steps {
                  script {
                      env.CBP_ARTIFACT_ID = registerBuildArtifactMetadata(
                          name: "my-artifact",
                          version: "1.0.0.${BUILD_NUMBER}",
                          type: "docker",
                          url: "https://example.com",
                          componentId: "fffd876f-1cac-4d03-ba2f-ab813ad583d6",
                          digest: "abc123",
                          label: "latest"
                      )
                  }
              }
          }
          stage('Register deployed artifact') {
              steps {
                  registerDeployedArtifactMetadata(
                      artifactId: env.CBP_ARTIFACT_ID,
                      targetEnvironment: "GregsSuborgEnv",
                      labels: "latest"
                  )
              }
          }
      }
  }
