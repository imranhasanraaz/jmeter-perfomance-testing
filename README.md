# Content

- [Load testing Report](https://github.com/imranhasanraaz/jmeter-perfomance-testing#load-testing-report)
- [Load testing Report](https://github.com/imranhasanraaz/jmeter-perfomance-testing#Summary)
- [Introduction](https://github.com/imranhasanraaz/jmeter-perfomance-testing#introduction)  
- [Install](https://github.com/imranhasanraaz/jmeter-perfomance-testingstall)      
- [Prerequisites](https://github.com/imranhasanraaz/jmeter-perfomance-testing#prerequisites)
- [Elements of a Minimal Test Plan](https://github.com/imranhasanraaz/jmeter-perfomance-testing#Elements-of-a-minimal-test-plan)    
- [Test Plan](https://github.com/imranhasanraaz/jmeter-perfomance-testing#test-plan)
- [Collection of API](https://github.com/imranhasanraaz/jmeter-perfomance-testing#collection-of-api)   
    - [List of API](https://github.com/imranhasanraaz/jmeter-perfomance-testing#list-of-api) 
    - [Load the JMeter Script](https://github.com/imranhasanraaz/jmeter-perfomance-testing#load-the-jmeter-script)
- [Make jtl File](https://github.com/imranhasanraaz/jmeter-perfomance-testing#make-jtl-file)  
- [Make html File](https://github.com/imranhasanraaz/jmeter-perfomance-testing#make-html-file)  
- [HTML Report](https://github.com/imranhasanraaz/jmeter-perfomance-testing#html-report) 

# Load testing Report

| Concurrent Request  | Loop Count | Avg TPS for Total Samples  | Error Rate | Total Concurrent API request |
|               :---: |      :---: |                      :---: |                        :---: |      :---: |
| 200  | 1  | 2.7  | 0%      | 1000   |
| 300  | 1  |  4.4     | 0%      | 1500   |
| 400  | 1  |  8    | 0.35%   | 2000   |


### Summary
- While executed 400 concurrent request, found  7 request got connection timeout and error rate is 0.35%.
- Server can handle almost concurrent 300 API call with almost zero (0) error rate.


# Introduction

This document explains how to run a performance test with JMeter against an simplelearn.com.

# Install

**Java**  
https://www.oracle.com/java/technologies/downloads/

**JMeter**  
https://jmeter.apache.org/download_jmeter.cgi  

Click =>Binaries    
=>**apache-jmeter-5.6.2.zip**

**We use BlazeMeter to generate JMX files**    
https://chrome.google.com/webstore/detail/blazemeter-the-continuous/mbopgmdnpcbohhpnfglgohlbhfongabi?hl=en

# Prerequisites
- As of JMeter 5.6, Java 8 and above are supported.
- we suggest  multicore cpus with 4 or more cores.
- Memory 16GB RAM is a good value.


# Elements of a minimal test plan
- Thread Group

    The root element of every test plan. Simulates the (concurrent) users and then run all requests. Each thread simulates a single user.

- HTTP Request Default (Configuration Element)

- HTTP Request (Sampler)

- Summary Report (Listener)

# Test Plan

Testplan > Add > Threads (Users) > Thread Group (this might vary dependent on the jMeter version you are using)

- Name: Users
- Number of Threads (users): 200 to 400
- Ramp-Up Period (in seconds): 1
- Loop Count: 1

  1) The general setting for the tests execution, such as whether Thread Groups will run simultaneously or sequentially, is specified in the item called Test Plan.

  2) All HTTP Requests will use some default settings from the HTTP Request, such as the Server IP, Port Number, and Content-Encoding.

  3) Each Thread Group specifies how the HTTP Requests should be carried out. To determine how many concurrent "users" will be simulated, one must first know the number of threads. The number of actions each "user" will perform is determined by the loop count.

  4) The HTTP Header Manager, which allows you to provide the Request Headers that will be utilized by the upcoming HTTP Requests, is the first item in Thread Groups.

# Collection of API

- Run BlazeMeter  
- Collect Frequently used API  
- Save JMX file then paste => **apache-jmeter-5.6.2\bin**

    ### List of API 

    - [https://www.simplilearn.com/](https://www.simplilearn.com/)
    - [https://www.simplilearn.com/resources](https://www.simplilearn.com/resources)
    - [https://www.simplilearn.com/business](https://www.simplilearn.com/business)
    - [https://www.simplilearn.com/become-our-trainer](https://www.simplilearn.com/become-our-trainer)
    - [https://www.simplilearn.com/reseller-partner-program-for-training-courses](https://www.simplilearn.com/reseller-partner-program-for-training-courses)

   **OR**
    
  ### Load the JMeter Script 
   - File > Open (CTRL + O)
   - Locate the "simpleLearn_u200.jmx" file contained on this repo
   - Continue open simpleLearn_u200.jmx to simpleLearn_u400.jmx
   - Open those file
   - The Test Plan will be loaded
![loadjmx](https://github.com/imranhasanraaz/jmeter-perfomance-testing/assets/110620143/8cc4198b-ab6e-4231-bd38-693ff3a99da7)


# Test execution (from the Terminal)
 
- JMeter should be initialized in non-GUI mode.
- Make a report folder in the **bin** folder.  
- Run Command in __jmeter\bin__ folder.

 ### Make jtl file

```bash
  jmeter -n -t  simpleLearn_u200.jmx -l simpleLearn_u200.jtl
```      
  Then continue to upgrade Threads(200 to 400) by keeping Ramp-up Same.   

After completing this command  
   ### Make html file   
  
  ```bash
  jmeter -g report\simpleLearn_u200.jtl -o simpleLearn_u200.html
```
  - **g**: jtl results file

  - **o**: path to output folder
  - \
    ![Capture](https://github.com/imranhasanraaz/jmeter-perfomance-testing/assets/110620143/eedfa7ad-4c4b-4bf2-9849-c2e2be8d3d0c)  

# HTML Report

**Number of Threads 200 ; Ramp-Up Period 1s**

Requests Summary             |  Errors
:-------------------------:|:-------------------------:
![1](https://github.com/imranhasanraaz/jmeter-perfomance-testing/assets/110620143/920735d6-5aa3-44d9-bb70-5740c1e942f7)  |  ![2](https://github.com/imranhasanraaz/jmeter-perfomance-testing/assets/110620143/38ffa17b-1912-4d18-a32b-719b9b705e3a)

**Number of Threads 300 ; Ramp-Up Period 11s**
   
Requests Summary             |  Errors
:-------------------------:|:-------------------------:
![3](https://github.com/imranhasanraaz/jmeter-perfomance-testing/assets/110620143/d1bf207c-3927-48d4-a9c4-449b4689047c) |  ![4](https://github.com/imranhasanraaz/jmeter-perfomance-testing/assets/110620143/05daa31b-aece-4474-9ea9-b79c9a63bf63)

**Number of Threads 400 ; Ramp-Up Period 1s**
   
Requests Summary             |  Errors
:-------------------------:|:-------------------------:
![5](https://github.com/imranhasanraaz/jmeter-perfomance-testing/assets/110620143/bb07a2f1-677a-4bea-b551-262769e23620)  |  ![6](https://github.com/imranhasanraaz/jmeter-perfomance-testing/assets/110620143/d8ff121d-8b61-4f34-91ca-9d16d7aae12d)
