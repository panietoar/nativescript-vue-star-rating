# NativeScript-Vue Star Rating

A plugin which provides a 1 to 5 Star Rating component to display and rate.

Features:

* Customizable stars by size, fill color and empty color.
* CSS only UI, no images used.
* Tap a star to rate from 1 to 5.

## Installation

```bash
npm i --save nativescript-vue-star-rating
```

```js
// main.js
import Vue from 'nativescript-vue';
...
import StarRating from 'nativescript-vue-star-rating';
Vue.use(StarRating);
```

Use in template:

```xml
...
<StarRating :value="rating" size="90" />
...
```

## Props

| Prop             | Type            | Description                                        | Default Value  |
|:----------------:|:---------------:| -------------------------------------------------- | -------------- |
| **value**        | Number          | The rating value  | true                           |  1             |
| **size**         | String, Number  | Size in pixels of width and height of the star     | 75             |
| **fillColor**    | String          | CSS color for the filled stars                     | <span style="color:#FFEB0A">'#FFEB0A'</span>      |
| **emptyColor**   | String          | CSS color for the empty stars                      | <span style="color:#ABABAB">'#ABABAB'</span>      |

## Events

| Event              | Returns | Description                                    |
|:------------------:|:-------:|:----------------------------------------------:|
| **ratingSelected** | Number  | Returns the rating selected by tap from 1 to 5 |

If you want to use the component as display only, just don't add an event listener for this event.

## Caveats
Since clip-path is used to draw the stars, there is no current way for the stars to have borders. So have in mind the background color before setting up the stars colors.