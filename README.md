# time-tracker

## Simple time tracker :watch: for teams, built with [Remix](https://remix.run/).

*The main purpose of the project is for me to learn about Remix, JSX and other useful stuff.*

### Non-functional requirements

1. Dead simple. We don't want the users to feel that using the tracker is a burden.
2. Should be fast enough, to not be infuriating to use.
3. Must work **ALL** the time. We don't want the tracker to stop working in the middle of the day or to be unable to start/stop tracking, because that would hurt the data in a big way.

### Functional requirements

1. Authentication. 
   - This data is probably considered sensitive to the company, so it should definitely be kept a secret from outsiders.
   - We must provide multiple choices for the users when it comes to login:
     - Github/GitLab OAuth sounds cool (and probably necessary).
     - Email/username - password login is also neccessary, because there might be people with no GH/GL accounts, that might also need to view the data.
   - This data could be cached, so the users wouldn't have to login every time they close their browser.
2. Authorization.
   - Users with different [Roles](#roles) will be able to access different data, so we will have to make the distinction between users.

### Roles

1. Developers/engineers/workers/whateveryoucallthem.
   - The users who want to track their work.
   - It is fine to assume they have a Github/GitLab account, which they are required to use, in order to scrape the tasks.
   - These users can only see and track their own tasks.
   - After logging in, users should see all of the tasks associated with them, where they can search, filter or start tracking instantly. 
   - These should be grouped by organizations and/or repositories. These groups should be highly customizable (ordering, maybe even "staring" them).
   - Users should be able to make a *"priority list"* from their tasks. 
     - Also, this could also be a useful feature for project managers as well, where they could prioritize tasks for developers.
2. Project managers/business/team leads
   - It might be useful for the team leads to evaluate the sprint and the estimations based on the tracked data.
   - For end-of-month reports/summaries it is nice-to-have this data in one place, aggregated, ready-to-use.
   - This data should be highly searchable, filterable and exportable in some format (e.g. CSV).
   - These users should be able to view everyone else's work, but no way to influence them in any way.
     - We might assume that for the team leads they would have their own tasks - *on which they could operate* - but also view other people's progress. So they will probably become a separate role in the near future.
