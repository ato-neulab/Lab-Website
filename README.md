# ATo Lab Website

A static website made with Jekyll for the ATo Lab, a multidisciplinary research lab at Northeastern University working at the intersections of human-computer interaction, games, and social justice.

## Tech Stack

**Namecheap** - Domain Hosting

**GitHub Pages** - Deployment, Serving

**Jekyll** (HTML, Sass, Bootstrap, Liquid) - Implementation

**Figma** - Design Prototype

**Midjourney** - Image Generation, Mockups

[**Realtime Colors**](https://realtimecolors.com/) - Color Palette

### Process:

1. Decide on a means of implementation: Jekyll Static Site Generator
2. Setup GitHub pages repository
3. Connect lab.alexandrato.com subdomain to GitHub Pages
4. Use Realtime Colors to decide on a palette
5. Use Midjourney to generate mockups to take inspiration from
6. Design prototype in Figma
7. Cropped headshot image files using Photoshop
8. Implement prototype using Jekyll
9. Write documentation explaining how it works and how to update

## How it works

Jekyll is a static site generator (SSG)

At a high level, a static site generator is a tool that produces a fully static website based on **raw data** and **templates**.

1. **Data** : This can be your blog posts, images, information about you or your company, and so on. This data can be stored in various forms, such as text files, Markdown files, or even data files like JSON or YAML.
2. **Templates** : These are structures or blueprints that define how your site should look. They can be in HTML, CSS, and JavaScript. The templates specify where and how to display your data.

When you run the static site generator, it takes each piece of data, puts it into a template, and then generates a corresponding static HTML file.

The data and templates to be converted into static web pages are defined by the file structure of the website. The most relevant files and folders are:

- **\_config.yml:** The configuration file for your Jekyll site. It contains global configurations and variables for your site. Things like your site's name, URL, pagination settings, and more can be set in this file
- **\_includes:** This directory is for HTML or Markdown files that you want to include in other files. It's a way to reuse code. For instance, we have files for the header (`header.html`) and footer (`footer.html`) of the site that get included in our `wrapper` layout to avoid repeating the same code for each page on the site.
- **\_data:** This directory is where you can store additional data for your site in formats like YAML, JSON, or CSV. This data can then be accessed via templates in your site. For example, we have a YAML file (`people.yml`) with a list of all the members of your team and their information, that gets used to generate the Meet the People page.
- **\_layouts:** This directory contains your site's layouts. These are templates that wrap around your content and define the structure for pages on your site. (As of writing this) Our only layout is the aforementioned `wrapper` layout that includes a header and footer, a sidebar, and a space for the main content.
- **\_sass:** If you're using Sass for your CSS, this is where your Sass files go. Jekyll will automatically compile your Sass into CSS as part of the build process. Learn more about Sass [here](https://sass-lang.com/documentation/).
- **assets:** This directory is for static files like images, CSS, JavaScript, etc. Basically, any files that should be included as-is in your final site go here
- **.markdown (.md) files and .html files:** Provided that the file has a [front matter section](https://jekyllrb.com/docs/front-matter/), Jekyll converts Markdown files in the root directory into HTML pages. It also uses any HTML files with front matter you put here. By default, these pages can be found at, \<site URL\>/\<name\>. For example, a `publications.md` file would be found at _lab.alexandrato.com/publications_ and a `projects.html` file would be found at _lab.alexandrato.com/projects_.

For more information about how Jekyll works, check [its documentation](https://jekyllrb.com/docs/).

## How to update

### Workflows for different objectives

Assumes you know how to use GitHub well enough to be able to change files, make commits, etc. If not, [this link](https://docs.github.com/en/get-started/quickstart/hello-world) is a good place to start learning the basics of GitHub.

#### How to create a new page

1. Create a new `.md` or `.html` file in the root directory
2. Add front matter so Jekyll knows to compile it
   1. Set `layout` to `wrapper`.
      1. Ensures all the prerequisites for the site get loaded in the page you're making. It's almost always recommended you do this, unless you really know what you're doing.
   2. Set `title` to whatever you want your title to be
3. Write whatever content you want

#### How to edit, add, or remove someone on the People page

1. Navigate to `/_data/people.yml`
2. Edit, add, or delete content
   1. To change someone's picture:
      1. Crop the image to 1:1 aspect ratio (important for maintaining format of polaroids)
      2. Add image file to `/assets/images/headshots/`
      3. In `people.yml`, change headshot field to filename of image (including the suffix)

#### How to edit the text sections

1. Navigate to `/_includes/text-content/`
2. Edit file of your choosing
   1. Do not remove any tags (ie: \<p\>,\<h1\>), just edit the text in between
