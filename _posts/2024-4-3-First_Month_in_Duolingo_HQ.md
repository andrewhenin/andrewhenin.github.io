---
layout: post
title: The First Month at Duolingo - Summer 2023
---

The first two weeks had more of a training-like structure. There would be sessions about the basics, like frontend, backend, APIs, collaboration on GitHub, etc. As a cohort, we would 
apply whatever we learned in those sessions in our respective projects when possible. In parallel, as a team, we worked on making engineering decisions and compiling as much content in technical
specifications (tech specs for short) as possible. We ended up writing more than 100 pages describing everything about a feature from how it would look like on the frontend and the network 
calls it would trigger to the architecture of the API responses and data management in the backend. While other teams started working on the technical side of the project right away, we 
took more time in the beginning to plan everything out.

## My Team's Project
My team's assigned project was to build a reading platform to help users read longer chunks of text in a foreign language. This platform should support two major capabilities:
- A translation feature and
- A summary generation feature using an LLM.

## Daily Standups
We had three tech specs in total, one for each major feature:
- The paragraph display,
- The translation feature, and
- The summary generation.

I kept a record of the updates for every stand-up we had since we started the technical implementation of the platform, and I'm going to share some of it here. We would 
have a one-hour sprint-planning meeting on Mondays and 15-minute stand-ups for the rest of the week.

### 06/23 (Friday)
> Summary tech spec is done and now in review. I will be waiting on approval from the rest of the team by the end of today.
> - The front-end layout is done.
> - All the screens are generated and attached to the Tech Specs
> - All JIRA Tasks are updated.
> - Blockers: no blockers so far!

What’s next? We had already reviewed the other two tech specs, and we sent them to our host, Jimmy, for review.

### 06/27 (Tuesday):
> Updates:
> - Simple Paragraph Display mostly done, we’re working on the json response parsing function
> - Added highlight feature + buttons with response
> - Currently researching DynamoDB structure
> - No blockers
>
> Up next:
> - Json parse
> - Code cleanup and commenting, and creating a pull request

This was my first time ever creating a PR, requesting reviews, resolving comments, and merging it. It was a very unique memory.

<!-- Joseph -->
My teammate had already started working on the Python script to read books from an open-source library. He picked 3 books, represented them as a list of lines, 
split by “\n,” and did a lot of good string manipulation work. He was able to read and store the Title, Author, and Language consistently. It was a huge script.
We ended up picking [Project Gutenberg](https://www.gutenberg.org/), which is intuitive for parsing as the books in 
their collection have similar properties.


### 06/28 (Wednesday):
> Updates:
> - Local database is now set up. We have a local table with the name duo-reads-local. Pull request is going to be submitted shortly after the meeting and the corresponding JIRA task will be moved accordingly.
> Blockers: None
>
>  Next Steps:
> - Setting up the database on aws, which will be done tomorrow
> - Working on the DAL with Joe and Jayden for the Book API

On this day, another teammate had set up a way to store highlighted text in the paragraph display, as this would enable us to implement a feature where the user can
request to translate some text as easily as just highlighting it. We had done work to split the current component into a paragraph navigator component and a main page.
In the meantime, we finished and tested the view methods that get chapter data from the database. This was a part of the "paragraph API."

We built two APIs: one that serves the content of our books in the library (i.e., fetching certain books, chapters, paragraphs, translations, etc.) and one that 
stores information about the signed-in user. For both APIs, we used an approach known as a Multi-Layered structure of building APIs. Each API consisted of three layers:
- A View layer,
- A Manager, and
- A Data-Access Layer (DAL).

The responsibilities differed for each individual layer. For example, the DAL was concerned with accessing the database and fetching the requested information.
This information is returned to the Manager or the [Business Logic Layer](https://www.geeksforgeeks.org/business-logic-layer/), which validates input data to ensure 
that it meets the necessary rules and constraints; performs calculations and transformations on data as necessary; enforces business rules and policies, 
such as access control and security; communicates with the DAL to retrieve and store data; and, of course, handles errors and exceptions, returning the appropriate status
code to the caller from the View, which is the interface provided to the frontend developer to use these methods. These levels of abstraction helped incredibly with debugging 
later when we were using Postman to test API health and merge the frontend with the backend.

#### Challenges:
We were faced with some challenges:
- How do we test the View method that patches data to the database?
- How can we read books in other languages that use non-Latin characters?
- How do we automate populating the local DB instead of adding items manually every time we need to test?     

### 06/29 (Thursday):
> Updates:
> - AWS Terraform files for both staging and production are ready, and should be able to create the PR today.
> - Blockers: None, but I’m doing readings on how to add monitor configurations for the database
> 
> Next Steps:
> - Working on the book DAL 

Here, I was able to set up the local database for testing. It had taken a few days as I had changed a file name in the Docker stuff by mistake.

### 06/30 (Friday):
> What was done:
> - I’m almost done reviewing two huge Pull Requests
> - Blockers: None after we talked to Jimmy in Office Hours
> 
> Next steps:
> - I will communicate with the team to make sure the View, Manager, and DAL communicate with each other and the database the way they should and with the correct format. 

My team had already submitted the PR concerning the Python script that reads the books, and we were starting to explore [boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html).

This Friday concluded about a full month of working at Duolingo. How comfortable was I with the amount of new condensed exposure I was presented with?
How were the dynamics between my teammates and manager? How confident was I in my own skills and receptivity? I hadn't had enough time to process all of that. Yet, 
it had been a great month. I became more bold and willing to take risks, even if that meant there was a chance I make a mistake. I had great people around me, who were 
always willing to help, so it would have been completely unreasonable to remain risk-averse. Stay tuned for the updates of July! 
