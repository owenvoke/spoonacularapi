# spoonacularapi

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Software License][ico-license]](LICENSE)
[![Build Status][ico-travis]][link-travis]
[![Style CI][ico-styleci]][link-styleci]
[![Code Coverage][ico-code-quality]][link-code-quality]
[![Total Downloads][ico-downloads]][link-downloads]

The spoonacular Nutrition, Recipe, and Food API allows you to access over 360,000 recipes and 80,000 food products.

## Install

Via Composer

``` bash
$ composer require pxgamer/spoonacularapi
```

## Usage

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

#### Get singleton instance

The singleton instance of the ``` APIController ``` class can be accessed from the API Client.

```php
$client = $client->getClient();
```

#### getProductInformation

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


#### findSimilarRecipes

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


#### getAutocompleteIngredientSearch

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


#### createVisualizePriceBreakdown

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


#### createVisualizeNutrition

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


#### createVisualizeIngredients

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


#### getSummarizeRecipe

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


#### searchGroceryProducts

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


#### getQuickAnswer

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


#### getRecipeInformation

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


#### createParseIngredients

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


#### createMapIngredients

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


#### getExtractRecipeFromWebsite

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


#### getComputeDailyMealPlan

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


#### createClassifyGroceryProductsBatch

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


#### createClassifyCuisine

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


#### createClassifyAGroceryProduct

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


#### searchRecipes

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


#### findByNutrients

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


#### findByIngredients

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


#### createRecipeCard

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

## Change log

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Testing

``` bash
$ composer test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) and [CODE_OF_CONDUCT](CODE_OF_CONDUCT.md) for details.

## Security

If you discover any security related issues, please email owzie123@gmail.com instead of using the issue tracker.

## Credits

- [pxgamer][link-author]
- [apimatic][link-original-author]
- [All Contributors][link-contributors]

## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.

[ico-version]: https://img.shields.io/packagist/v/pxgamer/spoonacularapi.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[ico-travis]: https://img.shields.io/travis/pxgamer/spoonacularapi/master.svg?style=flat-square
[ico-styleci]: https://styleci.io/repos/111661083/shield
[ico-code-quality]: https://img.shields.io/codecov/c/github/pxgamer/spoonacularapi.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/pxgamer/spoonacularapi.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/pxgamer/spoonacularapi
[link-travis]: https://travis-ci.org/pxgamer/spoonacularapi
[link-styleci]: https://styleci.io/repos/111661083
[link-code-quality]: https://codecov.io/gh/pxgamer/spoonacularapi
[link-downloads]: https://packagist.org/packages/pxgamer/spoonacularapi
[link-author]: https://github.com/pxgamer
[link-original-author]: https://github.com/apimatic
[link-contributors]: ../../contributors
