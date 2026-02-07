# dev-docker-compose-files

Collection of Docker Compose files for development environments.

## Usage

Navigate to each project directory and use the following commands.

### Starting Containers

```bash
# Navigate to the project directory
cd <project-name>

# Start the dev service in the background
docker compose up -d dev
```

### Accessing Containers

```bash
# Access the running container with bash
docker compose exec dev bash
```

### Stopping and Removing Containers

```bash
# Stop the container
docker compose stop dev

# Stop and remove the container
docker compose down
```

## Project List

### nuplan_devkit-base
NuPlan DevKit base development environment

```bash
cd nuplan_devkit-base
docker compose up -d dev
docker compose exec dev bash
```

### nuplan_devkit-diffusion-planner
NuPlan DevKit Diffusion Planner development environment

```bash
cd nuplan_devkit-diffusion-planner
docker compose up -d dev
docker compose exec dev bash
```

### ros_noetic-carmaker
ROS Noetic + CarMaker development environment

```bash
cd ros_noetic-carmaker
docker compose up -d dev
docker compose exec dev bash
```

### ros2_humble-gazebo-sim
ROS2 Humble + Gazebo simulation environment

```bash
cd ros2_humble-gazebo-sim
docker compose up -d dev
docker compose exec dev bash
```

## Environment Variables

Each project directory contains a `.env` file. Configure environment variables as needed.

Key environment variables:
- `DEV_IMAGE`: Docker image to use
- `DOCKER_MOUNTED_ROOT`: Root directory to mount
- `NUPLAN_DATASET`: NuPlan dataset path (for relevant projects)
- `DISPLAY`: X11 display settings

## Notes

- All containers run in `privileged` mode and use NVIDIA GPU.
- `/tmp/.X11-unix` is mounted for X11 forwarding.
- Network mode is set to `host`.
