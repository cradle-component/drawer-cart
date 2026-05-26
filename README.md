# drawer-cart
A drawer cart component for [CradleCMS](https://cradlecms.com) `eCommerce`.

<img width="auto" height="480" alt="Screenshot 2026-05-22 at 22 08 37" src="https://github.com/user-attachments/assets/0a1525b3-2c76-47a5-a9fd-3537f6407b9e" />
<img width="auto" height="480" alt="Screenshot 2026-05-26 at 07 26 33" src="https://github.com/user-attachments/assets/2abd5b1b-f9af-4ab6-bd5a-fd0fb9150783" />


It uses `alpinejs` templates, you can get alpinejs [here](https://github.com/alpinejs/alpine).

> Currency is formatted using the `cart` locale (language and country) `en-US` 

## installation
Put the `adrawer-cart.liquid` file into your theme `components` folder.

## example

In `layout/theme.liquid` include the component somewhere, like after the html `</body>` tag. 
```
</body>
{% component 'adrawer-cart' %}
</html>
```
You add a `cart-button` and place the markup for in inside the component, in the example below we're using an inlined svg image with a `quantity` badge on the top right corner. 

> We are using [tailwindcss](https://tailwindcss.com) here but it's not required for you to use. 

In your site header, where you want to have a cart `icon` add the following snippet.

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

### Customisation
You pass configuration using html attributes on the `<a-drawer-cart ...>` tag.

* `background` color, default `#fafafa`
* `color` text, default `#555` 
* `border` style, default `1px solid #ddd`
* `radius` border, default `3px`
* `thumb` image size in pixels, default `50x50`
* `width` of the cart, default `20rem`
* `height` of the cart, default `100vh`
* `offset` top of cart, default `0`
* `target` cart button, default `#cart-button`
* `button` class, default `btn btn-primary`
* `url` button action url, default `/checkout`

Add your cart button wrapped inside the component.
```
<a-drawer-cart width="20rem" background="#555" color="#fafafa" border="1px solid #888" thumb="64x64"  class="relative inline-block p-2 pl-0 group">
  <!- add what you want in here ->  
  <div id="cart-button"> ... </div>
 </a-drawer-cart>
```
