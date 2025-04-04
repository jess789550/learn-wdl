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


### YouTube Playlists

- Cromwell: https://www.youtube.com/playlist?list=PL4Q4HssKcxYv5syJKUKRrD8Fbd-_CnxTM
- MiniWDL: https://www.youtube.com/playlist?list=PL4Q4HssKcxYv1FQJUD6D1Cu0Q1O-_S1hM

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

################################################

# MiniWDL: https://miniwdl.readthedocs.io/en/latest/runner_cli.html
miniwdl run -i <input.json>

# To aid the workflow development cycle, miniwdl includes a code quality checker which statically analyzes WDL source code to generate warnings and suggestions.
miniwdl check <file.wdl>

# miniwdl input_template generates a JSON skeleton for the inputs required to run a given WDL.
miniwdl input_template <file.wdl> > <file.json>

# miniwdl zip generates a ZIP file including a given WDL source code file and any other WDL files it imports. 
miniwdl zip <file.wdl>
```

---

### Execution environments
- Google Cloud
- Terra Bio
- Cromwell
- MiniWDL

---

### Variable types

https://docs.openwdl.org/language-guide/variables.html#variables

---

### Quickstart guide

https://docs.openwdl.org/getting-started/quickstart.html

- Tasks are comprise of inputs, outputs, and a command. Support requirements.
- Workflows string together tasks via inputs/outputs into larger computation graph that can be executed. Can use if statements, scatter keyword, and messages output.
- JSON is used for specifying both inputs to and outputs from a workflow. 


---

### Multi-input/Multi-output

- Linear chaining relies on hierarchial naming https://support.terra.bio/hc/en-us/articles/360037128532-Multi-input-Multi-output
- You can connect multiple outputs to  multiple inputs https://support.terra.bio/hc/en-us/articles/360037128532-Multi-input-Multi-output

---

### Structs

- Custom types that you can define
- Member fields with name and associated type
- Like a Class in Python
- Group items together in category
- https://docs.openwdl.org/language-guide/structs.html

---

### Scatter-gather

- Parallel computing
- Computation split into smaller, independent pieces
- Multiple, parallel executions
- Gather into single results
- Optimise speed
- https://docs.openwdl.org/design-patterns/scatter-gather/index.html
