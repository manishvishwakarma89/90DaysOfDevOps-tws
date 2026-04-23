### Task 1: What is Docker?
Docker is an open source containerization platform that allows you to package any application along with dependencies (libraries, environment, configs, runtime) into a container so it runs consistently across environments (dev, test, production).
Simple words: build app; run anywhere
A container is a lightweight, standalone unit that includes:
- Application code
- Runtime (e.g., Python, Node)
- Libraries & dependencies
  It runs on top of the host OS but stays isolated from other containers.
Why do we need containers?
Before containers:

“It works on my machine” problem 
Dependency conflicts
Difficult deployments

- We need for consistency, fast deployment, lightweight, easly scaling

Q. Containers vs Virtual Machines — what's the real difference?
COntainers vs Virtual can be differntiate for the following features are:

Virtual Containers- Works on OS-Level doesn't use hardware  whereas Virtual machines works on Hardware and software.
Size: Containers size is in MB whereas VM size is in GB
Time: Container starts time is fast in seconds whereas VM starting time is in Minutes.
Resources: Resource usuage take less whereas VM takes much time.
Application Uses: COntainer used for micro-services app but VMs used as a legacy application with running different OS (Linux, Window OS etc)

Q. What is the Docker architecture? (daemon, client, images, containers, registry)
 Docker uses a client–server architecture to build, manage, and run containers.
<img width="1536" height="1024" alt="ChatGPT Image Apr 23, 2026, 04_11_01 PM" src="https://github.com/user-attachments/assets/1bcf4c7a-8905-4969-9083-6739cc8ee620" />
 
  Docker Core Components are:
  1. Docker Client
       The tool you interact with (CLI/API)
        Example commands:
        - docker build
        - docker pull
        - docker run
            Sends requests to the Docker Daemon
  2. Docker Daemon (dockerd)
   - The main engine running in the background
    It is Responsible for building images, running containers, managing volumes & netowks
  3. Docker Images:
     Its blueprint tempalte of container
     contains application-code, runtime, install dependencies & libraries
  4. Docker Containers
  Docker container has follwing lifecycle
  - start
  - stop
  - Delete
  Docker container is running instance of images, and its lightweight and isolated.
 5. Docker Registry
    It contains running container both on public and private network
    - storing images for locally or docker hub as public repo
    1. Developer runs a command (docker run nginx)
    2. Docker Client sends request to Docker Daemon
    3. Daemon checks local system for image
    4. If not found → pulls image from Registry
    5. Daemon creates and starts Container
    6. Application runs inside container
<hr>
### Task 2: Install Docker
1. Install Docker on your machine (or use a cloud instance)
I install Ubuntu server
command for installing docker:
sudo apt update -y
sudo apt install -y docker.io
- Start and enable Docker:
sudo systemctl start docker
sudo systemctl enable docker
Run Docker without sudo:
sudo usermod -aG docker $USER docker
Log out and log back in after this

2. Step 2: Verify Installation
docker --version
Expected output:
Docker version XX.X.X
docker info
Step 3: Run Hello World Container
docker run hell-world
Step 4: Understand the Output
What actually happens behind the scenes:
1. Client → Daemon
  - Your command goes from Docker Client → Docker Daemon
2. Check for Image Locally
  Docker looks for hello-world image on your system
    Not found (first time)
3. Pull from Registry
    - Docker pulls the image from Docker Hub
4. Create Container
  Docker creates a container from the image
5. Run the Container
  - The container runs and prints a message


