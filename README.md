<p align ="center"> 
    <img src="https://media.github.ecodesamsung.com/user/22717/files/f0f1b0d1-71e4-4a2e-b728-3db9922afaca" height ="200"/> 
    
# OPEN EVENT FORWARDER SOLUTION

## About the Project:-

An open event forwarder solution (OEFS) is a tool that allows you to collect and forward events from various sources to a central location. This project compares Kafka and Pulsar for building a performant OEFS.

## Problem Statement:

To Develop an event forwarder solution as open interface.

• Current 5G network elements event is collected and transferred only via proprietary interface and elements from same vendor.

• Solution should be running in Kubernetes environment

• Solution should have unified event using JSON with VES 7.2

• Solution should be able to configure & adapt to multiple end point server configurations.

• Compare performance of apache pulsar & kafka in terms of delay and no of msgs transferred, CPU and memory of client library with min 10 pods with 1000 events/pod.

## Table of content:-

1. Prerequisites
2. Setup
3. Approach
4. Performance Comparison
5. Contribution

### Prerequisites:

Before you begin, ensure you have the following prerequisites installed and configured:

- Kubernetes
- Docker
- VES
- Apache Kafka and Pulsar
- Fluentd
- Prometheus
- Grafana
- Linux/Unix command line interface (CLI)

### Setup

1. Clone the repository:

```bash
git clone https://github.com/your-username/open-event-forwarder-solution.git
cd open-event-forwarder-solution
```

3. Deploy the Kubernetes pods and containers using the provided YAML files in the `kubernetes-configs` directory:

```bash
kubectl apply -f kubernetes-configs/
```

4. Deploy Kafka, Pulsar, and monitoring stacks on Kubernetes using Helm charts.

5.Configure Kafka and Pulsar clusters for event streaming.

- Start load generation and benchmarking using Locust.
- Metrics are collected in Prometheus and visualized in Grafana.

### Approach

<p align ="center"> 
    <img src="Documentation/Images/Approach.png" height ="200"/>


### Performance Comparison

We performed extensive benchmarking of Kafka vs Pulsar for event streaming performance:

**Metrics**

- End-to-end latency
- Throughput
- CPU Utilization
- Memory Utilization

**Parameters**

- Number of pods
- Event sizes
- Event generation rate

**Results**

Kafka performed better than Pulsar in latency sensitive use cases with lower throughput. Pulsar was more resilient for high throughput applications.

| Parameter      | Kafka                   | Pulsar                    |
| -------------- | ----------------------- | ------------------------- |
| Latency        | Lower by 15-20%         | Higher latency spikes     |
| Throughput     | Saturation at ~3000 eps | Increased beyond 5000 eps |
| Resource Usage | Lower by 20-30%         | Higher CPU and Memory     |

**Conclusion**

- For low latency applications with throughput below 1000 events/sec, Kafka is
  recommended due to lower resource usage and better real-time performance.
- For high throughput applications with 5000+ events/sec, Pulsar is recommended for
  better scalability.
- There is further scope to optimize configurations, evaluate compression and encryption overheads.

## Contribution

Contributions to this project are welcome! Please open issues and pull requests.

**CU_23NWOAM08CU_Open_Event_Forwarder_Solution**
SRIB-PRISM Program
