# Parri plugins for Claude

This marketplace contains Parri Academic, a course-scoped tutoring plugin.

In Claude, open **Customize → Plugins → Add → Add marketplace**, enter `ElaNahmias9/parri-plugins`, then select **Parri Academic** and click **Add**. Connect your
Parri account and choose the courses it may access. No API key is required.

The plugin connects to https://parr-seven.vercel.app/mcp using OAuth and PKCE.
Course access can be revoked from Parri at any time. No credentials or course
data are included in this repository.

For Claude Code, add the repository with `/plugin marketplace add ElaNahmias9/parri-plugins`
and install `/plugin install parri-academic@parri`.
