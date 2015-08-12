# Smoothies

This is a simple static web site containing various Smoothie recipes.

## Steps to Reproduce This Project

The steps below will demonstrate how to create this project from scratch:

* [Step 1 - Setup The Project](#step-1---setup-the-project)
* [Step 2 - Adding Some Recipes](#step-2---adding-some-recipes)
* [Step 3 - Add a CSS file](#step-3---add-a-css-file)
* [Step 4 - Add Twitter Bootstrap](#step-4---add-twitter-bootstrap)
* [Step 5 - Add Bootstrap Grid Layout](#step-5---add-bootstrap-grid-layout)

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
  background-color: #ffffff;
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

### Step 5 - Add Bootstrap Grid Layout

In this step we will use Bootstrap's _Grid_ to layout our recipes horizontally.

5a. First let's add some more recipes:

```html
<h2>Banana-Berry</h2>
    <ul>
      <li>1 small banana</li>
      <li>6 oz. pineapple juice</li>
      <li>0.50 cup ice</li>
      <li>6 oz. blueberries</li>
      <li>6 oz. raspberries or blackberries</li>
      <li>2 tsp. honey</li>
      <li>1 tsp. grated peeled fresh ginger</li>
    </ul>

    <h2>Irresistible Peach</h2>
    <ul>
      <li>2 cup peaches</li>
      <li>0.50 cup milk</li>
      <li>1 cup Ice cream</li>
      <li>1 tbsp. lemon juice</li>
      <li>peach slices</li>
    </ul>

    <h2>Kiwi Strawberry</h2>
    <ul>
      <li>1 banana</li>
      <li>6 strawberries</li>
      <li>1 kiwi</li>
      <li>1/2 cup vanilla frozen yogurt</li>
      <li>3/4 cup pineapple and orange juice blend</li>
    </ul>

    <h2>Chocolate Banana</h2>
    <ul>
      <li>1 banana</li
      <li>1 tablespoon cocolate syrup</li>
      <li>1 cup milk</li
      <li>1 cup crushed ice</li>
    </ul>

    <h2>Feel Good</h2>
    <ul>
      <li>1/2 cup nonfat milk</li>
      <li>1/2 cup fat-free plain yogurt</li>
      <li>1/2 frozen banana, peeled and chopped</li>
      <li>2 tablespoons powdered protein supplement</li>
      <li>1 1/2 tablespoons flax seed</li>
      <li>1 teaspoon honey</li>
      <li>1/2 cup frozen strawberries</li>
    </ul>

    <h2>Mango Lassi II</h2>
    <ul>
      <li>2 mangos - peeled, seeded and diced</li>
      <li>2 cups plain yogurt</li>
      <li>1/2 cup white sugar</li>
      <li>1 cup ice</li>
    </ul>
```

Refresh your browser and scroll down. Did you notice that the background repeats and it is a bit distracting? Let's fix it.

5b. Change background to be fixed with no repeat:

Change the `body` rule in `main.css` to the following:

```css
body {
  background-color: #ffaaff;
  background-image: url("images/background.jpg");
  background-size: 1600px auto;
  background-repeat: no-repeat;
  background-attachment: fixed;
}
```

Now you should see a nice background image that stretches to 1600px and does not repeat.
But it seems like we are wasting a lot of space on the right side of our page and doing a lot of vertical scrolling. Let's fix that with a Grid.

5c. Add the container and row for the Bootstrap Grid:

```html
<section class="recipes container-fluid">
  <div class="row">
  ...
  </div>
</section>
```

Remember to keep your indentation consistent.

5d. Wrap each recipe in it's own div and add the grid col rules:

```html
<div class="col-lg-4 col-sm-6 col-xs-12 recipe">
  ...
</div>
```

You can use Sublime's multi-select to add the above opening `<div>` before each `<h2>` and the closing `</div>` after each `</ul>`.

You should end up with this HTML for your recipes section:

```html
<section class="recipes container-fluid">
    <div class="row">
      <div class="col-lg-4 col-sm-6 col-xs-12 recipe">
        <h2>Classic</h2>
        <ul>
          <li>2 small bananas, broken into chunks</li>
          <li>1 cup frozen unsweetened strawberries</li>
          <li>1 (8 ounce) container vanilla low-fat yogurt</li>
          <li>3/4 cup milk</li>
        </ul>
      </div>

      <div class="col-lg-4 col-sm-6 col-xs-12 recipe">
        <h2>Purple Monster</h2>
        <ul>
          <li>2 frozen bananas</li>
          <li>1/2 cup frozen blueberries</li>
          <li>1 cup orange juice</li>
          <li>1 tablespoon honey (optional)</li>
          <li>1 teaspoon vanilla extract (optional)</li>
        </ul>
      </div>

      <div class="col-lg-4 col-sm-6 col-xs-12 recipe">
        <h2>Peanut Butter Banana</h2>
        <ul>
          <li>2 bananas, broken into chunks</li>
          <li>2 cups milk</li>
          <li>1/2 cup peanut butter</li>
          <li>2 tablespoons honey, or to taste</li>
          <li>2 cups ice cubes</li>
        </ul>
      </div>

      <div class="col-lg-4 col-sm-6 col-xs-12 recipe">
        <h2>Banana-Berry</h2>
        <ul>
          <li>1 small banana</li>
          <li>6 oz. pineapple juice</li>
          <li>0.50 cup ice</li>
          <li>6 oz. blueberries</li>
          <li>6 oz. raspberries or blackberries</li>
          <li>2 tsp. honey</li>
          <li>1 tsp. grated peeled fresh ginger</li>
        </ul>
      </div>

      <div class="col-lg-4 col-sm-6 col-xs-12 recipe">
        <h2>Irresistible Peach</h2>
        <ul>
          <li>2 cup peaches</li>
          <li>0.50 cup milk</li>
          <li>1 cup Ice cream</li>
          <li>1 tbsp. lemon juice</li>
          <li>peach slices</li>
        </ul>
      </div>

      <div class="col-lg-4 col-sm-6 col-xs-12 recipe">
        <h2>Kiwi Strawberry</h2>
        <ul>
          <li>1 banana</li>
          <li>6 strawberries</li>
          <li>1 kiwi</li>
          <li>1/2 cup vanilla frozen yogurt</li>
          <li>3/4 cup pineapple and orange juice blend</li>
        </ul>
      </div>

      <div class="col-lg-4 col-sm-6 col-xs-12 recipe">
        <h2>Chocolate Banana</h2>
        <ul>
          <li>1 banana</li
          <li>1 tablespoon cocolate syrup</li>
          <li>1 cup milk</li
          <li>1 cup crushed ice</li>
        </ul>
      </div>

      <div class="col-lg-4 col-sm-6 col-xs-12 recipe">
        <h2>Feel Good</h2>
        <ul>
          <li>1/2 cup nonfat milk</li>
          <li>1/2 cup fat-free plain yogurt</li>
          <li>1/2 frozen banana, peeled and chopped</li>
          <li>2 tablespoons powdered protein supplement</li>
          <li>1 1/2 tablespoons flax seed</li>
          <li>1 teaspoon honey</li>
          <li>1/2 cup frozen strawberries</li>
        </ul>
      </div>

      <div class="col-lg-4 col-sm-6 col-xs-12 recipe">
        <h2>Mango Lassi II</h2>
        <ul>
          <li>2 mangos - peeled, seeded and diced</li>
          <li>2 cups plain yogurt</li>
          <li>1/2 cup white sugar</li>
          <li>1 cup ice</li>
        </ul>
      </div>
    </div>
  </section>
```

Inspect your results. You should see the recipes in a grid but notice that the last recipe doesn't quite look right? Why?

Let's fix it by defining a `min-height` for each `recipe` in our `main.css` file:

```css
.recipe {
  min-height: 220px;
}
```

Note that we added the `recipe` class to our HTML just so that we could control the look of each recipe.

Now we should see that all of our recipes look nice. Try resizing your browser window to see how it looks at smaller screen sizes.

5e. Change the color of each recipe's `<h2>` to `blue`:

```css
.recipe h2 {
  color: blue;
}
```

5f1. (Option 1) Fade out the background image a bit.

CSS does not have a way to make a background image semi-transparent. So let's use `imagemagick` to make our background image a little less distracting. The `imagemagick` app should have been installed during *InstallFest* and its executable is called `convert`:

```bash
which convert
convert --version
cd images
convert background.jpg -fill white -colorize 50% background-faded.jpg
cd ..
```

Edit `main.css` and change the `body` rule to use `background-faded.jpg`:

```css
body {
  ...
  background-image: url("images/background-faded.jpg");
  ...
}
```

Now refresh the browser and note the faded background. If you like the original background better, you still have that file in `images`, or feel free to download and use your own background image.

5f2. (Option 2) Alternate Way to Fade Background Image

There is a new CSS feature that is supported by most modern browsers called `background-blend-mode`. See [CSS Blend Modes](https://css-tricks.com/basics-css-blend-modes/).

To use this feature, simply edit `main.css` and set the content of the `body` rule to:

```css
body {
  background-color: #808080;
  background-image: url("images/background.jpg");
  background-blend-mode: screen;
  background-size: 1600px auto;
  background-repeat: no-repeat;
  background-attachment: fixed;
}
```

5g. Save your work using `git`:

```bash
git add -A
git commit -m "Added Twitter Bootstrap Grid and faded the background image."
git tag step5
```
