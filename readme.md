# Github Actions for dotnet projects

## Table of contents
- [Github Actions for dotnet projects](#github-actions-for-dotnet-projects)
  - [Table of contents](#table-of-contents)
  - [Github Action for dotnet-format](#github-action-for-dotnet-format)
    - [Usage](#usage)
    - [Parameters](#parameters)
      - [Inputs](#inputs)
      - [Outputs](#outputs)
  - [License](#license)


## Github Action for dotnet-format
Run [dotnet-format](https://github.com/dotnet/format) as part of your workflow to auto fix violations as part of your pull request workflow.

### Usage
Running on `pull_request`
```yaml
name: "[CI]Build, Test and Lint"

on: pull_request
jobs:
  dotnet-format:
    uses: tegrasystems/actions/.github/workflows/dotnet-format.yml@master
    with:
        project: PROJECT_PATH
        project-name: PROJECT_NAME
```

### Parameters
#### Inputs

| Name | Description | Type |
| --- | ----------- | ----- |
| project | Path to `.csproj` or `.sln` file | string |
| project-name | Name of the project, will be displayed as name of job  | string |

#### Outputs
| Name | Description | Type |
| --- | ----------- | ----- |
| has-changes | `true` if any files were found to have fixes applied. Will be a string of `true` or `false` | string |
| changes | (optional) if `has-changes` is `true`, every change made by [dotnet-format](https://github.com/dotnet/format) will be returned as [git-diff](https://git-scm.com/docs/git-diff) | string |

## License
The scripts and documentation in this project are released under the [MIT License](https://github.com/xt0rted/dotnet-format/blob/main/LICENSE)
