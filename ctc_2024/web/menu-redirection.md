# menu-redirection
This challenge involved using a webhook and general analysis of the webpage.

The first step was to create an account on the website with a unique webhook url on https://webhook.site.
![image](https://github.com/Fryslan-Boppe/notes/assets/96194510/6c75ffcb-a40d-440f-94dd-baf11a4e2895)

After you created an account you probably saw the following hint in the challenge description: "I always say that if it's on the menu, you should be able to order it." 

This indicated that a food item was not being displayed on the menu page. Upon inspecting the source you'll see that cupcake was the hidden item.

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
If we order a food item on the order page and intercept the POST request with Burp Suite we can change the value from pizza to cupcake.
![image](https://github.com/Fryslan-Boppe/notes/assets/96194510/b73b20be-2b2b-433a-99e2-254787474afa)

After we ordered the cupcake we will get a POST request in our webhook with an image of a cupcake that contains the flag.
![image](https://github.com/Fryslan-Boppe/notes/assets/96194510/b410215f-5374-459c-946c-d91e5e1fb238)

Flag:
![image](https://github.com/Fryslan-Boppe/notes/assets/96194510/3d36ddf0-2177-4b31-abbc-c62def3a7704)
