# ASSIGNMENT: Sampling and Reproducibility in Python

Read the blog post [Contact tracing can give a biased sample of COVID-19 cases](https://andrewwhitby.com/2020/11/24/contact-tracing-biased/) by Andrew Whitby to understand the context and motivation behind the simulation model we will be examining.

Examine the code in `whitby_covid_tracing.py`. Identify all stages at which sampling is occurring in the model. Describe in words the sampling procedure, referencing the functions used, sample size, sampling frame, any underlying distributions involved, and how these relate to the procedure outlined in the blog post.

Run the Python script file called whitby_covid_tracing.py as is and compare the results to the graphs in the original blog post. Does this code appear to reproduce the graphs from the original blog post?

Modify the number of repetitions in the simulation to 100 (from the original 1000). Run the script multiple times and observe the outputted graphs. Comment on the reproducibility of the results.

Alter the code so that it is reproducible. Describe the changes you made to the code and how they affected the reproducibility of the script file. The output does not need to match Whitby’s original blogpost/graphs, it just needs to produce the same output when run multiple times

# Author: Ece Yucer

## Answers

Note: the section on examining `whitby_covid_tracing.py` refers to the line numbers for the original file. Since the random seed is added at the top, I included the actual line of code as a snippet as well.

### Examinining `whitby_covid_tracing.py`:

The random sampling first occurs in line 47 while infecting a random subset of people:
```python
    infected_indices = np.random.choice(ppl.index, size=int(len(ppl) * ATTACK_RATE), replace=False)
```
Here, the sample size is 100 individuals, sampling frame is the entire population so 1000, the distribution is uniform. Basically, this step portrays the initial infections of 10% of individuals randomly occuring among wedding and brunch goers from the blog post.

Next, another random sampling occurs in line 51 during primary contact tracing, where we randomly decide which infection people get traced:
```python
    ppl.loc[ppl['infected'], 'traced'] = np.random.rand(sum(ppl['infected'])) < TRACE_SUCCESS
```
Here, the sample size varies in each run as demonstrated by the prop_df dataframe, but the average should be around 20% of infected people, so around 20, the sampling frame is the infected individuals so 100, the distribution is binomial since there are two outcomes: traced or not traced. This section reflects the imperfect nature of contact tracing mentioned in the original blog post.

Last, a cluster-based sampling occurs in lines 54-56 during secondary contact tracing based on event attendance:
```python
    event_trace_counts = ppl[ppl['traced'] == True]['event'].value_counts()
    events_traced = event_trace_counts[event_trace_counts >= SECONDARY_TRACE_THRESHOLD].index
    ppl.loc[ppl['event'].isin(events_traced) & ppl['infected'], 'traced'] = True
```
Here, if two or more infected people that attended a wedding or brunch were traced in the first round, then all infected people at that same event are automatically marked as traced. The event type, so wedding or brucnh, acts as a cluster and once the SECONDARY_TRACE_THRESHOLD is reached in a cluster more people are traced. So, the sample size is the number of infected individuals who attended an event with more than two traced cases and the sampling frame is the population of infected individuals who attended an event where two or more people were traced in the primary contact tracing. While the blog post has 2 weddings and 8 brunches separately, our code clusters individuals as attended to a wedding or attended to a brunch. The secondary tracing rule amplifies the bias towards weddings in Whitby's post because weddings are more likely to meet the SECONDARY_TRACE_THRESHOLD due to the larger event size.

### Comparing results to the original post:

In the blog post, Whitby shows the distribution of true versus observed proportion of cases from weddings. Their code uses a different event structure compared to ours. In Whitby's code (and blog post), there are 2 weddings of 100 people each and 80 brunches of 10 people each, while our code clusters wedding attendees (200 people) and brunch attendees (800) into two large groups. While Whitby's methodology infects attendees per event using the 10% infection rate, ours uniformly infects a random 10% of the wedding and brunch goers. In both scripts, an infection has only a 20% chance of being traced to a source event during primary contact tracing. However, during secondary contact tracing, the fact that Whitby's code necessitates at least 2 infections to be traced to the same source event (where we have 80 small brunches and just 2 weddings), weddings partake in this process more often. While brunches of 10 people each requires 2 people, so 20% of individuals at the event, to be traced to conduct secondary contact tracing, weddings of 100 people each requires only 5% of the individuals at the event to be traced to conduct secondary tracing. This means that when Whitby graphs the distribution of true versus observed proportion of cases from weddings, despite the weddings having a smaller number of overall infections, weddings end up being overrepresented in the traced sample due to the larger event size and the secondary tracing rule. 

On the other hand, the provided code does 1000 simulations on 800 brunch and 200 wedding attendees and during secondary contact tracing, having any 2 out of 800 brunch attendees or 2 out of 200 wedding attendees triggers the process. As a result, the traced cases are proportional to the event sizes since both wedding and brunch event types are treated as a whole. So, the output of the provided code shows two histograms: blue distribution showing the infections from wedding and the red distribution showing the infections traced to weddings. Overall, the output shows that 20% of all cases get traced to weddings; hence, eliminating the bias from the Whitby blog post. 

### Modifying to 100 repetitions:

When the number of simulations is changed to 100, the histograms show great variability between runs, where the means and ranges of the distributions change due to fewer samples. Since we are using fewer samples, the impact of randomness is a lot more visible, deteriorating the reproducibility of the code. 

### Editing for reproducibility:

To make the code reproducible to provide the same output when run multiple times, I incorporated a random seed. This way the same sequence of random numbers will be used in each execution, meaning the randomness will be the same every time the script is run, generating the same graphs.


## Criteria

|Criteria|Complete|Incomplete|
|--------|----|----|
|Altercation of the code|The code changes made, made it reproducible.|The code is still not reproducible.|
|Description of changes|The author explained the reasonings for the changes made well.|The author did not explain the reasonings for the changes made well.|

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `23:59 - 11/04/2025` -- have an extension from Lindsay!
* The branch name for your repo should be: `assignment-1`
* What to submit for this assignment:
    * This markdown file (a1_sampling_and_reproducibility.md) should be populated.
    * The `whitby_covid_tracing.py` should be changed.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `assignment-1`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via the help channel in Slack. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
