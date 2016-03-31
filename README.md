# openssl 安裝與使用

下載 github 上的 openssl-for-iphone  
或者  
直接開啟該檔案
此 openssl 的版本為 1.0.2e

## 說明
在 ios 上使用，openssl 可處理

- md5 
- sha256 
- base64 
- aes 系列 
- pkcs12 
- rsa 
- ssl 系列 
- x509 系列 ..與其他處理

ios 某些一般的加解密，可用 NSData 系列，進行 base64 的加解密 

而aes或其他方法，可

```
#import <CommonCrypto/CommonCryptor.h> 
#import <CommonCrypto/CommonHMAC.h> 
```
或使用 security.framework

## 相容性
可查看檔案內的 README.md

## 編譯 openssl
執行 ```bash build-libssl.sh``` ，會建立：  

- AppleTVSimulator9.1-x86_64.sdk
- iPhoneOS9.2-arm64.sdk
- iPhoneOS9.2-armv7.sdk
- iPhoneOS9.2-armv7s.sdk
- iPhoneSimulator9.2-i386.sdk
- iPhoneSimulator9.2-x86_64.sdk

## 將 lib 與 header 放入測試

1. 選擇適當的 sdk
2. 將 sdk 內的 『lib』與『include』 中的內容，拷貝到 OpenSSL-for-iPhone/ 的目錄下，你可以在裡面發現有一樣的資料夾
3. 開啟 OpenSSL-for-iOS.xcodeproj
4. 執行裡面範例即可，若您選擇的 lib 與執行的版本(armv7 or arm64 or armv7s...等等)不對，則無法 compile
5. 裡面有簡單的使用範例可參考