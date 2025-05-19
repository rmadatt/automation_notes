# automation_notes
Automation help by Grok. I have been lazy to learn automation properly and depended on others to do it for platforms

GitHub Contribution Grader
Overview

This project automates grading and tracking of GitHub contributions (commits, pull requests, issues) and inferred logins (active days) for repository members. It uses the GitHub API to fetch data, calculates scores based on a customizable rubric, and outputs results to a CSV file. The automation runs via GitHub Actions for periodic updates.

Features

Tracks commits, pull requests, issues, comments, and active days.
Assigns scores (e.g., 5 points/commit, 10 points/merged PR).
Outputs grades to contribution_grades.csv.
Runs automatically via GitHub Actions.
Setup

Clone the Repository: Download the script (github_contribution_grader.py).
Install Dependencies: Run pip install requests.
Configure Environment:
Set GITHUB_TOKEN as an environment variable (GitHub Personal Access Token with repo and user scopes).
Update REPO in the script (e.g., owner/repo).
Adjust DAYS_TO_CHECK and RUBRIC as needed.
Set Up GitHub Actions:
Add grade-contributions.yml to .github/workflows/.
Store GITHUB_TOKEN in repository secrets (Settings > Secrets and variables > Actions).
Run Manually (Optional): Execute python github_contribution_grader.py to test.
Usage

The script runs automatically per the GitHub Actions schedule (daily by default).
Check contribution_grades.csv for results, including usernames, total grades, and contribution details.
Customize the rubric in the script to align with your team’s priorities.
Notes

GitHub API rate limits apply (5,000 requests/hour for authenticated users).
Login tracking infers active days from events, as GitHub doesn’t expose login data.
Ensure team consent for contribution tracking.
