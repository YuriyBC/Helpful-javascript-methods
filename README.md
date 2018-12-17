Helphul Javascript Methods
===============

**1. Local Storage Decorator:**
```
function storage (...args) {
   if (args.length === 1) {
       return window.localStorage.getItem(args[0])
   } else if (args.length === 2) {
       return window.localStorage.setItem(args[0], args[1])
   }
}
```
**2. Calculate next id of array:**
```
function calculateNextId (arr) {
    let idCollection = arr.map((el) => el.id);
    let id = 0;

    for (let i = 0; i < arr.length; i++) {
        if (idCollection.indexOf(id) === -1) {
            return id;
        }
        id++
    }
    return id
}
```
**3. Check for IE browser:**
```
function isIeBrowser () {
  return /MSIE (\d+\.\d+);/.test(navigator.userAgent) || navigator.userAgent.indexOf("Trident/") > -1
}
```

Sass functions (not js, but anyway)
===============

**1. Adaptive size:**
```
$browserContext: 16;
$baseWidth: 1000;
$baseHeight: 547;

@function em($pixels, $context: $browserContext) {
  @return #{$pixels/$context}em;
}

@function vh($target) {
  $vh-context: ($baseHeight*.01);
  @return #{$target/$vh-context}vh;
}

@function vw($target) {
  $vw-context: ($baseWidth*.01);
  @return #{$target/$vw-context}vw;
}
