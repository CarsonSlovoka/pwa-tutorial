## FAQ

- Site cannot be installed: no matching service worker detected. You may need to reload the page, or check that the
  service worker for the current page also controls the start URL from the manifest

  可能是scope的關係

```json5
{
  "name": "",
  "short_name": "",
  // "start_url": "/index.html", // 這邊最好要確定URL一定抓地到，用/開頭表示在站點的根位置，但如果您的站點根位置壓根就不是專給PWA使用，這時候就會有問題。我建議用. 也就是使用當前URL所訪問的的路徑為準
  "start_url": "./index.html",
  // "scope": "." // scope是用來限制瀏覽的範圍，例如把scope設定為"https://example.com/subdirectory/"，那麼使用者就只能瀏覽subdirectory的東西而已 // 值得一提的是start_url的路徑必須在scope之中，不然會遇到錯誤: property 'scope' ignored. Start url should be within scope of scope URL.

}
```

> 如果還是沒解決也許可以看一下此問題: https://stackoverflow.com/q/45534076/9935654
