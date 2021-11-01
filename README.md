# Template App Migration Dojo Cookbook Site

This is a [Hugo](https://github.com/gohugoio/hugo) site. It is driven by markdown files that can be generated using the commands provided in this document.

# What makes a good recipe cookbook
1. Prefer `markdown` over `asciidoc`. Definitely don't write recipes in doc or docx.
2. Use TOML instead of `JSON` or `YAML` in the frontmatter.
3. Categorize your recipe from one of the following by adding one of the categories in the taxonomy below this in the front-matter markup like `taxonomy = ["API-FIRST"]`
4. Put all markdown files in the `content/recipes` and `content/documents`
5. Put good camel case title in `title=xxx` front matter to be automatically picked up by landing pages
6. Add `taxonomy=["CLIENT"]` to exclude the rendering of the recipe/doc or add `review_status = ["DONE"]` to get it published externally.
7. If in doubt look at the recipes in this template repo.

## Taxonomy
1. **REPLATFORMING**  fa-cloud-upload "Best practices and tips for replatforming applications"
2  **MODERNIZATION** "Tips and tricks to move your application the cloud nativity scale. Recipes on DDD and Event Storming."
2. **CODE-ORGANIZATION** "One codebase tracked in revision control, many deploys. Explicitly declare and isolate dependencies. Best practices around code hygiene and general Java development idioms."
3. **DESIGN-BUILD-RELEASE-RUN** "Strictly separate build and run stages. Continous Integration, Pipeline and release management best practices."
4. **CONFIG-CREDENTIALS-CODE**  "Store Configuration and Credentials in the environment. Injection of credentials and configuration into the application environment."
5. **LOGS** "Treat logs as event streams"
6. **AUTHn-AUTHz**  "Security related topics."
7. **TROUBLESHOOTING** "Debugging and Troubleshooting of apps and modules during staging and running of apps"
8. **DAY2-OPS** "Operating an app in production."
9. **TAS** "Recipes to do with TAS/PCF".
10. **TKGI** "Recipes to do with PKS, Lift & Shift and AppTx".
11. **GENERAL** "General uncategorized recipes"


## Getting Started

### Initial Setup

- Install `hugo`
  - With homebrew (Mac): `brew update && brew install hugo`
  - Manual download and install: https://github.com/gohugoio/hugo/releases


### Run locally (default: `localhost:1313`)
```
./localserver
```

### Publish Instructions
```
./publish
cf push
```

### Add New Recipe
```
hugo new recipes/(title).md
```

## Updating the theme

This site uses the `hugo-theme-docdock` theme, which is stored as a git submodule
under the `themes` directory.

To pull the latest version of the theme, update your submodules: `git submodule update --remote` and commit the change to customer cookbook repo.

## Disable Home Page Icon
To disable the homepage and remove icon from sidebar, set the `noHomeIcon` param in `/config.toml`:

``` toml
[params]
noHomeIcon = false
```

## Redirect to Different URL
To redirect to the `/recipes` route by default, uncomment the following in `/layouts/partials/index.html`:
``` html
<meta http-equiv="refresh" content="0; url=/recipes" />
```
