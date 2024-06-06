# Get started with GA integration with JFrog

This project has several workflows, each progresing on integration steps between GitHub Actions and JFrog. Follow each build by number to understand the integration points. 

Each build is configure to be executed manually.

## Pre-reqs
You can read detailed documentation about how OIDC works, but the most important thing to understand is that GirHub and JFrog exchange tokens to validate each other's trust. 

- Clone this project
- Set these environment variables for GitHub Actions (GH Repo - > Settings->Secrets and variables->Variables)
    - JF_URL:  JFrog Domain on (Eg. soleng.jfrog.io)
    - JF_PROJECT: Your project name
- Setup OIDC integration in JFrog
    - NOTE: **at this point, do not set identity mapping**
    - Provider Name: remember this, you will need it.
    - Provider Type: GitHub
    - Leave the rest blank

## 1.ga-jfrog-primer-oidc.yaml
In this action we will explore the token we receive from GitHub. I am taking you trhrough this because you will need to understand the payload to construct a claim for the identity mapping. The only purpose of this action is to intercept the token and review it.

1. Go to https://webhook.site 
2. Copy url (Eg. webhook.site/f90405ea-3192-44c7-b8c5-0618011f0949)
![Image](assets/webhook-site-url.png)
3. Change the GH repo variable JF_URL to the url you got (it should be domain/uuid)
4. Run the workflow
5. Watch the webhook.site activity.
    - You should see the payload with the token.







