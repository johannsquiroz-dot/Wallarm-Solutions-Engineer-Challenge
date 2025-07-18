.# Wallarm Solutions Engineer Technical Evaluation

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


johanns@Discovery:~$ docker run -d -e WALLARM_API_TOKEN='rII9h4BWnfZpkagibXQdXHDF35iOVh4YEOqrxnlbfNuMoTaR9SxMwLD6rzvuJN2r' -e WALLARM_LABELS='group=<GROUP>' -e NGINX_BACKEND='httpbin.org' -e WALLARM_API_HOST='us1.api.wallarm.com' -e WALLARM_MODE='block' -p 8100:80 wallarm/node:6.3.0
8698d2ee610f5274f9f11f9e57fc2ee8b8fdcd71fd52c049dbedf2e84ebac27c



✅ Configure a backend origin to receive test traffic. 


johanns@Discovery:~$ curl -v httpbin.org/get
*   Trying 3.229.116.23:80...
* Connected to httpbin.org (3.229.116.23) port 80 (#0)
> GET /get HTTP/1.1
> Host: httpbin.org
> User-Agent: curl/7.81.0
> Accept: */*



✅ Use the **GoTestWAF** attack simulation tool to generate traffic. 


Johanns@Discovery:~$ docker run --rm --network="host" -it -v ${PWD}/reports:/app/reports wallarm/gotestwaf   --url=http://localhost:8100
INFO[0000] GoTestWAF started                             version=v0.5.7
INFO[0000] Test cases loading started                   
INFO[0000] Test cases loading finished                  
INFO[0000] Test cases fingerprint                        fp=910a7162ec5355b41a27a2ef0caa3574
INFO[0000] Try to identify WAF solution                 
INFO[0000] WAF was not identified                       
INFO[0000] gohttp is used as an HTTP client to make requests  http_client=gohttp
INFO[0009] WAF pre-check                                 url="http://localhost:8100"
INFO[0009] WAF pre-check                                 blocked=true code=403 status=done
INFO[0009] gRPC pre-check                                status=started
INFO[0009] gRPC pre-check                                connection="not available" status=done
INFO[0009] GraphQL pre-check                             status=started
INFO[0018] GraphQL pre-check                             connection="not available" status=done
INFO[0018] Scanning started                              url="http://localhost:8100"
INFO[0305] Scanning finished                             duration=4m46.97465497s  

✅ Document the deployment and troubleshooting process.  


* Conflicts on docker container and node ports used, had to select different ports to establish connectivity.
    * Filtering Node was deployed locally on Ubuntu with passthrough variables. I had to verify and change the commands since I was getting syntax errors.
    * Had to create a second filtering node to set the blocking directive. This was most likely due to my lack of experience setting up this platorm.

## ℹ️ Additional Notes

AT the end of this evaluation, I was able to:


✅ Configure a backend origin to receive test traffic. (httpbin.org) 
✅ Use the GoTestWAF attack simulation tool to generate traffic.
✅ Document the deployment and troubleshooting process.
✅ Navigated Wallarm's official documentation to complete the steps.


Notes & Observations
This project demonstrates how to run a local Wallarm filtering node on Ubuntu OS Docker and generate attack traffic using GoTestWAF against a backend origin (httpbin.org).

    
## ✅ Evaluation Criteria

Your submission will be evaluated based on:

📌 **Completeness**: Were all required tasks completed?  
📌 **Clarity**: Is the documentation clear and well-structured?  
📌 **Troubleshooting**: How well did you document and resolve any issues?  
📌 **Understanding of the Product**: Did you correctly set up and use the Wallarm filtering node?  
📌 **Use of Official Documentation**: Did you successfully leverage Wallarm's official resources?  


