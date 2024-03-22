# Create Docker Image

docker build -t k8ssample-image -f DockerFile .

# Create Container

docker create --name core-k8ssample k8ssample-image

# Run Container App

docker run --rm -p 4040:4040 k8ssample-image
