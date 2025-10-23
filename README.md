# CI/CD Template Repository

This repository contains a **reusable CI/CD workflow** for building, testing, and deploying Docker-based applications.  

## How to Use

In your project repository, create a `.github/workflows/pipeline.yml` file like:

```yaml
name: CI/CD Pipeline

on:
  push:
      branches:
            - main
                  - develop
                        - release/*

                        jobs:
                          ci-cd:
                              uses: org/cicd-templates/.github/workflows/ci-cd-template.yml@v1
                                  with:
                                        branch-name: ${{ github.ref_name }}
                                              environment: dev
                                                    docker-image-tag: myapp:${{ github.ref_name }}-${{ github.sha }}

