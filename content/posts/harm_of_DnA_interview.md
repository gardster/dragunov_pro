---
title: "The Harm of Design & Architectire Interviews"
date: 2024-02-03T23:00:00+01:00
# weight: 1
# aliases: ["/first"]
tags: ["interview", "architecture"]
author: "Lev Dragunov"
# author: ["Me", "You"] # multiple authors
showToc: false
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "The popular section that decreases quality of candidates"
disableHLJS: true # to disable highlightjs
disableShare: true
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "posts/harm_of_dna_interview/castle.jpeg" # image path/url
    alt: "Archtecture of the castle" # alt text
    caption: "" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: false # only hide on current single page
editPost:
    URL: "https://github.com/gardster/dragunov_pro/tree/main/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

The past year was quite eventful for me: I changed my job, my stack, domain and even my country of residence. This process was accompained by a series of interviews in not the most favorable season for hiring. And now I have some thoughts to share about the whole process of interviewing.

While there are many articles and opinions criticizing the algorithmic section and LeetCode problems during the interviews, I believe that between popular interview types, there's a more detrimental section: Design & Architecture.

I have experienced this type of interview as an applicant, conducted it as an interviewer, and led a team where people came after this interview. So I faced the results of the selection of this interview essentially without the possibility to influence it. It's important to note that in the company where I used to work, and in many other large companies pre-COVID, technical interview stages were conducted by engineers from other teams, and the only time you could talk to a potential colleague was during the final team match meeting.

To summarize my experience, I want to say that in the form in which it is conducted in most companies, the design and architecture interview stage is harmful for the company.

## Challenge dilemma

Most of the D&A interviews that I have participated in can be roughly divided into three large groups:

* Build a complex mechanism based on some "insights". Apply HashRing, BloomFilter, RedLock etc.
* Discuss the company's pain points. "Design the company's website where you're applying."
* Create a popular website.

All three groups are inherently flawed:

**Insights** are bad, obvaiously. You either know the algorithm or come up with something deliberately inconvenient. Essentially, this interview tests knowledge of exactly one algorithm. At the beginning of my career, before a difficult interview, folks would reread the balancing of red-black trees. Now everyone is reading Kafka.

Discussing the **company's pain points** is slightly better. On one hand, it's specific: we talk within the company's domain, hopefully about something that we will see during the future work. But here a asymmetry in knowledge between applicant and the interviewer comes into play. The interviewer already knows what doesn't work. It's especially dreadful when a company is reworking its initial unsuccessful solution, and after a 5-minute problem description, you suggest exactly that solution. Another trap is that questions often become very specialized and revolve around the pain points that company employees themselves barely solved.

To level the knowledge inequality, interviewers choose the third option: an **external popular website unrelated to the interviewer and the candidate**.

However, even this option leads to complete failure. To understand why, let's take a step back and examine why Design & Architecture interviews are conducted in the first place:

## Why is it even necessary?
According to companies themselves, the design and architecture interview stage evaluates parameters such as:

* Ability to design systems.
* Identifying requirements.
* Finding and explaining compromises.
* Operating in conditions of uncertainty.
* Overall communication skills.

The average Design & Architecture interview fails on all these points:

* Limited set of challanges: there are not so many companies that everyone knows and usually they are sites with some social network features. Candidates memorize the "correct" answers from how-to-interview books without understanding them and then theatrically recite it including clarification questions.
* Oh yes, questions! Identifying requirements isn't very good aligned with operating in conditions of uncertainty but everyone knows that questions at the beginning of the section greatly influence the grade. Some interview goals are clearly contradictory to each other!
* High-level discussions: due to time constratints and limited knowledge about discussed system from both sides you will not be able to dive deep into discussed problems. All discussions will be around big boxes: services, queues and databases.
* Limited compromises. They simply have nowhere to come from in high-level discussions, so be prepared to talk again about which database to use: SQL or noSQL.

Only a highly qualified interviewer, who you're unlikely to encounter, can navigate through all this. As a result, the interview becomes a ritualized description of the same systems, with expectations of who says what at each stage.

## Impact on Work

Everything could be fine, and we could leave it as is — just another entry ticket. You'd have to read 1-2 books that have no impact on your work, memorize their content for a week, and pass this stage into a "big tech". During the next job search, you'd reread/refresh. But I witnessed how this interview literally ruins young professionals.

The typical scenario for the first projects of an ambitional mid-level professional who prepared for such interview:
microservices, a Kafka queue in long-term storage mode, DynamoDB and many other popular words for the admin panel of an internal project with 100 requests per day. The list can be continued: Spark pipelines with dozens of nodes heroically processing a couple of gigabytes of data, Flink jobs to calculate rows count in database by counting events from the write endpoint...
However, all this expensive machinery still crashes at the first minor gap in the query. Exception handling becomes too burdensome for the newly minted architect.

Now, every newcomer knows how to design Twitter and distribute data like Netflix, but they don't know how to build a regular web application and how many users it can handle. The irony is that typically they won't be allowed to tackle serious architecture until they successfully complete a simple project.

As a result, instead of verifying a person's ability to design systems, companies not only fail to check candidate's design skills but also ensure that they can design in a destructive way. An interview with negative utility.

## What to Do?
Candidates cannot overcome this problem. They can read 1-2 books with popular questions, skim through the images before the interview, and learn to articulate their thoughts and possible failure cases incessantly. The rest of the time is better invested in personal development as a specialist, and please do not use snippets from interview preparation books on your first job.

Interviewers in large companies also cannot instantly change the interview paradigm. The only option is to constantly remind ourselves that this format is highly subjective, and the main task of this stage is not to design Twitter. For entry-level grades, it's better not to conduct this type of interview at all.

And I still believe that the sooner more people understand that this type of challenges is harmful, the sooner we can abandon them and improve interview processes at whole.
