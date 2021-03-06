# TwZipcode
1. 將中華郵政（www.post.gov.tw）的**「臺灣地區郵遞區號前3碼一覽表 103/12(Excel版)」**轉成各種格式，方便軟體開發時可直接引用。
2. 英文譯名來自於地名資訊服務網（gn.moi.gov.tw）的**「臺灣地區鄉鎮市區級以上行政區域名稱中英對照表.pdf」**。

### Bower
```sh
bower install twzipcode-data
```

### 資料結構
| 參數    | 說明           |
|---------|----------------|
| zipcode | 3碼郵遞區號    |
| county  | 縣、市或直轄市 |
| city    | 鄉鎮市區       |

### 資料說明

#### twzipcode-data.json
```javascript
{

    /**
    *  縣市列表  
    */
    "counties" : [
        "臺北市", 
        ...
    ],
    
    /**
    *  清單
    */
    "list" : [
            {"zipcode" : 100, "county" : "臺北市", "city" : "中正區" },
            ...
    ],

    /**
    *  依縣、市或直轄市分類
    */
    "groupByCounty" : {
        "臺北市": [
            {"zipcode" : 100, "county" : "臺北市", "city" : "中正區" },
            ...
         ],
         "基隆市": [
         	{"zipcode" : 200, "county" : "基隆市", "city" : "仁愛區" },
            ...
         ],
         ...
    },
    
    /**
    *  依郵遞區號作為key
    */
    "mapByZipcode" : {
        "100" : {"zipcode" : 100, "county" : "臺北市", "city" : "中正區" },
        ...
    }
};
        
```
> 以UNICODE編碼，看[預覽](http://yyc1217.github.io/twzipcode-data/twzipcode-data.js.demo.html)

#### twzipcode-data.js
```html
<!-- 可以用<script>引入，用twzipcode變數取得 -->
<script src="twzipcode-data.js"></script>
```

```javascript
/**
* 資料存在window.twzipcode
*/
var twzipcode = {
...
```
> 以UNICODE編碼儲存，看[預覽](http://yyc1217.github.io/twzipcode-data/twzipcode-data.js.demo.html)

#### twzipcode-data.csv
> csv以UTF-8編碼儲存
