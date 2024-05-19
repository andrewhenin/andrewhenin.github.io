---
layout: post
title: A Hot July at Duolingo - Summer 2023
---

The second month allowed a steady pace of work. Daily tasks seemed somewhat more manageable, even predictable at times. I grew more comfortable approaching my project and using the internal tools. By the way, while I was preparing for this post I realized that I have pictures that I can share! Some of them are screenshots from the project that I got the permission to share publically. I will also dedicate a different post on the non-technical side of my time there.

## The Daily Standups

In the second third of the internship, we got down in the weeds with our project. I said the word "PR" (for Pull Request) more times than a toddler says "why." I faced a few issues with Docker, Git, and even the coffee machine. At times, nothing was working, and at other times, everything would just magically fill into place.

### 07/03 (Monday)
I thankfully had no challenges, because I was mainly reviewing critical PRs that day. I also worked on Jira to update our backlog.

### 07/04 (4th of July)

### 07/05 (Wednesday)
> Updates:
> - I was able to add a chatbox that stacks the messages we input and send.
> - I’m currently working on the Summary API DAL <i>(The Data Access Layer)</i>.
> 
> Blockers:
> - I’m facing some difficulty in storing the API Key as a secret variable in the repository. I’m not sure how sensitive the key is. I thought of adding it to the `.yml` files. <i>This is bad practice. I realized this later.</i>
> 
> Next steps:
> - This afternoon, I will continue working on the chatbox. We will add the “Get me a Summary” button and some styling.

### 07/06 (Thursday)
I finished the Summary DAL and finalized unit tests. I remember I found so much joy in building unit tests for any added functionality. I was absorbed in testing for a few weeks. This was the first time we received meaningful responses from OpenAI GPT-4 API! It was a moment of euphoria. I was so happy to write that PR.

I had a lot of linting issues. It was always a reminder to learn the best practices of coding in TypeScript. I would read articles on that every now and then towards the end of my work day.

### 07/07 (Friday)
> Updates:
> - I submitted another Terraform PR for the database, but it’s blocked by the Summary DAL PR, because it has Terraform changes, which must be resolved first.
>
> Blockers:
> - The pre-commit test that is failing “Library stubs are missing”
>
> Next steps:
> - Regarding the front-end work, I will have to work on it today, since next week is Hackathon, so we have to finalize it today and submit a PR.

### 07/10, 07/11, and 07/12 (Hackathon)

Duolingo dedicates a whole week for a hackathon. See the [CTO's post on LinkedIn](https://www.linkedin.com/posts/severinhacker_duolingo-innovation-hackathon-activity-7186038155458879488-ZjMU/) for more info. I participated in it during the summer, but I'm not sure I can share the work unfortunately. My team needed me for only the first three days.

### 07/13 (Thursday)

I was finally done with the Summary API DAL! After setting up the backend, we started discussing the frontend architecture. I had some confusion about the button "Explain more" in the chatbox, which is supposed to provide more in-depth explanation about something, and I wasn't sure if that was concerning the provided summary of the paragraph or the paragraph itself. I asked my manager for a task as well. In retrospect, that was such a nerd move.

### 07/14 (Friday)

> Updates:
> - I looked at how to call the functions my teammate built for accessing the book API. 
> - For the rest of the day I will build functions to communicate with the Summary API from the frontend.
>
> Blockers:
> - Not really blockers, but I’m waiting for the final versions of the chatbox.
>
> Next steps:
> - Will try to merge the repos that are about to be merged so I’m able to work with them, and later hopefully I shouldn’t have a lot of merge conflicts.

### 07/17 (Monday)
Sprint Planning

### 07/18 (Tuesday)
> Updates:
> - Finished the button after some help from my teammate to explain his chatbox work
> - Reviewed the frontend PR
Waiting on someone's review 
> - Some old IAM Terraform PR will get merged after Ming’s approval
>
> Blockers:
> - Not so much of a blocker, but my button won’t work until my teammate merges his pop-up button. After that I will submit my button
>
> Next step:
> - I don’t know, I want a task

### 07/19 (Wednesday)
> Updates:
> - I submitted the PR for the translation explain-more button. Its review is over, but I’m blocked on merging my teammate's PR so that I can also merge mine (because I checked out his code so I can work on my button, and now the files changed in my PR show both my work and his work.)
> - I’m done with the tech spec for the interactive chatbot feature. I assigned my buddy to review it. I will get it back to you once it’s reviewed.
>
> Blockers:
> - No blockers at the moment
> 
> Next steps:
> - I need a task lol.

### 07/20 (Thursday)
> Updates:
> - Was floating around to fix blockers within the rest of the PRs. Reviewed the PRs that needed reviews.
> 
> Blockers:
> - None
>
> Next steps:
> - Set up dogfooding for the team
> 
> Questions:
> - When should we work on styling?


This was the day I started setting up dogfooding software for the team. [Dogfooding](https://blog.duolingo.com/dogfooding-app/) is a process through which we test our own product before we ship it, as if we were first-hand users. We were able to catch a lot of bugs and solved them throughout the following weeks.

### 07/12 (Friday)
> Updates:
> - Designed the tech spec for my extension. 
> - I’m working on the extension API right now.
>
> Blockers:
> - I had a blocker with postman, but fixed it. It was a URL issue.
> 
> Next steps:
> - Finalize PRs for both frontend and backend.


### 07/24 (Monday)
Sprint planning.
> Updates:
> - Done with API design. Submitted a PR on the backend and a PR on the frontend.
> 
> Blockers:
> - None
> 
> Next steps:
> - Work on bugs on frontend,
merge translation explain more button once the other frontend PR is merged, and
> - Add calls for Chatbot API in the Chatbox.ts component.

### 07/25 (Tuesday)
> Updates:
> - I’m solving merging conflicts for the translation button, applying the comments
> - `Chatbot` routes should be good to merge after I apply the comments
> - I created a login page, discussing with jayden how we want to approach this
> 
> Blockers:
> - For some reason when I merged master on my explain more branch, it now does not add the messages because `translationEntry` is null all the time.
> - There is a comment on my PR that I want to discuss later to better understand
> 
> Next steps:
> - Will keep working to merge the remaining PRs and work on `Auth`
> 
> Thoughts:
> - Use dogfooding documents

### 07/26 (Wednesday)
> Updates:
> - Dogfooding documents are ready to use
> - Once my PRs are merged, we should be able to prompt GPT from the chat box
> - We will proceed with the login page already built!
> 
> Blockers:
> - No blockers
> 
> Next steps:
> - Work on login

### 07/27 (Thursday)
Probably there was a company-wide event or something.

### 07/28 (Friday)
> Updates:
> - I built the script for creating the indexes
> 
> Blockers:
> - I have the same blocker from yesterday, reached out to people on slack but still blocked.
> 
> Next steps:
> - Will submit this PR once unblocked.
> - Will merge my two PRs after applying comments.
> - Then work on a page to allow users to choose a book.
> 
> Thoughts:
> - How is next week looking like? Is it going to be fixing the bugs we have?

### 07/31 (Monday)
Sprint planning!

With this, July is wrapped up with a product that is almost ready to be used! I will publish the stand-up notes for Augut in a future post. See you then!
