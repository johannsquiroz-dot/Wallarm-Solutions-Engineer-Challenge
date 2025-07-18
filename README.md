# Wallarm Solutions Engineer Technical Evaluation

## 📌 Overview

This technical challenge was a good exercise to get me familiar with the deployment of a Wallarm filtering node, connect to a backend and create syntetic traffick using the GoTestWaf attack simulation tools. The exercise showed traffic being monitored by the Wallarm solution, and subsequently the malicious traffic getting blocked. All of the tools and processes used are new to me (since my experience has been showcasing the value and benefits of solutions from the user interface perspective). This was a good learning experience personally. 

---

## 🎯 Objectives


✅ Deploy a Wallarm filtering node using a supported method of your choice.  
✅ Configure a backend origin to receive test traffic. (httpbin.org is also acceptable)  
✅ Use the **GoTestWAF** attack simulation tool to generate traffic.  
✅ Document the deployment and troubleshooting process.  
✅ Demonstrate proficiency in using **Wallarm's official documentation**.  

---

## 🚀 Task Breakdown

✅ Deploy a Wallarm filtering node using a Docker





### 1️⃣ Deploy a Wallarm Filtering Node

🔹 Choose a [deployment method](https://docs.wallarm.com/installation/supported-deployment-options/) (**e.g., Docker, Kubernetes, AWS, etc.**).  
🔹 Follow the [**official Wallarm documentation**](https://docs.wallarm.com/) to install and configure the filtering node.  
🔹 Verify that the filtering node is properly deployed and running.  

### 2️⃣ Set Up a Backend Origin

🔹 Configure a simple **backend API or web application** to receive traffic.  
🔹 Ensure the backend is **reachable from the filtering node**.  

### 3️⃣ Generate Traffic Using GoTestWAF

🔹 Install and configure **GoTestWAF**.  
🔹 Send attack simulation traffic through the **Wallarm filtering node**.  
🔹 Analyze the results and confirm that attacks are being detected.  

### 4️⃣ Document Your Process

📝 Provide an **overview summary** of your deployment and why you chose it.  
🛠️ Document any **issues encountered and how you resolved them**.  
📸 Include **relevant logs, screenshots, or outputs** where applicable.  

---

## ✅ Evaluation Criteria

Your submission will be evaluated based on:

📌 **Completeness**: Were all required tasks completed?  
📌 **Clarity**: Is the documentation clear and well-structured?  
📌 **Troubleshooting**: How well did you document and resolve any issues?  
📌 **Understanding of the Product**: Did you correctly set up and use the Wallarm filtering node?  
📌 **Use of Official Documentation**: Did you successfully leverage Wallarm's official resources?  

---

## 📬 Submission

Once you have completed the evaluation, submit the following:

📂 Fork this **GitHub repo** and use it as the repository for your documentation, configuration files, and any relevant logs or screenshots.  
📜 A **README file** summarizing your process and key findings.  
📜 A **HIGH Level Diargram** that illustrates what you built and how traffic is flowing.  

---

! [ ] 



## ℹ️ Additional Notes


AT the end of this evaluation, I was able to:


✅ Configure a backend origin to receive test traffic. (httpbin.org) 
✅ Use the GoTestWAF attack simulation tool to generate traffic.
✅ Document the deployment and troubleshooting process.
✅ Navigated Wallarm's official documentation to complete the steps.


Notes & Observations
This project demonstrates how to run a local Wallarm filtering node on Ubuntu OS Docker and generate attack traffic using GoTestWAF against a backend origin (httpbin.org).

    * Conflicts on docker container and node ports used, had to select different ports to establish connectivity.
    * Filtering Node was deployed locally on Ubuntu with passthrough variables. I had to verify and change the commands since I was getting syntax errors. 



