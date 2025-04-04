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

### **GitLab CI/CD Basic Interview Questions & Answers**  

#### **1. What is GitLab CI/CD?**  
**Answer:**  
GitLab CI/CD (Continuous Integration and Continuous Deployment/Delivery) is a DevOps tool that automates the process of building, testing, and deploying code changes. It allows developers to define CI/CD pipelines using a `.gitlab-ci.yml` file to ensure smooth software delivery.  

---

#### **2. What are the key components of GitLab CI/CD?**  
**Answer:**  
- **.gitlab-ci.yml** – A configuration file that defines the pipeline.  
- **Jobs** – Individual tasks in a pipeline (e.g., build, test, deploy).  
- **Stages** – A sequence of job execution (e.g., `build → test → deploy`).  
- **Runners** – Machines that execute CI/CD jobs.  
- **Artifacts** – Files generated during the pipeline execution.  

---

#### **3. How does GitLab CI/CD work?**  
**Answer:**  
1. **Code Commit** – Developers push code to a GitLab repository.  
2. **Pipeline Trigger** – GitLab CI/CD detects changes and triggers a pipeline.  
3. **Jobs Execution** – CI/CD jobs are executed in defined stages.  
4. **Results & Deployment** – If successful, the changes are deployed.  

---

#### **4. What is a Runner in GitLab CI/CD?**  
**Answer:**  
A **Runner** is an agent that executes CI/CD jobs in GitLab. It can be:  
- **Shared Runner** – Provided by GitLab and shared across projects.  
- **Specific Runner** – Dedicated to a particular project or group.  
- **Self-hosted Runner** – Manually installed on a custom server.  

---

#### **5. What is the .gitlab-ci.yml file?**  
**Answer:**  
It is a YAML configuration file located in the root of a GitLab repository. It defines the **CI/CD pipeline**, specifying jobs, stages, scripts, and execution conditions.  

Example:  
```yaml
stages:
  - build
  - test
  - deploy

job1:
  stage: build
  script:
    - echo "Building the project..."

job2:
  stage: test
  script:
    - echo "Running tests..."

job3:
  stage: deploy
  script:
    - echo "Deploying the application..."
```

---

#### **6. What are Artifacts in GitLab CI/CD?**  
**Answer:**  
Artifacts are files generated by CI/CD jobs and stored for later use. They can be logs, compiled binaries, or reports.  

Example in `.gitlab-ci.yml`:  
```yaml
test_job:
  stage: test
  script:
    - echo "Running tests..."
  artifacts:
    paths:
      - test-results/
    expire_in: 1 day
```

---

#### **7. How do you define stages in GitLab CI/CD?**  
**Answer:**  
Stages are defined in the `.gitlab-ci.yml` file using the `stages` keyword. Jobs are then assigned to these stages.  

Example:  
```yaml
stages:
  - build
  - test
  - deploy
```

---

#### **8. How do you trigger a pipeline manually in GitLab?**  
**Answer:**  
- Go to **CI/CD > Pipelines** in GitLab UI and click **Run Pipeline**.  
- Use GitLab API:  
  ```sh
  curl --request POST --form "token=your-token" --form "ref=main" \
  https://gitlab.com/api/v4/projects/:id/trigger/pipeline
  ```
- Use GitLab CLI:  
  ```sh
  git push
  ```

---

#### **9. How do you use environment variables in GitLab CI/CD?**  
**Answer:**  
Environment variables store sensitive data like API keys or configuration settings. They can be defined in:  
- GitLab UI under **Settings > CI/CD > Variables**.  
- `.gitlab-ci.yml` using `variables`:  
  ```yaml
  variables:
    DATABASE_URL: "postgres://user:password@host:5432/db"
  ```

---

#### **10. What is the difference between Continuous Integration, Continuous Deployment, and Continuous Delivery?**  
**Answer:**  
| Term                  | Meaning |
|-----------------------|---------|
| **Continuous Integration (CI)** | Automates code merging, builds, and testing. |
| **Continuous Delivery (CD)** | Automates deployment but requires manual approval before release. |
| **Continuous Deployment (CD)** | Fully automated deployment without manual intervention. |

---

#### **11. How do you deploy a Docker container using GitLab CI/CD?**  
**Answer:**  
Example `.gitlab-ci.yml` file for Docker deployment:  
```yaml
stages:
  - build
  - deploy

build:
  stage: build
  script:
    - docker build -t myapp:latest .

deploy:
  stage: deploy
  script:
    - docker run -d -p 80:80 myapp:latest
```

---

#### **12. How do you retry a failed job in GitLab CI/CD?**  
**Answer:**  
- Go to **CI/CD > Pipelines** in GitLab UI, find the failed job, and click **Retry**.  
- Use GitLab API:  
  ```sh
  curl --request POST --header "PRIVATE-TOKEN: your-token" \
  https://gitlab.com/api/v4/projects/:id/jobs/:job_id/retry
  ```

---

#### **13. How do you cache dependencies in GitLab CI/CD?**  
**Answer:**  
Use the `cache` keyword to store dependencies and speed up builds.  

Example:  
```yaml
cache:
  paths:
    - node_modules/
```

---

#### **14. How do you run a job only for a specific branch?**  
**Answer:**  
Use the `only` keyword in `.gitlab-ci.yml`:  
```yaml
deploy:
  stage: deploy
  script:
    - echo "Deploying..."
  only:
    - main
```

---

#### **15. What is a GitLab CI/CD Badge?**  
**Answer:**  
A **badge** is a visual indicator showing the pipeline status (passed, failed, running). It can be added to a README file.  

Example badge URL:  
```
https://gitlab.com/user/project/badges/main/pipeline.svg
```

---
