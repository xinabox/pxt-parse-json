
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
