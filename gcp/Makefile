# Define Variables
IMAGE_NAME := terraform-gcp:$(shell date +%s)
CONTAINER_NAME := terraform_container

# Default Target
.PHONY: all
all: build up

# Build Docker Image Dynamically
.PHONY: build
build:
	@echo "🚀 Building Docker Image: $(IMAGE_NAME)"
	docker build -t $(IMAGE_NAME) .

# Run Docker Compose with the Latest Image
.PHONY: up
up:
	@echo "🔥 Starting Docker Compose with Image: $(IMAGE_NAME)"
	IMAGE_NAME=$(IMAGE_NAME) docker-compose up --build -d

# Stop and Remove Containers
.PHONY: down
down:
	@echo "🛑 Stopping and Removing Docker Containers..."
	docker-compose down

# Clean Unused Docker Images
.PHONY: clean
clean:
	@echo "🧹 Cleaning up unused Docker images..."
	docker image prune -f
