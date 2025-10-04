# Lab – Sequential Workflow with Artifacts

## Overview
This lab demonstrates how to **pass files (artifacts) between jobs** in a GitHub Actions workflow. Artifacts allow one job to **share data with another**, enabling sequential workflows that depend on generated files.

---

## Repo
`sequential-artifacts`

---

## Workflow Concept

- The workflow runs **on every push**.  
- It contains two jobs:  
  1. **Build job** – creates a file (`version.txt`) and uploads it as an artifact.  
  2. **Test job** – depends on the build job (`needs: build`) and downloads the artifact to use it.  

---

## Purpose / Scope

- Learn how to **upload and download artifacts** between jobs.  
- Understand **sequential workflows** where one job’s output is used by another.  
- Useful in real-world CI/CD pipelines where **build outputs are needed in later steps**.

---

## Expected Results

- After pushing a commit:  
  1. The **build** job creates `version.txt` and uploads it.  
  2. The **test** job runs after build, downloads the artifact, and displays its content (`version 1.0`).  
- The Actions tab shows **two jobs running sequentially**.  

---

## Key Takeaway

Artifacts make it possible to **share files between jobs**, allowing workflows to pass data along a sequence of steps. This is essential for **real-world CI/CD pipelines** where jobs are interdependent.
