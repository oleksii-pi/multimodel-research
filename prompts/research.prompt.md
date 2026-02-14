Act as a solutions architect. What are the best practices to automate the review process using LLM and GenAI?

Setup: team of 8 engineers, monorepo, standalone application for building digital ad creatives, written in TypeScript, hosted on GCP, Kubernetes, Postgres, and GitLab. The repository contains 900 files. The application is UI-focused, with 2/3 of the code in the frontend. There is some unit test coverage, along with linting, pre-commit, and pre-push hooks.

Problem:

- Sometimes engineers create large merge requests.
- Engineers write lots of code using Copilot, making it hard to review such volumes.
- Engineers generate many unit tests with mocks, but it seems they are not reviewed thoroughly as they are generated. (I have some doubts that the mock approach is optimal, as it fixates low-level class designs, seems to discourage refactoring, and does not cover integration aspects.)
- I want to encourage a culture of manual testing first when we create MRs, as complex code changes are hard to review and predict potential issues.
- There is a lack of e2e tests to catch critical flows (smoke tests).
- Implementing a new feature in a non-critical flow can accidentally break a nearby feature.
- Engineers also feel a lack of documentation and alignment on best practices.

Desire:

- Minimize the number of uncaught mistakes or bugs during runtime.
- Minimize the amount of manual review or the need to point out areas that require attention.

After reasoning, provide a markdown file review.agent.md:

Craft a good prompt in Markdown for Copilot that will address my team's challenges. Make it concise, no longer than 100 lines of instructions.
