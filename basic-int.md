Got it! Here are more **basic GitLab CI/CD interview questions** with simple answers:  

---

### **1. What is CI/CD?**  
**Answer:**  
CI/CD stands for:  
- **Continuous Integration (CI)** – Automatically builds and tests code changes.  
- **Continuous Deployment/Delivery (CD)** – Automates software release processes.  

---

### **2. What is GitLab?**  
**Answer:**  
GitLab is a DevOps platform that provides **version control, issue tracking, and CI/CD** tools in a single interface.  

---

### **3. What is a GitLab CI/CD Pipeline?**  
**Answer:**  
A **pipeline** is a series of automated steps (jobs) defined in a `.gitlab-ci.yml` file to build, test, and deploy code.  

---

### **4. How do you enable GitLab CI/CD for a project?**  
**Answer:**  
1. Create a `.gitlab-ci.yml` file in the repository.  
2. Define jobs and stages in the file.  
3. Push the code to GitLab, and the pipeline will automatically start.  

---

### **5. What is a GitLab Runner?**  
**Answer:**  
A **GitLab Runner** is a tool that executes CI/CD jobs. It can be **shared**, **specific**, or **self-hosted**.  

---

### **6. Where is the GitLab CI/CD configuration stored?**  
**Answer:**  
In the `.gitlab-ci.yml` file located in the root of the repository.  

---

### **7. What are the main stages in GitLab CI/CD?**  
**Answer:**  
Common stages include:  
- `build` – Compiling the application.  
- `test` – Running tests.  
- `deploy` – Deploying the application.  

---

### **8. What is the purpose of the `.gitlab-ci.yml` file?**  
**Answer:**  
It defines the pipeline configuration, including **stages, jobs, scripts, and execution rules**.  

---

### **9. How do you check the pipeline status in GitLab?**  
**Answer:**  
Go to **CI/CD > Pipelines** in GitLab UI.  

---

### **10. What happens when a GitLab pipeline fails?**  
**Answer:**  
- The job stops execution.  
- GitLab marks the pipeline as **failed**.  
- Developers can **retry** or **debug** the issue.  

---

### **11. How do you manually trigger a pipeline?**  
**Answer:**  
1. Go to **CI/CD > Pipelines** in GitLab UI.  
2. Click **Run Pipeline**.  

---

### **12. What is the difference between `script` and `before_script`?**  
**Answer:**  
- **`before_script`** runs before each job.  
- **`script`** contains the main commands for the job.  

Example:  
```yaml
job1:
  before_script:
    - echo "Setting up..."
  script:
    - echo "Running the job..."
```

---

### **13. How do you define a simple pipeline in GitLab?**  
**Answer:**  
Example `.gitlab-ci.yml` file:  
```yaml
stages:
  - build
  - test
  - deploy

build_job:
  stage: build
  script:
    - echo "Building the project..."

test_job:
  stage: test
  script:
    - echo "Running tests..."

deploy_job:
  stage: deploy
  script:
    - echo "Deploying..."
```

---

### **14. What is an artifact in GitLab CI/CD?**  
**Answer:**  
Artifacts are **files stored** after a job completes (e.g., build output, reports).  

Example:  
```yaml
job:
  script: echo "Creating artifact"
  artifacts:
    paths:
      - output/
```

---

### **15. How do you specify a job should only run on the `main` branch?**  
**Answer:**  
```yaml
deploy:
  script: echo "Deploying..."
  only:
    - main
```

---

### **16. How do you cache dependencies in GitLab CI/CD?**  
**Answer:**  
Using the `cache` keyword:  
```yaml
cache:
  paths:
    - node_modules/
```

---

### **17. What is a GitLab CI/CD variable?**  
**Answer:**  
A **variable** stores environment-specific values (e.g., API keys, database URLs). They are set in:  
- GitLab UI (**Settings > CI/CD > Variables**)  
- `.gitlab-ci.yml` file using `variables`  

Example:  
```yaml
variables:
  ENV: "production"
```

---

### **18. How do you make a job run on a schedule?**  
**Answer:**  
Use **GitLab Schedules** under **CI/CD > Schedules** in the UI.  

---

### **19. What is the difference between `only` and `except` in `.gitlab-ci.yml`?**  
**Answer:**  
- **`only`** – Runs the job **only** for specified branches.  
- **`except`** – Excludes the job from specified branches.  

Example:  
```yaml
deploy:
  script: echo "Deploying..."
  only:
    - main
  except:
    - feature/*
```

---

### **20. How do you deploy a Docker container using GitLab CI/CD?**  
**Answer:**  
```yaml
stages:
  - build
  - deploy

build:
  script:
    - docker build -t myapp:latest .

deploy:
  script:
    - docker run -d -p 80:80 myapp:latest
```

---

These are the **basic GitLab CI/CD interview questions** you might get asked. Do you need more **practice questions** or **hands-on examples**? 😊
