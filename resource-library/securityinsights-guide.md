# Getting Started with Security Insights

Security in open source projects is a top priority, and it's crucial to ensure that your projects meet robust security standards. This is where the Security Insights specification comes into play, offering a structured approach to documenting security decisions in a human-readable and machine-readable format.

Maintaining the security of your CNCF projects isn't just about writing secure code; it's also about transparently communicating your security practices. Security Insights empowers project maintainers and contributors to report vital security information in a structured manner. This not only aids in maintaining a high level of trust within the CNCF community but also fosters confidence among your project's users.

One of the more impactful early adopters of Security Insights for automated checks is the Linux Foundation's CLOMonitor— a powerful tool for monitoring the security hygiene of select projects. 

By using Security Insights, projects tracked by CLOMonitor can document their security measures, making them machine-readable for several of the automated checks. This integration streamlines the evaluation of each project's security, allowing maintainers to proactively address vulnerabilities and concerns.

To get started, familiarize yourself with the official [Security Insights specification](https://github.com/ossf/security-insights-spec/releases/download/v1.0.0/specification.md) which is released with semantic versioning on [the project's GitHub repo](https://github.com/ossf/security-insights-spec). This specification outlines the structure and requirements for creating a Security Insights file.

Remember, when implementing Security Insights in your project, the file should be named `SECURITY-INSIGHTS.yml` and reside at the top layer of your project repository. This ensures that readers and automated tools can easily access and analyze the security information you provide.

By adopting Security Insights and integrating it with a tool such as CLOMonitor, you take a proactive step toward enhancing the security of your project. It's not simply about writing secure code; it's about demonstrating your commitment to transparency and best security practices within the open-source community.
