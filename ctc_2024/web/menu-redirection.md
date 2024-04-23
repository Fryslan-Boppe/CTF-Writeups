# menu-redirection

![image](https://github.com/Fryslan-Boppe/notes/assets/96194510/a4d8d38f-c2b1-4141-a11e-c8ec50fed4ab)

The initial step involves creating an account on the designated website. In the URL field, enter a URL from https://webhook.site to receive callbacks from the website.

![image](https://github.com/Fryslan-Boppe/notes/assets/96194510/6c75ffcb-a40d-440f-94dd-baf11a4e2895)

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

![image](https://github.com/Fryslan-Boppe/notes/assets/96194510/b73b20be-2b2b-433a-99e2-254787474afa)

Upon successfully ordering the cupcake, a POST request containing an image of the cupcake, which harbors the flag, will be received in the designated webhook.

![image](https://github.com/Fryslan-Boppe/notes/assets/96194510/b410215f-5374-459c-946c-d91e5e1fb238)

Flag:

![image](https://github.com/Fryslan-Boppe/notes/assets/96194510/3d36ddf0-2177-4b31-abbc-c62def3a7704)
