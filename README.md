<p align="center">
  <img width="780" height="585" src="images/crash_image.jpg">
</p>

<!---

![Screenshot of Crash Bandicoot Coding.](images/crash_image.jpg)
-->


# Nerd Nest
NerdNest is a comprehensive, open-source repository that provides tutorials, guides, and practical examples across key IT domains. The mission is to empower learners with the knowledge and skills needed to succeed in IT, from technical expertise to professional soft skills.

**Attribution**  
Significant parts of this repository's content were created with the assistance of Grok by xAI.  
For more information visit https://grok.x.ai


# Table of Contents

## [Tech Topics](#tech-topics) 
  - [Linux](#linux)
  - [Networking](#networking)
  - [Security](#security)
  - [Virtualization](#virtualization)
  - [Cloud Computing](#cloud-computing)
  - [Kubernetes](#kubernetes)
  - [Openshift](#openshift)
  - [Git](#git)
  - [Agile](#agile)
  - [Automation](#automation)
  - [Development](#development)
  - [Tools/Applications](#tools/applications)
  - [Artificial Intelligence](#artificial-intelligence)
  - [AI Agents](#ai-agents)
## [Career Topics](#career-topics)
  - [Roles and Responsiblilities](#roles-and-responsiblilities)
  - [Meeting Types](#meeting-types)
  - [Soft-Skills](#soft-skills)
  - [Documentation](#documentation)
## [Useful Resources](#useful-resources)
  - [Book Recommendations](#book-recommendations)
  - [Other Useful Resources](#other-useful-resources)

# Tech Topics

## Linux
[home &uarr;](#nerd-nest)

> **Linux** is more than an operating system; it is a programmable interface for hardware. Whether you are deploying to the cloud, managing a database, or running containers, Linux is the environment where your code actually lives.
>
> This section is designed to turn the command line into your primary productivity tool. We begin with a high-level **Introduction** to the Linux philosophy, then dive straight into **Essential Commands** and the **Vim editor**. Once the basics are second nature, we explore the deep technical mechanics—from **Bash One-Liners** and **Shell Scripting** to the inner workings of the **Linux Kernel**. This path is built to transform you from a user who "runs commands" into an engineer who orchestrates systems.

| Topic | Description |
| :--- | :--- |
| [Introduction to Linux](topics/linux/01_intro.md) | The history, philosophy, and why Linux is the backbone of modern engineering. |
| [Essential Linux Commands](topics/linux/02_essential_commands.md) | Getting comfortable with the CLI: Navigating, reading, and moving files. |
| [Mastering the Vim Editor](topics/linux/03_vim.md) | A practical guide to survival and efficiency in the world's most famous text editor. |
| [Users, Permissions & Sudo](topics/linux/04_sudo_permissions.md) | Managing the security model, `root` access, and the `chmod/chown` system. |
| [Pipes, Redirection & Streams](topics/linux/05_streams.md) | Learning the "Linux Way": Connecting small tools to solve big data problems. |
| [Bash One-Liners for Efficiency](topics/linux/06_bash_oneliners.md) | A collection of lethal, single-line commands for logs, files, and system checks. |
| [Shell Scripting Fundamentals](topics/linux/07_scripting.md) | Moving from commands to automation: Variables, loops, and conditional logic. |
| [The Linux Kernel & Architecture](topics/linux/08_kernel.md) | Peeking under the hood at syscalls, memory management, and hardware abstraction. |
| [Process Management](topics/linux/09_processes.md) | How the OS handles multitasking, signals, and monitoring system resources. |
| [Networking & SSH](topics/linux/10_networking.md) | Understanding the stack, troubleshooting connectivity, and securing remote access. |
| [Package & Service Management](topics/linux/11_packages_services.md) | How software is installed and managed as background services via `systemd`. |
| [Linux Troubleshooting](topics/linux/12_troubleshooting.md) | Common error patterns, log analysis, and "first-response" recovery tactics. |
| [Additional Resources](topics/linux/13_resources.md) | A curated list of Linux books, cheat sheets, and advanced interactive tutorials. |
| [Linux Glossary](topics/linux/14_glossary.md) | A comprehensive reference for essential terms from Kernel Panic to Symbolic Links. |


## Networking
[home &uarr;](#nerd-nest)

Computer networking connects devices to share data via wired (Ethernet) or wireless (Wi-Fi) technologies, using protocols like TCP/IP for reliable communication. It involves routers, switches, and servers, supporting everything from local networks (LANs) to the internet.

Software engineers learn networking to build and maintain web apps, cloud services, or IoT systems. It helps optimize data transfer, secure communications, and troubleshoot issues like latency. Essential for backend, DevOps, and cybersecurity, networking knowledge supports scalable systems and boosts career growth in cloud-based industries.

 | Topic         | Description   |
 | :------------ | :----------- |
 | [Networking Fundamentals](topics/networking/networking_fundamentals.md) | An overview  of networking fundamentals and the main concepts. |
 | [The OSI Model and Networking Layers](topics/networking/networking_osi_model.md) | Description of the OSI Model which is a conceptual framework to standardize and simplify network communication. |
 | [Protocols: The Language of Networks](topics/networking/networking_protocols.md) | Understanding the fundamental concepts in computer networking that enable devices to communicate over a network |
 | [Understanding TCP and UDP](topics/networking/networking_tcp_udp.md) | Description of TCP and UDP which define how data is transmitted between devices over a network, handling the packaging, delivery, and integrity of data. |
 | [Ports and Network Communication](topics/networking/networking_ports.md) | Understanding the fundamental concepts in computer networking that enable devices to communicate over a network |
 | [IP Addressing and Subnetting](topics/networking/networking_ipaddr_subnet.md) | Understanding how to calculate subnets, address allocation, and differences between public and private addresses |
 | [Networking Devices and Infrastructure](topics/networking/networking_devices_infrastructure.md) | Exploring key hardware components like routers, switches, access points, and firewalls, while delving into their operational layers, segmentation techniques, and wireless capabilities |
 | [Common Networking tools](topics/networking/networking_tools.md) | A list of top Linux networking tools which are widely used for network administration, monitoring, troubleshooting, and security tasks. |
 | [Networking Tools and Troubleshooting](topics/networking/networking_tools_troubleshooting.md) | Introduces essential command-line and graphical tools for inspecting network behavior, from basic connectivity checks to advanced packet analysis. |
 | [Toubleshooting vs debugging](topics/networking/networking_troubleshooting_debugging.md) | Describing and comparing the basic principles of troubleshooting and debugging. |


## Security
[home &uarr;](#nerd-nest)

Computer security, or cybersecurity, is the practice of protecting computers, networks, and data from unauthorized access, attacks, or damage. It involves techniques like encryption, firewalls, and authentication to safeguard systems against threats such as malware, phishing, or data breaches. Cybersecurity ensures confidentiality, integrity, and availability of information in applications like online banking or cloud storage.

Software engineers learn cybersecurity to build secure applications, protect user data, and prevent vulnerabilities in code. It’s critical for designing APIs, securing cloud services, and mitigating risks like SQL injection or cross-site scripting. Understanding security helps engineers comply with regulations and maintain user trust, while expertise in this field is vital for careers in web development, DevOps, and system administration.

 | Topic         | Description   |
 | :------------ | :----------- |
 | [Introduction to Network Security](topics/security/network_security_intro.md) | Introduces network security principles, the CIA triad, and its role in IT systems. |
 | [Common Network Threats and Vulnerabilities](topics/security/network_threats__vulnerabilities.md) | Explores prevalent threats like DDoS and vulnerabilities like misconfigurations. |
 | [Firewalls and Access Control](topics/security/network_firewalls_access_control.md) | Covers firewall types and configurations to regulate network traffic and access. |
 | [Encryption and Secure Communication](topics/security/network_encryption_secure_comms.md) | Explains encryption protocols like SSL/TLS for securing data in transit. |
 | [Intrusion Detection and Prevention Systems (IDPS)](topics/security/network_intrusion_detection.md) | Details tools like Snort for detecting and mitigating network intrusions. |
 | [Network Authentication and Authorization](topics/security/network_authentication_authorization.md) | Discusses protocols like RADIUS and MFA for securing network access. |
 | [Securing Wireless Networks](topics/security/securing_wireless_networks.md) | Focuses on Wi-Fi security protocols and protecting wireless access points.  |
 | [Network Monitoring and Security Tools](topics/security/network_monitoring_tools.md) | Introduces tools like Wireshark and SIEM for monitoring and analyzing threats. |
 | [Best Practices for Network Security](topics/security/network_security_best_practices.md) | Provides strategies like patching and segmentation for robust network protection. |

## Virtualization
[home &uarr;](#nerd-nest)

Virtualization is the creation of virtual versions of computing resources, such as servers, operating systems, or storage, using software called hypervisors (e.g., VMware, VirtualBox). It allows multiple virtual machines to run on a single physical machine, isolating environments while sharing hardware resources, enabling efficient testing, development, or cloud computing.

Software engineers learn virtualization to build and test applications in isolated, reproducible environments, like simulating different operating systems. It’s crucial for DevOps, cloud platforms (e.g., AWS, Azure), and containerization (e.g., Docker), optimizing resource use and scalability. Understanding virtualization enhances skills in system deployment and management, boosting career prospects in cloud-based and enterprise development.

 | Topic         | Description   |
 | :------------ | :----------- |
 | [Introduction to Virtualization ](topics/virtualization/virtualization_introduction.md) | Introduces virtualization concepts, benefits, and its role in IT ecosystems. |
 | [Types of Virtualization ](topics/virtualization/virtualization_types.md) | Explores server, desktop, network, storage, and application virtualization use cases. |
 | [Hypervisors: The Core of Virtualization ](topics/virtualization/virtualization_hypervisors.md) | Explains Type 1 and Type 2 hypervisors and their role in managing VMs. |
 | [Setting Up Virtual Machines ](topics/virtualization/virtual_machines.md) | Guides learners through creating and configuring virtual machines with tools like KVM. |
 | [Virtualization in Linux Environments ](topics/virtualization/virtualization_linux.md) | Covers Linux-native virtualization tools like KVM and VirtualBox for practical deployment. |
 | [Networking in Virtual Environments ](topics/virtualization/networking_virtual_environments.md) | Details virtual networking, including switches and configurations for VM connectivity. |
 | [Storage Virtualization ](topics/virtualization/virtualization_storage.md) | Introduces techniques for abstracting and managing storage in virtual environments. |
 | [Security in Virtualized Environments ](topics/virtualization/virtualized_environments_security.md) | Discusses securing VMs and hypervisors against threats like VM escape. |
 | [Virtualization Management and Automation ](topics/virtualization/virtualization_management.md) | Explores tools and scripts for managing and automating VM tasks in Linux. |

## Cloud Computing
[home &uarr;](#nerd-nest)

Cloud computing is the delivery of computing resources, like servers, storage, or software, over the internet, using services like AWS, Azure, or Google Cloud. It enables on-demand access to scalable, flexible infrastructure without physical hardware management, supporting applications from web hosting to AI model training.

Software engineers learn cloud computing to build, deploy, and scale applications efficiently, such as web apps or machine learning pipelines. It streamlines development with tools for automation, storage, and networking, while ensuring cost-efficiency and reliability. Mastery of cloud platforms is essential for careers in DevOps, backend development, and modern software engineering.

 | Topic | Description |
 | :---- | :---------- |
 | [Introduction to Cloud Computing](topics/cloud_computing/introduction_to_cloud_computing.md) | Introduces cloud computing concepts, benefits, and its role in IT ecosystems. |
 | [Cloud Computing Fundamentals](topics/cloud_computing/cloud_computing_fundamentals.md) | An overview of definitions, key service and deployment models, core characteristics, and associated benefits and challenges. |
 | [Cloud Computing Concepts](topics/cloud_computing/cloud_concepts.md) | Describes Cloud Computing concepts, service models (IaaS, PaaS, SaaS), deployment models, virtualization, scalability, pricing, and security. |
 | [Cloud Service Models](topics/cloud_computing/cloud_service_models.md) | Explores IaaS, PaaS, and SaaS models and their applications in cloud environments. |
 | [Cloud Deployment Models](topics/cloud_computing/cloud_deployment_models.md) | Covers public, private, hybrid, and community clouds for different organizational needs. |
 | [Cloud Providers and Platforms](topics/cloud_computing/cloud_providers_and_platforms.md) | Introduces major cloud providers like AWS and tools for managing cloud resources. |
 | [Setting Up Cloud Instances](topics/cloud_computing/setting_up_cloud_instances.md) | Guides learners through creating and managing virtual machine instances in the cloud. |
 | [Cloud Networking and Security](topics/cloud_computing/cloud_networking_and_security.md) | Details virtual network configurations and security practices for cloud environments. |
 | [Cloud Storage and Data Management](topics/cloud_computing/cloud_storage_and_data_management.md) | Explores object, block, and file storage for efficient data management in the cloud. |
 | [Automation and Orchestration in the Cloud](topics/cloud_computing/automation_and_orchestration_in_cloud.md) | Covers tools like Kubernetes for automating and managing cloud resources. |
 | [Cost Management and Optimization in the Cloud](topics/cloud_computing/cost_management_and_optimization_in_cloud.md) | Provides strategies for monitoring and optimizing cloud costs effectively. |

## Kubernetes
[home &uarr;](#nerd-nest)

 | Topic | Description |
 | :------------ | :----------- |
 | [Kubernetes Overview and Introduction](topics/kubernetes/kubernetes_overview_and_introduction.md) | Introduces Kubernetes, its role in container orchestration, and key use cases like cloud and edge deployments. Covers history and comparisons with alternatives. |
 | [Kubernetes Fundamentals](topics/kubernetes/kubernetes_fundamentals.md) | Explains core components (pods, nodes, clusters, control plane) and the Kubernetes architecture for managing containers at scale. |
 | [Key Kubernetes Concepts](topics/kubernetes/key_kubernetes_concepts.md) | Details essential objects like Deployments, Services, ConfigMaps, and Namespaces, with YAML-based configuration examples. |
 | [Setting Up and Managing Kubernetes Clusters](topics/kubernetes/setting_up_and_managing_clusters.md) | Guides on creating and maintaining clusters using Minikube, cloud providers (e.g., AWS EKS), or kubeadm for local and production environments. |
 | [Workloads and Resource Management](topics/kubernetes/workloads_and_resource_management.md) | Covers workload types (Pods, ReplicaSets, StatefulSets) and resource management techniques like autoscaling and scheduling. |
 | [Networking in Kubernetes](topics/kubernetes/networking_in_kubernetes.md) | Explores pod communication, Services (ClusterIP, NodePort), Ingress, and network policies, with emphasis on edge computing applications. |
 | [Storage in Kubernetes](topics/kubernetes/storage_in_kubernetes.md) | Describes storage solutions like Persistent Volumes, Claims, and StorageClasses, including edge-specific local storage options. |
 | [CI/CD and DevOps with Kubernetes](topics/kubernetes/cicd_and_devops.md) | Shows how to integrate Kubernetes with CI/CD pipelines (e.g., Jenkins, ArgoCD) and GitOps for automated, scalable deployments. |
 | [Security and Best Practices in Kubernetes](topics/kubernetes/security_and_best_practices.md) | Covers securing clusters with RBAC, Pod Security Policies, and monitoring tools (e.g., Prometheus) for reliable operations. |
 | [Advanced Kubernetes Topics](topics/kubernetes/advanced_kubernetes_topics.md) | Dives into custom controllers, CRDs, Operators, and edge integrations (e.g., KubeEdge) for AI and distributed systems. |

## Openshift
[home &uarr;](#nerd-nest)

 | Topic | Description |
 | :------------ | :----------- |
 | [OpenShift Overview and Introduction](topics/openshift/openshift_overview_and_introduction.md) | Introduces OpenShift, its role as a Kubernetes-based platform, and enterprise use cases like cloud and edge deployments. |
 | [OpenShift Architecture and Components](topics/openshift/openshift_architecture_and_components.md) | Explores OpenShift’s architecture, Kubernetes integration, and unique features like the web console and CLI. |
 | [Key OpenShift Concepts](topics/openshift/key_openshift_concepts.md) | Details core objects like Projects, Routes, BuildConfigs, and DeploymentConfigs for app management. |
 | [Setting Up an OpenShift Cluster](topics/openshift/setting_up_an_openshift_cluster.md) | Guides on creating and managing local or cloud-based OpenShift clusters for learning and production. |
 | [Deploying Applications on OpenShift](topics/openshift/deploying_applications_on_openshift.md) | Explains deploying apps using Source-to-Image (S2I), templates, and Docker images. |
 | [Networking and Routes in OpenShift](topics/openshift/networking_and_routes_in_openshift.md) | Covers OpenShift’s networking model, Routes for external access, and edge computing applications. |
 | [Storage Management in OpenShift](topics/openshift/storage_management_in_openshift.md) | Describes persistent storage, Persistent Volume Claims, and edge storage solutions. |
 | [CI/CD and DevOps with OpenShift](topics/openshift/cicd_and_devops_with_openshift.md) | Explores OpenShift Pipelines, GitOps, and CI/CD integration for automated deployments. |
 | [Security and Best Practices in OpenShift](topics/openshift/security_and_best_practices_in_openshift.md) | Covers securing clusters with RBAC, Security Context Constraints, and monitoring tools. |
 | [Advanced OpenShift Topics](topics/openshift/advanced_openshift_topics.md) | Dives into Operators, serverless computing, and edge integrations like OpenShift Edge. |

 | [Understanding Kubernetes](docs/kubernetes_overview.md) |  |
 | [Understanding Openshift](docs/openshift_overview.md) |  |


## Git
[home &uarr;](#nerd-nest)

Git is a distributed version control system that tracks changes to code, allowing multiple developers to collaborate on projects. It stores code versions in repositories, enabling branching, merging, and rollback to manage updates efficiently, with platforms like GitHub or GitLab hosting remote repositories.

Software engineers use Git to manage codebases, coordinate team contributions, and maintain project history. It’s essential for collaborative development, CI/CD pipelines, and open-source projects, ensuring code integrity and streamlined workflows. Learning Git is critical for careers in software engineering, DevOps, and team-based development.

 | Topic         | Description   |
 | :------------ | :----------- | 
 | [Github Overview](topics/git/github_overview.md) | An overview of GitHub, its uses, and its main concepts. |
 | [Git Overview](topics/git/git_overview.md) | An overview of Git which is a distributed version control system used to track changes in source code or other files during collaborative projects |
 | [Git Tutorial](topics/git/git_tutorial.md) | A beginner-friendly tutorial on using the Git version control system for software engineers. |

## Agile
[home &uarr;](#nerd-nest)

Agile is a software development methodology that emphasizes iterative, flexible, and collaborative approaches to building software. It uses short development cycles (sprints), frequent feedback, and adaptive planning, with frameworks like Scrum or Kanban, to deliver working software incrementally.

Software engineers adopt Agile to enhance teamwork, adapt to changing requirements, and deliver high-quality code faster. It’s vital for managing complex projects, ensuring customer satisfaction, and aligning with business needs. Proficiency in Agile is essential for careers in software engineering, DevOps, and project management, fostering efficient and responsive development processes.

 | Topic         | Description   |
 | :---- | :----------- |
 | [Agile concepts](topics/agile/agile_concepts.md) | Comprehensive guide to Agile software development principles and practices. |
 | [Jira concepts](topics/agile/jira_concepts.md) | Comprehensive guide to Jira: features, workflows, and Agile usage in software engineering. |

## Automation
[home &uarr;](#nerd-nest)

Automation in software engineering is the use of tools and scripts to perform repetitive tasks, such as testing, deployment, or system monitoring, without manual intervention. It leverages technologies like CI/CD pipelines, scripting (e.g., Python), and tools like Jenkins or Ansible to streamline processes.

Software engineers use automation to boost efficiency, reduce errors, and accelerate development cycles, such as automating code testing or server provisioning. It’s critical for DevOps, cloud computing, and scalable systems, ensuring consistent, reliable workflows. Mastering automation is essential for careers in software engineering, DevOps, and system administration.

| Topic | Description |
| :---- | :---------- |
| [Introduction to Automation](topics/automation/introduction_to_automation.md) | Introduces automation concepts, benefits, and its role in IT efficiency. |
| [Scripting for Automation](topics/automation/scripting_for_automation.md) | Covers writing scripts in Bash and Python for automating IT tasks. |
| [Automation Tools and Frameworks](topics/automation/automation_tools_and_frameworks.md) | Explores tools like Ansible and Puppet for configuration management. |
| [Task Scheduling and Cron Jobs](topics/automation/task_scheduling_and_cron_jobs.md) | Details scheduling automated tasks using cron in Linux environments. |
| [Automation in System Administration](topics/automation/automation_in_system_administration.md) | Focuses on automating Linux system tasks like user and package management. |
| [Automation in Networking](topics/automation/automation_in_networking.md) | Covers automating network configurations and monitoring tasks. |
| [Automation in Virtualization and Cloud](topics/automation/automation_in_virtualization_and_cloud.md) | Discusses automating VM and cloud resource management with tools like Terraform. |
| [Continuous Integration and Deployment (CI/CD)](topics/automation/continuous_integration_and_deployment.md) | Introduces CI/CD pipelines for automating software delivery. |
| [Monitoring and Error Handling in Automation](topics/automation/monitoring_and_error_handling_in_automation.md) | Explores monitoring automation workflows and handling errors effectively. |

## Development
[home &uarr;](#nerd-nest)

Software development is the process of designing, coding, testing, and maintaining software applications or systems to solve problems or meet user needs. It involves programming languages (e.g., Python, Java), tools like IDEs, and methodologies like Agile to create everything from mobile apps to enterprise systems.

Software engineers learn software development to build functional, efficient, and user-friendly applications, such as web platforms or AI tools. It’s essential for creating scalable, secure software and collaborating on projects using version control like Git. Proficiency in software development is critical for careers in programming, DevOps, and tech innovation.

 | Topic         | Description   |
 | :------------ | :----------- |
 | [Understanding Languages](resources/understanding_languages.md) | A brief description of the different types of of languages and what they are used for. |
 | TODO | |

## Tools/Applications
[home &uarr;](#nerd-nest)
 

## Artificial Intelligence
[home &uarr;](#nerd-nest)

Artificial Intelligence has evolved from a specialized academic discipline into a fundamental toolset for the modern software engineer. Rather than writing every line of logic manually, we now architect systems capable of understanding intent, processing vast amounts of unstructured data, and generating complex outputs through Large Language Models (LLMs).

This section provides a structured roadmap for engineers to master this new paradigm. We move beyond basic chat interfaces to explore the underlying architecture of Transformers, the precision of Prompt Engineering, and the integration of AI into the Software Development Lifecycle (SDLC). By bridging the gap between foundational theory and production-grade implementation—including RAG and secure API integration—you will learn how to build applications that are not just "smart," but robust, ethical, and scalable.

| Topic | Description |
| :--- | :--- |
| [AI Fundamentals & Mental Models](topics/ai/01_ai_fundamentals.md) | Breaking down what AI actually is and moving past the "magic" to engineering reality. |
| [How AI Works: The Architecture](topics/ai/02_how_ai_works.md) | Understanding Transformers, Neural Networks, and the math behind the predictions. |
| [Prompt Engineering Mastery](topics/ai/03_prompt_engineering.md) | Techniques for structured prompting, including Few-Shot, System Roles, and Delimiters. |
| [Advanced AI Workflows](topics/ai/04_advanced_workflows.md) | Moving beyond basic chat into complex reasoning and multi-step automation. |
| [AI for Software Developers](topics/ai/05_ai_for_devs.md) | Practical integration of AI into the SDLC, from coding assistants to automated testing. |
| [Data Basics for AI](topics/ai/06_data_basics.md) | Exploring the data lifecycle, tokenization, and how data quality affects AI output. |
| [Machine Learning Fundamentals](topics/ai/07_machine_learning.md) | A deep dive into supervised, unsupervised, and reinforcement learning principles. |
| [Deep Learning & Neural Networks](topics/ai/08_deep_learning.md) | Understanding layers, weights, and the biological inspiration for modern AI models. |
| [Building with LLMs](topics/ai/09_building_with_llms.md) | How to build applications using APIs, RAG (Retrieval-Augmented Generation), and fine-tuning. |
| [AI Ethics, Security & Trends](topics/ai/10_ethics_security.md) | Navigating the challenges of bias, security vulnerabilities, and future technology trends. |
| [Extra Learning Resources](topics/ai/11_extra_resources.md) | A curated list of books, courses, and YouTube channels for continued mastery. |
| [Core AI Glossary](topics/ai/12_glossary.md) | A comprehensive reference for essential terms from Backpropagation to Zero-Shot. |

## AI Agents
[home &uarr;](#nerd-nest)

AI Agents represent the shift from AI as a chatbot to AI as an autonomous coworker. While standard models respond to prompts, Agentic Systems are designed to perceive their environment, reason through complex goals, and execute actions using external tools. This section moves beyond simple generation and into the world of autonomous architecture.

You will explore the "Agentic Loop"—the cycle of sensing, deciding, and acting—that allows AI to solve multi-step engineering problems. By mastering persona design, multi-agent orchestration, and advanced reasoning patterns like ReAct, you will learn to build digital teams capable of self-correction and goal-oriented execution. This is the blueprint for the next generation of software: systems that don't just suggest code, but actively build, test, and maintain it.

| Topic | Description |
| :--- | :--- |
| [The Anatomy of an Agent](topics/ai_agents/01_anatomy_of_agents.md) | Explores the fundamental loop of Sensors, Models, and Actuators within an Environment. |
| [Types of Agent Structures](topics/ai_agents/02_agent_types.md) | Categorizes agents from Simple Reflex systems to sophisticated Learning Agents. |
| [Persona Design & Guardrails](topics/ai_agents/03_persona_design.md) | How to define an agent's role, expertise, and boundaries to ensure consistent behavior. |
| [Reasoning Patterns (CoT & ReAct)](topics/ai_agents/04_reasoning_patterns.md) | Deep dive into "thinking out loud" through Chain-of-Thought and Action-Observation loops. |
| [Tool Use & Function Calling](topics/ai_agents/05_tool_calling.md) | Connecting AI reasoning to Virtual Actuators and APIs to affect the digital world. |
| [Agent Memory Systems](topics/ai_agents/06_agent_memory.md) | Balancing Short-Term context windows with Long-Term storage using Vector Databases. |
| [Reflection Loops & Self-Correction](topics/ai_agents/07_reflection_loops.md) | Implementing feedback mechanisms so agents can critique and improve their own output. |
| [Multi-Agent Teams & Orchestration](topics/ai_agents/08_multi_agent_teams.md) | Coordinating specialized agents to work together using frameworks like CrewAI and AutoGen. |
| [Agent Security & Guardrails](topics/ai_agents/09_agent_security.md) | Protecting infrastructure through sandboxing, least privilege, and Human-in-the-Loop patterns. |
| [Capstone Project: Log-to-Fix Agent](topics/ai_agents/10_capstone_project.md) | A comprehensive project applying all concepts to build an autonomous SRE assistant. |
| [Agentic AI Resources](topics/ai_agents/11_agent_resources.md) | A curated list of 2026's best frameworks, research papers, and learning materials. |
| [Agentic AI Glossary](topics/ai_agents/12_agent_glossary.md) | Quick reference for specialized terminology from ReAct loops to Agentic Drift. |

## Job Roles

 | Topic         | Description   |
 | :------------ | :----------- |
 | [SysAdmin](resources/sysadmin_role.md) | |
 | Devops | |
 | [SRE](resources/sre_role.md) | |
 | [Customer-facing roles](resources/customer_facing_roles.md) | |
 | [Engineering roles](resources/software_eng_roles.md) | |
 | Leadership roles | |

## Roles and Responsiblilities
[home &uarr;](#nerd-nest)

 | Topic         | Description   |
 | :------------ | :----------- |
 | [Meeting types](resources/meeting_types.md) | |
 | [Documentation types](doc_types/documentation-types.md) | A basic template with tips on how to write a proposal document. |
 | [Writing a Proposal Doc](resources/proposal_doc.md) | A basic template with tips on how to write a proposal document. |
 | [SLA's, SLO's, and SLI's](resources/sla_slo_sli.md) | |
 | [Error Budget and Burn Rate](resources/error_budget_burn_rate.md) | A brief explination of Error Budgets and Burn Rates with examples. |
 
## Soft-Skills
[home &uarr;](#nerd-nest)

Soft skills are non-technical abilities, like communication, teamwork, problem-solving, and adaptability, that enhance interpersonal interactions and workplace effectiveness. In software engineering, they complement technical skills, enabling collaboration, project management, and client engagement in dynamic team settings.

Software engineers develop soft skills to work effectively in Agile teams, communicate ideas clearly, and adapt to changing project demands. These skills are vital for collaborating on codebases, resolving conflicts, and delivering user-focused solutions. Mastering soft skills is essential for career growth in software engineering, leadership roles, and cross-functional tech projects.

 | Topic         | Description   |
 | :------------ | :----------- |
 | [Soft-skills Overview](resources/understanding_soft_skills.md) | |
 | [Crucial Conversations](resources/crucial_conversations.md) | |
 | [Giving and Receiving Feedback](resources/giving_receiving_feedback.md) | |
 | [Importance of Accountability](resources/importance_of_accountability.md) | |
 | [Driving Accountability](resources/driving_accountability.md) | |
 | [Understanding Unconscious Bias](resources/unconscious_bias.md) | |

## Book Recommendations

### Soft-skills Books
- 5 Choices of Extraordinary Productivity
    - by Adam Merrill, Kory Kogon, and Leena Rinne
- 7 Habits of Highly Effective People
    -  by Stephen Covey
- Crucial Conversations: Tools for Talking When Stakes Are High 
    - by Kerry Patterson, Joseph Grenny, Ron McMillan, and Al Switzler  
- Deep Work: Rules for Focused Success in a Distracted World 
    - by Cal Newport
- Influence: The Psychology of Persuasion 
    - by Robert B. Cialdini
- Soft Skills: The Software Developer’s Life Manual
    - by John Sonmez

### Engineering books
- Think Like a Programmer: An Introduction to Creative Problem Solving
    - by V. Anton Spraul
- Clean Code: A Handbook of Agile Software Craftsmanship
    - by Robert C. Martin
- The Pragmatic Programmer: Your Journey to Mastery
    - by Andrew Hunt and David Thomas
- Design Patterns: Elements of Reusable Object-Oriented Software
    - by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides 
- Refactoring: Improving the Design of Existing Code
    - by Martin Fowler
- Introduction to Algorithms
    - by Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, and Clifford Stein  

### Networking books
-

### Security books
-

### Virtualisation books
-

### Cloud books
-

### SRE/OPS books
- [Google SRE Book - (read online)](https://sre.google/sre-book/table-of-contents/)

### Management books
-

## Useful Resources
- 
