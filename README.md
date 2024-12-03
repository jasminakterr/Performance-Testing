## Performance Testing for A booking Website

Testing Site - "https://restful-booker.herokuapp.com"

## Introduction

This document explains how to run a performance test with JMeter against the Booking  Website. The performance test will help evaluate the website's performance under various load conditions.

## Install

Before running the performance test, ensure you have the following prerequisites installed:

- **Java**: [Download Java](https://www.oracle.com/java/technologies/downloads/)
- **JMeter**: [Download JMeter](https://jmeter.apache.org/download_jmeter.cgi) 

Click =>Binaries  
=>apache-jmeter-5.6.3.zip
We can also use BlazeMeter and Lighthouse to generate JMX files for our performance tests.
- **BlazeMeter**:
 [BlazeMeter Chrome Extension](https://chrome.google.com/webstore/detail/blazemeter-the-continuous/mbopgmdnpcbohhpnfglgohlbhfongabi?hl=en)

- **Lighthouse**:
[Lighthouse Chrome Extension](https://chromewebstore.google.com/detail/lighthouse/blipmdconlkpinefehnmjammfjpmpbjk)

## Prerequisites

- As of JMeter 5.6, Java 8+ and above are supported.
- we suggest multicore cpus with 4 or more cores.
- Memory 16GB RAM is a good value.

## Elements of a Minimal Test Plan 

Create a test plan with the following elements:

- Thread Group: Simulates concurrent users.
- HTTP Request Defaults (Configuration Element): Set default values for HTTP requests.
- HTTP Request (Sampler): Define the HTTP requests to be executed.
- Summary Report (Listener): Collect and display test results.

## Test Plan
Testplan > Add > Threads (Users) > Thread Group (this might vary dependent on the jMeter version you are using)

- Name: Thread group

- Number of Threads (users): 1 to 800

- Ramp-Up Period (in seconds): 30

- Loop Count: 1

  i. The general setting for the tests execution, such as whether Thread Groups will run simultaneously, is specified in the item called Test Plan.

  ii. All HTTP Requests will use some default settings from the HTTP Request, such as the Server IP, Port Number, and Content-Encoding.

  iii. Each Thread Group specifies how the HTTP Requests should be carried out. To determine how many concurrent "users" will be simulated, one must first know the number of threads. The number of actions each "Thread Group" will perform is determined by the loop count.

  iv. The HTTP Header Manager, which allows you to provide the Request Headers that will be utilized by the upcoming HTTP Requests, is the first item in Thread Groups.

## Test Execution

Follow these steps to execute the performance test:

1. **Load the JMeter Script:**
   - File > Open (CTRL + O)
   - Locate the appropriate JMX file for your test scenario.
   - Open the JMX file.
   - The Test Plan will be loaded.

2. **Run the Test:**
   - In the JMeter terminal, navigate to the `bin` folder.
   -  Open Command prompt (CMD).

```
Booking
```
`jmeter -n -t b29_demo.jmx -l report\b29_demo.jtl`
```
Aarong
```
`jmeter -n -t Aarong_t100.jmx -l report\Aarong_t100.jtl`
- Repeat the above command for different test scenarios as needed.

3. **Generate HTML Report:**
- Execute the following command to generate an HTML report :
```
Booking
```
`jmeter -g report\b29_demo.jtl -o report\b29_demo.html`

```
Aarong
```
`jmeter -g report\Aarong_t100.jtl -o report\Aarong_t100.html`
  
- This will create an HTML report in the `Report` folder.

## Screenshots

```
Booking
```
![Booking(1)](https://github.com/user-attachments/assets/75be147d-8d22-4226-86e3-cd081bc1da02)

![Booking(2)](https://github.com/user-attachments/assets/f1e8f49a-ac3e-44af-9346-bba718cb4898)

```
Aarong
```
![Aarong(1)](https://github.com/user-attachments/assets/bb6271d7-648a-44d6-96a9-9d61bafae9e5)

![Aarong(2)](https://github.com/user-attachments/assets/f4ebf324-1d58-4da1-8bb3-fd9eab21cc9e)
