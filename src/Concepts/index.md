# Concepts

Welcome to OpenLabs! Our goal is to make designing, deploying, and managing network labs (especially for cybersecurity) straightforward and efficient.

## Core Components

* **Range:** The overall boundary and management container for your deployed lab in a specific cloud and region. It groups all related live resources.
* **VPC:** Provides network isolation for a part of your Range, defining a private IP address space. Essential for creating secure and organized network segments.
* **Subnet:** Allows further segmentation within a VPC. Useful for organizing hosts based on function or security requirements (e.g., public-facing vs. internal).
* **Host:** The individual virtual machines within your lab. These are defined in your Blueprint with specific OS, hardware (CPU/RAM), and storage, and become running instances within a Subnet when deployed.

## Collaboration and Organization

* **Workspaces:** Allow you to group users into teams. Workspaces facilitate sharing Blueprints and potentially managing access to deployed Ranges within a collaborative environment.
* **Permissions:** Control who can view (`read`) or modify (`write`) your Blueprints, enabling secure sharing and reuse of designs among users or within Workspaces.