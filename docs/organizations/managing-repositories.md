# Managing repositories

To see a list of the repositories that Codacy is monitoring, open the page **Repositories** under your organization.

![Repositories list](images/repositories.png)

This page lists the repositories that already belong to your organization on Codacy sorted by [last updated date](organization-overview.md#last-updated-repositories), and allows you to compare the repositories in the list according to the following metrics:

-   [Grade](../faq/code-analysis/which-metrics-does-codacy-calculate.md#grade)
-   [Issues](../faq/code-analysis/which-metrics-does-codacy-calculate.md#issues)
-   [Complexity](../faq/code-analysis/which-metrics-does-codacy-calculate.md#complexity)
-   [Duplication](../faq/code-analysis/which-metrics-does-codacy-calculate.md#duplication)
-   [Coverage](../faq/code-analysis/which-metrics-does-codacy-calculate.md#code-coverage)

The list also displays error and warning messages for repositories that have issues, such as when there are no committers added to the organization or when Codacy stopped having access to the repository. Hover the mouse cursor over the warning icons or open the repository to see more details.

If you have many repositories, you can use the search field above the list to <span class="skip-vale">quickly</span> find a specific repository.

## Adding a repository

{%
    include-markdown "../assets/includes/paid.md"
    start="<!--paid-private-repositories-start-->"
    end="<!--paid-private-repositories-end-->"
%}

To add a new repository to Codacy, click the button **Add repository** at the top right-hand corner of the page. This opens a window listing the repositories in your Git provider organization that don't belong to your organization on Codacy yet.

![Adding a repository](images/repositories-add.png)

!!! important
    To see your repositories in this list, make sure that you have admin permissions over the repositories on the Git provider and that [Codacy has permissions to access the repositories](../faq/troubleshooting/why-cant-i-see-or-add-my-organizations-repositories.md).

Add one or multiple repositories to your organization by clicking **Add** next to the repositories. If you have many repositories, you can use the search field above the list to <span class="skip-vale">quickly</span> find a specific repository.

After adding repositories, close the window to return to the list of repositories in your organization. Although Codacy will immediately start analyzing the new repositories, they will display empty metrics until the first analysis returns results.

![Waiting for first analysis results](images/repositories-analyzing.png)

## See also

-   [Which metrics does Codacy calculate?](../faq/code-analysis/which-metrics-does-codacy-calculate.md)
