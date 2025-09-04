# CI-driven-burpscan

You can use this Action to integrate vulnerability scans into your CI/CD pipeline in two different ways:

CI-driven scans - You need an installation of Burp Suite Enterprise Edition for this option. You can view the results of your scans in your CI/CD platform, or in the Burp Suite Enterprise Edition dashboard. For more information, see CI-driven scans.
CI-driven scans with no dashboard - You don't need an installation of Burp Suite Enterprise Edition for this option. You can view the results of your scan in your CI/CD platform. For more information, see CI-driven scans with no dashboard.

This action enables you to integrate vulnerability scans into your CI/CD pipeline. A CI-driven scan runs Burp Scanner from a Docker container on a CI/CD platform agent node.
On completion, it generates a JUnit XML report about the vulnerabilities found. This report includes:
* The locations of the vulnerabilities
* Additional information about each vulnerability
* Links to our learning resources, with remediation advice

In order to use this action you need an installation of Burp Suite Enterprise Edition. You need to create an API user with the CI-driven scan initiator role and provide the API key to this action. To learn more, see [Creating API users](https://portswigger.net/burp/documentation/enterprise/api-documentation/create-api-user.html).

## About CI-driven scans
* Easily integrate Burp Suite Enterprise Edition with your CI/CD pipeline
* Run Burp Scanner directly from your CI/CD platform
* Supports [login details and recorded login sequences](https://portswigger.net/burp/documentation/enterprise/working-with-sites/configure-logins/)

For full documentation about CI-driven scans, please see Integrating CI-driven scans.

## Inputs
Inputs can be used to provide values to the container. If you use a configuration file, the values in that file have priority over the input values.

### `enterprise-server-url`

The URL of your Enterprise server.

### `enterprise-api-key`

The API key for your API user.

### `start-url`

The URL of the website you want Burp Scanner to scan.

**The above values must be specified either as inputs or in a configuration file.**

### `correlation-id`

**Optional** You only need to input a correlation ID if you want to view the scan results on the Burp Suite Enterprise Edition web interface. You can use a text string up to 64 
characters long. Scans with the same correlation ID will be treated as the same site in the web interface.

### `report-file-path`

**Optional** The output path for the scan report. This is relative to the working directory of the container.

**Default** `burp_junit_report.xml`

### `config-file-path`

**Optional** The path to the configuration file. This path must be an absolute path.

**Default** `burp_config.yml` in the container's working directory.

