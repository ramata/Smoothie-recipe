# Smoothies

This is a simple static web site containing various Smoothie recipes.

## Steps to Reproduce This Project

The steps below will demonstrate how to create this project from scratch:

* [Step 1 - Setup The Project](#step-1---setup-the-project)

### Step 1 - Setup The Project

In this step we will create a directory for our project, create the `index.html` file in the new directory, edit the file in sublime, and finally initialize it as a git repository.

1a. Create a directory for this project and create the `index.html` file.

```bash
cd ~/ga/wdi
mkdir -p mini-projects/smoothie-recipes
cd mini-projects/smoothie-recipes
touch index.html
subl .
```

1b. Open `index.html` in *Sublime* and add the following content:

```html
<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Smoothies!</title>
  <meta name="description" content="Awesome Smoothie Recipes">
  <meta name="author" content="Mike Hopper">
</head>

<body>
  <div class="banner">
    <h1>Welcome to Smoothie Recipes</h1>
    <p>Welcome to my collection of delicious and healthy smoothie recipes. Enjoy!!!</p>
  </div>
</body>
</html>
```

1c. Test the `index.html` file by opening it in your default browser:

```bash
open index.html
```

1d. Save your work using `git`:

```bash
git init
git add -A
git commit -m "Just getting started with our smoothies website."
git tag step1
```

### Step 2 - Adding Some Recipes

Let's add some recipes to our Smoothies Website.

2a. Put the following HTML code inside the `<body>` under the banner div:

```html
  <div class="recipes">
    <h2>Classic</h2>
    <ul>
      <li>2 small bananas, broken into chunks</li>
      <li>1 cup frozen unsweetened strawberries</li>
      <li>1 (8 ounce) container vanilla low-fat yogurt</li>
      <li>3/4 cup milk</li>
   </ul>

    <h2>Purple Monster</h2>
    <ul>
      <li>2 frozen bananas</li>
      <li>1/2 cup frozen blueberries</li>
      <li>1 cup orange juice</li>
      <li>1 tablespoon honey (optional)</li>
      <li>1 teaspoon vanilla extract (optional)</li>
    </ul>

    <h2>Peanut Butter Banana</h2>
    <ul>
      <li>2 bananas, broken into chunks</li>
      <li>2 cups milk</li>
      <li>1/2 cup peanut butter</li>
      <li>2 tablespoons honey, or to taste</li>
      <li>2 cups ice cubes</li>
    </ul>
  </div>
```

2b. Test it with your default browser:

```bash
open index.html
```

2c. Save your work using `git`:

```bash
git init
git add -A
git commit -m "Added some recipes."
git tag step2
```
