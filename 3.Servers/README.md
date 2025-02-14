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

# copy id_rsa.pub ke authorized.key di semua server agar bisa masuk menggunakan 1 ssh-key yaitu id_rsa.pub  dengan menggunakan ansible

![image](https://github.com/user-attachments/assets/5e94e1bc-d9bd-4b99-a91d-6859f9051718)

![image](https://github.com/user-attachments/assets/ffe6e053-e95f-4229-8fcf-4c99425fcd8a)

![image](https://github.com/user-attachments/assets/75cd6060-3a30-4139-a683-f33dd179bac7)

![image](https://github.com/user-attachments/assets/614c097e-70ea-4d45-82fe-ff2f2d1dadf0)

#
