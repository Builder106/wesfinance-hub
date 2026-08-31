# Branching and deployment

WesFinance Hub is a separate monorepo for related economics and finance
projects. It should keep repository-wide integration separate from any future
project-specific release lines.

## Current branch model

The repository uses this initial flow:

```text
feature/<short-name> -> staging -> main
```

- `feature/*` branches contain short-lived changes.
- `staging` is the persistent shared preview and acceptance environment.
- `main` is the production branch for the unified WesFinance Hub portal.

The repository currently enables automatic Vercel deployments only for
`main` and `staging`. Feature branches still receive CI checks; they do not
automatically create Vercel deployments unless the deployment policy changes.

## When to add a project branch

Do not create a branch for every economics project merely because it has its
own directory. Add a persistent project branch only when that project has:

- its own Vercel project and root directory;
- a release schedule that differs from the unified portal;
- a need for independent production promotion or rollback; and
- an owner responsible for keeping the branch current.

If those conditions become true, use a matching production branch such as
`business-review` or `consulting-pathways`, configure that branch as the
matching Vercel Production Branch, and keep `staging` as the shared pre-release
environment. Record the decision in `JOURNAL.md` before changing the branch
policy.

## Vercel environments

The Vercel project for the unified portal should use:

| Branch | Environment | Role |
| --- | --- | --- |
| `staging` | Preview or Custom Environment | Shared QA and acceptance |
| `main` | Production | Live WesFinance Hub portal |

Keep the staging domain, database, session settings, and third-party
credentials separate from production. Do not use production financial data or
credentials for staging tests.

The committed [`vercel.json`](../vercel.json) limits automatic Git-triggered
deployments to `main` and `staging`. Vercel project settings still control the
Production Branch, domains, environment variables, and project root directory.
Those settings must be verified in the Vercel dashboard when the project is
created or changed.

## Promotion flow

1. Open a pull request from a feature branch into `staging`.
2. Let CI complete and test the staging deployment.
3. Confirm the deployed commit, migrations, authentication, and integrations.
4. Open a pull request from `staging` into `main`.
5. Merge after review; Vercel deploys the resulting `main` commit to
   production.

If the portal later splits into independently deployed applications, promote
the tested changes from `staging` into the relevant project production branch
instead of changing `main` into a collection of project release lines.

## Related guidance

The reusable pattern is documented at
`CS/projects/personal/monorepo-playbook.md`. That guide is outside this
repository, so this document records only the decisions that apply to
WesFinance Hub.
