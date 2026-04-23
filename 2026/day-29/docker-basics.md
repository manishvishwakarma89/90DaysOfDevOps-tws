Task 1: What is Docker?
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
  Docker Core Components are:
  1. Docker Client
       The tool you interact with (CLI/API)
        Example commands:
        docker build
        docker pull
        docker run
            Sends requests to the Docker Daemon

