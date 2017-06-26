/**
* @param {string} element 検索する要素を指定します
* @param {string} idToFind idを指定します
* @return {string} element 対象の要素を返します
*/ 

function getElementById(element, idToFind) {
  var descendants = element.getDescendants();
  for (var i in descendants) {
    var elem = descendants[i].asElement();
    if ( elem != null) {
      var id = elem.getAttribute('id');
      if ( id != null && id.getValue() == idToFind) return elem;
    }
  }
}


/**
* @param {string} element 検索する要素を指定します
* @param {string} classToFind クラス名を指定します
* @return {string} element 対象の要素を返します
*/ 

function getElementsByClassName(element, classToFind) {
  var data = [], descendants = element.getDescendants();
  descendants.push(element);
  for (var i in descendants) {
    var elem = descendants[i].asElement();
    if (elem != null) {
      var classes = elem.getAttribute('class');
      if (classes != null) {
        classes = classes.getValue();
        if (classes == classToFind) {
          data.push(elem);
        } else {
          classes = classes.split(' ');
          for (var j in classes) {
            if (classes[j] == classToFind) {
              data.push(elem);
              break;
            }
          }
        }
      }
    }
  }
  return data;
}

/**
* @param {string} element 検索する要素を指定します
* @param {string} tagName タグを指定します
* @return {string} element 対象の要素を返します
*/ 

function getElementsByTagName(element, tagName) {
  var data = [], descendants = element.getDescendants();
  for(var i in descendants) {
    var elem = descendants[i].asElement();
    if ( elem != null && elem.getName() == tagName) data.push(elem);
  }
  return data;
}


/**
以下テストコードです。
*/ 

var testData = 
          '<doc>'
        + '  <title id="doc-title">Anime Japan Expo</title>'
        + '  <chapter class="chapter">'
        + '    <paragraph class="paragraph">Do you like Anime?</paragraph>'
        + '  </chapter>'
        + '</doc>';

function testParseXMLById_() {
  var doc  = XmlService.parse(testData),
      xml   = doc.getRootElement(),
      title = getElementById(xml, 'doc-title');
      if (title === "Anime Japan Expo"){
          Logger.log("getById is OK");
      }else{
          Logger.log("getById is BAD");
      }
}

function testParseByClassName_() {
  var doc  = XmlService.parse(testData),
      xml   = doc.getRootElement(),
      paragraph = getElementsByClassName(xml, 'paragraph');
      paragraph = paragraph[0].getValue();
      if (paragraph === "Do you like Anime?"){
          Logger.log("getByClassName is OK");
      }else{
          Logger.log("getByClassName is BAD");
      }
  
}

function testParseXMLByTagName_() {
  var doc = XmlService.parse(testData),
      xml   = doc.getRootElement(),
      title = getElementsByTagName(xml, 'title');
      title = title[0].getValue();
      if (title === "Anime Japan Expo"){
          Logger.log("getById is OK");
      }else{
          Logger.log("getById is BAD");
      }
}
