# cs601_hw6_mgkramer

## Requirements
* Create a HTML Page with four images of your choice. For example, images of you or your pet at different ages
* Using Vue.js library, provide the following functionality
  * When you hover over the image it will change from a current image to a earlier one (example baby/teenage picture)
* Add any other feature or event that demonstrates your knowledge of Vue.js

### How I met the requirements
* I chose to feature two comic strips 
  * The Peanuts strip progresses with hovers as per the requirements
    * The initial image is chosen with Vue.js ```created()``` method
  * The Curtis strip demonstrates further knowledge of Vue by:
    * using ```v-show``` along with boolean ```data()``` instance variables to toggle 
    * I chose to use css grid to allow this slide show to progress along the screen
  * I further chose a css theme that reminds me of newspaper parchment
  
## Project setup
```
npm install
```

### How to Run 
* publically hosted [here](https://kramer-bu-vue-comic-strip.netlify.app/) OR:
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
