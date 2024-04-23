# menu-redirection

![image](./menu-redirection1.jpg)

The initial step involves creating an account on the designated website. In the URL field, enter a URL from https://webhook.site to receive callbacks from the website.

![image](./menu-redirection2.jpg)

Following the account setup, users gain the ability to order various food items. Upon placing an order for a food item, a POST request is sent to your specified webhook.

The challenge description hints at the presence of a concealed food item on the menu. Upon inspecting the source code of the menu page, it becomes apparent that "cupcake" is the hidden item.
```html
</section>
  <section class="hero mb-6">
    <div class="hero-body">
      <div class="columns">
        <div class="column is-one-third">
          <figure class="image is-square">
            <img src="/menu/cupcake.webp"/>
          </figure>
        </div>
        <div class="column ml-6">
          <p class="title is-size-1">Cupcake</p>
          <p class="is-size-2">Heerlijke cupcakes met niet te versmaden cyber sprinkles, opgetopt met een prachtig vlaggetje.</p>
        </div>
    </div>
```
Now aware of this hidden item, users can navigate to the order page and intercept the POST request using tools like Burp Suite. This allows for the modification of the item value from "pizza" to "cupcake".

![image](./menu-redirection3)

Upon successfully ordering the cupcake, a POST request containing an image of the cupcake, which harbors the flag, will be received in the designated webhook.

![image](./menu-redirection4)

Flag:

![image](./menu-redirection5)
