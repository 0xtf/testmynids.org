# testmynids.org
A website and framework for testing NIDS detection

## What is it?

A simple project that aims to centralize testing of network intrusion detection engines detection of malicious events. The tests in this project are built against rulesets, not software. Therefor, if you're using ET Open, coverage for these tests will work.

There are two parts to it:

* A website - that is used to hold some tests/files
* A script - That runs/simulates interaction with the website or with 3rd party website, meant to be executed on the client for which you want to test coverage of your NIDS.

## Usage

Easiet way is to download and run the [script](./tmnids.sh). You can also run the tests manually by looking at the script.

## Included tests

* Linux UID
* HTTP Basic Authenticatio over clear text
* Several known malware-related user agents
* HTTPS - Known bad CA's
* Tor - .onion response and random Tor nodes connection

If you want to run the tests manually, you can. To make things a bit easier, the script in this repository *(only requirements are wget, curl and nc, which should be included in your distro)* does make all the tests available from a single file.

## Have an idea for a new test?

Please let me know. Purpose of this project is to be community-driven and we want to provide a framework that allows for testing of as many as possible protocols *(DNS, SMTP, HTTP, etc)*.

## Why? What about _insert_project_here_?

I'm aware that other websites, projects or scripts exist. I created this one because the existing ones were

* lacking features
* no longer supported 
* not portable enough.

Choose whatever works best for you.
