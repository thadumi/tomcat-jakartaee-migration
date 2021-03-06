# Apache Tomcat migration tool for Jakarta EE

## Overview

This tool is a work in progress.

The aim of the tool is to take a web application written for Java EE 8 that runs on Apache Tomcat 9 and convert it automatically so it runs on Apache Tomcat 10 which implements Jakarta EE 9.

## Usage

### Build

Build the migration tool with:

    ./mvnw verify

### Migrate

Migrate your Servlet application with:

    java -jar target/jakartaee-migration-*-shaded.jar <source> <destination>

The source should be a path to a compressed archive, a folder or an individual file. The destination will be created at the specified path as a resource of the same type as the source.

> **INFO**
> This tool will remove cryptographic signatures from JAR files contained in the *source*, as the changed resources would not match them anymore.
>
> A warning will be logged for each JAR file where the signature has been removed.

## Differences between Java EE 8 and Jakarta EE 9

Jakarta EE 9 is still under development and there are some details that remain to be worked out.

The differences currently supported by this tool are:

* Renaming packages for Jakarta EE 9 APIs from `javax.*` to `jakarta.*`

The differences yet to be implemented by this tool are:

* Remaining issues once resolved

The issues still to be resolved by the Jakarta EE projects that will impact this tool are:

* XML schemas
