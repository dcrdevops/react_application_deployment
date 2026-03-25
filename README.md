# react_application_deployment

## 🛠️ Prerequisites

Make sure you have:

- EC2 instance (Amazon Linux / Ubuntu)
- Internet access
- Installed:
    - Git
    - Docker

**Step 1: Install Required Tools**

Install Git

```yaml
sudo yum install git -y
```

Install Docker

```
sudo yum install docker -y
sudo service docker start
sudo systemctl enable docker
```

Add user to Docker group

```
  sudo usermod -aG docker ec2-user
```

**Step 2: Clone the Project**

```
  git clone https://github.com/digidense/react_application_deployment.git
```

you see this:

<img width="811" height="115" alt="Screenshot 2026-03-25 144016" src="https://github.com/user-attachments/assets/22b0c507-c882-4473-84b8-f13ef5b7445e" />


cd react_application_deployment
cd To-Do-List


**Step 3: Create Dockerfile**

Create a file named `Dockerfile`

**Step 4: Build Docker Image**

```
  docker build -t react-vite-app .
```

<img width="1859" height="431" alt="Screenshot 2026-03-25 144232" src="https://github.com/user-attachments/assets/8b5e2a77-8c7c-488e-b901-a7cb283beb9b" />


**Step 5: Run Docker Container**

```
  docker run -d -p 3000:80 react-vite-app
```

**Step 6: Configure Security Group**

| Type | Port | Source |
| --- | --- | --- |
| Custom TCP | 3000 | 0.0.0.0/0 |

**Step 7: Access Application** 

Open in browser:

```
http://<EC2-PUBLIC-IP>:3000
```

see this page

<img width="1067" height="410" alt="Screenshot 2026-03-25 144649" src="https://github.com/user-attachments/assets/48e07556-24cc-4554-97e2-9b7b48f0c0f8" />
