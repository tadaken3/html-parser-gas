# HTML/XML parser for Google Apps Script

parser is HTML/XML parser for Google Apps Script.

## Install

Script ID: 1Jrnqmfa6dNvBTzIgTeilzdo6zk0aUUhcXwLlQEbtkhaRR-fi5eAf4tBJ

## Example
```javascript
var src = '<doc>'
        + '  <title id="doc-title">Anime Japan Expo</title>'
        + '  <chapter class="chapter">'
        + '    <paragraph class="paragraph">Do you like Anime?</paragraph>'
        + '  </chapter>'
        + '</doc>';

function parseXML() {
  var doc   = XmlService.parse(src),
      xml   = doc.getRootElement(),
      title = parser.getElementById(xml, 'doc-title');
  Logger.log(title.getValue());
}


function parseXMLByClassName() {
  var doc   = XmlService.parse(src),
      xml   = doc.getRootElement(),
      paragraph = parser.getElementsByClassName(xml, 'paragraph');
  Logger.log(paragraph[0].getValue());
}

function parseXMLByTagName() {
  
  var doc   = XmlService.parse(src),
      xml   = doc.getRootElement(),
      title = parser.getElementsByTagName(xml, 'title');
  Logger.log(title[0].getValue());
}
```

## Contribution

1. Fork ([https://github.com/tadaken3/html-parser-gas](https://github.com/tadaken3/html-parser-gas))
2. Create a feature branch
3. Commit your changes
4. Rebase your local changes against the master branch
5. Create new Pull Request

## Licence

[MIT](https://github.com/taddaken3/html-parser-gas/blob/master/LICENCE)

## Author

[tadaken3](https://github.com/tadaken3)
