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
  <section class="banner">
    <h1>Welcome to Smoothie Recipes</h1>
    <p>Welcome to my collection of delicious and healthy smoothie recipes. Enjoy!!!</p>
  </section>
</body>
</html>
```

Substitute your name in the "author" metadata above.


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

2a. Put the following HTML code inside the `<body>` under the banner section:

```html
  <section class="recipes">
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
  </section>
```

2b. Test it with your default browser:

```bash
open index.html
```

2c. Save your work using `git`:

```bash
git add -A
git commit -m "Added some recipes."
git tag step2
```

### Step 3 - Add a CSS file

In this step we will create a `css` file for styling and link it into our index.html page. We will also add a background image to our css.

3a. Create the file `main.css`:

```bash
touch main.css
```

3b. Open the file `main.css` in _Sublime_ and add the following content:

```css
body {
  background-color: #ffaaff;
}
```

3c. Add the link for `main.css` to the file `index.html` (add the link to the `<head>` section of `index.html`):

```html
<link rel="stylesheet" type="text/css" href="main.css">
```

3d. Test the results in your default browser:

```bash
open index.html
```

Experiment with different background colors.

3e. Now let's add a pretty background image. Create a directory for the images and then download the background image using the following commands:

```bash
mkdir images
wget https://raw.githubusercontent.com/drmikeh/smoothie-recipes/master/images/background.jpg -O images/background.jpg
```

3f. Replace the contents of `main.css` with the following:

```css
body {
  background-color: #ffaaff;
  background-image: url("images/background.jpg");
  background-size: 100% auto;
}
```

3g. Test the results in your default browser:

```bash
open index.html
```

3h. Save your work using `git`:

```bash
git add -A
git commit -m "Added a CSS file and a background image."
git tag step3
```

### Step 4 - Add Twitter Bootstrap

In this step we will add the [Twitter Bootstrap](http://getbootstrap.com/) CSS library to our project. Then we will add a Bootstrap _Jumbotron_ to our web site.

4a. Use `bower` to download _Twitter Bootstrap_ and its dependencies into our project. Note that `bower` will put these files into a directory called `bower_components`:

```bash
bower install bootstrap
git ignore bower_components
```

We have also added the `bower_components` directory to our `.gitignore` file so that we will *not* be tracking these downloaded files in our project.

4b. Add the following `link` and `script` tags to the `index.html` file:

```html
<!-- the following line goes inside the <head> section just before the link to main.css -->
<link rel="stylesheet" type="text/css" href="bower_components/bootstrap/dist/css/bootstrap.min.css">

...

<!-- the following lines go at the bottom of the <body> section -->
<script type="text/javascript" src="bower_components/jquery/dist/jquery.min.js" defer></script>
<script type="text/javascript" src="bower_components/bootstrap/dist/js/bootstrap.min.js" defer></script>
```

4c. Convert the banner to a Bootstrap _Jumbotron_. Edit `index.html` and replace the "banner" class with Bootstrap's `jumbotron` class:

```html
  <section class="jumbotron">
    <h1>Welcome to Smoothie Recipes</h1>
    <p>Welcome to my collection of delicious and healthy smoothie recipes. Enjoy!!!</p>
  </section>
```

Refresh your browser and inspect the results. You should see a nice _Jumbotron_ at the top of the page. The only problem is that the _Jumbotron_ is sitting on top of our background image and it doesn't look right. We will fix this by making the _Jumbotron_ background mostly transparent. We do this by adding a rule to our `main.css` file:

```css
.jumbotron {
  padding: 20px;
  background: rgb(255, 255, 255); /* This is for ie8 and below */
  background: rgba(255, 255, 255, 0.3); /* the last argument is the opacity */
}
```

Let's also add some padding for our `.recipes` class:

```css
.recipes {
  padding: 20px;
}
```

Refresh your browser again and check it out!

4d. Save your work using `git`:

```bash
git add -A
git commit -m "Added Twitter Bootstrap and a Jumbotron."
git tag step4
```
