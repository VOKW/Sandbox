---
layout: archive
title: DevOps Release Process
section: DevOps Release
permalink: /va-release/
---

# Steps for following the the VA DevOps Release process
* <strong> Delivering features to end users faster </strong>
* <strong> Delivering features with higher quality standards </strong>
* <strong> Reducing risk by releasing in smaller batches </strong>

## Step 0:Understanding the users need

## Step 1: Create a ticket to define and track the work
* A ticket (or some ticket tracking products call them “issues”) should be created that documents the problem, feature required, or other change to make, as well as describing the steps needed to identify a solution. All tickets should relate back to an user need identified in Step 0.
* Clear success criteria should be defined within this ticket. Possible solutions may be included in the ticket, but are not required.
* Possible solutions may be included in the ticket, but are not required. The final decision on what solution to implement is made by the person working on the ticket after reviewing the user need and discussing with the team.
* Tickets should be broken into manageable chunks; an individual ticket should not take more than 1-2 person-days of work to resolve, while most tickets should be significantly smaller than that.
* All new work should be tied to a specific ticket, so changes can be traced to tickets and then back to a specific user need.

## Step 2: Develop new feature in a branch
* After a ticket is created, a team member should create a feature branch within the source code version control and begin implementation based on the details of the ticket, committing code along the way directly to their feature branch.
* As the team member is implementing the feature, they should add automated unit, integration, or end-to-end tests, ensuring a high level of code coverage. All code committed should include tests that validate that code works, including negative and edge cases.
* A good practice is to write tests prior to implementing the feature; the test should fail, and then pass upon completion of the feature.
* The team member should regularly merge the latest master branch into their feature branch to ensure their feature branch does not become stale as compared to the master branch.

## Step 3: Create pull request and run automated tests
* When the developer believes the ticket is complete, they should create a pull request to request to merge their feature branch code into the main development branch (often the ‘master’ branch). The pull request should reference the ticket the change addresses.
* When the pull request is created, the automated test server should run the full suite of unit, integration, and endtoend tests.
* Scans should also run to perform both static code analysis, to scan for common security vulnerabilities, and dependency vulnerability detection, to check if any dependencies being used have known vulnerabilities.
* Linters should run to ensure consistent styling and catch detectable bugs or unused sections of code.
* If any of these automated tests, scans, or linters fail, the developer should be automatically notified and should return to Step 2 to address the problems.

## Step 4: Code Review
* Once all the automated tests, scans, and linters have passed and before any code can be merged into the master branch*, it needs to be reviewed by a qualified teammate or teammates who did not make this change. The changes for each feature branch should be manageable chunks for a teammate to review, generally not more than one hundred lines of changes. If the reviewer(s) is unable to understand every proposed change, the changes should be broken up into smaller tickets in Step 1 and reviewed individually.
* The code reviewer(s) should look for everything from content and design accuracy to technical and security considerations. Reviews should also verify the proposed change includes automated tests that verify the new functionality. Code reviews are the last line of defense for catching bugs, stopping bad architectural changes, and making sure that things being added are in sync with user needs. They should be taken seriously and not rubber stamped.

## Step 5: Merge code, deploy to nonproduction environment(s), verify functionality
* Once the code has been reviewed and approved, the feature branch should be merged into the master branch.
* This act should automatically begin a process in which all tests, including long running tests that were not run when the pull request was created because of the length of time they take, such as accessibility scans run to verify 508 compliance or code security scans, should be run on the master branch after each merge to test for regressions.
* Once all tests pass, the code should be automatically deployed to a nonproduction environment (often known as “development” or “QA”). If the tests do not pass on the master branch (or other main development branch), the team should return to Step 1 to create a ticket and quickly address the problem. Tests should rarely fail on the master branch and when they do, it should be remediated as quickly as possible. To keep velocity high, the master branch must not be left in a state in which tests are failing, since all members of the team will be referencing the validity of their specific changes against the master branch.
* This nonproduction environment gives the team, stakeholders, and product owner the ability to test the updated functionality. Usability testing may also be performed on this nonproduction environment to test for any bugs or usability issues prior to the code being deployed to production.

## Step 6: Production approval
* The VA product owner, or their designee, has sole discretion of when to release code to production. There is no requirement that a meeting needs to occur or concurrence needs to be received from anyone else for updates to be made to production.  The only condition the VA product owner must consider in exercising their discretion is whether the release will improve or diminish the user experience.
* For low risk or minor updates, such as bug fixes or content updates, it is expected that the VA product owner may delegate the decision to make a production deployment to the product manager or engineering lead closest to the work. If the product owner approves, it is also possible that production deployments of the latest master branch will occur automatically at a given time daily; this is possible because the master branch only has code that has been reviewed by a qualified teammate and all automated tests have passed.
* For major updates, such as new pieces of functionality, the product owner will likely want to be involved in seeing and verifying the functionality directly addresses the user needs documented in Step 0, as well as conferring with business partners, before approving the production deployment.
* Once the product owner gives the goahead to get the updated code in production, the team should begin an automatic production deployment.

## Step 7: Build code and create necessary artifacts
* An artifact, such as a GitHub release, should be created to automatically show the differences in version control from the previous deployment. This allows tracking of what changed between each release (for both compliance and debugging if issues arise) without adding additional burden of humans having to document this manually.
* A test log, such as the output from Jenkins, should be permanently stored to validate that the tests, scans, and linters all passed. Additionally, a reference, such as a GitHub Release, should be created to the exact code that was deployed to production.  This documentation allows auditability of what ran before code got to production and what code was in production at a specific time.

## Step 8: Deploy to Production
* Once the artifacts have been created, the code should be deployed to production with zero downtime to users using the same automated deployment tools described in step 5.
* It is a best practice to send a small percentage of traffic to the new version of the code and measure for unusual activity or responses, before ramping up traffic to the new version, eventually getting to 100% of traffic on the new version and being able to automatically destroy the previous environment.
* If necessary, it should be possible to quickly “roll back” any production deployment either by redeploying the previous version, or falling back to the previous copy of “production” which will remain deployed for some period (i.e. an hour).
* Except in rare cases where downtime is anticipated and overtime is planned, it is a best practice to avoid issuing major releases on Fridays, weekends, days before holidays, or other periods in which key personnel are likely to be difficult to reach in case issues arise.

## Step 9: Measure
* Teams need to continually test and measure the products they build with real users to keep themselves honest about what is important, and what is and isn’t working. KPIs should be measured over time and against the previously identified baseline and goals.
* Team retrospectives should be conducted on a regular basis, such as at the end of each sprint, to learn what went well and what could be improved in the process.  Lessons learned should be adapted into future sprints. 

## Step 10: Iterate
* After a successful production deployment, teams should start back at Step 0 to determine if the user need has been met, regardless if there are still open tickets that were created in Step 1. User research may need to be performed to understand if this is the case.
* If the need has not been met, evaluate any outstanding tickets in light of the latest release. There may be a need to further “groom” and reprioritize these tickets before for moving through the process again. 
