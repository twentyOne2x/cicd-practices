# Railway

Sources read: 2026-10-10. Platform documentation is undated; engineering accounts retain their publication dates.

Railway's engineering account from 2023-01-31 describes tests and builds on every commit, API checks on PRs, and automated migrations and monitoring. Its Railway Station account from 2024-05-01 describes preview testing, merge, preview removal and production redeployment. Those are historical accounts with defined scope. [Ship on Friday](https://blog.railway.com/p/ship-on-friday), [Building Railway on Railway](https://blog.railway.com/p/building-railway-on-railway).

Railway says PR environments let teams "preview code changes in isolated, temporary environments". They are created and removed automatically when enabled. The default base includes production configuration and variables, and bot PRs need enabling. [Preview deployments with PR environments](https://docs.railway.com/guides/preview-deployments-with-pr-environments).

Connected-branch pushes can trigger deployment. The optional Wait for CI feature follows GitHub Actions workflows and has documented exceptions for skipped, neutral and some cancelled results. It is narrower than every required repository check passing. [GitHub autodeploys](https://docs.railway.com/guides/github-autodeploys).

Configured health checks gate traffic activation and stop checking afterward. Rollback restores a prior deployment's image and custom variables; the documentation does not establish reversal of database changes. [Health checks](https://docs.railway.com/deployments/healthchecks), [Deployment actions](https://docs.railway.com/deployments/deployment-actions).

The feature-flags announcement, dated 2026-07-17, describes controlling exposure separately from deployment and disabling a feature without redeploying. It is a product capability. [Feature flags](https://blog.railway.com/p/feature-flags).
