# NativeScript-Vue Star Rating  
  
A plugin which provides a 1 to 5 Star Rating component to display and rate.  
  
## Features  
  
* Customizable stars by size, fill color and empty color.  
* CSS only UI, no images used.  
* Tap a star to rate from 1 to 5.  
  
## Screenshots  
  
![Screenshot 1](https://raw.githubusercontent.com/panietoar/nativescript-vue-star-rating/master/docs/screenshot-1.png)  
  
## Installation  
  
```bash  
npm i --save nativescript-vue-star-rating```  
  
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

I found that in {NS}6+ the size attribute either doesn't work or it deforms the stars.
Therefore a solution is to use:

```xml
<StarRating :value="rating" scaleX="0.8" scaleY="0.8" />

```   

## Properties  
  
| Prop             | Type            | Description                                        | Default Value  |  
|:----------------:|:---------------:| -------------------------------------------------- | -------------- |  
| **value** | Number          | The rating value                                   |  1             |  
| **size** | String, Number  | Size in DIP* of width and height of the star     | 75             |  
| **fillColor** | String          | CSS color for the filled stars                     | <span style="color:#FFEB0A">'#FFEB0A'</span>      |  
| **emptyColor** | String          | CSS color for the empty stars                      | <span style="color:#ABABAB">'#ABABAB'</span>      |  
| **outlineColor** | String          | CSS color for the star outline                     | <span style="color:#000">'#000'</span>            |  
* DIP - device independent pixels  
## Events  
  
| Event              | Returns | Description                                    |  
|:------------------:|:-------:|:----------------------------------------------:|  
| **ratingSelected** | Number  | Returns the rating selected by tap from 1 to 5 |  
  
If you want to use the component as display only, just don't add an event listener for this event.  
  
## Caveats  
Star outline is a work in progress, you can customize the color but the outline width is still missing.
