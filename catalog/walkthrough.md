# Publish Catalog on Netlify

Example for creating and publishing an instance of [Catalog](https://catalog.style/) using [Netlify](https://www.netlify.com/).

## 1. Install Catalog

1. Create a new Catalog following these [instructions](https://docs.catalog.style/installation/create-catalog).
2. Create a new repository on Github following these [instructions](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-new-repository).
3. Add your Catalog code to the new repository following these [instructions](https://help.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line).

For more details about how to use Catalog, check out the [documentation](https://docs.catalog.style/).

## 2. Configure Netlify

1. Create a new site on Netlify following these [three easy steps](https://app.netlify.com/start).
2. Add the script `yarn catalog-build` as the build command and `catalog/build` as the publish directory.

```image
plain: true
span: 4
src: "/netlify-build-settings.png"
```

## 3. Publish to Netlify

- Everytime you push new code to the `master` branch, your Catalog will be deployed automatically.
- You can set up a custom domain for your site and secure it with HTTPS on Netlify.
