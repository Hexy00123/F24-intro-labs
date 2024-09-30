# Introduction to DevOps Lab 9
## Ruslan Izmailov B22-DS-01 

### Task 1: Create Your First GitHub Actions Pipeline

#### 1. Create directory to pipeline configs: 
```sh
> mkdir -p .github/workflows 
```

#### 2. Create pipeline config: 
```sh
touch .github/workflows/github-actions-demo.yml
```

#### 3. Write a pipeline: 
Just put the following content to github-actions-demo.yml.  

```sh
name: GitHub Actions Demo
run-name: ${{ github.actor }} is testing out GitHub Actions 🚀
on: [push]
jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code
        uses: actions/checkout@v4
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
```

#### 4. Results: 
