---
description: Example of how to obtain information about issues in a repository programmatically using the Codacy API endpoint searchRepositoryIssues.
---

# Obtaining current issues in repositories

To obtain information about the current issues in your repositories in a flexible way, use the Codacy API endpoint [searchRepositoryIssues](https://app.codacy.com/api/api-docs#searchrepositoryissues).

For example, you may want to generate a report that includes only issues that belong to specific categories (such as security issues), or that have a minimum severity level.

## Example: Obtaining security issues with level Error and Warning

This example exports the pattern ID, issue level, file path, and timestamp for all security issues that have the severity level `Warning` or `Error` in the GitHub repository `codacy/website`.

The example script:

1.  Defines the [account API token](../api-tokens.md#account-api-tokens) used to authenticate on the Codacy API.
1.  Calls the Codacy API endpoint [searchRepositoryIssues](https://app.codacy.com/api/api-docs#searchrepositoryissues) to retrieve information about the issues, filtering the results by security issues with the relevant severity levels.
1.  Uses [jq](https://github.com/stedolan/jq) to select only the necessary data fields and convert the results to the CSV format.

```bash
CODACY_API_TOKEN="<your account API token>"
GIT_PROVIDER="<your Git provider>" # gh, ghe, gl, gle, bb, or bbe
ORGANIZATION="<your organization name>"
REPOSITORY="<your repository name>"

curl -X POST "https://app.codacy.com/api/v3/analysis/organizations/$GIT_PROVIDER/$ORGANIZATION/repositories/$REPOSITORY/issues/search" \
     -H "api-token: $CODACY_API_TOKEN" \
     -H "Content-Type: application/json" \
     -d '{ "levels": ["Error", "Warning"], "categories": ["Security"] }' \
| jq -r ".data[] | [.patternInfo.id, .patternInfo.level, .filePath, .commitInfo.timestamp] | @csv"
```

Example output:

```text
"BundlerAudit_Insecure Dependency","Error","Gemfile.lock","2021-06-16T11:46:24Z"
"Custom_Scala_PredictableRandom","Warning","src/test/database/SpecsHelper.scala","2021-05-21T16:20:15Z"
"Custom_Scala_PlayUntrustedHttpRequestParameter","Warning","app/RedirectController.scala","2021-04-26T15:06:33Z"
[...]
```

{% include-markdown "../../assets/includes/api-example-pagination-important.md" %}

## See also

-   [Which metrics does Codacy calculate?](../../faq/code-analysis/which-metrics-does-codacy-calculate.md)
-   [Issues page](../../repositories/issues.md)
