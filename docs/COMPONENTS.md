<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

# Cart

**Extends React.PureComponent**

Component which represents shopping cart.

**Meta**

-   **author**: Oleg Nosov &lt;olegnosov1@gmail.com>
-   **license**: MIT

## propTypes

**Properties**

-   `showHeader` **[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** Show or hide header 'Shopping cart'.
    Default is true
-   `iconTrashClassName` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** ClassName for
    trash icon on remove button.
    Default is 'icon-trash'
-   `cartTransition` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Cart's config for Transition.
    Default is
     {
       style: animate(500),
       enteringClassName: 'fadeInUp',
       exitingClassName: 'fadeOut',
       exitedClassName: 'invisible',
       timeout: 500,
     }.
    Look at src/components/Cart/Cart.js for details.
-   `cartItemTransition` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Cart item's config
    for ReactCSSTransitionGroup.
    Default is
      {
        transitionName: {
          enter: 'bounceInLeft',
          leave: 'bounceOutRight',
        },
        transitionEnterTimeout: 500,
        transitionLeaveTimeout: 500,
      }.
    Look at src/components/Cart/Cart.js for details.
-   `linkComponent` **[Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)** React Component(stateful or not,
    as you wish), which represents a Link. It will receive props:
    to="%your product's page%".
    I'd recommend you to take a look at react-router's Link.
    Wrapped <a/> by default.

## containerPropTypes

**Properties**

-   `products` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)&lt;[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), ProductType>** Products map. Required.
-   `currency` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Current currency. Required.
-   `isCartEmpty` **[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** Display cart or not. Required.
-   `checkoutButton` **ReactElement** Button in the bottom of cart.
    Required.
-   `onUpdateProduct` **onUpdateProductType** Callback
    function which will be called when product should be updated.
    First arg is product's key in products, second - props to update.
    For instance, it may be called like:
    onUpdateProduct('macbook-case/\_red', { quantity : 50 });
    Required.
-   `onRemoveProduct` **onRemoveProductType** Callback to call
    when need to remove product from products.
    Accept product's key in products.
    For example: onRemoveProduct('/shop/macbook-case/\_red');
    Required.
-   `getLocalization` **getLocalizationType** Required.

# Product

**Extends React.PureComponent**

React component - Product form with price.

**Meta**

-   **author**: Oleg Nosov &lt;olegnosov1@gmail.com>
-   **license**: MIT

## propTypes

**Properties**

-   `name` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Name to display. Required.
-   `id` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Product's id. Required.
-   `path` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Path to product. Required.
-   `prices` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)&lt;[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)>** Prices (currency-value). Required.
-   `imagePath` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Path to main image. Required.
-   `currency` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Price currency. Required.
-   `properties` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)&lt;[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;(ProductPropertyOptionType)>>** Custom product properties. May be array of number, string or
    shape({ additionalCost(optional), onSelect(optional), value(required)})
    Default is {}.
-   `propertiesToShowInCart` **[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)>** Array of propery names to
    display in cart. Default is \[].
-   `scrollAnimationConfig` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Config for animateScroll
    (from react-scroll) scrollTo function.
    Default is
     {
       duration: 750,
       delay: 0,
       smooth: true,
     }.
-   `iconAddProductClassName` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** ClassName for cart icon
    on add to button.
    Default is 'icon-cart-plus'.
-   `afterPriceNode` **ReactNode** Node to display after price element.
    Optional.
-   `descriptionNode` **ReactNode** Node to display before price element.
    Optional.

## containerPropTypes

**Properties**

-   `CheckoutButton` **ReactElement** Button in the bottom of product.
    Required.
-   `onAddProduct` **onAddProductType** Callback to call when
    user wants to add product in his cart.
    Example:
    onAddProduct(
      'macbook-case',
      {
        quantity: 30,
        properties: { colour: 'red' },
        productInfo: {
          prices: {
           GBP: 70
          },
         ...etc
        },
      },
      'GBP'
    );
    Required.
-   `getLocalization` **getLocalizationType** Required.
-   `generateProductKey` **generateProductKeyType** Function which generates
    product's key based on id and properties. Example:
    generateProductKey('macbook-case', { colour: 'red' } ).

# CheckoutButton

**Extends React.PureComponent**

Checkout button with grand total.

**Meta**

-   **author**: Oleg Nosov &lt;olegnosov1@gmail.com>
-   **license**: MIT

## propTypes

**Properties**

-   `checkoutURL` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Link to checkout page.
    Required.
-   `iconCheckoutClassName` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** ClassName
    for cart icon on checkout button.
    Default is 'icon-basket'.
-   `transitionConfig` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** CheckoutButton's transition config
    for react-overlays Transition.
    Default is {
      style: animate(500),
      enteringClassName: 'fadeInUp',
      exitingClassName: 'fadeOut',
      timeout: 500,
      unmountOnExit: true,
    }.
-   `linkComponent` **[Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)** React Component(stateful or not,
    as you wish), which represents a Link. It will receive props:
    role="button",
    to="%your checkout%",
    className-"%bs4's className for button%".
    I'd recommend you to take a look at react-router's Link.
    Wrapped <a/> by default.

## containerPropTypes

**Properties**

-   `grandTotal` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Amount of money to pay. Required.
-   `hidden` **[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** Show or hide button. Required.
-   `currency` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Current cart currency. Required.
-   `getLocalization` **getLocalizationType** Required.