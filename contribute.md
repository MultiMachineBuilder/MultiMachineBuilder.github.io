---
layout: page
title:  "Contribute"
categories: help
---
## IDE used
I use Eclipse. Use Eclipse to be able to import the project settings.

## Plugins
* SonarLint
* WindowBuilder
* ResourceBundle editor
* [Eclipse Maven integration (M2E extension) for null analysis](https://github.com/lastnpe/eclipse-external-annotations-m2e-plugin)

## IDE setup
0. Import the project (#How to contribute)
1. Download and install Eclipse with JDT
2. Import the 'MultiMachineBuilder' project in Eclipse
3. Enter `https://github.com/MultiMachineBuilder/MultiMachineBuilder` as the URI
4. Create a Personal Access Token for your account with only full repository access.
5. Provide your username, and PAT instead of a password.
Store the credentials in Secure Store, because PAT won't appear ever again
6. Ask me at the organization's email for guidance to link your SonarLint to the SonarCloud

## How to contribute
1. Fork the project and create a draft pull request from your fork to the main repo
2. Import your fork into eclipse (like steps 3 and 5 of IDE setup, but with your fork)
2. Pull the desired branch (usually `master`) using Eclipse.
3. Write some code, translate the game, or create assets in Eclipse
4. Test your changes
5. Commit small changes often
6. When finished work, convert PR to ready to review
7. Discuss changes and adjust them
8. When you agree with Monniasza, request a merge
9. Monniasza merges your changes
10. Your changes are integrated with the game