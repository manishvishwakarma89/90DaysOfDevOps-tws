# Day 32 – Docker Volumes & Networking

## Challenge Tasks

### Task 1: The Problem
1. Run a Postgres or MySQL container
    
    ![image](images/task1.1.png)

2. Create some data inside it (a table, a few rows — anything)

    ![image](images/task1.2.png)

3. Stop and remove the container

    ![image](images/task1.3.png)

4. Run a new one — is your data still there?

    ![image](images/task1.4.png)

    - No, Data is lost when a container is removed because containers are ephemeral and do not persist data by default.

---

### Task 2: Named Volumes
1. Create a named volume

    ![image](images/task2.1.jpg)

2. Run the same database container, but this time **attach the volume** to it

   <img width="1280" height="800" alt="task2 2" src="https://github.com/user-attachments/assets/18a44c88-444d-4300-903c-531ab8769c2b" />


3. Add some data, stop and remove the container

<img width="2532" height="1177" alt="task2 3" src="https://github.com/user-attachments/assets/f46d5a04-a795-4138-92bc-c6455bbf20c5" />


4. Run a brand new container with the **same volume**

    ![image](images/task2.4.jpg)

5. Is the data still there?
    - Yes,all previous data ,tables and rows are still there.

    Verify: `docker volume ls`, `docker volume inspect`

    ![image](images/final.jpg)

---



---
