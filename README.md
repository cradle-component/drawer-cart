# drawer-cart

## installation
Put the `adrawer-cart.liquid` file into your theme `components` folder.

## usage

In `layout/theme.liquid` include the component after the html `body` and before `</html>`. 
```
{% component 'adrawer-cart' %}
```

Then in your site header, where you want to have a cart `icon` add the following snippet.

```
<a-drawer-cart width="20rem" background="#555" color="#fafafa" border="1px solid #888" thumb="64x64"  class="relative inline-block p-2 pl-0 group">
  <div id="cart-button">
    <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 group-hover:scale-110 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
    </svg>
    {% if cart.quantity > 0 %}
      <span class="absolute -top-2 -right-2 badge badge-primary badge-xs p-1">
      {{ cart.quantity }}
      </span>
    {% endif %}
  </div>
 </a-drawer-cart>
```

### You can pass in some customisation through attributes.

* `background` color
* `color` text 
* `border` style
* `thumb` image size in pixels
* `width` of the cart, default is `20rem`
* `height` of the cart, default is `100vh`
* `offset` top of cart
* `target` cart button, default is `#cart-buttom`
* `button` class, default is `btn btn-primary`
* `url` button url, default is `/checkout`

Also you are free to use own content inside the component tag.
```
<a-drawer-cart width="20rem" background="#555" color="#fafafa" border="1px solid #888" thumb="64x64"  class="relative inline-block p-2 pl-0 group">
  <div id="cart-button">
  <!- add whatever you want here -> 
  </div>
 </a-drawer-cart>
```

