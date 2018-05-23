# taq.website
🎉🎈🎂🍾🎊🍻💃

*General purpose README ➡️ RevealJS presentation viewer*

## Motivation

This project allows for setting up a simple (ie, easy to remember/spell) domain name to a flexible, general purpose webpage typically to be used as a landing page. For now, the actual domain redirect portion kinda sucks, on an apache server somewhere, I have this:

```php
<?php

print(file_get_contents("https://mottaquikarim.github.io/WEBSITE2"));
```

Which loads the root level `index.html` that immediately redirects to `presentation_latest`. This could and will be improved in the future, in particular:

1. Implementation of Domain Masking to avoid having to rely on PHP / code for redirect
2. Removal of the root level index.html redirect *OR* implementation of a better way to maintain multiple content versions for the landing page itself.

## App

The `stage` dir implements a simple webpage that will pull down a README file from any directory on this repo starting with `presentation_`. It parses the README file and injects into a RevealJS instantiation, rendering slides.

Ideally, user can swap README content in `presentation_latest` and have that seamless show up **[here](https://mottaquikarim.github.io/WEBSITE2/stage/index.html?p=latest#/)**.

To generate README content, consider using **[rehearsal](https://mottaquikarim.github.io//public/index.html)**
