# Styleplate : Semantic SCSS Grid
A super flexible, simple, and 'semantic' SASS-based grid system.  This SCSS partial can be used stand alone or part of the Styleplate build system. 

# How to use: #
1.  Edit variables to match design  
2.  Add the grid-container mixin to parent element(s)  
3.  Start adding the span(n) mixin to your individual grid elements  
4.  Add the span(n) mixin to your media queries for a responsive grid flow  
5.  Be happy with your clean semantic HTML!!!

#sample usage:#
**Variables:**  
Use the `$number_of_columns` variable to choose how your grid will work for your design.  i.e., a percentage based grid would have 100 columns, 12 column would be "12", etc. 
<pre>
    $number_of_columns: 100;  
    $max_width: 1140px;   
    $spacing_unit: px;  
    $horizontal_spacing: 20;  
    $vertical_spacing: 0;
</pre>  
  
**SCSS:**
<pre>
   .parent {
    @include grid_container;
   }
   
   .child1 {
     @include span(25);
     
     @media screen and (max-with:767px) { // mobile
       @include span(50);
     }
   }
   
   .child2 {
     @include span(75);
     
     @media screen and (max-with:767px) { // mobile
       @include span(100);
     }
   }
</pre>
  
**HTML usage:**  
<pre>
  &lt;div class=&quot;parent&quot;&gt;
    &lt;div class=&quot;child1&quot;&gt;Foo&lt;/div&gt;
    &lt;div class=&quot;child2&quot;&gt;Bar&lt;/div&gt;
  &lt;/div&gt;
</pre>  
  
**CSS Output:**  
<pre>
*, *:before, *:after {
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

.parent {
  padding-left: 10px;
  padding-right: 10px;
  padding-top: 5px;
  padding-bottom: 5px;
  margin-left: auto;
  margin-right: auto;
  max-width: 960px;
}

.parent::after {
  content: "";
  display: table;
  clear: both;
}

.child1 {
  padding-left: 10px;
  padding-right: 10px;
  padding-top: 5px;
  padding-bottom: 5px;
  float: left;
  width: 25%;
}

@media screen and (max-with: 767px) {
  .child1 {
    padding-left: 10px;
    padding-right: 10px;
    padding-top: 5px;
    padding-bottom: 5px;
    float: left;
    width: 50%;
  }
}

.child2 {
  padding-left: 10px;
  padding-right: 10px;
  padding-top: 5px;
  padding-bottom: 5px;
  float: left;
  width: 75%;
}

@media screen and (max-with: 767px) {
  .child2 {
    padding-left: 10px;
    padding-right: 10px;
    padding-top: 5px;
    padding-bottom: 5px;
    float: left;
    width: 100%;
  }
}
</pre>
  


 
 
   
