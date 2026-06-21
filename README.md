# Byzantine-Attack-on-Complex-DFL-Topologies

An empirical study analyzing the vulnerability and sensitivity of Decentralized Federated Learning (DFL) architectures against malicious Byzantine actors. This project specifically evaluates the impact of network topology on the performance of robust aggregation rules under both random and targeted poisoning campaigns.

---

## 📌 Project Overview

Traditional Federated Learning relies on a central server, making it a single point of failure. Decentralized Federated Learning (DFL) distributes this responsibility across a peer-to-peer network. However, DFL's reliance on graph topologies introduces unique security vulnerabilities. 

This research investigates how **small-world** and **scale-free** network topologies respond to Byzantine attacks when utilizing standard robust aggregation methods like **Krum**. 

### Key Findings
* **Random Attacks:** Both topologies degrade equally (dropping to ~60% accuracy) under a 30% random node poisoning attack.
* **Strategic/Targeted Attacks:** Scale-free networks are highly vulnerable to targeted hub poisoning, plummeting to **15% accuracy**, whereas small-world networks maintain a resilient **70% accuracy**.
* **Conclusion:** Existing robust aggregation methods (like Krum) fail against targeted central hub poisoning because they lack intrinsic **network topology awareness**.

---

## 🔬 Methodology & Experimental Setup

### 1. Network Topologies Modeled
* **Small-World Networks:** Modeled using the **Watts-Strogatz** graph mechanism to simulate high clustering and short path lengths.
* **Scale-Free Networks:** Modeled using the **Barabási-Albert** graph model to simulate a power-law degree distribution with highly connected central hubs.

### 2. Learning System & Workload
* **Framework:** Decentralized Federated Learning (DFL) on a **32-node** setup.
* **Model:** Convolutional Neural Network (CNN).
* **Dataset:** MNIST image classification.
* **Aggregation Rule:** Krum Aggregation (evaluated with both random and strategic node placement).

---

## 📊 Results Summary

| Attack Type | Node Placement / Target | Small-World Accuracy | Scale-Free Accuracy |
| :--- | :--- | :---: | :---: |
| **Baseline (No Attack)** | - | **85%** | **85%** |
| **Random Attack (30%)** | Randomly selected nodes | **60%** | **60%** |
| **Strategic Attack (30%)**| Targeted high-degree central hubs | **70%** | **15%** |
