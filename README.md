# Getting Started with the UNDP Accelerator Labs Toolkit Micro-site

Welcome to the UNDP Accelerator Labs Toolkit Micro-site project! This README provides a quick guide on how to set up and customize your Toolkit site.

## Table of Contents

- [Introduction](#introduction)
- [Toolkit Webpage Sample](#toolkit-webpage-sample)
- [Folder Structure](#folder-structure)
- [Creating Pages](#creating-pages)
- [Customizing Configuration](#customizing-configuration)
- [Create New Toolkit](#create-new-toolkit)
- [Set Up the Toolkit Micro-site Locally](#set-up-the-toolkit-micro-site-locally)
- [License](#license)

## Introduction

The Toolkit micro-site is built using Jekyll, a static site generator. It allows you to create documentation websites with ease. Follow the steps below to get started.

## Toolkit webpage sample
The toolkit generated from this template will look like [this](https://undp-accelerator-labs.github.io/national_innovation_ecosystems_toolkit/). There is flexibility for minimum configuration of text, header, color, logo, background, etc.

## Folder Structure

Here's the recommended folder structure for your NIE Toolkit project:
```markdown
├── index.md # This is the home page
├── _data/
│ ├── site_info.yml # Customize site configuration here
├── _layouts/
│ ├── default.html # Default layout template
content
│ ├── getting-started/
│ ├── index.md # Getting started side menu config
│ │ ├── values.md # Example page under the Getting Started category
│ ├── Second Topic/
├── index.md # Side menu config
│ │ ├── values.md # Example page new sub topic
├── public/
│ ├── imgs/ # Image files
├── _config.yml # Jekyll configuration file
├── README.md # Instructions for users (you're reading this)

``````


## Creating Pages

To organize your content effectively, it's recommended to create a new folder for each topic, with subfiles representing different subtopics under it. Here's an example of how you can structure your pages:

```markdown
    * Policy making
        * index.md
        * values-of-creating-new-policy.md
        * how-to-create-national-policy.md
```


### Creating a New Topic with sub-topics

1. Create a new folder in the root directory with a meaningful name for your topic. For example, `policy-making`.

2. Inside the new folder, create an `index.md` file. This file will serve as the configuration for the topic in the menu.

3. In the `index.md` file, add Jekyll's front matter to specify the metadata for the topic. Provide the `title` of the topic as it should appear in the menu and the `menu` hierarchy order for its position in the menu tree.

Example `index.md` content:

```markdown
---
title: Policy making  # This is the title of the topic in the menu list
menu: 2  # This is the hierarchy of this topic in the menu tree
---
```


### Creating Subtopics
1. Inside the same topic folder, create additional .md files for each subtopic you want to cover. For example, `values-of-creating-new-policy.md ` and `how-to-create-national-policy.md`.
Use Jekyll's front matter in each subtopic file to specify metadata such as title, parent, layout, and nav_order.
Example subtopic content:
```markdown
---
title: Values of Creating New Policy
parent: Policy making
layout: default
nav_order: 1
---
```


2. Add your content using Markdown syntax to each subtopic file.
By following this structure, you can easily organize and create a hierarchy of topics and subtopics in your Toolkit micro-site.


### Creating a Main Topic (Without Sub-Topics)

To generate a main topic without any sub-topics, follow these steps. For instance, if you intend to establish a topic named "Contributors" as a menu list item, directing to a contributors page, you can achieve this by creating a file named `Team.md`.

In the created file, it's crucial to set the `has_children` property to `false`. This ensures that topics lacking sub-topics are correctly displayed in the menu list.

### Customizing the Contributors Page

The current version of this template incorporates both a contributor profile page and a contributors list page. If you wish to integrate these pages into your website, you must update the `_data/contributors.yml` file with a list of your project's contributors.

To access an individual contributor's profile page, you can link to the respective profile using the ID from your `_data/contributors.yml` file. For example: `[Jane Doe]({{ site.baseurl }}/contributors/Jane-doe.html)` directs to Jane Doe's profile based on the YAML file.

If you decide not to display the contributors page in your side menu, you can exclude it by adding `Team.md` to the `excludes` list in your `_config.yml` file.


## Customizing Configuration

You can customize the site's configuration by editing the `_data/site_info.yml` and `_data/site_styles.yml` files. These files contain settings for the site's title, background color, and more.

For navigation and menu customization, update the nav.html and sidebar.html partials.

That's it! You're ready to create, customize, and deploy your Toolkit site. Have fun documenting and sharing your content!


## Create a New Toolkit

You can fork this repository to create a copy of it for your use. Follow these steps to create a new toolkit based on the UNDP Accelerator Labs Toolkit Micro-site template:

1. Click on [Create New Toolkit](https://github.com/UNDP-Accelerator-Labs/toolkit-micro-site-template/fork).

2. Provide a name for your new toolkit repository.

3. Choose to include all branches (main and gh-pages) to ensure your micro-site is ready to deploy on GitHub Pages.

4. Click the "Create fork" button to generate your new toolkit repository.

5. Once the repository is created, you are ready to start adding content to your micro-site or you can clone it to your local machine using Git:

   ```markdown
   git clone https://github.com/your-username/your-new-toolkit.git
   ```

## Set Up the Toolkit Micro-site Locally

Follow these steps to set up the UNDP Accelerator Labs Toolkit Micro-site locally on your computer for development and customization:

1. **Clone the Repository**: Open your terminal or command prompt and navigate to the directory where you want to clone the repository. Then, run the following command to clone the repository to your local machine:

    ```markdown
    git clone https://github.com/UNDP-Accelerator-Labs/toolkit-micro-site-template.git
    ```

2. ### Navigate to the Repository

Change your current directory to the cloned repository:

```markdown
cd toolkit-micro-site-template
```

3. Install Dependencies
Ensure you have Ruby and Bundler installed on your computer. If not, you can install them following these instructions. Then, install the required dependencies by running:

```markdown
    bundle install
```

5. Run the Local Server
Start the local development server by running the following command:

```markdown
bundle exec jekyll serve 
```

This command will build the site and start a local server. You'll see an output with a URL like http://127.0.0.1:4000/. Open this URL in your web browser to view your locally hosted toolkit micro-site.

## License
This project is licensed under the Creative Commons Attribution 4.0 International License.

You can view the full license text [here](https://creativecommons.org/licenses/by/4.0/legalcode).

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
