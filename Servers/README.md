Requirements

    1 SSH keys max.
    SSH Config.
    Ubuntu 22.04 lts

Instructions

    Create new user finaltask-$USER (this new user was your final tasks playground)
    Server login with SSH key and Password
    Create a working SSH config to log into servers
    Only use 1 SSH keys for all purpose (Repository, CI/CD etc.)
    UFW enabled with only used ports allowed
    Change ssh port from (22) to (1234)

JAWABAN:

# Buat file Inventory

![image](https://github.com/user-attachments/assets/e86b0f87-dd89-46ce-b8bd-2e83d60164ab)

![image](https://github.com/user-attachments/assets/23b1e369-80a1-45bb-8f2f-4887eb16100a)

# Buat file ansible.cfg

![image](https://github.com/user-attachments/assets/7886a00b-7fb5-4dd0-8301-a4bec8d5a001)

![image](https://github.com/user-attachments/assets/b28a92f3-f22f-4d68-9493-1010c6134a33)

# copy id_rsa.pub ke authorized.key di semua server agar bisa masuk menggunakan 1 ssh-key yaitu id_rsa.pub  

![image](https://github.com/user-attachments/assets/4f0e2c96-d3d0-4cca-af0b-45b4b9b6cba8)  

![image](https://github.com/user-attachments/assets/1c2ee05f-3485-4ff8-8cb3-29a244443cb1)
