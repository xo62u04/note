# AWS + laravel S3配置說明

env只要設定這四個參數即可
AWS_ACCESS_KEY_ID=創建IAM使用者給的ID
AWS_SECRET_ACCESS_KEY=創建IAM使用者給的access_key
AWS_DEFAULT_REGION : 主機的位置
AWS_BUCKET:該S3的名稱

# 到IAM創建使用者
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
到該網址去建立IAM使用者
https://us-east-1.console.aws.amazon.com/iamv2/home#/users

![](https://i.imgur.com/NSNAs5N.png)

資料來源：https://ithelp.ithome.com.tw/articles/10249918

## 地雷注意：
/config/filesystems 這兩個參數不要動他們，不需要設定，否則會報錯

```
's3' => [
    ...
    'url' => env('AWS_URL'),
    'endpoint' => env('AWS_ENDPOINT'),
],
```

# 實驗結果驗證：
在route貼上以下程式碼後，在storage/app 放入elephant.png進行測試，上傳檔案後，並抓取上船的檔案是否有成功傳入AWS內
```
Route::get('/s3', function () {
    $content = Storage::get('elephant.png');
    Storage::disk('s3')->put('elephant2.png', $content, 'public');
    return response(Storage::disk('s3')->get('elephant2.png'), 200,  ['Content-Type' => 'image/png']);
});
```