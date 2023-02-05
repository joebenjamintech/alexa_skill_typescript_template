# AWS Lambda Hosted Alexa Skill w/ Typescript Boilerplate and Debugging in VIM

------
# Requirements

## Vimspector
* vimspector is a multi language graphical debugger for vim
* must have [vimspector](https://github.com/puremourning/vimspector) plugin for vim
  * the site shows 3 different ways to get the plugin setup in vim

## AWS
* must have AWS IAM user set up to use AWS Lambda to host your skills
* user must have access keys to be able to send programmatic calls to AWS from the AWS CLI
* the user must have the correct [credentials](https://developer.amazon.com/en-US/docs/alexa/smapi/manage-credentials-with-ask-cli.html#create-aws-credentials) --- could also be a user with the AdministratorAccess policy which basically allows for everything (but be careful b/c it means the user can do anything on your AWS account)
* must have [AWS CLI](https://aws.amazon.com/cli/) installed
* use aws configure to set up aws profile, this profile will be used by the alexa skill kit cli

## ASK
* must have an [amazon developer account](https://developer.amazon.com)
* must have [ASK CLI](https://developer.amazon.com/en-US/docs/alexa/smapi/quick-start-alexa-skills-kit-command-line-interface.html) installed
* use ask configure to set up ask profile

------
* There are two main folders
  * boilerplate
    * the boilerplate for the alexa skill
    * the vimspector file
  * scripts
    * **I have only run these scripts on linux**
      * you could prob run on windows by using git bash --
      * for mac, if any of the commands fail, it may be a slight change in the command between linux and mac (you would have to make that update)
    * ask_access_token_set
      * must configure ask cli for this to work 
      * this will be used whenever you need to update/set your access token to a valid one
      * uses the ask cli to generate a token
      * saves the token in your .zshrc file (if using .bashrc, change .zshrc to .bashrc)
      * this assumes you already have a line in your .zshrc file in the format ``` export ASK_ACCESS_TOKEN="some_random_token" ```
    * ask_access_token_get
      * this will be used inside of vimspector to grab the token needed to debug 
      * gets the access token from your .zshrc file (if using .bashrc, change .zshrc to .bashrc)
      * uses sed to find the token in your .zshrc file in the format ``` export ASK_ACCESS_TOKEN="some_random_token" ```
    * ask_skill_id_get
      * must configure ask cli for this to work
      * must have [jq](https://stedolan.github.io/jq/download/) installed 
      * uses the ask cli and jq ( to get back the skill id from the skill_name passed in
    * ask_boilerplate_setup
      * grabs the boilerplate and copies all to a new folder of your choice
      * updates the skill name and invocation name to the skill name passed in
        * the invocation name will be the skill name with underscores replaced as spaces
      * runs npm install to install the packages
      * if passed in deploy as 3rd param, will go ahead and run build-deploy for you
