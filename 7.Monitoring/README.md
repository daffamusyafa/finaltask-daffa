Requirements

    Deployments on top Docker

Instructions

    Create Basic Auth into your Prometheus
    Monitor resources for all your servers
    Create a fully working dashboard in Grafana
        Disk
        Memory Usage
        CPU Usage
        VM Network
        Monitoring all of container resources on VM
    Grafana Alert/Prometheus Alertmanager for:
        Send Notification to Telegram
        CPU Usage
        RAM Usage
        Free Storage
        Network I/O (NGINX Monitoring)

JAWABAN:

# Buat configurasi ansible untuk install node-exporter di semua server dan grafana+prometheus di 1 server monitoring

![image](https://github.com/user-attachments/assets/a52c708d-79ab-434f-896e-7bd00391d304)

# Jalankan setup start-node-exporter terlebih dahulu

![image](https://github.com/user-attachments/assets/9458ef9c-162e-483a-8f6b-d6973a4e7ac0)

![image](https://github.com/user-attachments/assets/eaef37aa-2801-40ba-9a19-c8fc4d47b3e9)

![image](https://github.com/user-attachments/assets/f51ceac6-97c7-4efe-a083-4aeddbde54ba)

# Jalankan setup start-monitoring

![image](https://github.com/user-attachments/assets/f3de86b2-86d0-4fbf-a4ad-b907ae259477)

# Buat dasboard di grafana

![image](https://github.com/user-attachments/assets/f47a9f23-efa4-4a30-ac1c-9b5662d99768)

# Buat alert ke telegram

![image](https://github.com/user-attachments/assets/b64f9fd1-7ee4-4fad-80fc-d36f32548d7c)

![image](https://github.com/user-attachments/assets/3f2290a9-2642-420d-9b97-eb868410d250)

![image](https://github.com/user-attachments/assets/438f3e7b-8765-4c8d-a656-fc2d3b17c3af)

