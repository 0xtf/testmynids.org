# testmynids.org
A website and framework for testing NIDS detection

## What is it?

A simple project that aims to centralize testing of network intrusion detection engines detection of malicious events. The tests in this project are built against rulesets, not software. Therefor, if you're using ET Open, coverage for these tests will work.

There are two parts to it:

* **A website** - that is used to hold some tests/files. It will also hold sub-domains and DNS records for when testing via DNS is required.
* **A script** - That runs/simulates interaction with the website or with 3rd party website, meant to be executed on the client for which you want to test coverage of your NIDS sensor.

## Usage

Easiet way is to download and run the [script](./tmNIDS) *(only requirements are curl and nc, which should be included in your distro)*. You can also run the tests manually by looking at the script.

After downloading the script, make it executable *(chmod +x tmNIDS)* and run it to be presented with the wizard:

![image](./assets/imgs/screenshot.png)

## Included tests

* Linux UID (HTTP)
* Basic Authentication over clear text (HTTP)
* Several known malware-related user agents (HTTP)
* Known bad CA's (HTTPS)
* Tor .onion response and random Tor nodes connection (DNS & HTTPS)
* EXE download over HTTP *(from AWS S3)* & Packed Executable (HTTP)
* PDF download over HTTP with Embedded File (HTTP)

## Have an idea for a new test?

Please let me know. Purpose of this project is to be community-driven. We also want to provide a framework that allows for testing of as many different as possible protocols *(DNS, SMTP, HTTP, etc)*.

## Why? What about _insert_project\_here_?

**Why** - We can check if a NIDS engine is working with a simple rule. In most cases, a ping would do. From that moment on, it becomes a matter of rulesets if detection is working or not. The purpose of this project is more to quickly showcase detection and verify detection of as many protocols as possible, while keeping the whole process quick and simple.

**Other projects** - I'm aware that other websites, projects or scripts exist. I created this one because the existing ones were

* lacking features
* no longer supported 
* not portable enough

Choose whatever works best for you.
