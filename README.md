# dq2_accre_cluster_job_efficiency

Optimal use of ACCRE computing cluster

Data Question 2: The Advanced Computing Center for Research and Education
In this data question, you will be analyzing data on jobs run on ACCRE's hardware. You will need to do some data cleaning and preparation and then explore and analyze to answer the following questions.

Project questions
We strongly discourage users from running large numbers (>500) of very short ( < 5 mins) jobs within 4 hours. Are there any users who are repeat offenders?
Are any of these short jobs failing, i.e. exit code not "0:0"? If large arrays of jobs are failing quickly, it indicates that users are not debugging their jobs well before large scale submissions.
What groups are best optimizing their memory usage in terms of percent of actual memory used of the memory requested for a job? What is the average percent for each group?
Optimizing memory is more important for longer running jobs then shorter running jobs as the resources are tied up for longer. If jobs are weighted by runtime, what is the average percent of memory used of the requested memory for each group?
Data cleaning / formatting
We really only want to look at the "production" partition so rows with other partitions should be removed
Job time is in a format of either d-hh:mm:ss or hh:mm:ss, it needs to be converted to total seconds
Only successful jobs with "0:0" exit codes should be considered for memory use analysis
Memory is reported in terms of Megabytes per node (Mc) or Megabytes per core (Mc), this needs to be uniformly converted to Megabytes per core by dividing by the number of cores per node in a job.