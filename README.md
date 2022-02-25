# CBEM with Selectors - Enhanced BEM Methodology #

## BEM ##
The Block, Element, Modifier (BEM) methodology is a popular naming convention for classes in HTML and CSS. Full Article
### Main problems with BEM ###
#### 1. Container ####
Some blocks and elements needs a parent container for styling, which is used outside of the block. It feels slightly wrong to call it something like .block__container and have it placed outside the .block block itself.
#### 2. Class everything ####
BEM dictates that you should add classes to each element in a component. 

## CBEM with Selectors ##
**CBEM with Selectors - Enhanced BEM Methodology** is not officialy created by the BEM author and is just a methodology that I'm using additionaly to BEM in order to make using CSS a bit easier.
CBEM with Selectors is an extension to the BEM Methodligy to avoid the main problems you get while using BEM. CBEM is using **Container**, **Block**, **Element** and **Modifier** as it's main structure. Container alows to add a Container around a block with a specific naming convention. 
### RS ###
To get less CSS code, we use RS (reusable, specific).
#### Reusable #####
Are Reusable HTML Elements can be reused within the project.
#### Specific ####
Speficic HTML Elements can be identified with it's class or id within the project.
### Selectors ###
In CSS, selectors are patterns used to select the element(s) you want to style. full article
#### Child ####
Child Block of a Block or Element. Using the Selector > to identify the child element. 
#### Multiclass ####
Using multiple classes to identifing  the Modifier regarding it's parents.

## Container ##
In order to use a container above a block or element we use a dash `-` r to make it clear that it relates to your block. This is used to name a parent HTML element of a Block or Element. Used to name Wrapper, Container, etc of a block.
**HTML** 
```
<div class="block-container">
   <div class="block-wrapper">
      <div class="block">
      </div>
   </div>
</div>
```
**CSS**
.block-container{
}
.block-wrapper{
}
## Block ##
Standalone entity that is meaningful on its own. 
### Reusable Block ###
Reusable Blocks can be reused within the project. 
### Specific Block ###
Specific Blocks are identified by its Class or ID.
### Specific Reusable Block ###
Specific Blocks Resusable Block is reusable and is identified by its Class or ID within the project. 
**HTML** 
```
<nav>
</nav>
<nav class="navigation">
</nav>
<nav id="navigation">
</nav>
```
**CSS**
```
//Reusable_Block
nav {
  
}
//Specific_Block
#navigation {
  
}
//Reusable_Specific_Block
.navigation {
  
}
```
## Elements ##
A part of a block that has no standalone meaning and is semantically tied to its block. Depending on whether you want to use it in relation to its parent, you can use the selector to create a relationship within the CSS.

**HTML** 
```
<div class="block">
   <span></span>
   <div class="block__element"></div> 
   <div class="block__element"></div>
</div>
```
** CSS **
```
//Reusable_Element_Selector
.block > span{
   
}
//Specific_Reusable_Element_Selector
.block > .block__element{
   
}
//Specific_Reusable_Element 
.block__element{

}
```
## Modifier ##
A flag on a block or element. Use it to change the appearance or behavior. Depending on whether you want to use it in relation to its parent, you can use the selector to create a relationship within the CSS.

### HTML ###
```
<div class="block">
   <div class="block__element modifier"></div>
   <div class="block__element modifier"></div>
</div>
```
### CSS ###
**Specific Reusable Modifier Selector**
Modifier is within the block__element and has a specific class name.
```
.block__element.modifier{

}
```
**Specific Reusable Modifier**
Modifier is can be anywhere and has a specific class name.
```
.modifier {

}
```
