# Awin API

[![npm package](https://nodei.co/npm/awin-api.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/awin-api/)

API integration with Awin

## Install

```bash
$ npm install awin-api
```

## Get ConnectID and SecretKey

* Create account - https://marketplace.zanox.com/publisher-signup
* ConnectID and SecretKey - https://developer.zanox.com/blog?p_p_id=148_INSTANCE_n5kwq91nKP5Y&p_p_lifecycle=0&p_p_state=normal&p_p_mode=view&p_p_col_id=column-2&p_p_col_count=1&p_r_p_564233524_tag=publisher+api&p_r_p_564233524_resetCur=true
* Adspace Management - http://www.zanox.com/gb/publishers/faq/ad-space-management/

## Usage

```js
"use strict";

let Awin = require("awin-api"),
    awin = new Awin("connectid", "secretkey");

awin.programs({region: "BR"}, function(err, result){
    console.log(result.programItems.programItem);
});

awin.programapplications({region: "BR"}, function(err, result){
    console.log(result.programApplicationItems.programApplicationItem);
});

awin.deeplink("http://www.extra.com.br/", "adspace", function(err, url){
    console.log(url); //https://ad.zanox.com/ppc/?40352125C16456675&ULP=[[http://www.extra.com.br/?utm_source=zanox&utm_medium=deeplink&utm_campaign=deeplink]]
});
```
