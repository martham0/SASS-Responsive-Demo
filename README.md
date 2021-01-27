# SASS-Responsive-Demo

### Description

This is a basic responsive frontend highlighting some of the key aspects of the CSS preprocessor SASS. </br>

Based on the tutorial by [DesignCourse](https://www.youtube.com/watch?v=roywYSEPSvc)</br>

In `./css/main.scss` you will find the main code for the project. </br>

### Key Points

1. **Variables**

   ```css
   //Creation
   $padding: 15px;
   $borders: 15px;

   //Use
   padding: $padding;
   ```

2. **Grouped Variables (objects)**

   ```css
   $colors: (
     primary: #005dff,
     primary-light: lighten(#005dff, 40%),
     primary-dark: darken(#005dff, 40%),
     accent: #fff6bb
   );
   ```

3. **Functions**
   </br>Create Function

   ```css
   //function below is cleaning up object variable call

   @function color($color-name) {
     // way to call key:value pairs from sass objects
     @return map-get($colors, $color-name);
   }
   ```

   </br>Use Function</br>

   ```css
   background-color: color(primary);
   ```

4. **Mixins**
   </br>Creat Mixin

   ```css
   //below is used to make basic @media query formate

   @mixin desktop {
     @media (min-width: #{$desktop}) {
       @content;
     }
   }
   ```

   </br>Use Mixin</br>

   ```css
   @include desktop {
     display: grid;
     grid-template-columns: 50% auto;
     grid-template-areas: "primary card";
   }
   ```

5. **Nested Structure**
   </br>It is possible to use nested structures in SASS to mimic the HTML structure. This helps with organization.

   ```css
   ul {
     list-style-type: none;
     margin: 0;
     padding: 0;

     li {
       margin-bottom: 10px;

       span {
         position: absolute;
         width: 30px;
         height: 30px;
         background-color: color(primary-light);
         border-radius: 50%;
         margin-right: 10px;
       }

       strong {
         display: inline-block;
         margin-left: max(40px);
         margin-top: 10px;
       }
     }
   }
   ```

6. **Math**
   </br> You can do math in SASS.

   ```css
   //Use Case

   padding: $padding * 4;
   ```
