# Running local analysis

## Set up the Codacy Analysis CLI

Follow the [installation guide](https://github.com/codacy/codacy-analysis-cli#install) to get the `codacy-analysis-cli` executable running on your build server.

## Running an analysis with the CLI

At the moment, the CLI still requires to retrieve the configuration from Codacy to perform an analysis. To access the repository, you will have to obtain a *Project Token* as explained in the [CLI documentation](https://github.com/codacy/codacy-analysis-cli#project-token). Then, you can invoke the CLI to get a report with all the issues:

!!! important
    **If you're using Codacy Self-hosted** you must also specify the endpoint where the Codacy instance is running either by using the flag `--codacy-api-base-url` or the environment variable `CODACY_API_BASE_URL`.

```bash
codacy-analysis-cli analyze --directory <SOURCE-CODE-PATH> \
                            --project-token <PROJECT-TOKEN> \
                            --allow-network \
                            --verbose \
                            --upload
```

If you don't specify the tool, the analysis will run as Codacy does in the backend. To obtain results for [a particular tool](../../repositories-configure/codacy-configuration-file.md#which-tools-can-be-configured-and-which-name-should-i-use), specify the tool with `--tool`.

### Advanced configuration

For advanced configuration details, check all the CLI flags in the [CLI documentation](https://github.com/codacy/codacy-analysis-cli#commands-and-configuration).

Some flags you might be interested in:

-   `--allow-network` - to run the tools that require compilation like SpotBugs, FindBugs, FindSecBugs
-   `--max-allowed-issues` - returns a non-zero exit code when a certain number of issues is exceeded
-   `--fail-if-incomplete` - to return a non-zero exit code when any tool fails to run successfully

## Notes on ignored issues

If you have ignored issues on Codacy be aware that the CLI won't respect those ignored issues when printing the results locally.

However, if you upload the results, the ignored issues will be reflected on the Codacy UI after the analysis is complete.
