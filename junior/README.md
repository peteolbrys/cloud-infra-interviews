# Interview Questions for a Junior DevOps/SRE/Cloud Infrastructure Engineer

## Before You Begin

### Notes

The questions in this interview are not meant to be 100% correct. In my eyes, it is not possible to fully grasp what this role entails until you've done it for a few years. These questions are designed and presented in a way that hopefully showcases the way you think and communicate versus the actual solution. Essentially, be ready to talk about anything you have put together during the video call next week.

With that said, please follow these below guidelines. It is tough to interview entry level candidates for a career path that most software developers don't even understand fully, so I am going into this trusting that you can do research and present your thoughts clearly.

- Do not use ChatGPT/any flavor of the month generative AI tool. There is a time and place in a technical career for that type of help, but you are going to hamstring yourself if you don't learn the hows and whys before you go straight for the answer.
- While researching the questions, do a bit of a deep dive and please take notes as you go. These questions are common topics in this world, so if you learn something now, it will absolutely benefit you in the future.
- Don't spend too much mental energy on this. You have a week to prepare on purpose, split it out across multiple days and take breaks if you feel burnt out. In the real world, you aren't going to complete most *slightly more than* complicated tasks in one day. This take home is no exception.

Please, if you have any questions or get stuck, please email me at pete.olbrys@gmail.com.

### Pre-requisites

- Create a Github account if you do not have one already.
- Install and configure the Github CLI.
- Create and add an SSH key to your account for CLI access.
- Fork this repo. Name it as you see fit.
- Clone the repo on your local machine.
- Set the repo to private.
- Add me (Github username: peteolbrys) as a collaborator.
- Create a test commit and push to verify your local setup is correct. Feel free to use the `--empty-commit` flag.

## Questions 

When answering these questions, please create a separate text file (or markdown file if you feel fancy) for each, and commit changes as you go.

### Question 1 - Cloud Infrastructure

Describe and/or diagram a solution to the following scenario.

```There is a development feature team that is nearing code complete on a new microservice. This service is fairly simple: a Javascript front end landing page for customers to view data, a Python backend to manage the data, and a Postgres database to serve the data. The development team have already containerized the three parts that make up the microservice as a whole, and has asked that we build the infrastructure in our AWS account so they can be begin testing with production level loads and datasets.```

Here are some assumptions you can make:
- The database DOES NOT need to run in a container.
- They do not have a chosen technology to serve the Front End static artifacts yet. The Development environment uses Nginx, but the configuration is too hacky to use in Prod and would need to be rewritten from the ground up if chosen.
- The Python is ready to run inside it's container, no modifications needed.

While you research and design a solution, consider the following questions:
- How would you reliably and consistently build the containers?
- Where would you store the containers after they are built?
- How would you run the containers in AWS?
- What would you do with the database?
- What networking would be necessary for your solution?
- How would build all of this infrastructure?

### Question 2 - Site Reliability

Using your solution from Question 1, what would you do to create resiliency and fault tolerance to your setup? For example:
- How would you mitigate an issue with a network outage in your chosen availability zone?
- How would you handle interruptions in end-user service access when deployments occur?
- What would you do if your database had a catastrophic failure?

Bonus points: Feel free to expand beyond the three examples above in any other ways you can think of/find during your research.

### Question 3 - Security

Using your solution from Question 1, what would you do to make your infrastructure secure? For example:
- How would you lock down access from malicious actors (on the infra-side, ignore anything that can be done application-side)?
- What are necessary components for hosting a modern web front end?

Bonus points: Feel free to expand beyond the two examples above in any other ways you can think of/find during your research.

### Bonus round - Development Operations

DevOps by definition is a collaborative culture between software developers, QA testers, systems engineers, security, etc. Part of this is creating/implementing tooling to make the process of getting code from keyboard to production as painlessly and seamlessly as possible.

- What tooling would you implement to automate things (things being builds, tests, etc.)?
- Using your solution from Question 1, how would utilize your automation tooling to connect to your infrastructure?
- How would you notify users of events from automation tooling?

