# Line ShareTargetPicker

Example static web file to use feature shareTargetPicker api (integrate with LIFF), Can be used in many places, such as Flex message, Rich menu.

![](https://github.com/angkarn/line-share-target-picker/blob/main/screenshot.gif)

## Features!

  - Customs share dynamic content from query url.
  - Use parameter in your content to replace with user data from LINE.
  - Compatible with both on LINE application and external browser.


## Usage

You just copy only index.html file and place to some static web host, such as [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

Create you content to share, such as flex message, see example in [exampleFlex.json](https://github.com/angkarn/line-share-target-picker/blob/main/exampleFlex.json).

*options*:  use [parameter](#content-parameter) for replace your content with data from line

 Put your content file or api to somewhere host, you can quick try on some free service like [mocki.io](https://mocki.io/fake-json-api) or [create file on github](https://docs.github.com/en/github/managing-files-in-a-repository/managing-files-on-github/creating-new-files) as well.
 
Create LIFF and enter full url of index.html is placed and along with [query params](#query-params) with value from the above steps to *Endpoint URL* setting.
e.g. *value in Endpoint URL*
```json
https://mysite.com/sharetarget/index.html?liffId=1234-abcd&content=https://mysite.com/flex.json
```
---
Try to enter LIFF url is created on Line App such as, *Text Message*, *Flex message*, *Rich menu* to view result. 👍

PS. You can split content query params on *Endpoint URL*  and place it after LIFF URL.
e.g.
```json
https://liff.line.me/1234-abcd?content=https://mysite.com/flex.json
```

## Demo
You can try with this resouce.

app url:
```json
https://tues.cc/line/shareTargetPicker
```
\
content url (it's flex with use parameter):
```json
https://tues.cc/line/shareTargetPicker/exampleFlex.json
```
\
or my result LIFF Url:
```json
https://liff.line.me/1654395981-1Enp60g8?content=https://tues.cc/line/shareTargetPicker/exampleFlex.json
```

## Query Params:

|Name|Require|Description|
|-|-|-|
| liffId | yes | LIFF ID e.g. `1234-abcd`. |
| content | yes | Url of json content file or api. |


## Options

### Content Parameter
use e.g. `{{parameterKey}}` place to somewhare on your content will replace by data from line.

|Key|Description|
|-|-|
| profile.`key`  | Can access all key and return follow [liff.getProfile()](https://developers.line.biz/en/reference/liff/#get-profile) `displayName` `pictureUrl` `statusMessage` `userId`, e.g. `{{profile.displayName}}`|
| shareThis | Return current LIFF url and all query params  e.g. `{{shareThis}}` |
