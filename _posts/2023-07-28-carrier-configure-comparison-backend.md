---
title:  Carrier Comparison
author: User
date: 2023-07-28 12:00:00 +0800
categories: [Performance, Tutorial, SLA,SLO, SLI, Thresholds, Comparison, Baseline, NFRs]
tags: [performance, backend, comparison, notifications, verification, validation, quality gate]
render_with_liquid: false
---

## Configuring Performance Thresholds and Baselines in Carrier - Step-by-Step Guide

To efficiently configure performance thresholds and baselines in Carrier for your performance tests, follow these easy-to-use steps. We will consolidate and provide options to cover all test cases:

### Step 0: Open Test Parameters

1. Open your test "Settings" with the desired name (e.g., "DemoWithTransactions").
2. Set or collect the following test parameters:
   - Test Type: Choose the appropriate test type (e.g., Validation).
   - Environment: Specify the environment for the test (e.g., Testing).
   - VUSERS: Set the number of virtual users for the test.
   - EMAIL: Set the email address for the test

### Step 1: Set the baseline for comparison

1. Run "DemoWithTransactions" tests with parameters from the "Step 0: Open Test Parameters"
2. Set test run as a "Baseline"

### Step 2: Enable Baline QualityGate Checkbox

1. Open "DemoWithTransactions" test "Settings"
2. Turn on the PROCESSING -> QualityGate checkbox if enabled.

### Step 3: Start the Test Run

1. Click on the "Update And Start" button at the top of the page to start the test run.

### Step 4: Get Test Metrics

1. After the test run is completed, you will receive an email with following test metrics comparison to Baseline:
   - Ttl (total requests)
   - Thrghpt (throughput total), req/sec
   - Error rate, %
   - Pct95 (response by 95th percentile max), seconds
2. Inside email review next metrics in comparison to Baseline:
   - Success Rate
   - RPS/TPS Rate (throughput)

### Step 5: Configure Thresholds

1. Navigate to the "Thresholds" panel in the Backend tab.
2. Click the "+" button to add a new threshold.
3. Fill in the data for the new threshold:
   - Test: Enter the test name (e.g., "DemoWithTransactions").
   - Test Environment: Specify the environment (e.g., Testing).
   - Scope: Choose "All" to apply the threshold to all virtual users.
   - Target: Choose the target metric (e.g., Throughput, Response Time).
   - Aggregation: Set the aggregation method (e.g., Maximum).
   - Comparison: Choose the comparison operator (e.g., >=, <=).
   - Threshold Value: Set the threshold value for the target metric (e.g. 0.5).
4. Click Save button

### Step 6: Enable QualityGate Checkbox

1. Open your test Settings with the name (e.g., "DemoWithTransactions").
2. Activate the PROCESSING -> SLA (Service Level Agreement) for the test.


### Step 7: Configure Advanced Settings

1. Expand the PROCESSING -> ADVANCED SETTINGS section.
2. Activate the "Summary results" checkbox.
3. Check the "Check throughput" box and set the deviation value (e.g., 5).

### Step 8: Start the Test Run Again

1. Click on the "Update And Start" button at the top of the page to start the test run again.

### Step 9: Check the Test Result

1. Once the test is finished, check the test result in the Carrier UI.
2. Verify the status in the UI and the status in the letter to assess if the test meets the configured thresholds and baseline expectations.

### Options for Thresholds and Baselines

- **Thresholds**: You can set thresholds for various performance metrics like throughput and response time. Define the threshold values based on your application's performance requirements and SLAs.

- **Baselines**: Setting baselines allows you to compare test results against a predefined performance standard. Choose the appropriate baseline for your test to assess deviations from expected performance.

By following these steps and configuring thresholds and baselines, you can easily track the performance of your application and identify areas for improvement to deliver optimal user experiences.