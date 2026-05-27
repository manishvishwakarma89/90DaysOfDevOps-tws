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

    ![image](images/task2.1.png)

2. Run the same database container, but this time **attach the volume** to it

    ![image](images/task2.2.png)

3. Add some data, stop and remove the container

    ![image](images/task2.3.png)

    ![image](images/task2.3.2.png)

4. Run a brand new container with the **same volume**

    ![image](images/task2.4.png)
5. Is the data still there?
    - Yes,all previous data ,tables and rows are still there.

    Verify: `docker volume ls`, `docker volume inspect`

    ![image](images/task2verify.png)

---



---
