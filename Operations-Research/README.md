# TRTS Interval Train Scheduling Optimization

An operations research project that optimizes **short-turn train intervals, service boundaries, and train allocation** to reduce passenger waiting time on the Taipei MRT system.

## Overview

During peak hours, passengers on the Taipei MRT may experience long waiting times due to high station demand and limited train capacity. In addition to full-route trains, the system also operates short-turn trains over selected high-demand sections to improve passenger flow.

This project develops a **nonlinear optimization model** for the Songshan–Xindian Line to determine:

- the service interval of full-route trains
- the service interval of short-turn trains
- the number of trains allocated to each service type
- the optimal starting and ending stations for short-turn service

The objective is to **minimize total passenger waiting time** during peak periods.

## Data

The model uses publicly available Taipei MRT data, including:

- Hourly station-level origin–destination passenger flows
- Train capacity
- Total available train fleet
- Minimum feasible headway
- Route and station information

Passenger arrivals and departures are assumed to be uniformly distributed within each hour, allowing hourly OD flows to be converted into average per-minute passenger demand.

## Modeling Approach

Passenger waiting time is modeled by combining station demand, train frequency, and vehicle capacity.

Passengers are divided into different groups depending on whether their destination can be served by short-turn trains or requires full-route service.

The model jointly determines:

- **Full-route train frequency**
- **Short-turn train frequency**
- **Full-route train allocation**
- **Short-turn train allocation**
- **Short-turn service boundaries**

Key constraints include:

- Total train fleet availability
- Minimum train headway
- Vehicle capacity
- Short-turn and full-route scheduling coordination
- Feasible ordering of short-turn starting and ending stations
- Passenger overflow when train capacity is insufficient

The resulting **nonlinear programming model** was solved using **Gurobi**.

## Results

The optimized solution produced a total passenger waiting time objective of **602,349 minutes** over the two analyzed peak hours.

The model recommended:

- **12** full-route trains
- **1** short-turn train
- **6-minute headways** for both service types
- **Chiang Kai-Shek Memorial Hall – Guting** as the optimal short-turn section

The selected short-turn section differs substantially from the current **Songshan – Taipower Building** service pattern.

The result suggests that, when minimizing passenger waiting time alone, concentrating short-turn service on the most congested central stations may provide greater benefit than operating a longer short-turn segment.

However, the model does not account for infrastructure and operational costs such as turnaround tracks and train reversing constraints. These factors would need to be incorporated before the solution could be interpreted as a practical deployment recommendation.

## Repository Structure

```text
Operations-Research/
├── TRTS-Interval-Train-Scheduling-Optimization-Report.pdf   # Full project report
├── TRTS-Interval-Train-Scheduling-Optimization-Slides.pdf   # Final presentation slides
└── README.md
```

## Tech Stack

`Operations Research` · `Nonlinear Programming` · `Gurobi` · `Optimization` · `Transportation Analytics`

## Project Context

**Operations Research, National Taiwan University**  
Team Project · Transportation Optimization · Public Transit · Mathematical Programming
