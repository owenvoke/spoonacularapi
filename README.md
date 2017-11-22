# Getting started

## How to Build

The generated code has dependencies over external libraries like UniRest. These dependencies are defined in the ```composer.json``` file that comes with the SDK. 
To resolve these dependencies, we use the Composer package manager which requires PHP greater than 5.3.2 installed in your system. 
Visit [https://getcomposer.org/download/](https://getcomposer.org/download/) to download the installer file for Composer and run it in your system. 
Open command prompt and type ```composer --version```. This should display the current version of the Composer installed if the installation was successful.

* Using command line, navigate to the directory containing the generated files (including ```composer.json```) for the SDK. 
* Run the command ```composer install```. This should install all the required dependencies and create the ```vendor``` directory in your project directory.

![Building SDK - Step 1](https://apidocs.io/illustration/php?step=installDependencies&workspaceFolder=spoonacular%20API-PHP)

### [For Windows Users Only] Configuring CURL Certificate Path in php.ini

CURL used to include a list of accepted CAs, but no longer bundles ANY CA certs. So by default it will reject all SSL certificates as unverifiable. You will have to get your CA's cert and point curl at it. The steps are as follows:

1. Download the certificate bundle (.pem file) from [https://curl.haxx.se/docs/caextract.html](https://curl.haxx.se/docs/caextract.html) on to your system.
2. Add curl.cainfo = "PATH_TO/cacert.pem" to your php.ini file located in your php installation. “PATH_TO” must be an absolute path containing the .pem file.

```ini
[curl]
; A default value for the CURLOPT_CAINFO option. This is required to be an
; absolute path.
;curl.cainfo =
```

## How to Use

The following section explains how to use the SpoonacularAPI library in a new project.

### 1. Open Project in an IDE

Open an IDE for PHP like PhpStorm. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

![Open project in PHPStorm - Step 1](https://apidocs.io/illustration/php?step=openIDE&workspaceFolder=spoonacular%20API-PHP)

Click on ```Open``` in PhpStorm to browse to your generated SDK directory and then click ```OK```.

![Open project in PHPStorm - Step 2](https://apidocs.io/illustration/php?step=openProject0&workspaceFolder=spoonacular%20API-PHP)     

### 2. Add a new Test Project

Create a new directory by right clicking on the solution name as shown below:

![Add a new project in PHPStorm - Step 1](https://apidocs.io/illustration/php?step=createDirectory&workspaceFolder=spoonacular%20API-PHP)

Name the directory as "test"

![Add a new project in PHPStorm - Step 2](https://apidocs.io/illustration/php?step=nameDirectory&workspaceFolder=spoonacular%20API-PHP)
   
Add a PHP file to this project

![Add a new project in PHPStorm - Step 3](https://apidocs.io/illustration/php?step=createFile&workspaceFolder=spoonacular%20API-PHP)

Name it "testSDK"

![Add a new project in PHPStorm - Step 4](https://apidocs.io/illustration/php?step=nameFile&workspaceFolder=spoonacular%20API-PHP)

Depending on your project setup, you might need to include composer's autoloader in your PHP code to enable auto loading of classes.

```PHP
require_once "../vendor/autoload.php";
```

It is important that the path inside require_once correctly points to the file ```autoload.php``` inside the vendor directory created during dependency installations.

![Add a new project in PHPStorm - Step 4](https://apidocs.io/illustration/php?step=projectFiles&workspaceFolder=spoonacular%20API-PHP)

After this you can add code to initialize the client library and acquire the instance of a Controller class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

### 3. Run the Test Project

To run your project you must set the Interpreter for your project. Interpreter is the PHP engine installed on your computer.

Open ```Settings``` from ```File``` menu.

![Run Test Project - Step 1](https://apidocs.io/illustration/php?step=openSettings&workspaceFolder=spoonacular%20API-PHP)

Select ```PHP``` from within ```Languages & Frameworks```

![Run Test Project - Step 2](https://apidocs.io/illustration/php?step=setInterpreter0&workspaceFolder=spoonacular%20API-PHP)

Browse for Interpreters near the ```Interpreter``` option and choose your interpreter.

![Run Test Project - Step 3](https://apidocs.io/illustration/php?step=setInterpreter1&workspaceFolder=spoonacular%20API-PHP)

Once the interpreter is selected, click ```OK```

![Run Test Project - Step 4](https://apidocs.io/illustration/php?step=setInterpreter2&workspaceFolder=spoonacular%20API-PHP)

To run your project, right click on your PHP file inside your Test project and click on ```Run```

![Run Test Project - Step 5](https://apidocs.io/illustration/php?step=runProject&workspaceFolder=spoonacular%20API-PHP)

## How to Test

Unit tests in this SDK can be run using PHPUnit. 

1. First install the dependencies using composer including the `require-dev` dependencies.
2. Run `vendor\bin\phpunit --verbose` from commandline to execute tests. If you have 
   installed PHPUnit globally, run tests using `phpunit --verbose` instead.

You can change the PHPUnit test configuration in the `phpunit.xml` file.

## Initialization

### 
You need the following information for initializing the API client.

| Parameter | Description |
|-----------|-------------|
| xMashapeKey | The Mashape application you want to use for this session. |



API client can be initialized as following.

```php
// Configuration parameters
$xMashapeKey = "xMashapeKey"; // The Mashape application you want to use for this session.

$client = new SpoonacularAPIClient($xMashapeKey);
```

## Class Reference

### <a name="list_of_controllers"></a>List of Controllers

* [APIController](#api_controller)

### <a name="api_controller"></a>![Class: ](https://apidocs.io/img/class.png ".APIController") APIController

#### Get singleton instance

The singleton instance of the ``` APIController ``` class can be accessed from the API Client.

```php
$client = $client->getClient();
```

#### <a name="get_product_information"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.getProductInformation") getProductInformation

> *Tags:*  ``` Skips Authentication ``` 

> Get information about a packaged food product.


```php
function getProductInformation($id)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  ``` DefaultValue ```  | The id of the packaged food product. |



#### Example Usage

```php
$id = 22347;

$result = $client->getProductInformation($id);

```


#### <a name="find_similar_recipes"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.findSimilarRecipes") findSimilarRecipes

> *Tags:*  ``` Skips Authentication ``` 

> Find recipes which are similar to the given one.


```php
function findSimilarRecipes($id)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  ``` DefaultValue ```  | The id of the source recipe to which similar recipes should be found. |



#### Example Usage

```php
$id = 156992;

$result = $client->findSimilarRecipes($id);

```


#### <a name="get_autocomplete_ingredient_search"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.getAutocompleteIngredientSearch") getAutocompleteIngredientSearch

> *Tags:*  ``` Skips Authentication ``` 

> Autocomplete a search for an ingredient.


```php
function getAutocompleteIngredientSearch($query)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| query |  ``` Required ```  ``` DefaultValue ```  | The query - a partial or full ingredient name. |



#### Example Usage

```php
$query = 'appl';

$result = $client->getAutocompleteIngredientSearch($query);

```


#### <a name="create_visualize_price_breakdown"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.createVisualizePriceBreakdown") createVisualizePriceBreakdown

> *Tags:*  ``` Skips Authentication ``` 

> Visualize the price breakdown of a recipe.


```php
function createVisualizePriceBreakdown(
        $ingredientList,
        $servings,
        $defaultCss = 'checked',
        $mode = 1,
        $fieldParameters = NULL)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| ingredientList |  ``` Required ```  ``` DefaultValue ```  | The ingredient list of the recipe, one ingredient per line. |
| servings |  ``` Required ```  ``` DefaultValue ```  | The number of servings. |
| defaultCss |  ``` Optional ```  ``` DefaultValue ```  | Whether the widget should be styled with the default css. |
| mode |  ``` Optional ```  ``` DefaultValue ```  | The mode in which the widget should be delivered. 1 = separate views (compact), 2 = all in one view (full). |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |



#### Example Usage

```php
$ingredientList = '3 oz flour';
$servings = 2;
$defaultCss = 'checked';
$mode = 1;
// key-value map for optional form parameters
$formParams = array('key' => 'value');


$result = $client->createVisualizePriceBreakdown($ingredientList, $servings, $defaultCss, $mode, $formParams);

```


#### <a name="create_visualize_nutrition"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.createVisualizeNutrition") createVisualizeNutrition

> *Tags:*  ``` Skips Authentication ``` 

> Visualize a recipe's nutritional information.


```php
function createVisualizeNutrition(
        $ingredientList,
        $servings,
        $defaultCss = 'checked',
        $fieldParameters = NULL)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| ingredientList |  ``` Required ```  ``` DefaultValue ```  | The ingredient list of the recipe, one ingredient per line. |
| servings |  ``` Required ```  ``` DefaultValue ```  | The number of servings. |
| defaultCss |  ``` Optional ```  ``` DefaultValue ```  | Whether the ingredient list should be styled with the default css. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |



#### Example Usage

```php
$ingredientList = '3 oz flour';
$servings = 2;
$defaultCss = 'checked';
// key-value map for optional form parameters
$formParams = array('key' => 'value');


$result = $client->createVisualizeNutrition($ingredientList, $servings, $defaultCss, $formParams);

```


#### <a name="create_visualize_ingredients"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.createVisualizeIngredients") createVisualizeIngredients

> *Tags:*  ``` Skips Authentication ``` 

> Visualize ingredients of a recipe.


```php
function createVisualizeIngredients(
        $ingredientList,
        $servings,
        $defaultCss = 'checked',
        $measure = 'metric',
        $view = 'grid',
        $fieldParameters = NULL)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| ingredientList |  ``` Required ```  ``` DefaultValue ```  | The ingredient list of the recipe, one ingredient per line. |
| servings |  ``` Required ```  ``` DefaultValue ```  | The initial number of servings. |
| defaultCss |  ``` Optional ```  ``` DefaultValue ```  | Whether the ingredient list should be styled with the default css. |
| measure |  ``` Optional ```  ``` DefaultValue ```  | The initial measure, either "metric" or "us". |
| view |  ``` Optional ```  ``` DefaultValue ```  | The initial view, either "grid" or "list". |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |



#### Example Usage

```php
$ingredientList = '3 oz flour';
$servings = 2;
$defaultCss = 'checked';
$measure = 'metric';
$view = 'grid';
// key-value map for optional form parameters
$formParams = array('key' => 'value');


$result = $client->createVisualizeIngredients($ingredientList, $servings, $defaultCss, $measure, $view, $formParams);

```


#### <a name="get_summarize_recipe"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.getSummarizeRecipe") getSummarizeRecipe

> *Tags:*  ``` Skips Authentication ``` 

> Summarize the recipe in a short text.


```php
function getSummarizeRecipe($id)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  ``` DefaultValue ```  | The id of the recipe that should be summarized. |



#### Example Usage

```php
$id = 4632;

$result = $client->getSummarizeRecipe($id);

```


#### <a name="search_grocery_products"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.searchGroceryProducts") searchGroceryProducts

> *Tags:*  ``` Skips Authentication ``` 

> Search packaged food products like frozen pizza and snickers bars.


```php
function searchGroceryProducts(
        $query,
        $number = 10,
        $offset = 0,
        $queryParameters = NULL)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| query |  ``` Required ```  ``` DefaultValue ```  | The search query. |
| number |  ``` Optional ```  ``` DefaultValue ```  | The number of results to retrieve, defaults to 10. |
| offset |  ``` Optional ```  ``` DefaultValue ```  | The number of results to skip, defaults to 0. |
| queryParameters | ``` Optional ``` | Additional optional query parameters are supported by this method |



#### Example Usage

```php
$query = 'snickers';
$number = 10;
$offset = 0;
// key-value map for optional query parameters
$queryParams = array('key' => 'value');


$result = $client->searchGroceryProducts($query, $number, $offset, $queryParams);

```


#### <a name="get_quick_answer"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.getQuickAnswer") getQuickAnswer

> *Tags:*  ``` Skips Authentication ``` 

> Answer a nutrition related natural language question.


```php
function getQuickAnswer($q)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| q |  ``` Required ```  ``` DefaultValue ```  | The nutrition-related question. |



#### Example Usage

```php
$q = 'How much vitamin c is in 2 apples?';

$result = $client->getQuickAnswer($q);

```


#### <a name="get_recipe_information"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.getRecipeInformation") getRecipeInformation

> *Tags:*  ``` Skips Authentication ``` 

> Get information about a recipe.


```php
function getRecipeInformation($id)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  ``` DefaultValue ```  | The id of the recipe. |



#### Example Usage

```php
$id = 156992;

$result = $client->getRecipeInformation($id);

```


#### <a name="create_parse_ingredients"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.createParseIngredients") createParseIngredients

> *Tags:*  ``` Skips Authentication ``` 

> Extract an ingredient from plain text.


```php
function createParseIngredients(
        $ingredientList,
        $servings)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| ingredientList |  ``` Required ```  ``` DefaultValue ```  | The ingredient list of the recipe, one ingredient per line. |
| servings |  ``` Required ```  ``` DefaultValue ```  | The number of servings that you can make from the ingredients. |



#### Example Usage

```php
$ingredientList = '3 oz pork shoulder';
$servings = 2;

$result = $client->createParseIngredients($ingredientList, $servings);

```


#### <a name="create_map_ingredients"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.createMapIngredients") createMapIngredients

> *Tags:*  ``` Skips Authentication ``` 

> Map ingredients to food products.


```php
function createMapIngredients(
        $ingredientList,
        $servings)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| ingredientList |  ``` Required ```  ``` DefaultValue ```  | A new line-separated list of ingredients. |
| servings |  ``` Required ```  ``` DefaultValue ```  | The number of servings this recipe makes. |



#### Example Usage

```php
$ingredientList = '200g flour\\n3 eggs';
$servings = 1;

$result = $client->createMapIngredients($ingredientList, $servings);

```


#### <a name="get_extract_recipe_from_website"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.getExtractRecipeFromWebsite") getExtractRecipeFromWebsite

> *Tags:*  ``` Skips Authentication ``` 

> Extract recipe data from a recipe blog or Web page.


```php
function getExtractRecipeFromWebsite(
        $url,
        $forceExtraction = false,
        $queryParameters = NULL)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| url |  ``` Required ```  ``` DefaultValue ```  | The URL of the recipe page. |
| forceExtraction |  ``` Optional ```  ``` DefaultValue ```  | If true, the extraction will be triggered no matter whether we know the recipe already. Use that only if information is missing as this operation is slower. |
| queryParameters | ``` Optional ``` | Additional optional query parameters are supported by this method |



#### Example Usage

```php
$url = 'http://www.melskitchencafe.com/the-best-fudgy-brownies/';
$forceExtraction = false;
// key-value map for optional query parameters
$queryParams = array('key' => 'value');


$result = $client->getExtractRecipeFromWebsite($url, $forceExtraction, $queryParams);

```


#### <a name="get_compute_daily_meal_plan"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.getComputeDailyMealPlan") getComputeDailyMealPlan

> *Tags:*  ``` Skips Authentication ``` 

> Compute a meal plan for a day.


```php
function getComputeDailyMealPlan(
        $targetCalories,
        $timeFrame)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| targetCalories |  ``` Required ```  ``` DefaultValue ```  | The target number of calories per day. |
| timeFrame |  ``` Required ```  ``` DefaultValue ```  | For one day or a complete week, allowed values are "day" and "week". |



#### Example Usage

```php
$targetCalories = 2000;
$timeFrame = 'day';

$result = $client->getComputeDailyMealPlan($targetCalories, $timeFrame);

```


#### <a name="create_classify_grocery_products_batch"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.createClassifyGroceryProductsBatch") createClassifyGroceryProductsBatch

> *Tags:*  ``` Skips Authentication ``` 

> Given a set of product jsons, get back classified products.


```php
function createClassifyGroceryProductsBatch($productJsonArray)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| productJsonArray |  ``` Required ```  ``` Collection ```  | A JSON Array of products. |



#### Example Usage

```php
$productjsonarray = new Productjsonarray();
$productJsonArray = array($productjsonarray);

$result = $client->createClassifyGroceryProductsBatch($productJsonArray);

```


#### <a name="create_classify_cuisine"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.createClassifyCuisine") createClassifyCuisine

> *Tags:*  ``` Skips Authentication ``` 

> Classify the recipe's cuisine.


```php
function createClassifyCuisine(
        $ingredientList,
        $title)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| ingredientList |  ``` Required ```  ``` DefaultValue ```  | The ingredient list of the recipe, one ingredient per line. |
| title |  ``` Required ```  ``` DefaultValue ```  | The title of the recipe. |



#### Example Usage

```php
$ingredientList = '3 oz pork shoulder';
$title = 'Pork roast with green beans';

$result = $client->createClassifyCuisine($ingredientList, $title);

```


#### <a name="create_classify_a_grocery_product"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.createClassifyAGroceryProduct") createClassifyAGroceryProduct

> *Tags:*  ``` Skips Authentication ``` 

> Given a grocery product title, this endpoint allows you to detect what basic ingredient it is.


```php
function createClassifyAGroceryProduct($productJson)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| productJson |  ``` Required ```  | The json representation of a product. |



#### Example Usage

```php
$productJson = new Productjson();

$result = $client->createClassifyAGroceryProduct($productJson);

```


#### <a name="search_recipes"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.searchRecipes") searchRecipes

> *Tags:*  ``` Skips Authentication ``` 

> Search recipes in natural language.


```php
function searchRecipes(
        $query,
        $cuisine = 'italian',
        $diet = 'vegetarian',
        $excludeIngredients = 'coconut',
        $intolerances = 'egg, gluten',
        $limitLicense = false,
        $number = 10,
        $offset = 0,
        $type = 'main course',
        $queryParameters = NULL)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| query |  ``` Required ```  ``` DefaultValue ```  | The (natural language) recipe search query. |
| cuisine |  ``` Optional ```  ``` DefaultValue ```  | The cuisine(s) of the recipes. One or more (comma separated) of the following: african, chinese, japanese, korean, vietnamese, thai, indian, british, irish, french, italian, mexican, spanish, middle eastern, jewish, american, cajun, southern, greek, german, nordic, eastern european, caribbean, or latin american. |
| diet |  ``` Optional ```  ``` DefaultValue ```  | The diet to which the recipes must be compliant. Possible values are: pescetarian, lacto vegetarian, ovo vegetarian, vegan, and vegetarian. |
| excludeIngredients |  ``` Optional ```  ``` DefaultValue ```  | An comma-separated list of ingredients or ingredient types that must not be contained in the recipes. |
| intolerances |  ``` Optional ```  ``` DefaultValue ```  | A comma-separated list of intolerances. All found recipes must not have ingredients that could cause problems for people with one of the given tolerances. Possible values are: dairy, egg, gluten, peanut, sesame, seafood, shellfish, soy, sulfite, tree nut, and wheat. |
| limitLicense |  ``` Optional ```  ``` DefaultValue ```  | Whether the recipes should have an open license that allows for displaying with proper attribution. |
| number |  ``` Optional ```  ``` DefaultValue ```  | The number of results to return (between 0 and 100). |
| offset |  ``` Optional ```  ``` DefaultValue ```  | The number of results to skip (between 0 and 900). |
| type |  ``` Optional ```  ``` DefaultValue ```  | The type of the recipes. One of the following: main course, side dish, dessert, appetizer, salad, bread, breakfast, soup, beverage, sauce, or drink. |
| queryParameters | ``` Optional ``` | Additional optional query parameters are supported by this method |



#### Example Usage

```php
$query = 'burger';
$cuisine = 'italian';
$diet = 'vegetarian';
$excludeIngredients = 'coconut';
$intolerances = 'egg, gluten';
$limitLicense = false;
$number = 10;
$offset = 0;
$type = 'main course';
// key-value map for optional query parameters
$queryParams = array('key' => 'value');


$result = $client->searchRecipes($query, $cuisine, $diet, $excludeIngredients, $intolerances, $limitLicense, $number, $offset, $type, $queryParams);

```


#### <a name="find_by_nutrients"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.findByNutrients") findByNutrients

> *Tags:*  ``` Skips Authentication ``` 

> Find a set of recipes that adhere to the given nutrient limits. All the found recipes will have macro nutrients within the calories, protein, fat, and carbohydrate limits.


```php
function findByNutrients(
        $maxcalories = 1500,
        $maxcarbs = 100,
        $maxfat = 100,
        $maxprotein = 100,
        $mincalories = 0,
        $minCarbs = 0,
        $minfat = 0,
        $minProtein = 0,
        $queryParameters = NULL)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| maxcalories |  ``` Optional ```  ``` DefaultValue ```  | The maximum number of calories the recipe can have. |
| maxcarbs |  ``` Optional ```  ``` DefaultValue ```  | The maximum number of carbohydrates in grams the recipe can have. |
| maxfat |  ``` Optional ```  ``` DefaultValue ```  | The maximum number of fat in grams the recipe can have. |
| maxprotein |  ``` Optional ```  ``` DefaultValue ```  | The maximum number of protein in grams the recipe can have. |
| mincalories |  ``` Optional ```  ``` DefaultValue ```  | The minimum number of calories the recipe must have. |
| minCarbs |  ``` Optional ```  ``` DefaultValue ```  | The minimum number of carbohydrates in grams the recipe must have. |
| minfat |  ``` Optional ```  ``` DefaultValue ```  | The minimum number of fat in grams the recipe must have. |
| minProtein |  ``` Optional ```  ``` DefaultValue ```  | The minimum number of protein in grams the recipe must have. |
| queryParameters | ``` Optional ``` | Additional optional query parameters are supported by this method |



#### Example Usage

```php
$maxcalories = 1500;
$maxcarbs = 100;
$maxfat = 100;
$maxprotein = 100;
$mincalories = 0;
$minCarbs = 0;
$minfat = 0;
$minProtein = 0;
// key-value map for optional query parameters
$queryParams = array('key' => 'value');


$result = $client->findByNutrients($maxcalories, $maxcarbs, $maxfat, $maxprotein, $mincalories, $minCarbs, $minfat, $minProtein, $queryParams);

```


#### <a name="find_by_ingredients"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.findByIngredients") findByIngredients

> *Tags:*  ``` Skips Authentication ``` 

> Find recipes that use as many of the given ingredients as possible and have as little as possible missing ingredients. This is a whats in your fridge API endpoint.


```php
function findByIngredients(
        $ingredients,
        $limitLicense = false,
        $number = 5,
        $ranking = 1,
        $queryParameters = NULL)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| ingredients |  ``` Required ```  ``` DefaultValue ```  | A comma-separated list of ingredients that the recipes should contain. |
| limitLicense |  ``` Optional ```  ``` DefaultValue ```  | Whether to only show recipes with an attribution license. |
| number |  ``` Optional ```  ``` DefaultValue ```  | The maximal number of recipes to return (default = 5). |
| ranking |  ``` Optional ```  ``` DefaultValue ```  | Whether to maximize used ingredients (1) or minimize missing ingredients (2) first. |
| queryParameters | ``` Optional ``` | Additional optional query parameters are supported by this method |



#### Example Usage

```php
$ingredients = 'apples,flour,sugar';
$limitLicense = false;
$number = 5;
$ranking = 1;
// key-value map for optional query parameters
$queryParams = array('key' => 'value');


$result = $client->findByIngredients($ingredients, $limitLicense, $number, $ranking, $queryParams);

```


#### <a name="create_recipe_card"></a>![Method: ](https://apidocs.io/img/method.png ".APIController.createRecipeCard") createRecipeCard

> *Tags:*  ``` Skips Authentication ``` 

> Create a recipe card given a recipe.


```php
function createRecipeCard(
        $backgroundImage,
        $image,
        $ingredients,
        $instructions,
        $mask,
        $readyInMinutes,
        $servings,
        $title,
        $author = 'Emily Henderson',
        $backgroundColor = '#ffffff',
        $fontColor = '#333333',
        $source = 'spoonacular.com',
        $fieldParameters = NULL)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| backgroundImage |  ``` Required ```  ``` DefaultValue ```  | The background image ("none","background1", or "background2"). |
| image |  ``` Required ```  ``` DefaultValue ```  | The binary image of the recipe as jpg. |
| ingredients |  ``` Required ```  ``` DefaultValue ```  | The ingredient list of the recipe, one ingredient per line. |
| instructions |  ``` Required ```  ``` DefaultValue ```  | The instructions to make the recipe. One step per line. |
| mask |  ``` Required ```  ``` DefaultValue ```  | The mask to put over the recipe image ("ellipseMask", "diamondMask", "diamondMask", "starMask", "heartMask", "potMask", "fishMask"). |
| readyInMinutes |  ``` Required ```  ``` DefaultValue ```  | The number of minutes it takes to get the recipe on the table. |
| servings |  ``` Required ```  ``` DefaultValue ```  | The number of servings that you can make from the ingredients. |
| title |  ``` Required ```  ``` DefaultValue ```  | The title of the recipe. |
| author |  ``` Optional ```  ``` DefaultValue ```  | The author of the recipe. |
| backgroundColor |  ``` Optional ```  ``` DefaultValue ```  | The background color on the recipe card as a hex-string. |
| fontColor |  ``` Optional ```  ``` DefaultValue ```  | The font color on the recipe card as a hex-string. |
| source |  ``` Optional ```  ``` DefaultValue ```  | The source of the recipe. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |



#### Example Usage

```php
$backgroundImage = 'background1';
$image = The image.;
$ingredients = '2 cups of green beans';
$instructions = 'cook the beans';
$mask = 'ellipseMask';
$readyInMinutes = 60;
$servings = 2;
$title = 'Pork tenderloin with green beans';
$author = 'Emily Henderson';
$backgroundColor = '#ffffff';
$fontColor = '#333333';
$source = 'spoonacular.com';
// key-value map for optional form parameters
$formParams = array('key' => 'value');


$result = $client->createRecipeCard($backgroundImage, $image, $ingredients, $instructions, $mask, $readyInMinutes, $servings, $title, $author, $backgroundColor, $fontColor, $source, $formParams);

```


[Back to List of Controllers](#list_of_controllers)



