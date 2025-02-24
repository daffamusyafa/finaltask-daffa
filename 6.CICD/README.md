Requirements

    CI/CD with Jenkins

Instructions

[ CI/CD ]

    Using Jenkins, create a pipeline running:
        Repository pull
        Image build
        Testing Your Code
        Push Image into your own docker registry private
        SSH into your server
        Pull image from docker registry private
        Redeploy your deployment apps
    For testing Stage, you must use sonarqube for testing your code quality
        Sonarqube
            On your cicd workflow, use sonarqube for testing your quality code.
            You can use others testing tools like trivy for scanning your images or some.
            And try test your running app by using wget spider
JAWABAN:

# Buat Jenkins menggunakan docker

![image](https://github.com/user-attachments/assets/fac6dafc-d1b0-4738-9218-3dddb27075ba)

# Buat reverser proxy

![image](https://github.com/user-attachments/assets/321cc4cc-949d-4264-9e8a-a76da6f635a8)

# Buka jenkins

![image](https://github.com/user-attachments/assets/e297bb36-1632-4615-ad9d-702e90aa2b0a)

# Install yang diperlukan

![image](https://github.com/user-attachments/assets/95d9895f-ebe0-4326-aeae-111994002e1a)

![image](https://github.com/user-attachments/assets/deb29864-85d7-4a2b-a8cb-7dbd506b50be)

![image](https://github.com/user-attachments/assets/b46c99d8-6a9d-4465-91b8-e6a959c52d9f)

![image](https://github.com/user-attachments/assets/736bf305-c714-4ca8-83a8-de122c70c015)

![image](https://github.com/user-attachments/assets/5961a6a6-9a50-4b78-aaa9-5c5f16e02628)

# Buat new item pipeline dengan nama be-production dan be-staging

![image](https://github.com/user-attachments/assets/6835457e-b5b6-4d53-937b-0f7b197dbd20)

# ceklis GitHub hook trigger for GITScm polling

![image](https://github.com/user-attachments/assets/0425a098-bd59-4551-8875-df0ca9a57b01)

# masukan link repository github

![image](https://github.com/user-attachments/assets/3da88a57-8b62-4b9a-b264-d517de3ed8e7)

# Buat PAT token classic

![image](https://github.com/user-attachments/assets/27986ef4-d613-4155-b8cb-3161682f5b99)

# Buat kredensial baru

![image](https://github.com/user-attachments/assets/08ccae87-651b-44d9-9698-29ec16244f8d)

# Buat kredensial untuk ssh key

![image](https://github.com/user-attachments/assets/daef9e57-4525-4cd6-a550-3170de7170d7)

# Tambahkan File .env

![image](https://github.com/user-attachments/assets/8ba0d40a-8922-4773-a5c6-3f361bd4ace4)

# Buat File Jenkinsfile

![image](https://github.com/user-attachments/assets/24f8f948-6689-4d11-a748-9ffe9f9a2e0b)

# Tambahkan link jenkins webhook ke github

![image](https://github.com/user-attachments/assets/d0386131-941e-4aa0-9bfd-55f857dba591)

![image](https://github.com/user-attachments/assets/baf22431-8af7-4abb-8436-49f4db980793)

# hasil otomatisasi jenkins menggunakan scanner trivy,wget spider dan sonarqube

![image](https://github.com/user-attachments/assets/45cede5a-acb7-4ac1-9fc6-7594cd91cff6)

![image](https://github.com/user-attachments/assets/48680b9e-1937-4605-b499-50f423efe483)

![image](https://github.com/user-attachments/assets/0bd2906b-a743-4a4a-a9ee-d78064a2dd90)

![image](https://github.com/user-attachments/assets/7ed9dca9-350e-4396-8a30-9f6be77ac30c)
