Requirements

    Local machine w/ Ansible & Terraform
    Biznet GIO NEO Lite Servers
        Appserver - 2 CPU, 2GB RAM
        Gateway - 1 CPU, 1GB RAM
    Others Servers if required

Instructions

    Attach SSH keys & IP configuration to all VMs
    Server Configuration using Ansible

JAWABAN:

# 1.Install Terraform
# 2.Buat file providers.tf

![image](https://github.com/user-attachments/assets/5d163039-1ddd-4150-b7f3-45ea826bdb94)

![image](https://github.com/user-attachments/assets/f9024b3e-e8a0-43ca-bc56-9eddf81e0625)

# 3.Buat file Variables.tf

![image](https://github.com/user-attachments/assets/aa46dcaf-a871-42fd-ac05-5783350abb57)

![image](https://github.com/user-attachments/assets/6a436921-9f3f-4de7-adea-a8f7bf981815)

# 4.Buat file main.tf

![image](https://github.com/user-attachments/assets/69e74553-33b0-4060-bcbd-c58f49216faa)

![image](https://github.com/user-attachments/assets/cfa8de86-04cb-4be3-b702-d057905ab820)

# 5.Buat file elastic_ip.tf

![image](https://github.com/user-attachments/assets/5cc5f406-f237-4bb1-8246-7a583c0ca3ee)

![image](https://github.com/user-attachments/assets/2114f908-0f47-40fc-b2f2-124dee97fa04)

# 6.Buat file storage.tf

![image](https://github.com/user-attachments/assets/1fb2a4b0-0a61-423f-87be-b167a167b72c)

![image](https://github.com/user-attachments/assets/5c35f78d-a379-4f46-a233-7d35213764f1)

# 7.Buat file outputs.tf

![image](https://github.com/user-attachments/assets/853867d6-66f7-492a-8f2c-862380e1fda0)

![image](https://github.com/user-attachments/assets/92d11e7b-0ca9-44ad-ba41-5e0070ec2821)

# 8.Jalankan Terraform

![image](https://github.com/user-attachments/assets/02535209-2514-40ae-bf53-75e5c1113f05)

![image](https://github.com/user-attachments/assets/35b12182-0eac-43fb-bc7e-c9ea9e3a06e8)

![image](https://github.com/user-attachments/assets/5ada3db9-3838-42d1-a426-a9d8f6023dc2)

# 9.Install ansible

![image](https://github.com/user-attachments/assets/c8eb8942-6712-4b1b-a471-d8c31f0c4334)

![image](https://github.com/user-attachments/assets/63447f07-4034-429f-840c-d3ac2c9472ff)

![image](https://github.com/user-attachments/assets/7c8658f0-4700-4d47-a0a2-65cdc9b61a01)

# 10.Buat konfigurasi agar bisa masuk ke semua server pake 1 ssh-key

![image](https://github.com/user-attachments/assets/4f0e2c96-d3d0-4cca-af0b-45b4b9b6cba8)

![image](https://github.com/user-attachments/assets/40cc8b00-05ac-458b-950d-f78040bde527)

# 11.copy id_rsa.pub ke authorized.key di semua server agar bisa masuk menggunakan 1 ssh-key yaitu id_rsa.pub

![image](https://github.com/user-attachments/assets/1c2ee05f-3485-4ff8-8cb3-29a244443cb1)
