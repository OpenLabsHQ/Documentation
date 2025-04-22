# Lab Lifecycle

OpenLabs uses distinct concepts to represent the lifecycle of your lab environment:

1.  **Blueprints: Your Lab Design**
    * **What it is:** A Blueprint is the *design* or *template* for your lab. It's a definition (in YAML or JSON) describing the desired structure: which VPCs, Subnets, and Hosts you want, their network configurations (like IP address ranges), and the specifications for each Host (OS, size, hardware).
    * **Why use it:** Blueprints allow you to define your infrastructure as code. This makes your lab designs **reusable**, **shareable**, **versionable**, and ensures **consistency** every time you deploy. You design it once and can deploy it many times.
    * **Key Point:** A Blueprint is just the plan – it **doesn't represent live, running resources** or incur cloud costs.

2.  **Ranges: Your Live Lab Environment**
    * **What it is:** When you *deploy* a Blueprint, OpenLabs creates a **Range**. This is the actual, **live, running instance** of your lab environment in your chosen cloud provider. It consists of real VPCs, Subnets, and Hosts that you can interact with.
    * **Why use it:** This is your operational lab environment where you conduct exercises, test configurations, or run simulations.
    * **Key Point:** A Deployed Range consists of active cloud resources and therefore **incurs costs** from your cloud provider. The term "Range" is often used to refer to this live, deployed state.

3.  **Snapshots: Saving Your Lab's State**
    * **What it is:** A Snapshot is a point-in-time **saved state** of a running **Range**. It captures the configuration and, crucially, the disk contents of all the Hosts within that Range exactly as they were when the snapshot was taken.
    * **Why use it:** Snapshots are powerful for:
        * Saving your progress within a complex lab exercise.
        * Creating a baseline state you can quickly revert to.
        * Capturing a specific scenario (e.g., a machine after a simulated attack) for later analysis or reuse.
        * Quickly spinning up identical copies of a configured environment.
    * **Key Point:** Redeploying from a Snapshot restores the lab to that exact saved state, including any software installed or configuration changes made *after* the initial deployment.