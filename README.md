# Content

- [Load testing Report](https://github.com/imranhasanraaz/jmeter-perfomance-testing#load-testing-report)
- [Load testing Report](https://github.com/imranhasanraaz/jmeter-perfomance-testing#Summary)
- [Introduction](https://github.com/imranhasanraaz/jmeter-perfomance-testing#introduction)  
- [Install](https://github.com/imranhasanraaz/jmeter-perfomance-testingstall)      
- [Prerequisites](https://github.com/imranhasanraaz/jmeter-perfomance-testing#prerequisites)

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
