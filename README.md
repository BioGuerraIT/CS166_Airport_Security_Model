# CS166 First Project
## Airport Security Queues

### Overview
In this project, you complete the implementation of a queueing simulation that we start in class during the first two weeks of the course. You will experiment with strategies for organizing travelers queueing in an airport and measure how well the different approaches work. This assignment aims to go through the entire modeling, simulation, and analysis process but with much support from the instructor and your peers through in-class discussions. We will repeat this modeling-simulation-analysis process a few times during the course. Use this project as an opportunity to learn how to do it right.

The main goals of this first project are to:
- Practice writing object-oriented programming code in Python,
- Use basic NumPy functionality (manipulating arrays, applying essential mathematical and statistical functions, generating random values),
- Use Matplotlib functionality for generating figures that describe simulation results,
- Provide convincing arguments that the simulation is correctly implemented and that the reviewer can trust your results,
- Document your project well while producing a readable and professional report.

### Model
A large airport operates 24 hours a day. All travelers have to go through an airport security screening before they can board their planes. At airport security, there are several queues, each with an assigned service station where travelers are asked to take off their shoes, etc., and have their carry-on bags screened.

The time between consecutive travelers joining a queue is assumed to come from an exponential distribution with a rate parameter λ = 10 travelers per minute. Travelers join the shortest queue when they are ready to pass through security.

Under normal circumstances, a security service station spends approximately 30 seconds per traveler to clear them through all the security checks. There is some variation in service time and generally the time taken per traveler follows a Truncated Normal distribution with parameters μ = 30 seconds and σ = 10 seconds. The distribution is truncated to allow for positive service times only.

To simplify this simulation (compared to the real world), we assume that only 1 traveler can be served by a security service station at one time. While a traveler is being screened, everybody behind that person has to wait in the queue.

There is a small chance (3%) that a traveler will need additional screening — for example, if there is something suspicious in their luggage. This requires a senior security officer to inspect the problem and clear the traveler. The additional screening follows a Truncated Normal distribution with μ = 2 minutes and σ = 2 minutes. There is only one senior security officer at the airport, and the senior officer can inspect only one traveler at a time. While a traveler is undergoing additional screening, everybody else in the queue has to wait for the additional screening to finish.

### Tasks
Main task: Provide an OOP-based Python implementation of the airport security scenario described above and demonstrate, using at least two test cases, that your coding leads to reasonable results. You should already be familiar with the concept of test cases, but here is a summary to refresh your memory.

Main question: How many service stations should airport security have? Address this staffing problem by implementing the simulation described above and analyzing the following metrics, informed by a thorough mathematical analysis.

You have to run the simulation multiple times and compute the expected value and a 95% confidence interval of each of the following metrics.
1. Average traveler waiting time given the number of service stations. Waiting time is the time between a traveler joining a queue and when the travel starts being screened by security.
2. Average queue length during a day, given the number of service stations.
3. Maximum queue length during a day, given the number of service stations.

You have to provide empirical results and compare them with the theoretical predictions from queueing theory.

It might not be possible to analyze the whole model analytically, which is okay. However, you still need to provide an analysis of some parts or special cases of the model and will need to expand on the results discussed in class. A good place to start (but aim to go further!) is to model each queue at the airport as an M/G/1 queue and analyze the system of n queues accordingly.

### Assignment guidelines
#### Feedback and grading
You will get assessed on the learning outcomes listed in the grading guide for this assignment. You are not required to read through the grading guide but it will be really helpful and will almost certainly help you to improve your grades and learn more about what is required to complete a high-quality project report.

Your instructor will use the same grading guide to assess your work, provide feedback, and assign grades.

#### How to submit your deliverables
Follow all these formatting requirements.
- You need to submit two files, namely a .pdf file with your project report and a .ipynb (or .zip) file with your Python notebook.
- The purpose of the project report, submitted as a primary resource, is to present your simulation model and summarize your results.
  - Prepare a well-structured report with sensible section headers to form a complete table of contents. Do not simply upload a PDF version of your Python notebook as your project report.
  - Do not zip your PDF report. If you do, your instructor can’t attach written feedback and grades to the relevant part of the report.
  - Include a word count of your report. This has to be between 1500 and 3000 words.
  - Format your report appropriately, using headings to organize your work.
  - Proofread and spell-check your report before submitting it. Use Grammarly.
- The purpose of the Python notebook, submitted as a secondary resource, is to show how your simulation generated your results and to ensure your instructor can reproduce your results by running your code.
  - The Jupyter notebook (.ipynb) must include all output (text and plots) generated, as well as a short discussion convincing the reader that the implementation is correct. This is something you are expected to demonstrate explicitly using test cases and/or a visualization of the simulation state.
  - If you wish, you may zip your Jupyter notebook to submit. This is not required.
  - Your instructor will rerun your notebook from start to finish, and it has to reproduce all your results without any bugs/errors. To be clear, the output of the submitted code must match the results in the report. (Small differences due to randomness are okay.)
