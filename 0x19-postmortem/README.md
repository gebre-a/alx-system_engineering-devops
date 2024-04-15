0x19. Postmortem
Any software system will eventually fail, and that failure can come stem from a wide range of possible factors: bugs, traffic spikes, security issues, hardware failures, natural disasters, human error… Failing is normal and failing is actually a great opportunity to learn and improve. Any great Software Engineer must learn from his/her mistakes to make sure that they won’t happen again. Failing is fine, but failing twice because of the same issue is not.

A postmortem is a tool widely used in the tech industry. After any outage, the team(s) in charge of the system will write a summary that has 2 main goals:

To provide the rest of the company’s employees easy access to information detailing the cause of the outage. Often outages can have a huge impact on a company, so managers and executives have to understand what happened and how it will impact their work.
And to ensure that the root cause(s) of the outage has been discovered and that measures are taken to make sure it will be fixed.
Resources
Read or watch:

Incident Report, also referred to as a Postmortem
The importance of an incident postmortem process
What is an Incident Postmortem?
q1:
Authentication outage incident report
April 15, 2024
By Gebrekidan Alemayehu
Earlier this week we experienced an outage in My API infrastructure. Today I am providing an incident report that details the nature of the outage and our response.
The following is the incident report for the authentication outage that occurred on April 15, 2024. I understand this service issue has impacted my valued developers and users, and we apologise to everyone who was affected.
Issue Summary:

On April 15, 2024, from 10:00 AM to April 15, 2024, 2:00 pm, my authentication service experienced a severe outage, impacting 80% of users who were unable to log in. The root cause of the issue was identified as a misconfigured firewall rule, which inadvertently blocked all incoming traffic to the authentication service.

Timeline:

10:00 AM: Issue detected through monitoring alerts indicating a spike in failed authentication attempts.
10:15 AM: Engineers investigated potential issues with the database server and load balancer, assuming the problem was related to database connectivity.
11:00 AM: Misleadingly pursued database performance optimization measures based on initial diagnostics.
12:30 PM: Escalated incident to network infrastructure team after further investigation pointed towards network-related issues.
2:00 PM: Network team identified a misconfigured firewall rule blocking incoming traffic to the authentication service.
3:30 PM: Firewall rule adjusted to allow incoming traffic, restoring service functionality.
2:00 AM: Service fully restored after thorough testing and validation.

Root Cause and Resolution:

The root cause of the outage stemmed from a misconfigured firewall rule that blocked all incoming traffic to the authentication service, effectively preventing users from accessing the system. The issue was resolved by promptly adjusting the firewall rule to allow incoming traffic, thereby restoring normal service functionality.

Corrective and Preventative Measures:

Improvements/Fixes:
Implement automated configuration checks to detect and prevent misconfigured firewall rules.
Enhance monitoring systems to provide more granular insights into network traffic and firewall configurations.

Tasks to Address the Issue:
Implement automated configuration checks for firewall rules by April 30, 2024.
Conduct a comprehensive review of all firewall configurations to ensure compliance with security policies by May 15, 2024.
Enhance monitoring systems to include real-time alerts for critical network infrastructure changes by June 1, 2024.
q2:
Incident Report: The Case of the Missing Environment Variable
In this short story, I shall chronicle a snapshot of my very first experiences in the world of devops and development, and rookie mistakes you can have a laugh about later in life.
There comes a time in a young developer’s life when you have to learn more than you signed up for on the job, become a jack of all trades if you will. Crafting personal and professional projects comes with the responsibility of gaining some knowledge in a different area of expertise just to get your project up and running.
In this fateful phase of my life, it seemed learning devops was the next step to take. I spent the next couple of weeks learning a bit of it, failing terribly at deploying something a couple of times.
After meticulously developing a feature for my current project, I was ready for it to see the light of day. Being new to continuous integration and continuous deployment (CI/CD) automation, I had setup a deployment pipeline for my project using hefty tutorials and documentations online and was sure it was watertight. Setting up simple GitHub workflow tests to ensure that builds were passing, and no type errors made it to production. “I run a very tight ship”, I thought to myself.
And that was the beginning of the rookie mistake. I excitedly began the process to ship my code through the pipeline, confident that this feature would definitely be received well. Once my pull request was made, time to wait on my handy GitHub workflow (that VERY simple one I wrote) to confirm that everything was working fine. Those green checks always make my day. With all tests green and the code up to date, its time to ship the feature.
Just as a routine check, I tested the feature to ensure its working fine. To my shock, the feature isn’t working. The first sensical thing to do is check the code running on localhost. Everything is working as expected.
“But it works on my machine,” says Every. Developer. Ever.Fast forward to me several hours later trying to pinpoint where exactly the problem is coming from.
After being frustrated for a while, I decided to take a walk, touch some grass, as one does, to unwind and kind of get my head straight before diving back in to get to the root cause of the
Problem.
Once I felt I was refreshed, I decided to start from the basics. They say as a developer, console.log() is your best friend. I logged every possible thing that I felt could be the problem.
In a moment of clarity, I took a long shot and decided to log the environment variable to see what value it was passing, only to realise the true nature of my folly — a humble environment variable, forgotten amidst the chaos of deployments and configurations. With a mixture of relief and embarrassment, I swiftly rectified my oversight, setting the missing variable in its rightful place.And lo and behold, the feature started working as perfectly as it was designed. All that fuss, just to find out how small the problem was! The only thing you can do in that moment is just laugh.
I emerged from the ordeal with a newfound appreciation for the intricacies of devops, a healthy dose of humility, and a resolve to always double-check my environment variables before embarking on future deployments😂
So, dear reader, let this tale serve as a cautionary reminder — in the world of software development, even the most trivial of oversights can lead to monumental mishaps. But with determination, a dash of humour, and a willingness to learn from our mistakes, we can turn even the most disastrous of incidents into valuable lessons learned.


Written by :
Gebrekidan Alemayehu
Frontend Developer skilled in JavaScript (React, NextJS, React Native). 



