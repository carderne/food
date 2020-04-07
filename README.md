# recipes
Repo for recipes with a simple site to view. Created using markdown files and [Jekyll](https://jekyllrb.com/).

## Instead and serve
```
gem install bundler jekyll
bundle exec jekyll serve
```

## Content
To edit the home page, simply edit `index.md`.

To add a new category, you need to create a file with the appropriate name (e.g. `bread.md`) in the `_categories/` directory following the example of the other category files. Front-matter (between the triple dashes `---`) must contain the title, and you must set `layout: category`. Any content below the front-matter will displayed on the page for that category. Then Create a new subdirectory underneath `_recipes` with the same name as the file above, in this case, `bread/`.

```
# Category example for _categories/bread.md
---
title: Bread
layout: category
---

We love making bread!
```

To add a recipe, add a file (e.g. `pizza.md`) under the appropriate subdirectory within `_recipes/` (if you put it at the top level, it won't be displayed) and follow the `_recipes/template.md` file or another recipe file. The variables `source`, `yield` and `notes` are optional. `source` can be a URL or simple text. Use quotes `""` around strings if they contain special characters such as colons `:`.

```
# Recipe example for _recipes/bread/pizza.md
---
layout: recipe
title: Pizza dough
source:
yield: 4 pizzas
time: 40 minutes
notes:
ingredients:
- 2 cups 00 flour
- 1 cup warm water
method:
- Mix together.
- Knead.
---
```

## Layouts
All layout and style is contained in the following files:
```
.
├── _includes
│   ├── cat-list.html   # menu list of categories
│   ├── rec-list.html   # menu list of recipes
│   └── style.scss      # all site styles
├───_layouts
│   ├── default.html    # root layout with HTML boiler plate etc
│   ├── index.html      # layout for home page
│   ├── category.html   # layout for a category page
│   └── recipe.html     # layout for an actual recipe
│
...
```

## Configuration
The Jekyll configuration is in `_config.yml`.
