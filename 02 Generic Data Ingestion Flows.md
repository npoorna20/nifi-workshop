# Generic Data Ingestion Flows

Let us understand how to build Generic Data Ingestion flows in this session. 

* Recap of simple pipeline
* Recap of Flowfiles and Attributes
* Overview of Scheduling
* Files to Flowfiles - Options
* Build Generic Pipeline
* Quick Overview of NiFi Expression Language

The content will be free, however if you want to watch videos to understand key concepts feel free to [join our YouTube Channel as a member](https://www.youtube.com/channel/UCakdSIPsJqiOLqylgoYmwQg/join).

[![NiFi - Building Generic Data Flows](http://img.youtube.com/vi/iZQI-i8PWY4/0.jpg)](http://www.youtube.com/watch?v=iZQI-i8PWY4 "NiFi - Building Generic Data Flows")


## Recap of simple pipeline
Earlier we have understood simple data ingestion pipeline using NiFi.
* Processor Group
* Processors
* Settings
* Scheduling
* Properties
* Connecting multiple Processors

## Recap of Flowfiles and Attributes
Let us recap of core data structures as part of NiFi.
* Flowfiles are the ones which will contain the data.
* Attributes consists of metadata generated by processors.
* We can review the contents of flowfiles using Data Provenance of the processor.

## Overview of Scheduling
NiFi supports 2 types of scheduling.
* Timer based
* Cron based

## Files to Flowfiles - Options
Here are the design patterns with respect to gettig data from files to flowfiles.
* List + Fetch (ListFile + FetchFile)
* Get (GetFile)
We can get data from local file system, HDFS, AWS S3, Azure Blob, SFTP and many more.

Flowfiles can also be saved to Files in all supported file systems.

## Build Generic Pipeline

Here are the instructions building generic pipeline.
* Use listFile to get the files recursively.
* Configure Age Attributes as per requirement.
* Use fetchFile to fetch files.
* Update attribute to define target location using Update Attribute Processor. We can use NiFi Expression Language for the same.
```
${absolute.path:substringBeforeLast('/'):substringAfterLast('/')}
```
* Use PutHDFS to save the files in the HDFS. We can simulate source directory structure while writing data to target file system.

## Quick Overview of NiFi Expression Language

Let us understand more about NiFi Expression Language.
* It is extensively used to mutate flowfiles or attributes.
* We can also use NiFi Expression Language as part of conditional flows using processors such as **Route On Attribute**.
* NiFi Expression Language provides robust set of functions for data manipulation as well as traversing to JSON Paths.
* We have used expression language as part of previous topics in this module. We will see more as we get into more complex modules.
