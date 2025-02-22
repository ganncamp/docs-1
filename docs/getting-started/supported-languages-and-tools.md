---
description: List of tools that Codacy uses to analyze over 40 supported languages and frameworks. Codacy provides static analysis for all programming languages and cloud infrastructure-as-code frameworks as well as code duplication, code complexity, and code coverage metrics for most programming languages.
---

# Supported languages and tools

Codacy uses industry-leading tools to perform automatic static code analysis over 40 supported languages and frameworks:

-   **For programming languages** Codacy provides static analysis as well as code duplication, code complexity, and code coverage metrics for key languages.

-   **For cloud infrastructure-as-code frameworks** Codacy provides static analysis to enforce security and compliance best practices.

The table below lists all languages and frameworks that Codacy supports and the corresponding tools that Codacy uses to analyze your source code. Besides this, Codacy uses [cloc](https://github.com/kentcdodds/cloc) to calculate the source lines of code for all supported languages and supports multiple [code coverage report formats](../coverage-reporter/index.md#generating-coverage).

<!--NOTE
    When adding a new supported tool, make sure that you update the following pages:

    docs/getting-started/supported-languages-and-tools.md
    docs/related-tools/codacy-plugin-tools.md
    docs/related-tools/local-analysis/client-side-tools.md (if the tool runs client-side)
    docs/repositories/security-monitor.md (if the tool reports security issues)
    docs/repositories-configure/configuring-code-patterns.md (supported configuration files table, or list of tools that don't support configuration files)
    docs/repositories-configure/codacy-configuration-file.md (list of tool short names to use on the Codacy configuration file)
-->

<table>
  <colgroup>
    <col width="20%"/>
    <col width="25%"/>
    <col width="15%"/>
    <col width="20%"/>
    <col width="20%"/>
  </colgroup>
  <thead>
    <tr>
      <th>Language or framework</th>
      <th><a style="color: white;" href="../../faq/code-analysis/which-metrics-does-codacy-calculate/#issues">Static analysis</a></th>
      <th><a style="color: white;" href="#suggest-fixes">Suggested fixes</a></th>
      <th><a style="color: white;" href="../../faq/code-analysis/which-metrics-does-codacy-calculate/#duplication">Duplication</a></th>
      <th><a style="color: white;" href="../../faq/code-analysis/which-metrics-does-codacy-calculate/#complexity">Complexity</a></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Apex</td>
      <td><a href="https://pmd.github.io/">PMD</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>AsyncAPI</td>
      <td><a href="https://stoplight.io/open-source/spectral/">Spectral</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>AWS CloudFormation</td>
      <td><a href="https://github.com/bridgecrewio/checkov/">Checkov</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Azure Resource Manager Templates</td>
      <td><a href="https://github.com/bridgecrewio/checkov/">Checkov</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>C</td>
      <td><a href="https://clang.llvm.org/extra/clang-tidy/">Clang-Tidy</a><a href="#client-side"><sup>1</sup></a>,
          <a href="http://cppcheck.sourceforge.net/">Cppcheck</a>,
          <a href="https://dwheeler.com/flawfinder/">Flawfinder</a></td>
      <td></td>
      <td><a href="https://pmd.github.io/pmd/pmd_userdocs_cpd.html">PMD CPD</a></td>
      <td>-</td>
    </tr>
    <tr>
      <td>C++</td>
      <td><a href="https://clang.llvm.org/extra/clang-tidy/">Clang-Tidy</a><a href="#client-side"><sup>1</sup></a>,
          <a href="http://cppcheck.sourceforge.net/">Cppcheck</a><a href="#cppcheck-misra"><sup>2</sup></a>,
          <a href="https://dwheeler.com/flawfinder/">Flawfinder</a></td>
      <td></td>
      <td><a href="https://pmd.github.io/pmd/pmd_userdocs_cpd.html">PMD CPD</a></td>
      <td>-</td>
    </tr>
    <tr>
      <td>C#</td>
      <td><a href="https://github.com/SonarSource/sonar-dotnet">Sonar C#</a></td>
      <td></td>
      <td><a href="https://pmd.github.io/pmd/pmd_userdocs_cpd.html">PMD CPD</a></td>
      <td><a href="https://github.com/SonarSource/sonar-dotnet">SonarC#</a></td>
    </tr>
    <tr>
      <td>CoffeeScript</td>
      <td><a href="http://www.coffeelint.org/">CoffeeLint</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Crystal</td>
      <td><a href="https://github.com/crystal-ameba/ameba">Ameba</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>CSS</td>
      <td><a href="http://csslint.net/">CSSLint</a>,
          <a href="https://stylelint.io/">Stylelint</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Dart</td>
      <td><a href="https://github.com/dart-lang/sdk/tree/main/pkg/analyzer_cli">dartanalyzer</a><a href="#dart-limitations"><sup>3</sup></a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Dockerfile</td>
      <td><a href="https://github.com/hadolint/hadolint">Hadolint</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Elixir</td>
      <td><a href="https://github.com/rrrene/credo">Credo</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Go</td>
      <td><a href="https://gitlab.com/opennota/check">aligncheck</a><a href="#client-side"><sup>1</sup></a>,
          <a href="https://github.com/tsenart/deadcode">deadcode</a><a href="#client-side"><sup>1</sup></a>,
          <a href="https://github.com/securego/gosec">Gosec</a><a href="#client-side"><sup>1</sup></a>,
          <a href="https://github.com/mgechev/revive">Revive</a>,
          <a href="https://staticcheck.io/">Staticcheck</a><a href="#client-side"><sup>1</sup></a></td>
      <td></td>
      <td><a href="https://pmd.github.io/pmd/pmd_userdocs_cpd.html">PMD CPD</a></td>
      <td><a href="https://github.com/fzipp/gocyclo">Gocyclo</a></td>
    </tr>
    <tr>
      <td>Groovy</td>
      <td><a href="https://codenarc.github.io/CodeNarc/">CodeNarc</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Java</td>
      <td><a href="https://checkstyle.sourceforge.io/">Checkstyle</a>,
          <a href="https://pmd.github.io/">PMD</a>,
          <a href="https://spotbugs.github.io/">SpotBugs</a><a href="#client-side"><sup>1</sup></a></td>
      <td></td>
      <td><a href="https://pmd.github.io/pmd/pmd_userdocs_cpd.html">PMD CPD</a></td>
      <td><a href="https://pmd.github.io/">PMD</a></td>
    </tr>
    <tr>
      <td>JavaScript</td>
      <td><a href="https://eslint.org/">ESLint</a>,
          <a href="https://jshint.com/">JSHint</a>,
          <a href="https://pmd.github.io/">PMD</a></td>
      <td><a href="https://eslint.org/docs/rules/">ESLint</a> <a href="#suggest-fixes">🔧</a></td>
      <td><a href="https://pmd.github.io/pmd/pmd_userdocs_cpd.html">PMD CPD</a></td>
      <td><a href="https://eslint.org/">ESLint</a></td>
    </tr>
    <tr>
      <td>JSON</td>
      <td><a href="https://github.com/codacy/codacy-jackson-linter">Jackson Linter</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>JSP</td>
      <td><a href="https://pmd.github.io/">PMD</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Kotlin</td>
      <td><a href="https://github.com/detekt/detekt">detekt</a></td>
      <td></td>
      <td><a href="https://github.com/kucherenko/jscpd">jscpd</a></td>
      <td><a href="https://github.com/detekt/detekt">detekt</a></td>
    </tr>
    <tr>
      <td>Kubernetes</td>
      <td><a href="https://github.com/bridgecrewio/checkov/">Checkov</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Less</td>
      <td><a href="https://stylelint.io/">Stylelint</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Markdown</td>
      <td><a href="https://github.com/remarkjs/remark-lint">remark-lint</a>, <a href="https://github.com/DavidAnson/markdownlint">markdownlint</a></td>
      <td><a href="https://github.com/DavidAnson/markdownlint">markdownlint</a> <a href="#suggest-fixes">🔧</a></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Objective-C</td>
      <td><a href="https://clang.llvm.org/extra/clang-tidy/">Clang-Tidy</a><a href="#client-side"><sup>1</sup></a>, <a href="http://fauxpasapp.com/">Faux Pas</a><a href="#client-side"><sup>1</sup></a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>OpenAPI</td>
      <td><a href="https://stoplight.io/open-source/spectral/">Spectral</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>PHP</td>
      <td><a href="https://github.com/squizlabs/PHP_CodeSniffer">PHP_CodeSniffer</a>,
          <a href="https://phpmd.org/">PHP Mess Detector</a></td>
      <td></td>
      <td><a href="https://github.com/sebastianbergmann/phpcpd">PHPCPD</a></td>
      <td><a href="https://github.com/pdepend/pdepend">PHP Depend</a></td>
    </tr>
    <tr>
      <td>PL/SQL</td>
      <td><a href="https://pmd.github.io/">PMD</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>PostgreSQL</td>
      <td><a href="https://github.com/purcell/sqlint">SQLint</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>PowerShell</td>
      <td><a href="https://github.com/PowerShell/PSScriptAnalyzer">PSScriptAnalyser</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Python
      </td>
      <td><a href="https://github.com/PyCQA/bandit">Bandit</a>,
          <a href="https://github.com/PyCQA/prospector">Prospector</a>,
          <a href="https://pylint.pycqa.org/">Pylint</a></td>
      <td></td>
      <td><a href="https://pmd.github.io/pmd/pmd_userdocs_cpd.html">PMD CPD</a></td>
      <td><a href="https://github.com/rubik/radon">Radon</a></td>
    </tr>
    <tr>
      <td>Ruby<a href="#ruby-31"><sup>4</sup></a>
      </td>
      <td><a href="https://brakemanscanner.org/">Brakeman</a>,
          <a href="https://github.com/rubysec/bundler-audit">bundler-audit</a>,
          <a href="https://github.com/rubocop/rubocop">RuboCop</a></td>
      <td></td>
      <td><a href="https://github.com/seattlerb/flay">Flay</a></td>
      <td><a href="https://github.com/rubocop/rubocop">RuboCop</a></td>
    </tr>
    <tr>
      <td>Sass</td>
      <td><a href="https://stylelint.io/">Stylelint</a>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Scala
      </td>
      <td><a href="https://github.com/codacy/codacy-scalameta">Codacy Scalameta Pro</a>,
          <a href="http://www.scalastyle.org/">Scalastyle</a>,
          <a href="https://spotbugs.github.io/">SpotBugs</a><a href="#client-side"><sup>1</sup></a></td>
      <td></td>
      <td><a href="https://pmd.github.io/pmd/pmd_userdocs_cpd.html">PMD CPD</a></td>
      <td><a href="http://www.scalastyle.org/">Scalastyle</a>,
          <a href="https://github.com/scala/scala">Scala 2 compiler and standard library</a></td>
    </tr>
    <tr>
      <td>Serverless Framework</td>
      <td><a href="https://github.com/bridgecrewio/checkov/">Checkov</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Shell</td>
      <td><a href="https://www.shellcheck.net/">ShellCheck</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Swift </td>
      <td><a href="https://github.com/realm/SwiftLint">SwiftLint</a>,
          <a href="https://github.com/sleekbyte/tailor">Tailor</a></td>
      <td></td>
      <td><a href="https://pmd.github.io/pmd/pmd_userdocs_cpd.html">PMD CPD</a></td>
      <td><a href="https://github.com/realm/SwiftLint">SwiftLint</a><a href="#swiftlint-complexity"><sup>5</sup></a></td>
    </tr>
    <tr>
      <td>Terraform</td>
      <td><a href="https://github.com/bridgecrewio/checkov/">Checkov</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Transact-SQL</td>
      <td><a href="https://github.com/tsqllint/tsqllint/">TSQLLint</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>TypeScript</td>
      <td><a href="https://eslint.org/">ESLint</a>,
          <a href="https://palantir.github.io/tslint/">TSLint</a></td>
      <td><a href="https://eslint.org/docs/rules/">ESLint</a> <a href="#suggest-fixes">🔧</a></td>
      <td><a href="https://github.com/kucherenko/jscpd">jscpd</a></td>
      <td><a href="https://eslint.org/">ESLint</a></td>
    </tr>
    <tr>
      <td>Unity</td>
      <td><a href="https://github.com/microsoft/Microsoft.Unity.Analyzers">Unity Roslyn Analyzers</a><a href="#client-side"><sup>1</sup></a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Velocity</td>
      <td><a href="https://pmd.github.io/">PMD</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Visual Basic</td>
      <td><a href="https://github.com/SonarSource/sonar-dotnet">SonarVB</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>Visualforce</td>
      <td><a href="https://pmd.github.io/">PMD</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>XML</td>
      <td><a href="https://pmd.github.io/">PMD</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <td>XSL</td>
      <td><a href="https://pmd.github.io/">PMD</a></td>
      <td></td>
      <td>-</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

<sup><span id="client-side">1</span></sup>: Supported as a [client-side tool](../related-tools/local-analysis/client-side-tools.md).  
<sup><span id="cppcheck-misra">2</span></sup>: Currently, Cppcheck only supports [checking the MISRA guidelines for C](https://cppcheck.sourceforge.io/misra.php).  
<sup><span id="dart-limitations">3</span></sup>: Currently, Codacy only supports including the packages [lints](https://pub.dev/packages/lints) and [flutter_lints](https://pub.dev/packages/flutter_lints) on dartanalyzer configuration files.  
<sup><span id="ruby-31">4</span></sup>: Currently, Codacy doesn't support any static code analysis tool for [Ruby 3.1](https://www.ruby-lang.org/en/news/2021/12/25/ruby-3-1-0-released/).  
<sup><span id="swiftlint-complexity">5</span></sup>: Supports [reporting warnings or errors](https://realm.github.io/SwiftLint/cyclomatic_complexity.html) on functions above specific complexity thresholds. Enable the rule **Cyclomatic Complexity** on the [Code patterns page](../repositories-configure/configuring-code-patterns.md), or use a [configuration file](https://realm.github.io/SwiftLint/index.html#configuration) to customize the thresholds.  
<sup><span id="suggest-fixes">🔧</span></sup>: Supports [suggesting fixes](../repositories-configure/integrations/github-integration.md#suggest-fixes) for identified issues.

## See also

-   [Codacy quickstart (5 min)](codacy-quickstart.md)
-   [Client-side tools](../related-tools/local-analysis/client-side-tools.md)
-   [Codacy plugin tools](../related-tools/codacy-plugin-tools.md)
-   [Which metrics does Codacy calculate?](../faq/code-analysis/which-metrics-does-codacy-calculate.md)
