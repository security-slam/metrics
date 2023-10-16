# Getting Started with the Security Slam

The Security Slam is a security hygiene effort that uses CLOMonitor to evaluate project progress toward metrics defined by the community.

CLOMonitor is a tool that helps projects measure their progress toward security hygiene goals. It is designed to be run on a regular basis and will track progress over time.

Some security hygiene elements have been identified that require additional human verification. To partially automate these elements, CLOMonitor now includes several checks that read a repo's `SECURITY-INSIGHTS.yml`. For more information about getting started with this file, see the [Security Insights guide](security-insights-guide.md).

_Roadmap Note: The quickstart below will need to be made ecosystem-agnostic if/when future events are planned for other communities who have expressed interest. For now, this is specific to the CNCF ecosystem._

## Quickstart

1. Review the [metrics that will be scored](../cncf/2023/README.md) during the event. 
1. Ensure your project is properly including every repo that should be tracked, with the correct check sets specified for each.
    - Read more in the [CLOMonitor Guide](clomonitor-guide.md).
1. Look for a GitHub Issue or Discussion thread in your project repo(s). If you don't see one, you can create one to start the conversation.
    - CLOMonitor has a helpful button for each repository that will create a checklist-style markdown list for you to put in a GitHub Issue. Look for the hamburger menu in the right of each repository section on your project page in the CLOMonitor UI.
1. As appropriate, create sub-issues with the `help wanted` label to help contributors quickly find ways to contribute to the Slam.
    - If your project community and/or maintainer base is small, consider asking for help on the Security Slam Slack channel.
1. If you get stuck while working on an issue, also consider asking for help on the Security Slam Slack channel or look to see if your question has already been answered. There are SMEs from Google, Sonatype, and across the CNCF community who have already expressed a desire to help in Slack!
