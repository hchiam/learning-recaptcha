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

Note that for proper usage on a real site you should also verify the reCAPTCHA response: https://developers.google.com/recaptcha/docs/verify#api-request

## to run the minimal example in this repo

```sh
yarn dev
```

or

```sh
npm start
```

(You won't be able to see reCAPTCHA on it though, since localhost:1234 isn't allowed. You'll have to see the live demo.)

```sh
# run yarn dev beforehand to generate the /dist folder with transpiled paths, etc.
yarn deploy
```

## live demo

This can show reCAPTCHA:

https://recaptcha-test.surge.sh/

https://recaptcha-test.surge.sh/demo2/

`your_site_key` can be public, and since I've specified the domain to be **recaptcha-test.surge.sh**, it won't work on other domains, like:

https://recaptcha-test-non.surge.sh/
