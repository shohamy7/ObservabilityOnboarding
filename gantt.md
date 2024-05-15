# Motivation

In order to stay focus and monitor the way learning will proceed, we'll make a gantt
that will specify the timeline of the learning.
The gantt will contain all the essential material with time period for each part.

The main goal is to provide maximum knowledge in minimum time.
Therefore, we'll aim that the whole learning period will be 2-3 month MAX!
That being said, we'll now divide the time between the topics.
Let's take n assumption that the learning will start from 1.4-1.6.
We'll take into account predicable events such as holidays and soldier vacations.

## Observability

We'll start with theoretical part:
The first thing they'll learn about is: what is Observability?
What hide behind this buzz words.
Though it mainly be a theoretical part, we'll make sure they have
rock solid fundamentals understanding for the rest of the learning.
The main subject they will learn in this part is going to be:

1. What is behind the buzz word - Observability?
2. What are Traces, Metrics & Logs and what is the differences?
3. Observability Vs. Monitoring
4. The history of Observability and OpenTelemetry protocol
5. Why it is important?
6. The importance of the project for the Unit - this is the most crucial
part in my opinion as this will set their motivation for the future.

The overall length of this part should be 4-5 days.
Though mainly theoretical, we allocate more time for them to get into the
world of Observability. One of the most important things is to let them
operate by themselves and let them learn the way they like to.
We should focus them using guideline questions and settings action items
for each day.

## OpenTelemetry

The second part of the learning is to deeply learn about OpenTelemetry.
This part will set there knowledge around the OpenTelemetry standard.
There multiple key points they should get from this part:

1. Deeply understanding the OpenTelemetry protocol
2. OpenTelemetry Collector and its usage
   1. Receivers
   2. Processors
   3. Exporters
   4. Connectors
3. OpenTelemetry contrib
4. OpenTelemetry sdk
   1. Automatic instrumentation
   2. Manual instrumentation
5. Core concepts such as
   1. Sampling
   2. OTLP
   3. protobuf + gRPC

The part will give them the understanding of how we transport telemetry
data between two sources. This also will show them how to integrate Observability to our codebase by adding instrumentation.
This part should be around 3-4 days.
Potential addition - adding manual instrumentation for existing code (can be real code or just something we'll write).
This can be 2-3 days. It's not a necessity cause they will do that in later exercises as well.

## Exercise 1

In this exercise, we'll test their theoretical knowledge by giving them
real/fake example of a system, and will ask them to give us an architecture that will allow us to add observability to our system.
In this exercise, they will need to research solutions about they can collect the telemetry data from the system (which may contain multiple services).
They also will need to provide a persistent solution for storing traces, metrics and logs.
IMPORTANT - this part does not limit them to specific piece of technology.
We mainly want to test their knowledge, and challenge them with questions about their architecture.
This exercise is theoretical, but may be used in the future (in the final exercise).
The overall length of this exercise is 2-3 days for the draft design and 1-2 extra days for polishing up after our questions.

## DevOps

In this part, we'll take a break from the observability stack (just for a short moment).
We'll focus on the main set of actions they will do as day-to-day operations in their work.
This contains:

1. Docker
2. Git
3. Gitlab CI
4. Helm
5. Deeply understand Kubernetes

In this part, we'll contain multiple "small" exercises:

1. Creating Dockerfile for an python application with OpenTelemetry integration (using automatic instrumentation)
2. Set up an Observability stack using Docker and docker compose.
3. Writing Helm chart deploying the stack to k8s
4. Doing labs
5. Advance k8s learning (if labs is not enough)
As this is crucial part of their day-to-day job, the length of this topic will be 10 days.

## Distributed tracing deep dive

This is the last part before the last big exercise.
In this part, they will learn more deeply about distributed tracing system (service map, RED metrics, etc.) and specifically about:

1. Tempo
2. Elastic APM

In Tempo, they'll learn about architecture and feature Tempo offers.
We'll test their knowledge about Tempo architecture.
Afterwards, they will deploy a tempo cluster over K8s using the helm chart and later they will use this Tempo in the final exercise.
We may add more demands as the exercise go to modify the tempo installation in order to support higher scale.
Tempo part should be no more than 6-8 days!
In the Elastic APM part they will learn what is an apmserver and how we deploy it using elastic agents. You will learn why we use this method and what are the advantages. 
After we test their knowledge of how the above topics work, we will let them deploy and try out these tools for themselves.
ElasticAPM part should take between 3-4 days.

## Final exercise

In this final exercise they will implement all theory they learned about observability.
They will write a small fastAPI application (or maybe we'll create one in advance), and the goal of the exercise is to add Observability support for that application. It means creating the necessary infrastructure (OpenTelemetry Collector, Tempo, APM, etc.) and integrating tracing to their application. They should have the ability to transport telemetry data to both Tempo and Elastic APM.
If we want - we can have them also integrating metrics and logs to their application and write them to the corresponding data source (prometheus, elastic, etc.).
They can (and ideally should) use the infrastructure they deployed in previous parts as part of the final solution.
In the end, they will have to showcase their solution and explain how Observability help them understand what happening in their application.
This part should take roughly 10 days.

Thats it!
