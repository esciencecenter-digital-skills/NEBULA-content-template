# NEBULA-content-template
This template repository can be used to create an easily maintainable, version-controllable, web-based lesson collection to be deployed with the [NEBULA framework](https://github.com/esciencecenter-digital-skills/NEBULA).

For elaborate setup instructions and other documentation, see the [NEBULA documentation](https://github.com/esciencecenter-digital-skills/NEBULA-docs)

## Repo instantiation
To create a custom-made lesson repository, click the `Use this template` button located at the top right of this page.

## Configure GitHub Pages
After instantiation, you need to set up your repo's GitHub Pages. Follow these steps:
- Go to `Settings` (located on the top toolbar), and then click on `Pages`.
- Under the `Branch` option, select the `gh-pages` branch and then click `Save`. Use the `/root` folder as the default.
- Return to your main repository page.
- In the `About` section of your repository details, find the `Website` field and select `Use your GitHub Pages website`.

## Add the title of your lesson and additional sections
This can be configured through the `config.json` file. Below is an example of its contents:
```
{
  "publicProps": {
    "title": "Add a title for your lesson/project",
    "baseURL": "NEBULA-content-template",
    "repoName": "NEBULA-content-template",
    "repoOwner": "esciencecenter-digital-skills",
    "organization": "Netherlands eScience Center",
    "categoryOrder": ["Category1", "Category2"]
  }
}
```
You can modify the `"title"` field to reflect your specific topic and add new sections to your lesson under `"categoryOrder"`.

The `"repoName"` and `"baseURL"` fields are automatically updated to the name of your new repository using the [generate_config.yml](https://github.com/esciencecenter-digital-skills/NEBULA-content-template/blob/main/.github/workflows/generate_config.yml) file. The corresponding workflow is triggered only once upon repository instantiation and is subsequently disabled.


## Quick local setup

More detailed information about local setup can be found in the [NEBULA local rendering docs](https://github.com/esciencecenter-digital-skills/NEBULA-docs/blob/main/local-rendering.md)

### Content directory/repository

To use NEBULA to build the content in this repository locally, you will need to clone this repository and the NEBULA repository:

```bash
git clone git@github.com:{GITHUB_ORGANIZATION}/{GITHUB_REPOSITORY_NAME}.git
git clone git@github.com:esciencecenter-digital-skills/NEBULA.git
```

### Link to the content repository

To make sure that NEBULA knows where to find the content, we create the following environment variable:

```bash
export CONTENT_PATH="~/path/to/your/content/repository"
```

### Install dependencies

Install the dependencies using the [node package manager](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm):

```bash
# node package manager
npm install
```

### Local development build

Start the development server on `http://localhost:3000`:

```bash
# node package manager
npm run dev
```

Now you can open a browser and navigate to `http://localhost:3000/{YOUR_BASE_URL}`
