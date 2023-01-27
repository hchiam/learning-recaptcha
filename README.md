# Learning Google reCAPTCHA

Just one of the things I'm learning. https://github.com/hchiam/learning

Register a new site and get `your_site_key` at https://www.google.com/recaptcha/admin/create/

Then view stats or edit settings at https://www.google.com/recaptcha/admin/

I think I personally prefer "Invisible" until-needed reCAPTCHA v2 auto-bind setup:
https://developers.google.com/recaptcha/docs/invisible#auto_render

```html
<html>
  <head>
    <title>reCAPTCHA demo: Simple page</title>
    <script src="https://www.google.com/recaptcha/api.js" async defer></script>
    <script>
      function onSubmit(token) {
        document.getElementById("demo-form").submit();
      }
    </script>
  </head>
  <body>
    <form id="demo-form" action="?" method="POST">
      <button
        class="g-recaptcha"
        data-sitekey="your_site_key"
        data-callback="onSubmit"
      >
        Submit
      </button>
      <br />
    </form>
  </body>
</html>
```

## to run the minimal example in this repo

```sh
yarn dev
```

or

```sh
npm start
```

## live demo

This can show reCAPTCHA:

https://recaptcha-test.surge.sh/

`your_site_key` can be public, and since I've specified the domain to be **recaptcha-test.surge.sh**, it won't work on other domains, like:

https://recaptcha-test-non.surge.sh/
