# Contributing

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-refresh-toc -->
**Table of Contents**

- [Introduce](#introduce)
    - [Code of Conduct](#code-of-conduct)
    - [We Develop with Github](#we-develop-with-github)
    - [Environment](#environment)
    - [Your First Contribution](#your-first-contribution)
    - [Contribution Targets](#contribution-targets)
- [Rules](#rules)
    - [Issue](#issue)
    - [Coding style](#coding-style)
    - [Commit](#commit)
    - [Commit Message](#commit-message)
    - [Pull request](#pull-request)
    - [License](#license)
- [References](#references)

<!-- markdown-toc end -->

## Introduce

I'm really glad you're reading this, because we need volunteer developers to help this project come to fruition.

Please note we have a code of conduct, please follow it in all your interactions with the project.

### Code of Conduct

Refer to [CODE\_OF\_CONDUCT.md](https://github.com/black7375/Fluid-Size/blob/master/CODE_OF_CONDUCT.md).

### We Develop with Github

We use [github](https://github.com/black7375/Fluid-Size) to host code, to track [issues](https://github.com/black7375/Fluid-Size/issues) and feature requests, as well as accept [pull requests](https://github.com/black7375/Fluid-Size/pulls).

After feedback has been given we expect responses within two weeks. After two weeks we may close the issue and pull request if it isn't showing any activity.

### Environment

You can configure it as follows:
```shell
## clone repository
git clone https://github.com/black7375/Fluid-Size.git
cd ./fluid-size

## install dependencies
npm install
```

### Your First Contribution

**Working on your first Pull Request?** You can learn how from this *free* series [How to Contribute to an Open Source Project on GitHub](https://egghead.io/series/how-to-contribute-to-an-open-source-project-on-github)

The following documents may be helpful:
- [README](https://github.com/black7375/Fluid-Size/blob/master/README.md)
- [Wiki:API](https://github.com/black7375/fluid-size/wiki/API)
- [Wiki:Comparison](https://github.com/black7375/Fluid-Size/wiki/Comparison)
- [Wiki:The theory of font size and readability](https://github.com/black7375/Fluid-Size/wiki/The-theory-of-font-size-and-readability)


### Contribution Targets

We love your input! We want to make contributing to this project as easy and transparent as possible, whether it's:

**Docs**
- Fix typos, alignments.
- Correct awkward sentences.
- Improve document readability.

**Issues**
- Found an error in the [Wiki:The theory of font size and readability](https://github.com/black7375/fluid-size/wiki/The-theory-of-font-size-and-readability).
- Report a bug.
- Discussing the current state of the code.
- Good theory or algorithm suggestion.
- Tell us about related or relevant projects and documents.
- Proposing others..

**Codes**
- [API](https://github.com/black7375/fluid-size/wiki/API) or feature extension.
- Bug fixes.
- Correct wrong implementation from theory.
- Improved compatibility or accessibility.
- Refactoring.

## Rules

### Issue

- **Versions:**
  - Make sure you’re on the latest version.
  - Try older versions.
  - Try switching up dependency versions.
- **Search:** Search the project’s [issues](https://github.com/black7375/Fluid-Size/issues) to make sure it's not a known issue.

### Coding style

- **Indent:** 2 spaces for indentation rather than tabs.
- **Columns:** Fit `80`~`100` columns as much as possible.

### Commit

- **Meaningfully:**: It doesn't make meaningless commits.
- **One per task:** It's difficult to distinguish when various tasks are mixed.
- **Often:** Codes may corrupt during large changes.
- **Build Check:** Check if SCSS can be compiled with the `npm run build` command.

### Commit Message

For intuitive recognition, I [put a **prefix**](https://github.com/black7375/Fluid-Size/commits/master).
- `Add:` Add feature or enhanced.
- `Fix:` Bug fix or change default values.
- `Clean:` Refactoring.
- `Doc:` Update docs.
- `Feature:` Milestone, The versioning scheme we use is [SemVer](https://semver.org/). (Maintainer decides, do not pull request.)

### Pull request

- **Doc:** Update the [README.md](https://github.com/black7375/Fluid-Size/blob/master/README.md) and [Wiki:API](https://github.com/black7375/fluid-size/wiki/API) with details of changes to the interface, this includes new environment variables, exposed ports, useful file locations and container parameters.
- **Issue:** We recommend that you open the issue first to discuss the changes with the owner of this repository.

### License

**Any contributions you make will be under the MIT Software License**

In short, when you submit code changes, your submissions are understood to be under the same [MIT License](https://choosealicense.com/licenses/mit/) that covers the project.
Feel free to contact the maintainers if that's a concern.

**Reference specification**

Even if you copy the code snippet, it is recommended that you leave a link.

## References

- [Good-CONTRIBUTING.md-template](https://gist.github.com/PurpleBooth/b24679402957c63ec426)
- [Contributing to Transcriptase](https://gist.github.com/briandk/3d2e8b3ec8daf5a27a62)
- [contributing-template](https://github.com/nayafia/contributing-template/blob/master/CONTRIBUTING-template.md)
- [Contributing to Open Source Projects](https://www.contribution-guide.org/)
