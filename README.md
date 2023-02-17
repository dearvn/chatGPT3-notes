# chatGPT3-notes
Some notes about coding chatGPT3


# seperate content of chatGPT3 in PHP

```
$text = '';// content from response of chatGPT3
$complete = trim($text);
$str = preg_replace('/\n$/', '', preg_replace('/^\n/', '', preg_replace('/[\r\n]+/', "\n", $text)));
$options = preg_split("/\r\n|\n|\r/", $str);
// delete 1. 2. 3. etc from beginning of the line
$options = preg_replace('/^\\d+\\.\\s/', '', $options);
// delete if there is a dot at the end of the line
$options = preg_replace('/\\.$/', '', $options);
```

