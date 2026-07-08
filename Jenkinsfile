def cbpArtifactId = registerBuildArtifactMetadata(
    name: "my-artifact",
    url: "https://example.com",
    version: "1.0.0.${BUILD_NUMBER}",
    componentId: "fffd876f-1cac-4d03-ba2f-ab813ad583d6"
)
echo "Registered artifact: $cbpArtifactId"
sleep 5
registerDeployedArtifactMetadata(
    artifactId: "$cbpArtifactId",
    targetEnvironment: "prod"
)
echo "Deploying"
if (Math.random() < 0.5) {
  error "Deployment failed"
}
echo "Deployment succeeded"
