### Task 1: Your First Dockerfile
1. Create a folder called `my-first-image`
2. Inside it, create a `Dockerfile` that:
   - Uses `ubuntu` as the base image
   - Installs `curl`
   - Sets a default command to print `"Hello from my custom image!"`
3. Build the image and tag it `my-ubuntu:v1`
<img width="945" height="423" alt="task-1" src="https://github.com/user-attachments/assets/f646535e-4c8e-408f-ad83-875075bd54fe" />


4. Run a container from your image

  <img width="649" height="83" alt="t2" src="https://github.com/user-attachments/assets/d6e31245-adca-4414-9f77-e48505e3c2e7" />

**Verify:** The message prints on `docker run`

---

### Task 2: Dockerfile Instructions

- `FROM` `python:3.12-alpine`
Uses lightweight Python image based on Alpine Linux.

- `WORKDIR` `/app`
Sets /app as working directory inside container.

- `COPY . .`
Copies everything from your my-first-image folder into /app inside container.

- `RUN` `pip install -r requirements.txt`
Installs all Python dependencies.

- `EXPOSE 5000`
Documents that container uses port 5000.

- `CMD ["python","app.py"]`
Runs Python app when container starts.

![image](images/task2.2.png)



---  
