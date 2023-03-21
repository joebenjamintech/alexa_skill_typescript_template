# AWS Lambda Hosted Alexa Skill w/ Typescript Boilerplate

This repository is a template repository you can use as a quickstart to building your own Alex Skills.

# Requirements

Before you begin using this repository, please ensure that you have:

- An [AWS developer account](https://developer.amazon.com)
- The [ASK CLI](https://developer.amazon.com/en-US/docs/alexa/smapi/quick-start-alexa-skills-kit-command-line-interface.html) installed and configured

# Getting Started

1. Use GitHub's "Create from Template" functionality via either:
  - [GitHub web UI](./generate)
  - [GitHub CLI](https://cli.github.com):  
    `gh repo create --template joedbenjamin/alexa_skill_typescript_template`

2. Once the repo is created, clone it and run the following script:
`./init_repo`
  This will initialize the template with a skill name and invocation name matching your current directory.
  Alternately, provide the skill name you would like to use, e.g.:
  `./init_repo the_coolest_skill_ever`

3. Start coding and deploy your new Alexa Skill
4. Profit!

# Repository Structure

This repository contains the following files:

```
.
├── .vscode            # configuration files for VS Code editor
├── scripts            # scripts for local development
│   ├── get_ask_skill_id      # reads the Skill ID from local files
│   ├── get_ask_token         # requests ASK token from ASK website
│   ├── get_env               # reads variables into memory for running tasks
│   └── set_ask_access_token  # generates and saves a new ASK Access Token
│                             # using the ASK CLI
├── skill              # source code and config for the Alexa Skill
│   ├── lambda         # source code for the Alexa Skill Lambda
│   └── skill-package  # configuration for the Alexa Skill
├── init_repo          # initialization script (will self-destruct!)
└── README.md
```
