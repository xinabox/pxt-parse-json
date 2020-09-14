
## pxt-parse-json

Use this makecode extension to parse upto two level nested json structures, very easy to use.

### Blocks

**load_json**

Use this block to load json file or string to be parsed

**getLevelOneValue("uid", "key")**

Use this block to search in level one the value with mentioned uid and key. If the the mentioned uid and/or key is not found in level one the program will not move to next block.

**getLevelTwoValue("uid", "key")**

Use this block to search in level two the value with mentioned uid and key. If the the mentioned uid and/or key is not found in level two the program will not move to next block.

### Example usage

**NOTE:**

Although json structure with spaces and line feed would work, it is recommended to avoid spaces and line feeds instead, use unformatted json to avoid unexpected results.

**Simple json**

```
{
   "0001":{
      "name":"temperature",
      "type":"sensor"
   }
}
```



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
