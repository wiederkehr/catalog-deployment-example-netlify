# Publish Catalog on Github Pages

Example for creating and publishing an fresh instance of [Catalog](https://catalog.style/) using [Github Pages](https://pages.github.com/).

## 1. Install Catalog

1. Create a new Catalog following these [instructions](https://docs.catalog.style/installation/create-catalog).
2. Create a new repository on Github following these [instructions](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-new-repository).
3. Add your Catalog code to the new repository following these [instructions](https://help.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line).

For more details about how to use Catalog, check out the [documentation](https://docs.catalog.style/).

## 2. Configure Github Pages

1. Setup Github Pages on the `Settings` page of your Github repository.
2. Select the `/doc` folder of the `master` branch as the source for your Github Pages.

```image
plain: true
span: 4
src: "/github-pages-source.png"
```

## 3. Publish to Github Pages

### Option 1: Publish Catalog Manually

You can build Catalog locally and then publish a new version manually whenever you’re ready.

1. Build your Catalog locally using the script `catalog-build --public-url=/[your-repo-name]/ --out=docs`.
2. Push the code changes to your repository on Github.
3. Navigate to `https://[your-username].github.io/[your-repo-name]/` to see your new Catalog in full bloom.

### Option 2: Publish Catalog Automatically

Alternatively, you can build Catalog automatically whenever you push changes to your repository using [Github Actions](https://github.com/features/actions).

1. Setup a new workflow on the `Actions` page of your Github repository.
2. Skip the template selection and set up a fresh workflow for yourself.
3. Give your workflow a descriptive name (i.e. `build-and-deploy-catalog.yml`).
4. Copy and paste the following workflow and change the `[repository-name]` to the name of your repository.
5. Save the workflow with _Start commit_ to commit the workflow file to your repository.
6. Navigate to `Actions` page of your repository to see your new workflow listed.
7. Make and commit a code change to your Catalog to see your publication workflow in action).
8. From now on, every new code change that you push to the `master` branch will publish a new version of Catalog.

#### Workflow

```
name: Build and Deploy Catalog

on: [push]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - name: Checkout
      uses: actions/checkout@v2
    - name: Use Node.js
      uses: actions/setup-node@v1
      with:
        node-version: '12.x'
    - name: Install Catalog
      run: yarn
    - name: Build Catalog
      run: yarn catalog-build --public-url=/[repository-name]/ --out=docs
    - name: Commit Changes
      uses: elstudio/actions-js-build/commit@v3
      with:
        commitMessage: Build Catalog
```
