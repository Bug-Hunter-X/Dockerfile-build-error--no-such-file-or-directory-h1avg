# Dockerfile Build Error: No such file or directory

This repository demonstrates a common error encountered when building Docker images: the inability to find a file during the COPY instruction.  The provided Dockerfile attempts to copy `app.py`, but this file might not be present in the build context or might be in the wrong directory.

## Problem

The primary issue is with how the context of the build is handled. If `app.py` isn't directly within the directory from which you run `docker build`, the COPY instruction will fail.  The solution involves properly setting up the build context to include all necessary files.

## Solution

A detailed solution is provided in the `DockerfileSolution.txt` file to show how to fix the issue.

## How to reproduce the error:
1. Create a new directory.
2. Create `Dockerfile` with the buggy content.
3. **Do not** create `app.py` in the same directory.
4. Run `docker build -t my-image .`
5. Observe the error message about a missing file.

## How to fix the error:
1. Follow the corrected Dockerfile in `DockerfileSolution.txt`
2. Create a directory structure as described in the solution.  Ensure you have `app.py` correctly placed.
3. Run `docker build -t my-image .`