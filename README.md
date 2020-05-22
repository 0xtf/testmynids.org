<img align="right" width="260" height="447" src="./assets/imgs/tmnids-mascot-small.png">

# testmynids.org
A website and framework for testing NIDS detection

## What is it?

A simple project that aims to centralize testing for detection of malicious events by network intrusion detection systems (NIDS). The tests in this project are built against rulesets, not software. Therefor, if you're using ET Open, coverage for these tests will work.

There are two parts to it:

* **A website** - that is used to hold some tests/files. It will also hold sub-domains and DNS records for when testing via DNS is required.
* **A script** - That runs/simulates interaction with the website or with 3rd party websites, meant to be executed on the client for which you want to test coverage of your NIDS sensor.

## Usage

Only requirements are `curl` and `nc`, which should be included in your distribution.

**One-liner to download and execute in interactive mode:** 
```
curl -sSL https://raw.githubusercontent.com/0xtf/testmynids.org/master/tmNIDS -o /tmp/tmNIDS && chmod +x /tmp/tmNIDS && /tmp/tmNIDS
```

**One-liner to download and execute in script mode:** 
```
curl -sSL https://raw.githubusercontent.com/0xtf/testmynids.org/master/tmNIDS -o /tmp/tmNIDS && chmod +x /tmp/tmNIDS && /tmp/tmNIDS -h
```
*Tip: Replace the -h with -N (where N is the test you want - see table below) at the end of the one-liner to automatically run the desired test*

### Interactive mode

To run tmNIDS in interactive mode without using the one-liner, download and run the [script](./tmNIDS).

After downloading **tmNIDS** make it executable *(chmod +x tmNIDS)* and run it *(./tmNIDS)* to be presented with the wizard:

![image](./assets/imgs/screenshot.png)

### Script mode

To run tmNIDS in script mode without using the one-liner, download and run the [script](./tmNIDS). 

After downloading **tmNIDS** make it executable *(chmod +x tmNIDS)* and run it *(./tmNIDS -h)* to be presented with the script options.

In summary, the usage of `./tmNIDS -N`, where N is the number of the test, will run the designated test for you.

# Included tests

| Test ID | Name                                                              |  Protocols used
|---------|-------------------------------------------------------------------|----------------|
| Test 1  | Linux UID                                                         | HTTP           |
| Test 2  | Basic Authentication over clear text                               | HTTP           |
| Test 3  | Several known malware-related user agents                          | HTTP           |
| Test 4  | Known bad CA's                                                     | TLS            |
| Test 5  | Tor .onion response and random Tor nodes connection                | DNS & TLS      |
| Test 6  | EXE download over HTTP *(from AWS S3)* & Packed Executable         | HTTP           |
| Test 7  | PDF download over HTTP with Embedded File                          | HTTP           |
| Test 8  | Simulate an outbound SSH scan                                      | SSH            |
| Test 9  | Miscellaneous *(TLD's, Sinkhole, DDNS, etc)* domains               | DNS            |
| Test 10 | MD5 in TLS Certificate                                            | TLS            |
| Test 99 | CHAOS! Run all tests!                                             | ☝️ ALL          |

## Have an idea for a new test?

Please [let me know](https://twitter.com/0xtf). Purpose of this project is to be community-driven. We also want to provide a framework that allows for testing of as many protocols as possible *(DNS, SMTP, HTTP, etc)*.

## Why? What about _insert_project\_here_?

**Why** - We can check if a NIDS engine is working with a simple rule. In most cases, a ping would do. From that moment on, it becomes a matter of rulesets if detection is working or not. The purpose of this project is to quickly verify and showcase detection of as many protocols as possible, while keeping the whole process quick, portable and simple.

**Other projects** - I'm aware that other websites, projects or scripts exist. I created this one because the existing ones were

* lacking features
* no longer supported 
* not portable enough
* too many dependencies

Choose whatever works best for you.
