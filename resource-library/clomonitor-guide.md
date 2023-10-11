# CLOMonitor Guide

The following is a guide to help you understand the value of CLOMonitor and get started setting your project up to be properly tracked. This is intended to be a living document, so please feel free to submit a pull request if you have any suggestions for improvements.

## Statistically Relevant Security Improvements

Sonatype's recently published 9th annual State of the Software Supply Chain shines a light on the significance of ongoing maintenance in open source projects. One chapter in particular focuses on open source security practices, emphasizing the importance of various checks and providing statistics that highlight their predictive power regarding vulnerability status.

Recognizing that small changes have long-lasting effects in reducing vulnerabilities and weaknesses in open source projects, Sonatype actively collaborates with the Cloud Native Security Foundation (CNCF) and Google Open Source Security Team (GOSST) to help elevate the security posture of the open source ecosystem.

This concerted effort takes shape with the Cloud Native Security Slam, an initiative aimed at incentivizing and fostering collaboration within the open source community. At the heart of this initiative lies CLOMonitor, a powerful tool designed to ensure projects within CNCF adhere to essential project health best practices.

As we explore the significance of ongoing maintenance in open source projects, we'll also highlight key aspects of Sonatype's State of the Software Supply Chain as well as how CLOMonitor serves as a crucial tool to ensure project health best practices. Additionally, we'll discuss the launch of this year's Cloud Native Security Slam - an event that further solidifies the commitment to open source security.

### Statistics from Sonatype's State of the Software Supply Chain

In Sonatype's State of the Software Supply Chain report, we took a deep dive into the state of adoption of open source software (OSS) security best practices, both overall and within specific ecosystems like Java and JavaScript.

We drew on a dataset consisting of OpenSSF Scorecard checks such as the following:

- **Code Review:** This practice of requiring peer reviews before merging code changes emerges as the most important practice, closely associated with better security outcomes.
- **Binaries:** Not checking binary data into the repository is another crucial factor.
- **Dependencies Pinned:** Pinning dependencies to specific versions also plays a significant role in project security.
- **Branch Protection:** Preventing direct pushes to the main branch is a practice that supports code review and security.

We analyzed the connection between higher scores on security checks and better security outcomes. These checks were found to be highly predictive of vulnerability status, underlining their crucial role in project security.

For more information and data, read our full chapter on open source security practices from our report published last week.

## CLOMonitor in the Cloud Native Security Slam

The Cloud Native Security Slam embodies the importance of ongoing maintenance, and the event leverages usage of an important tool: CLOMonitor.

CLOMonitor is designed to address critical challenges within the CNCF ecosystem. This tool acts as a watchman, constantly checking and ensuring that projects incorporate best practices.

It offers a systematic approach to monitor project repositories en masse, helping project maintainers and contributors across the ecosystem adhere to the CNCF's standards of project health and security.

### Ensuring your project is properly tracked within CLOMonitor

CLOMonitor is designed to keep track of CNCF projects and ensure they meet essential project health best practices.

To ensure that your project is correctly tracked and monitored, verify that your project data is correct including that the correct check set is applied to each repository.

To confirm your project's information is accurate and up to date, refer to the [CNCF project data file](https://github.com/cncf/clomonitor/blob/main/data/cncf.yaml).

Data Verification: Check that your project's name, display name, description, category, logo URL, and other relevant details are correctly listed in the data file.
Submit a Pull Request: If you notice any inaccuracies or missing information, consider creating a pull request to modify the data file. This helps keep your project's information accurate and ensures that it is correctly represented within CLOMonitor.

Each project registered with CLOMonitor is represented in a YAML format within the CNCF project data file. Understanding the structure of a YAML entry is essential to ensure that your project's data is correctly formatted.

Below is an explanation of the key elements of a project entry:

```yaml
- name: project_name
  display_name: Project Display Name
  description: Project Description
  category: Project Category
  logo_url: URL_to_Project_Logo
  devstats_url: URL_to_DevStats
  accepted_at: "YYYY-MM-DD"
  maturity: Project Maturity
  repositories:
    - name: repository_name
      url: URL_to_Repository
      check_sets:
        - check_set1
        - check_set2
```

Here is some additional context for the fields in the YAML above:

- **name:** This field should contain a unique identifier for your project. It is used as the reference point for your project within CLOMonitor.
- **display_name:** Specify the human-readable name of your project. This is the name that will be displayed in CLOMonitor.
- **description:** Provide a brief description of your project's purpose and functionality.
- **category:** Indicate the category to which your project belongs within CNCF.
- **logo_url:** Enter the URL to your project's logo. This logo will be used to visually represent your project within CLOMonitor.
- **devstats_url:** Include the URL to access your project's DevStats, which can provide valuable insights into your project's statistics and activity.
- **accepted_at:** Specify the date on which your project was accepted into CNCF in the format "YYYY-MM-DD."
- **maturity:** Indicate the maturity level of your project within CNCF (e.g., sandbox, incubating, graduated).
- **repositories:** Under this section, list the repositories associated with your project. For each repository, provide the following details:
- **name:** The name of the repository.
- **url:** The URL to access the repository.
- **check_sets:** Specify the check set(s) that should be applied to this repository (e.g., code, code-lite, community, docs).

### Understanding check sets

CLOMonitor runs sets of checks periodically on all registered repositories. These checks are organized into different sets, each tailored to specific aspects of your project.
 
Understanding check sets is essential to ensuring your project is evaluated correctly:
- **Code:** This set is recommended for a project's primary code repository. It includes checks related to documentation, licensing, best practices, security, and more.
- **Code-lite:** A subset of the code set, it is recommended for secondary code repositories and focuses on essential checks.
- **Community:** This set is suitable for repositories with community content and includes checks related to documentation, best practices, security, and legal matters.
- **Docs:** Recommended for repositories primarily containing documentation. It includes checks related to documentation quality and licensing.

Review the check sets and choose the one(s) most appropriate for each of your project's repositories. Properly selecting the check set ensures that CLOMonitor evaluates your project according to its specific context and purpose.

For a detailed list of checks performed in each set, please refer to the check sets documentation.

CLOMonitor operates by checking files in specific locations within your repositories. If your project follows a different layout, consider adding a section to your README file pointing users to the document location. This helps CLOMonitor correctly assess your project's compliance.

For further details on how each check is performed, consult the Check Reference. If you encounter issues or have suggestions for improvements, feel free to file an issue or initiate a discussion on GitHub.

### Creating exemptions in CLOMonitor

In some cases, certain checks performed by CLOMonitor may not be applicable to a particular repository. For example, a specific check may not be relevant to the nature or purpose of the repository. In such instances, project maintainers and contributors have the option to declare exemptions for these checks within the `.clomonitor.yml` metadata file.

Declaring exemptions serves as a way to inform CLOMonitor that specific checks should not be applied to a particular repository.

Follow these steps to declare exemptions:

- Edit the `.clomonitor.yml` Metadata File: Locate and access the `.clomonitor.yml` metadata file within your repository.
- Declare exemptions: Within the metadata file, specify the checks for which you are requesting exemptions. These checks are identified by their unique identifiers (IDs), which can be found in the CLOMonitor reference.
- Provide justifications: For each exemption declared, provide a clear and concise reason that justifies the exemption. Explain why the specific check is not applicable to your repository.
- Save and commit: Save the changes to the `.clomonitor.yml` file and commit them to your repository.

Once exemptions are declared in the metadata file, CLOMonitor will recognize them and adjust its checks accordingly. Exempted checks will be specially marked in the CLOMonitor user interface (UI), and the provided justification will be displayed. This ensures transparency and clarity, allowing users to understand why a particular check was not required in a specific case.

Please note that the unique identifiers (IDs) for checks that can be declared as exemptions can be found in the CLOMonitor reference. Before declaring exemptions, carefully review the checks and their IDs to determine which ones are not applicable to your repository.

Exemptions are a valuable tool for tailoring CLOMonitor's checks to your project's specific needs and ensuring that the evaluation of your project's health and security is as accurate as possible.

### Next steps

After you've finished setting up your project and you have your code checks in order, the changes will be visible on the next scan performed by CLOMonitor. Check back in an hour or two to see your results. Your next step will be to start digging in and making iterative improvements to your score.

As open source users and advocates, it is vital to choose well-maintained projects and actively monitor them to ensure they maintain high-security standards. By doing so, enterprises can minimize their open source vulnerability risk and contribute to the overall security of the open source ecosystem.

Sonatype's State of the Software Supply Chain serves as a valuable resource for guiding open source users and maintainers towards safer and more secure software development practices, especially when coupled with the insights from the Cloud Native Security Slam. Together, these initiatives fortify the security of the open source software landscape, ensuring its resilience and reliability for years to come.
