# How to Create a Self-documenting Makefile

> Accelerate your workflow and DevOps with command-line aliases you can check in

**Source**: [Link](https://victoria.dev/blog/how-to-create-a-self-documenting-makefile/)

<br/>

GNU `make` can be used to perform common development activities eg.:

- updating programs
- installing dependencies
- and testing

To do all the aforementioned with a Makefile (GNU `make`), we use **Makefile rules** and **recipes**.

Similar parallels exist for POSIX flavor `make`, like **Target Rules**; however they are outside the scope of this article.

<br/>

Example:

```Makefile
update: ## Do apt upgrade and autoremove
    sudo apt update && sudo apt upgrade -y
    sudo apt autoremove -y

env:
    pip3 install pipenv
    pipenv shell --python 3.8

install: ## Install or update dependencies
    pipenv install --dev
    npm install
    pre-commit install --install-hooks

serve: ## Run the local development server
    hugo serve --enableGitInfo --disableFastRender --environment development

initial: update env install serve ## Install tools and start development server
```

<br/>

## A Self-documenting Makefile

Here is an example of a `help` command:

```Makefile
.PHONY: help
help: ## Show this help
    @egrep -h '\s##\s' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-20s\033[0m %s\n", $$1, $$2}'
```

Using `egrep` and `awk`, this command takes the output of `MAKEFILE_LIST` and prints a formatted version of the strings that follow the `##` (comment) pattern.

If we put it at the top of the file (so that it is the default target), we can see all our shortcuts and what they do, we just run `make`, or `make help`:

```text
help                 Show this help
initial              Install tools and start development server
install              Install or update dependencies
serve                Run the local development server
update               Do apt upgrade and autoremove
```

Now we have our very own personalized and project-specific CLI tool!
