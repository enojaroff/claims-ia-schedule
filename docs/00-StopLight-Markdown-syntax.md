# StopLight Markdown Syntax extensions


## Format des blockquotes

<!-- theme: info -->

> #### ddsfdsfs
>
> fdsfdsfds

<!-- theme: success -->

> #### ddsfdsfs
>
> fdsfdsfds

<!-- theme: warning -->

> #### ddsfdsfs
>
> fdsfdsfds

<!-- theme: danger -->

> #### ddsfdsfs
>
> fdsfdsfds


## Ligne horizontale

* * *


## Présentation du JSON

### Format source

```json
{
    "title": "User",
    "type": "object",
    "properties": {
        "id": {
            "type": "string"
        },
        "name": {
            "type": "string",
            "description": "The user's full name."
        },
        "age": {
            "type": "number",
            "minimum": 0,
            "maximum": 150
        }
    },
    "required": [
        "id",
        "name"
    ]
}
```

### Format spécifique pour un schéma JSON

```json json_schema
{
    "title": "User",
    "type": "object",
    "properties": {
        "id": {
            "type": "string"
        },
        "name": {
            "type": "string",
            "description": "The user's full name."
        },
        "age": {
            "type": "number",
            "minimum": 0,
            "maximum": 150
        }
    },
    "required": [
        "id",
        "name"
    ]
}
```

* * *

## Onglets

<!--
type: tab
title: Format source
-->

```json
{
    "title": "User",
    "type": "object",
    "properties": {
        "id": {
            "type": "string"
        },
        "name": {
            "type": "string",
            "description": "The user's full name."
        },
        "age": {
            "type": "number",
            "minimum": 0,
            "maximum": 150
        }
    },
    "required": [
        "id",
        "name"
    ]
}
```

<!--
type: tab
title: Format JSON schema
-->

```json json_schema
{
    "title": "User",
    "type": "object",
    "properties": {
        "id": {
            "type": "string"
        },
        "name": {
            "type": "string",
            "description": "The user's full name."
        },
        "age": {
            "type": "number",
            "minimum": 0,
            "maximum": 150
        }
    },
    "required": [
        "id",
        "name"
    ]
}
```

<!-- type: tab-end -->

* * *

## Présentation du code

<!--
title: "My code snippet"
lineNumbers: true
-->

```javascript
// Javascript Sample
function fibonacci(num){
  var a = 1, b = 0, temp;

  while (num >= 0){
    temp = a;
    a = a + b;
    b = temp;
    num--;
  }

  return b;
}
```

<!--
title: "My PHP code snippet"
lineNumbers: true
-->

```php
// PHP Sample
class toto {
  var $i, $j;

  function fibonacci(num) {
    var $a = 1, $b = 0, $temp;

    while ($num >= 0) {
      $temp = $a;
      $a = $a + $b;
      $b = $temp;
      $num--;
    }

    return $b;
  }
}
```

* * *

## Tableaux

<!-- title: Titre de tableau -->

| Tables        |      Are      |   Cool |
| :------------ | :-----------: | -----: |
| col 3 is      | right-aligned | 1600 € |
| col 2 is      |    centered   |   12 € |
| zebra stripes |    are neat   |    1 € |

* * *

## Liste de tâches

- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

