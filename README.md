
## pxt-parse-json

Use this makecode extension to parse upto two level nested json structures, very easy to use.

### Blocks

**load_json**

![load json block](https://github.com/xinabox/pxt-parse-json/raw/master/.github/makecode/load_json.png)

Use this block to load json file or string to be parsed

**getLevelOneValue("uid", "key")**

![level one value](https://github.com/xinabox/pxt-parse-json/raw/master/.github/makecode/level_one.png)

Use this block to search in level one the value with mentioned uid and key. If the the mentioned uid and/or key is not found in level one the program will not move to next block.

**getLevelTwoValue("uid", "key")**

![level two value](https://github.com/xinabox/pxt-parse-json/raw/master/.github/makecode/level_two.png)

Use this block to search in level two the value with mentioned uid and key. If the the mentioned uid and/or key is not found in level two the program will not move to next block.

### Example usage

**NOTE:**

Although json structure with spaces and line feed would work, it is recommended to avoid spaces and line feeds. Instead, use unformatted json to avoid unexpected results.

**Simple json**

```
{
   "0001":{
      "name":"temperature",
      "type":"sensor"
   }
}
```

![Simple json](https://github.com/xinabox/pxt-parse-json/raw/master/.github/makecode/example1.png)

The micro:bit screen will display **temperature** on screen



**Nested json**

```
{
   "0001":{
      "name":"temperature",
      "type":"sensor",
      "0012":{
         "scale":"celsius",
         "value":"37"
      },
      "0013":{
         "scale":"fahrenheit",
         "value":"98"
      }
   },
   "0002":{
      "name":"light",
      "type":"actuator",
      "0022":{
         "scale":"lux",
         "value":"50"
      }
   }
}
```

![Nested json](https://github.com/xinabox/pxt-parse-json/raw/master/.github/makecode/example2.png)

The micro:bit screen will display **light**, **50** and **lux** on screen

### Guide on json structure

The json strucure should be symmetric, means the key names used in same level jsons should be same, so for example, this will not work:

```diff
{
   "0001":{
      "name":"temperature",
      "type":"sensor",
-"description":"weather sensing"
      "0012":{
         "scale":"celsius",
         "value":"37"
      },
      "0013":{
         "scale":"fahrenheit",
         "value":"98"
      }
   },
   "0002":{
      "name":"light",
      "type":"actuator",
      "0022":{
         "scale":"lux",
         "value":"50"
      }
   }
}
```


and this will also not work:


```diff
{
   "0001":{
      "name":"temperature",
      "type":"sensor",
      "0012":{
         "scale":"celsius",
         "value":"37",
-"maximum":"1000"
      },
      "0013":{
         "scale":"fahrenheit",
         "value":"98"
      }
   },
   "0002":{
      "name":"light",
      "type":"actuator",
      "0022":{
         "scale":"lux",
         "value":"50"
      }
   }
}
```


But, this will work:

```diff
{
   "0001":{
      "name":"temperature",
      "type":"sensor",
+"description":"weather sensing"
      "0012":{
         "scale":"celsius",
         "value":"37"
      },
      "0013":{
         "scale":"fahrenheit",
         "value":"98"
      }
   },
   "0002":{
      "name":"light",
      "type":"actuator",
+"description":"light sensing"
      "0022":{
         "scale":"lux",
         "value":"50"
      }
   }
}
```

and so will this:

```diff
{
   "0001":{
      "name":"temperature",
      "type":"sensor",
      "0012":{
         "scale":"celsius",
         "value":"37",
+"maximum":"1000"
      },
      "0013":{
         "scale":"fahrenheit",
         "value":"98",
+"maximum":"10000"
      }
   },
   "0002":{
      "name":"light",
      "type":"actuator",
      "0022":{
         "scale":"lux",
         "value":"50",
+"maximum":"3000"
      }
   }
}
```
