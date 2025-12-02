<<<<<<< HEAD
# devops_assignment
CRUD-DD-TASK-MEAN-APP
This repository contains a full-stack MEAN (MongoDB, Express, Angular, Node.js) application deployed using Docker on AWS. This setup was implemented as part of the DevOps Engineer Intern Assignment.
=======
Website URL - http://16.170.254.214/
# devops-mean-deploy
# DevOps MEAN App Deployment

## Overview
This repo contains Dockerfiles, docker-compose and GitHub Actions to build, push and deploy a MEAN app.

## Files added
- backend
- frontend
- docker-compose.yml
- nginx.conf
- .github/workflows/ci-cd.yml

## How to run
1. Create Docker Hub repos and set Secrets in GitHub:
   - DOCKERHUB_USERNAME
   - DOCKERHUB_TOKEN
   - SSH_PRIVATE_KEY
   - VM_HOST
   - VM_USER
   - VM_SSH_PORT

2. Provision Ubuntu VM (open ports 22 & 80) and install docker & compose:
   (see commands in repo or in the task description)

3. Push code to main → GitHub Actions will build and push images and deploy to VM.

## Verification
- Visit http://YOUR_VM_IP to see the frontend.
- API calls are proxied to /api/ to the backend.

## Screenshots

Github Actions CI/CD Pipeline for MEAN App Deployment

(Attach CI run, Docker Hub, VM docker ps, website)





