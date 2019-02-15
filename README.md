# Slide Menu with burger

A simple, lightweight, animated burger icon with only CSS. 

Tested in IE11, Firefox 64, Edge 44 and Chrome 71.

[View in CodePen](https://codepen.io/kevinmouzet/pen/zemmXJ)

## HTML

 
          <div class="burgerIcon" id="burgerButton">
            <span></span>
          </div>
        

## CSS


    /* animated burger icon */
    :root {
      --burger_background_color: transparent;
      --burger_color: #000000;
    }
    
    .burgerIcon {
      min-width: 60px;
      min-height: 60px;
      display: block;
      background-color: var(--burger_background_color);
      border-radius: 50%;
      position: relative;
      transition: transform 0.5s;
      cursor: pointer;
    }
    
    .burgerIcon span {
      display: block;
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translateX(-50%) translateY(-50%);
      height: 4px;
      border-radius: 10%;
      width: 40px;
      background-color: var(--burger_color);
      transition: background-color 0.5s;
    }
    
    .burgerIcon span::before {
      width: 40px;
      height: 4px;
      border-radius: 10%;
      content: "";
      display: block;
      position: absolute;
      background-color: var(--burger_color);
      transform: translateY(-10px);
      transition: transform 0.5s;
      transform-origin: 50% 50%;
    }
    
    .burgerIcon span::after {
      width: 40px;
      height: 4px;
      border-radius: 10%;
      content: "";
      display: block;
      position: absolute;
      background-color: var(--burger_color);
      transform: translateY(10px);
      transition: transform 0.5s;
      transform-origin: 50% 50%;
    }
    
    .burgerIcon:hover span::before {
      transform: translateY(-13px);
    }
    
    .burgerIcon:hover span::after {
      transform: translateY(13px);
    }
    
    .burgerIcon.open span {
      background: transparent;
    }
    
    .burgerIcon.open span::before {
      transform: rotate(45deg);
    }
    
    .burgerIcon.open span::after {
      transform: rotate(-45deg);
    }
    
    .burgerIcon.open {
      transform: rotate(180deg);
    }

## JavaScript

    // burger icon
    
      
    
    (function () {
    
    const  burgerButton  =  document.getElementById("burgerButton");
    
     
    burgerButton.addEventListener("click", function () {
    
    burgerButton.classList.toggle("open");
    
    })
    
    })();
