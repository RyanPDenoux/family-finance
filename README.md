
# Table of Contents

1.  [Purpose](#orgb902626)
2.  [Methodology](#orgea54de3)
    1.  [Ingestion](#orgeb95a3e)
        1.  [Transactions](#orgef903f8)
        2.  [Batch File](#orgbab86f0)
    2.  [Display](#orga8e09ce)
        1.  [CLI](#org45e2b14)
        2.  [GUI](#org0f358d3)
    3.  [Processing](#org5515bb1)
    4.  [Lib](#org19e3ea1)
        1.  [Repository](#org9ce6358)
        2.  [Utilites](#org7cbb064)
3.  [Tech in Use](#org8d76356)
    1.  [Pandas](#org31e466b)
    2.  [Dash](#org973f3e4)
    3.  [SQLAlchemy](#org183510c)



<a id="orgb902626"></a>

# Purpose

This program exists to help ingest and store transactions recorded by any source into a validated repository to guarantee that financial behavior is properly tracked. This should be easily started with any source and add to a repository of transactions in a hands off way to the user. Once transactions have been ingested, aggregate data should be ready to pull into meaningful statistics about spending habits and trends.


<a id="orgea54de3"></a>

# Methodology

I will implement this using the Ports and Adapters methodology through Object-Oriented patterns. While I am interested in the Funtional Paradigm, I need to get this built up before the next calendar year. Functional concerns will dictact the number of contexts necessary to get the program off the ground and running. Here are the contexts for this program


<a id="orgeb95a3e"></a>

## Ingestion

Responsible for taking in single transactions to entire file batches. It should be intelligent enough to parse input from different source and should conform it to the repository standard.


<a id="orgef903f8"></a>

### Transactions

Single line transactions should be eventually feasible and conform to the data schema


<a id="orgbab86f0"></a>

### Batch File

This is where the majority of input should come from. Should be able to handle overlapping records by using the repository object to ensure no duplicate transactions. Batch files should be able to take any text file spec and parse incoming data into usable records.


<a id="orga8e09ce"></a>

## Display

Responsible for communicating with the user about the status of current jobs or answering queries about stored data. Beyond the simple CLI, the user should eventually be able to interface with this through some GUI interface.


<a id="org45e2b14"></a>

### CLI

Probably where most user time spent issuing jobs and managing data.


<a id="org0f358d3"></a>

### GUI

This is going to take time to get done, and might only end up being locally hosted Dash apps.


<a id="org5515bb1"></a>

## Processing

Responsible for running analyses on stored data and delivering prepared (eventually live insights) about stored data


<a id="org19e3ea1"></a>

## Lib

Here is where all the shared resources are collected for the other contexts to freely use. Repository is defined and implemented here for all other contexts.


<a id="org9ce6358"></a>

### Repository

This will define how the data are shaped in storage and how it should be presented to each of the contexts. Each context will be required to use interfaces provided here to interact with the persistent data. In addition, the concept of the repository should be flexible enough to allow for different implementations to be used and translated between. It&rsquo;s almost a certainty that a transaction history will be started as a simple text file, converted into a database, then at some point dumped back out into a file artifact as machines and tech are upgraded.


<a id="org7cbb064"></a>

### Utilites

Self explanatory place for common tools.


<a id="org8d76356"></a>

# Tech in Use

The interface will be written in Python to use packages such as [Pandas](https://pandas.pydata.org/) for data processing, [Dash](https://plotly.com/dash/) for visualization, and [SQLAlchemy](https://www.sqlalchemy.org/) for simplified ORM access to the repository. I will keep the storage medium open for now, but plan to support single-file and database storage for the project.


<a id="org31e466b"></a>

## Pandas

Pandas will power data processing and potentially ingestion


<a id="org973f3e4"></a>

## Dash

Go to for data visualization


<a id="org183510c"></a>

## SQLAlchemy

It&rsquo;s magic

