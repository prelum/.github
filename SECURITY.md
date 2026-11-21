# Security

## Reporting a vulnerability

Please do not open a public issue. Report it privately through GitHub: on the repository, go to **Security → Report a vulnerability**. Only the maintainer sees the report.

Include the steps to reproduce it, and the smallest Markdown file that triggers it if there is one. You will get an answer within a week, and credit in the release notes once it is fixed, if you want it.

## What counts

Prelum converts Markdown files on your own machine, so the main concern is what a document can do while it is converted. For example:

- a Markdown file that makes prelum read or send local files it should not;
- a file that runs code outside the page that is printed;
- a published package that does not match its source (each release carries a provenance statement from the CI run that built it).

## Supported versions

Fixes go into the latest release. Update with `npx prelum@latest`.
