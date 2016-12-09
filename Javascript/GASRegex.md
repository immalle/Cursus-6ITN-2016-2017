# RegEx in GAS

Uit te proberen in Google Apps Scripting

```
function regexMetGroupings() {
  var regex = /(\w+)\/(\w+)/;

  var str = SpreadsheetApp.getActiveSheet().getActiveCell().getValue();

  Browser.msgBox(str);

  var result = regex.exec(str); // is een array owv groupings

  var totaal = result[0];
  var woordVoorDeSlash = result[1];
  var woordNaDeSlash = result[2];

  Browser.msgBox(woordVoorDeSlash + " ---- " + woordNaDeSlash);
}
```

