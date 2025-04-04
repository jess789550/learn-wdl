# learn-wdl

## What is WDL?

<img src="https://github.com/openwdl/learn-wdl/raw/master/images/wdl-icon.png" width="460" align="right">  

- The Workflow Description Language (WDL or 'widdle') is an [open source scripting language](https://github.com/openwdl/wdl) which allows you to specify data processing workflows with a human-readable and -writeable syntax. 
- [WDL](https://openwdl.org/) was originally developed for genomics, but can be extended to other domains.  
- This repository contains educational materials for learning to read and write WDL scripts.

---

<img src="https://github.com/openwdl/learn-wdl/raw/master/images/3-wdl.png" width="400" align="left">

---

## About WDL script execution

WDL scripts are not executable in and of themselves, but they require an execution engine and environment to be runnable. Compliant executions engines should support the features of a specific version of the WDL specification, i.e. WDL 1.0, etc...

Please see the linked engine documentation for information on available execution options and support. Some of the environments (shown linked below) include WDL parsing, linting and DAG (Directed Acyclic Graph or workflow) visualization tools as well.    

Most of these environments request one or more language runtimes (such as Java, Python).  Please read the documentation for the execution environment documentation for the particular environment for details.

---

### Environments 

 - [cromwell](https://github.com/broadinstitute/cromwell) - **IMPORTANT** This Repo uses `cromwell-50.jar` for testing all WDL example scripts
 - [miniwdl](https://github.com/chanzuckerberg/miniwdl) - WDL script local runner & developer toolkit for Python 3.6+ - [docs here](https://miniwdl.readthedocs.io/en/latest/getting_started.html) & [course here](https://github.com/openwdl/learn-wdl/tree/master/6_miniwdl_course)
 - [dxWDL](https://github.com/dnanexus/dxWDL) - takes a pipeline written in WDL and compiles it to an equivalent workflow on the DNAnexus platform. WDL draft-2, version 1.0, and the development version are supported
 - [wdlTools](https://github.com/dnanexus-rnd/wdlTools) - Scala programming language library for parsing WDL, and command-line tools for type-checking, code formatting, and more.
 ---

### 📺 Click below to WATCH 'Course Intro Video' (10 min) on YouTube

[![Welcome to Learn WDL](/images/learn-wdl-intro.png)](https://www.youtube.com/watch?v=RtcW2Zdn_28 "Welcome to Learn WDL")

---


### YouTube Playlist 

https://www.youtube.com/playlist?list=PL4Q4HssKcxYv5syJKUKRrD8Fbd-_CnxTM 

---

### To run WDL you need to install Cromwell/MiniWDL/womtool
git clone the latest release from https://github.com/broadinstitute/cromwell

```
# Run the workflow and print out the outputs in a JSON format
java -jar <cromwell.jar> run <file.wdl>
java -jar <cromwell.jar> run <file.wdl> -i <input.json>

# Submit the workflow to a Cromwell server
java -jar <cromwell.jar> submit <file.wdl>

# Validate a workflow source file. If inputs are provided then 'validate' also checks that the inputs file is a valid set of inputs for the workflow.
java -jar <womtool.jar> validate <file.wdl>

# Generate and output a new inputs JSON for this workflow.
java -jar <womtool.jar> inputs <file.wdl>

# Generate and output a list of output types in JSON for this workflow.
java -jar <womtool.jar> outputs <file.wdl>

# Generate and output a graph visualization of the workflow in .dot format
java -jar <womtool.jar> graph <file.wdl>
```

---

### Execution environments
- Google Cloud
- Terra Bio
- Cromwell
- MiniWDL