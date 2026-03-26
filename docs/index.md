# Continuous Intelligence

This site provides documentation for this project.
Use the navigation to explore module-specific materials.

## How-To Guide

Many instructions are common to all our projects.

See
[⭐ **Workflow: Apply Example**](https://denisecase.github.io/pro-analytics-02/workflow-b-apply-example-project/)
to get these projects running on your machine.

## Project Documentation Pages (docs/)

- **Home** - this documentation landing page
- **Project Instructions** - instructions specific to this module
- **Your Files** - how to copy the example and create your version
- **Glossary** - project terms and concepts

## Custom Project

### Dataset
The dataset is a table of system operational metrics that come from observed system behavior.
There are four columns:
- timestamp: the time of the observation
- requests: the number of requests handled
- errors: number of failed requests
- total_latency_ms: total response time in milliseconds

### Signals
A total of 6 signals were created:
- error_rate: How frequently errors occur
  A performance metric to see if the errors are high or low in frequency

- avg_latency_ms: The average response time in milliseconds
  Rather than total_latency_ms, this puts each request into perspective and lets us see if each request had an overall high, low, or normal latency

- request volume: Number of requests
  Simply the requests column, but can help comprehension when next to throughput_rps

- throughput_rps: Requests per second
  This is a performance metric of system efficiency

- poor_experience: Flag for high error rate OR high average latency
  Allows us to easily find poor performance

- hour_of_day: Hour of the day the observation took place
  Allows for time visuals to be created as well as a cleaner time than just a timestamp

### Experiments
Originally, the dataset only had requests, errors, and total_latency_ms as the columns.
The original signals were also only error_rate, avg_latency_ms, and throughput.

I started with just creating the flag for poor_experience then decided for this custom project to add timestamps to the data.

With the timestamp, and particularly the hour_of_day signal, line charts can be created to show requests over time, latency over time, etc.

### Results
It was observed that every row in the table returned "false" for poor_experience, meaning that there was no drastically poor performance.
This implies that all the error rates and average latencies were in normal ranges.

Similarly, throughput_rps gave values between 29 and 40, another normal range.  <20 would be low and >40 would be high.

### Interpretation
The results from the data show that the system is performing well.
No performance was flagged for being poor and all metrics were found to be in normal ranges (low error rates and average latency).
The system can be kept in its current condition as there isn't anything wrong.  It can always be made better/more efficient, although that is not an immediate concern.

## Additional Resources

- [Suggested Datasets](https://denisecase.github.io/pro-analytics-02/reference/datasets/cintel/)
