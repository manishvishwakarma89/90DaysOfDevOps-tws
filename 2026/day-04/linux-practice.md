### Linux Practice: Processes and Services
1️⃣ Check Running Processes


<img width="903" height="188" alt="image" src="https://github.com/user-attachments/assets/d1563e02-4d82-4804-8cbd-559f5d6e92d7" /><br>

<img width="1251" height="281" alt="image" src="https://github.com/user-attachments/assets/70d8842e-da30-49d4-a7a1-bb8700b1e2df" /><br>
top command: 
<img width="1850" height="949" alt="image" src="https://github.com/user-attachments/assets/367322d6-0cf2-478e-aaf3-4b8e83521443" />

📊 System Health Checks (Quick Snapshot)
| Check Item           | Command Used   | What It Shows              | What to Look For                     |
| -------------------- | -------------- | -------------------------- | ------------------------------------ |
| CPU Usage            | `top` / `htop` | Real-time CPU consumption  | High `%us` or `%sy` values           |
| Memory Usage         | `free -m`      | RAM & swap usage           | Low free memory, high swap usage     |
| Load Average         | `uptime`       | System load (1, 5, 15 min) | Load > CPU cores = possible overload |
| Running Processes    | `ps aux`       | All running processes      | High `%CPU` or `%MEM` values         |
| Live Process Monitor | `top`          | Dynamic process view       | Identify abnormal resource usage     |

usage
🔎 Identifying High CPU Process (Inside top)
| Action         | Key Press   | Purpose                                   |
| -------------- | ----------- | ----------------------------------------- |
| Sort by CPU    | `Shift + P` | Shows highest CPU-consuming process first |
| Sort by Memory | `Shift + M` | Shows highest memory-consuming process    |
| Kill a Process | `k`         | Terminate selected process                |
| Refresh Faster | `d`         | Change refresh interval                   |

2️⃣ Inspect One systemd Service

Check Status of SSH Service
<img width="1856" height="894" alt="image" src="https://github.com/user-attachments/assets/78492bb1-8093-49a8-9792-ee5ba6e030ae" />
<br>
)
🔹 View Logs for That Service

<img width="1734" height="357" alt="image" src="https://github.com/user-attachments/assets/ba972205-7d04-4d53-bc11-aa726680a01a" />
✅ Step 1: Check CPU & Load
top
uptime

<img width="1803" height="953" alt="image" src="https://github.com/user-attachments/assets/0c27bff0-d4cc-47d3-8e6d-a12da49ee16a" />
Step 2: Check Memory
free -h
<img width="1133" height="173" alt="image" src="https://github.com/user-attachments/assets/754df0b3-6f85-4f9a-89b0-8b321d77d781" />
Step 3: Check Disk
df -h
<img width="1269" height="435" alt="image" src="https://github.com/user-attachments/assets/60780147-2882-477a-9d7d-18047bbf49cd" />
If disk > 90% full → possible issue.


