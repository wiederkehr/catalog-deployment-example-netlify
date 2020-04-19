# Catalog on Netlify

Example for creating and publishing an instance of [Catalog](https://catalog.style/) using [Netlify](https://www.netlify.com/).

## 1. Install Catalog

1. Create a new Catalog following these [instructions](https://docs.catalog.style/installation/create-catalog).
2. Create a new repository on Github following these [instructions](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-new-repository).
3. Add your Catalog code to the new repository following these [instructions](https://help.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line).

For more details about how to use Catalog, check out the [documentation](https://docs.catalog.style/).

## 2. Configure Netlify

1. Create a new site on Netlify following these [three easy steps](https://app.netlify.com/start).

## FIXME: everything below this line has to be rewritten

1. Setup Netlify deployment with Git on the `Settings` page of your Github repository.
2. Select the `/doc` folder of the `master` branch as the source for your Github Pages.

![Github Pages section on the Settings page](https://github.com/wiederkehr/catalog-githubpages-example/raw/master/catalog/static/github-pages-source.png "Github Pages section on the Settings page")

## 3. Publish to Netlify

You can build Catalog locally and then publish a new version manually whenever you’re ready.

1. Build your Catalog locally using the script `catalog-build --public-url=/[your-repo-name]/ --out=docs`.
2. Push the code changes to your repository on Github.
3. Navigate to `https://[your-username].github.io/[your-repo-name]/` to see your new Catalog in full bloom.
