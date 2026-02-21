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


