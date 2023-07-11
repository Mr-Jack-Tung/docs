# Danh sách các hàm

## 1. Môi trường tích hợp

| Tên dịch vụ     | Tên môi trường | Host                           |
| --------------- | -------------- | ------------------------------ |
| FCTradingAPI    | PROD           | https://fc-tradeapi.ssi.com.vn |
| Order Streaming | PROD           | https://fc-tradehub.ssi.com.vn |

## 2. Thông tin đăng nhập

Thông tin cấu hình để tích hợp với FCTradingAPI

* ConsumerID: Thông tin định danh tài khoản.
* ConsumerSecrect: Key truy cập Server
* PrivateKey: Được sử dụng để tạo chữ ký số - Nguồn: [RSA algorithm](https://developers.momo.vn/#/docs/en/?id=encryption-rsa)

## 3. Yêu cầu Config

| Method | Content                              | Content     |
| ------ | ------------------------------------ | ----------- |
| Post   | Header (Authorization, Content-Type) | Body (json) |
| Get    | Header (Authorization)               | Params      |

## 4. FastConnect API

{% swagger method="post" path="" baseUrl=" https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="AccessToken" %}
{% swagger-description %}
Bạn cần tạo mã thông báo JWT với client_id và private đã được cung cấp. Vui lòng xem tài liệu để biết chi tiết.Với mã thông báo truy cập này, bạn có thể sử dụng cho tất cả các mô-đun FastConnect của mình có quyền truy cập.
{% endswagger-description %}

{% swagger-parameter in="body" name="consumerID" type="string" required="true" %}
ConsumerID trong thông tin kết nối
{% endswagger-parameter %}

{% swagger-parameter in="body" name="consumerSecret" type="string" required="true" %}
ConsumerSecret trong thông tin kết nối
{% endswagger-parameter %}

{% swagger-parameter in="body" name="code" type="string" required="true" %}
Mã xác thực cho API giao dịch
{% endswagger-parameter %}

{% swagger-parameter in="body" name="TwoFactorType" type="string" required="true" %}
Xác thực loại tài khoản, hỗ trợ type = 0 (PIN), type = 1 (OTP)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="isSave" type="boolean" required="true" %}
Lưu code khi giao dịch
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
{

&#x20; consumerID: "38f5fdfa56b44d5ab8b95895eb588e99",

&#x20; consumerSecret: "6d61bffefc6540fc837c71afd2ca4bcf",

&#x20; twoFactorType: 1,

&#x20; code: "123456789",

&#x20; isSave: false

}
{% endtab %}

{% tab title="Second Tab" %}
{

&#x20;   message: "Success",

&#x20;   status: 200,

&#x20;   data: {

&#x20;       "accessToken": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ”

}
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
{

&#x20; consumerID: "38f5fdfa56b44d5ab8b95895eb588e99",

&#x20; consumerSecret: "6d61bffefc6540fc837c71afd2ca4bcf",

&#x20; twoFactorType: 0,

&#x20; code: "123456789",

&#x20; isSave: true

}
{% endtab %}

{% tab title="Output" %}
{

message: "Key does not exist.",

status: 400,

data: null

&#x20;}
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="GetOTP" %}
{% swagger-description %}
Nhận tin nhắn OTP bằng tài khoản/tên đăng nhập đã đăng ký theo phương thức 2FA (SMS,Email).
{% endswagger-description %}

{% swagger-parameter in="body" name="consumerID" type="string" required="true" %}
Thông tin kết nối trong ConsumerID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="consumerSecret" type="string" required="true" %}
Thông tin kết nối trong ConsumerSecret
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```
{
  "consumerID": "968d7b5940f5437583021aea2b038f35",
  "consumerSecret": "11ab3fc6af954c59ba646fac016f30cb"
}
```
{% endtab %}

{% tab title="Output" %}
```
{
    message: "Success",
    status: 200
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```
{
  "consumerID": "968d7b5940f5437583021aea2b038f351",
  "consumerSecret": "11ab3fc6af954c59ba646fac016f30cb"
}
```
{% endtab %}

{% tab title="Output" %}
```
{
  "message": "ConsumerID is invalid",
  "status": 400
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="verifyCode" %}
{% swagger-description %}
Verify lại mã OTP khi khách hàng sứ dụng SMS/ Email/ SmartOTP và PIN khi khách hàng sử dụng PIN
{% endswagger-description %}

{% swagger-parameter in="body" name="code" type="string" required="true" %}
Điền PIN nếu khách hàng sử dụng PIN

Điền SMS/ Email/ SmartOTP nếu khách hàng dùng 2FA&#x20;
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
  "code": "123456"
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
"eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.ewogICJhdWQiOiAiO”
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
  "code": "123456789"
}
```
{% endtab %}

{% tab title="Output" %}
```
{
Internal Server Error
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="NewOrder" %}
{% swagger-description %}
Đặt lệnh
{% endswagger-description %}

{% swagger-parameter in="body" name="instrumentID" type="string" required="true" %}
mã chứng khoán đặt lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="market" type="string" required="true" %}
Sàn:&#x20;

VN: thị trường cơ sở

VNFE: thị trường phái sinh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="orderType" type="string" required="true" %}
Loại lệnh:&#x20;

LO|ATO|ATC|MP|MTL|MOK|MAK|PLO
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channelID" type="string" required="true" %}
Kệnh đặt lệnh

VD: TA (trader API)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="price" type="number" required="true" %}
Giá đặt lệnh:&#x20;

\- Nếu loại lệnh là LO -> Giá đặt > 0

\- Nếu loại lệnh khác LO -> Giá đặt = 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="quantity" type="interger" required="true" %}
Khối lượng đặt
{% endswagger-parameter %}

{% swagger-parameter in="body" name="account" type="string" required="true" %}
Số tài khoản muốn đặt lệnh:&#x20;

xxxxxx1: Cơ sở

xxxxxx8: Phái sinh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requestID" type="string" required="true" %}
ID đặt lệnh trong ngày. Bắt buộc 8 số random
{% endswagger-parameter %}

{% swagger-parameter in="body" name="stopOrder" type="string" required="true" %}
Loại lệnh:&#x20;

True: Đối với lệnh điều kiện&#x20;

False: Đối với lệnh thường
{% endswagger-parameter %}

{% swagger-parameter in="body" name="stopPrice" type="number" required="true" %}
Giá đặt mong muốn cắt lỗ/chốt lãi

Nếu stopOrder = true -> stopPrice > 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="stopType" type="string" required="true" %}
Loại điều kiện. Bắt buộc nhập nếu stopType = true

\- D: Down

\- U: Up

\- V: Trailling Up

\- E: Trailing Down

\- O: OCO

\- B: BullBear
{% endswagger-parameter %}

{% swagger-parameter in="body" name="stopStep" type="number" required="true" %}
Bước chốt lỗ, chỉ dùng cho lệnh điều kiện BullBear (stopType = B)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="profitStep" type="number" required="true" %}
Bước chốt lãi, chỉ dùng cho lệnh điện BullBear (stopType = B)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="code" type="number" %}
Trading code: PIN, OTP

Nếu API Xác thực người dùng input: isSave = false, code bắt buộc điền
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceID" type="string" %}
Thiết bị định danh từ máy tính (lap) khách hàng cài đặt
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userAgent" type="string" %}
Tác nhân người dùng&#x20;

VD: FCTrading
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{ 
instrumentID: "SSI",
market: "VN",
buySell: "B",
orderType: "LO",
channelID: "IW",
price: 21000,
quantity: 300,
account: "0901351",
stopOrder: false,
stopPrice: 0,
stopType: "string",
stopStep: 0,
lossStep: 0,
profitStep: 0
requestID: "1678195",
code: “123456789”,
deviceID: "MAC Address",
userAgent: “FCTrading”
 }
```
{% endtab %}

{% tab title="Output" %}
```
{
message: "Success",
status: 200,
data: {
requestID: "1678195",
requestData: 
{
instrumentID: "SSI",
market: "VN",
buySell: "B",
orderType: "LO",
channelID: "IW",
price: 21000,
quantity: 300,
account: "0901351",
stopOrder: false,
stopPrice: 0,
stopType: "string",
stopStep: 0,
lossStep: 0,
profitStep: 0
}
    }
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{  
instrumentID: "SSI",
market: "VN",
buySell: "B",
orderType: "ATO",
channelID: "IW",
price: 21000,
quantity: 300,
account: "0901351",
stopOrder: false,
stopPrice: 0,
stopType: "string",
stopStep: 0,
lossStep: 0,
profitStep: 0
requestID: "1678195",
code: “123456789”,
deviceID: "MAC Address",
userAgent: “FCTrading”
 }
```
{% endtab %}

{% tab title="Output" %}
```json
{
    message: "Price is null or equal zero when order is market order",
    status: 400,
    data: null
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="ModifyOrder" %}
{% swagger-description %}
Sửa lệnh
{% endswagger-description %}

{% swagger-parameter in="body" name="orderID" type="string" required="true" %}
ID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="price" type="number" required="true" %}
Giá mong muốn sửa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="quantity" type="string" required="true" %}
Khối lượng muốn sửa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="account" type="string" required="true" %}
Số tài khoản đã đặt theo orderID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="instrumentID" type="string" required="true" %}
Mã chứng khoán đã đặt theo orderID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="marketID" type="string" required="true" %}
Thị trường cơ sở/ phái sinh đã đặt theo orderID của lệnh

VN: thị trường cơ sở

VNFE: thị trường phái sinh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="buySell" type="string" required="true" %}
buy (B): mua/Sell (S): bán đã đặt theo orderID của lệnh

B: Buy

S: Sell
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requestID" type="number" required="true" %}
ID đặt lệnh trong ngày. Bắt buộc 8 số random
{% endswagger-parameter %}

{% swagger-parameter in="body" name="orderType" type="string" required="true" %}
Loại lệnh đã đặt theo orderID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="code" type="number" %}
Trading code: PIN, OTP

Nếu API Xác thực người dùng input: isSave = false, code bắt buộc điền
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceID" type="string" %}
Thiết bị định danh từ máy tính (lap) khách hàng cài đặt
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userAgent" type="string" %}
Tác nhân người dùng&#x20;

VD: FCTrading
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
requestID: "93235974",
orderID: "12658867",
price: 1410,
quantity: 2,
account: "0901358",
instrumentID: "VN30F2106",
marketID: "VNFE",
buySell: "B",
orderType: "LO"
code:”123456789”,
deviceID: "MAC Address",
userAgent: “FCTrading”
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
message: "Success",
status: 200,
data: {
   requestID: "93235974",
   requestData: {
         orderID: "12658867",
         price: 1410,
         quantity: 2,
         account: "0901358",
         instrumentID: "VN30F2106",
         marketID: "VNFE",
         buySell: "B",
         orderType: "LO"
      }
  }
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```
{
requestID: "93235971",
orderID: "",
price: 1410,
quantity: 2,
account: "0901358",
instrumentID: "VN30F2106",
marketID: "VNFE",
buySell: "B",
orderType: "LO"
code:”123456789”,
deviceID: "MAC Address",
userAgent: “FCTrading”
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
data: null,
message: "’Order ID’ must not be empty ",
status: 400
}

```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="CancelOrder" %}
{% swagger-description %}
Hủy lệnh
{% endswagger-description %}

{% swagger-parameter in="body" name="orderID" required="true" type="string" %}
ID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="account" type="string" required="true" %}
Số tài khoản đã đặt theo orderID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="instrumentID" type="string" required="true" %}
Mã chứng khoán đã đặt theo orderID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="marketID" type="string" required="true" %}
Thị trường cơ sở/ phái sinh đã đặt theo orderID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="buySell" type="string" required="true" %}
buy (B): mua

Sell (S): bán đã đặt theo orderID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requestID" type="string" required="true" %}
ID đặt lệnh trong ngày. Bắt buộc 8 số random
{% endswagger-parameter %}

{% swagger-parameter in="body" name="code" type="number" %}
Trading code: PIN, OTP

Nếu API Xác thực người dùng input: isSave = false, code bắt buộc điền
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```
{
orderID: "12658867",
account: "0901358",
marketID: "VNFE",
instrumentID: "VN30F2106",
buySell: "B",
requestID: "52513603"
code:”123456789”,
deviceID: "MAC Address",
userAgent: “FCTrading”
}

```
{% endtab %}

{% tab title="Output" %}
```json
{
message: "Success",
status: 200,
data: {
    requestID: "52513603",
    requestData: {
         orderID: "12658867",
         account: "0901358",
         marketID: "VNFE",
         instrumentID: "VN30F2106",
         buySell: "B",
         requestID: "52513603"
       }
    }
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
orderID: " ",
account: "0901358",
marketID: "VNFE",
instrumentID: "VN30F2106",
buySell: "B",
requestID: "52513603"
code:”123456789”,
deviceID: "MAC Address",
userAgent: “FCTrading”
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
message: "’Order ID' must not be empty.",
status: 400,
data: null
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="derNewOrder" %}
{% swagger-description %}
Đặt lệnh phái sinh
{% endswagger-description %}

{% swagger-parameter in="body" name="instrumentID" type="string" required="true" %}
mã chứng khoán đặt lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="market" type="string" required="true" %}
Sàn:&#x20;

VNFE: thị trường phái sinh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="orderType" type="string" required="true" %}
Loại lệnh:&#x20;

LO|ATO|ATC|MTL|MOK|MAK
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channelID" type="string" required="true" %}
Kệnh đặt lệnh

VD: TA (trader API)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="price" type="number" required="true" %}
Giá đặt lệnh:&#x20;

\- Nếu loại lệnh là LO -> Giá đặt > 0

\- Nếu loại lệnh khác LO -> Giá đặt = 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="quantity" type="interger" required="true" %}
Khối lượng đặt
{% endswagger-parameter %}

{% swagger-parameter in="body" name="account" type="string" required="true" %}
Số tài khoản muốn đặt lệnh:&#x20;

xxxxxx8: Phái sinh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requestID" type="string" required="true" %}
ID đặt lệnh trong ngày. Bắt buộc 8 số random
{% endswagger-parameter %}

{% swagger-parameter in="body" name="stopOrder" type="string" required="true" %}
Loại lệnh:&#x20;

True: Đối với lệnh điều kiện&#x20;

False: Đối với lệnh thường
{% endswagger-parameter %}

{% swagger-parameter in="body" name="stopPrice" type="number" required="true" %}
Giá đặt mong muốn cắt lỗ/chốt lãi

Nếu stopOrder = true -> stopPrice > 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="stopType" type="string" required="true" %}
Loại điều kiện. Bắt buộc nhập nếu stopType = true

\- D: Down

\- U: Up

\- V: Trailling Up

\- E: Trailing Down

\- O: OCO

\- B: BullBear
{% endswagger-parameter %}

{% swagger-parameter in="body" name="stopStep" type="number" required="true" %}
Bước chốt lỗ, chỉ dùng cho lệnh điều kiện BullBear (stopType = B)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="profitStep" type="number" required="true" %}
Bước chốt lãi, chỉ dùng cho lệnh điện BullBear (stopType = B)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="code" type="number" %}
Trading code: PIN, OTP

Nếu API Xác thực người dùng input: isSave = false, code bắt buộc điền
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceID" type="string" %}
Thiết bị định danh từ máy tính (lap) khách hàng cài đặt
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userAgent" type="string" %}
Tác nhân người dùng&#x20;

VD: FCTrading
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{  
instrumentID: "VN30F2306",
market: "VNFE",
buySell: "B",
orderType: "LO",
channelID: "TA",
price: 1200,
quantity: 10,
account: "1184418",
stopOrder: false,
stopPrice: 0,
stopType: "string",
stopStep: 0,
lossStep: 0,
profitStep: 0
requestID: "1678198",
code: “123456789”,
deviceID: "MAC Address",
userAgent: “FCTrading"
 }

```
{% endtab %}

{% tab title="Output" %}
```
{
  "message": "Success",
  "status": 200,
  "data": {
    "requestID": "3407154",
    "requestData": {
      "instrumentID": "VN30F2306",
      "market": "VNFE",
      "buySell": "B",
      "orderType": "LO",
      "channelID": "TA",
      "price": 1200,
      "quantity": 100,
      "account": "1184418",
      "stopOrder": false,
      "stopPrice": 0,
      "stopType": "",
      "stopStep": 0,
      "lossStep": 0,
      "profitStep": 0
    }
  }
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{  
instrumentID: "SSI",
market: "VN",
buySell: "B",
orderType: "ATO",
channelID: "IW",
price: 21000,
quantity: 300,
account: "0901351",
stopOrder: false,
stopPrice: 0,
stopType: "string",
stopStep: 0,
lossStep: 0,
profitStep: 0
requestID: "1678195",
code: “123456789”,
deviceID: "MAC Address",
userAgent: “FCTrading”
 }
```
{% endtab %}

{% tab title="Output" %}
```json
{
    message: "Price is null or equal zero when order is market order",
    status: 400,
    data: null
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="derModifyOrder" %}
{% swagger-description %}
Sửa lệnh phái sinh
{% endswagger-description %}

{% swagger-parameter in="body" name="orderID" type="string" required="true" %}
ID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="price" type="number" required="true" %}
Giá mong muốn sửa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="quantity" type="string" required="true" %}
Khối lượng muốn sửa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="account" type="string" required="true" %}
Số tài khoản đã đặt theo orderID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="instrumentID" type="string" required="true" %}
Mã chứng khoán đã đặt theo orderID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="marketID" type="string" required="true" %}
Thị trường cơ sở/ phái sinh đã đặt theo orderID của lệnh

VNFE: thị trường phái sinh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="buySell" type="string" required="true" %}
buy (B): mua/Sell (S): bán đã đặt theo orderID của lệnh

B: Buy

S: Sell
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requestID" type="number" required="true" %}
ID đặt lệnh trong ngày. Bắt buộc 8 số random
{% endswagger-parameter %}

{% swagger-parameter in="body" name="orderType" type="string" required="true" %}
Loại lệnh đã đặt theo orderID của lệnh
{% endswagger-parameter %}

{% swagger-parameter in="body" name="code" type="number" %}
Trading code: PIN, OTP

Nếu API Xác thực người dùng input: isSave = false, code bắt buộc điền
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceID" type="string" %}
Thiết bị định danh từ máy tính (lap) khách hàng cài đặt
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userAgent" type="string" %}
Tác nhân người dùng&#x20;

VD: FCTrading
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
requestID: "93235974",
orderID: "12658867",
price: 1410,
quantity: 3,
account: "1184418",
instrumentID: "VN30F2306",
marketID: "VNFE",
buySell: "B",
orderType: "LO"
code:”123456789”,
deviceID: "MAC Address",
userAgent: “FCTrading”
}

```
{% endtab %}

{% tab title="Output" %}
```json
{
message: "Success",
status: 200,
data: {
   requestID: "93235974",
   requestData: {
         orderID: "12658867",
         price: 1410,
         quantity: 3,
         account: "1184418",
         instrumentID: "VN30F2306",
         marketID: "VNFE",
         buySell: "B",
         orderType: "LO"
      }
  }
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```
{
requestID: "93235974",
orderID: "",
price: 1410,
quantity: 3,
account: "1184418",
instrumentID: "VN30F2306",
marketID: "VNFE",
buySell: "B",
orderType: "LO"
code:”123456789”,
deviceID: "MAC Address",
userAgent: “FCTrading”
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
data: null,
message: "’Order ID’ must not be empty ",
status: 400
}

```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="orderBook" %}
{% swagger-description %}
Lấy lệnh đặt trong ngày
{% endswagger-description %}

{% swagger-parameter in="query" name="account" type="string" required="true" %}
Số tài khoản muốn truy vấn bao gồm Cơ sở và Phái inh
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
account: "1184418"
}
```
{% endtab %}

{% tab title="Output" %}
```
{
  "message": "Success",
  "status": 200,
  "data": {
    "account": "1184418",
    "orders": [
      {
        "uniqueID": "73885549",
        "orderID": "T202306146w273885549",
        "buySell": "B",
        "price": 1000,
        "quantity": 100,
        "filledQty": 0,
        "orderStatus": "RJ",
        "marketID": "VNFE",
        "inputTime": "1686730747945",
        "modifiedTime": "1686730747945",
        "instrumentID": "VN30F2306",
        "orderType": "LO",
        "cancelQty": 0,
        "avgPrice": 0,
        "isForcesell": "F",
        "isShortsell": "F",
        "rejectReason": "Invalid market status"
      }     
    ]
  }
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
account: "118441”
}
```
{% endtab %}

{% tab title="Output" %}
```
{
  "message": "Account is not exist.",
  "status": 400,
  "data": null
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="orderHistory" %}
{% swagger-description %}
Truy vấn lịch sử lệnh
{% endswagger-description %}

{% swagger-parameter in="query" name="account" type="string" required="true" %}
Số tài khaorn muốn truy vẫn gồm Cơ sở và Phái sinh
{% endswagger-parameter %}

{% swagger-parameter in="query" name="startDate" type="date" required="true" %}
Ngày bắt đầu tìm kiếm

Định dạng dd/mm/yyyy
{% endswagger-parameter %}

{% swagger-parameter in="query" name="endDate" type="date" required="true" %}
Ngày kết thúc tìm kiếm

Định dạng dd/mm/yyyy
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```
{
account: "0901358",
startDate: “18/11/2020”,
endDate: “18/11/2020”
}
```
{% endtab %}

{% tab title="Output" %}
```
{
    message: "Success",
    status: 200,
    data: {
        orderHistories: [
      {
                uniqueID: null,
                orderID: "12626539",
                buySell: "B",
                price: 800.0,
                quantity: 10,
                filledQty: 0,
                orderStatus: "RJ",
                marketID: "VNFE",
                inputTime: "1603157594668",
                modifiedTime: "1603157594668",
                instrumentID: "VN30F2012",
                orderType: "LO",
                cancelQty: 0,
                avgPrice: 0.0,
                isForcesell: null,
                isShortsell: null
            }
],
        account: "0901358"
    }
 }
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
account: "0901358",
startDate: “”,
endDate: “18/11/2020”
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
    message: "'Start Date' must not be empty; StartDate is required.",
    status: 400,
    data: null
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="cashAcctBal" %}
{% swagger-description %}
Truy vấn thông tin tài khoản cơ sở
{% endswagger-description %}

{% swagger-parameter in="query" name="account" type="string" required="true" %}
Số tài khoản cơ sở muốn truy vấn
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```
{
    account: "0901351",
}
```
{% endtab %}

{% tab title="Output" %}
```
{
message: "Success",
status: 200,
data: {
account: "0901351",
cashBal: 7459369481,
cashOnHold: 0,
secureAmount: 0,
withdrawable: 7459367581,
receivingCashT1: 0,
receivingCashT2: 0,
matchedBuyVolume: 0,
matchedSellVolume: 0,
debt: 1900,
unMatchedBuyVolume: 0,
unMatchedSellVolume: 864619337,
paidCashT1: 0,
paidCashT2: 0,
cia: 0,
purchasingPower: 7459367581,
totalAssets: 9726161481
       }
}
```
{% endtab %}

{% tab title="Thông tin chi tiết Output" %}
<table><thead><tr><th width="218">Tên trường</th><th width="130">Kiểu dư</th><th>Mô tả</th></tr></thead><tbody><tr><td>account</td><td>string</td><td>Số tài khoản cơ sở</td></tr><tr><td>cashbal</td><td>number</td><td>Tổng tiền mặt</td></tr><tr><td>cashonhold</td><td>number</td><td>Tiền bị phong tỏa</td></tr><tr><td>secureamount</td><td>number</td><td>Secure amount intraday</td></tr><tr><td>withdrawable</td><td>number</td><td>Số tiền có thể rút</td></tr><tr><td>receivingcasht1</td><td>number</td><td>Tiền bán chờ về ngày T1</td></tr><tr><td>receivingcasht2</td><td>number</td><td>Tiền bán chờ về ngày T2</td></tr><tr><td>matchedbuyvolume</td><td>number</td><td>Tiền khớp mua trong ngày</td></tr><tr><td>matchedsellvolume</td><td>number</td><td>Tiền khớp bán trong ngày</td></tr><tr><td>unmatchedbuyvolume</td><td>number</td><td>Tiền mua chứng khoán chờ khớp</td></tr><tr><td>unmatchedsellvolume</td><td>number</td><td>Tiền bán chứng khoán chờ khớp</td></tr><tr><td>paidcasht1</td><td>number</td><td>Tiền mua chứng khoán ngày T1</td></tr><tr><td>paidcasht2</td><td>number</td><td>Tiền mua chứng khoán ngày T2</td></tr><tr><td>cia</td><td>number</td><td>Trả trước tiền mặt</td></tr><tr><td>debt</td><td>number</td><td>Dư nợ</td></tr><tr><td>purchasingpower</td><td>number</td><td>Sức mua</td></tr><tr><td>totalasset</td><td>number</td><td>Tổng tài sản</td></tr></tbody></table>
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```
{
    account: "0901357",
}
```
{% endtab %}

{% tab title="Output" %}
```
{
    message: "Account is not exist.",
    status: 400,
    data: null
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="derivAcctBal" %}
{% swagger-description %}
Kiểm tra số dư tiền tài khoản phái sinh
{% endswagger-description %}

{% swagger-parameter in="query" name="account" type="string" required="true" %}
Số tài khoản phái sinh muốn truy vấn
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```
{
    account: "0901358",
}
```
{% endtab %}

{% tab title="Output" %}
```
{
message: "Success",
status: 200,
data: {
account: "0901358",
accountBalance: 11166309263,
fee: 0,
commission: 0,
interest: 1514965,
loan: 0,
deliveryAmount: 0,
floatingPL: 0,
totalPL: 0,
marginable: 0,
depositable: 1148597520,
rcCall: 0,
withdrawable: 10912447363,
nonCashDrawableRCCall: 0,
internalAssets: {
cash: 1165730020,
validNonCash: 0,
totalValue: 11166309263,
maxValidNonCash: 0,
cashWithdrawable: 1148597520,
ee: 8197059272
        },
exchangeAssets: {
cash: 10000579243,
validNonCash: 0,
totalValue: 10000579243,
maxValidNonCash: 0,
cashWithdrawable: 9763849843,
ee: 7322887382
         },
        internalMargin: {
initialMargin: 172660800,
deliveryMargin: 0,
marginReq: 172660800,
accountRatio: 1.5462656096416592,
usedLimitWarningLevel1: 75,
usedLimitWarningLevel2: 85,
usedLimitWarningLevel3: 90,
marginCall: 0
        },
      exchangeMargin: {
marginReq: 172660800,
accountRatio: 1.7265079932330476,
usedLimitWarningLevel1: 75,
usedLimitWarningLevel2: 85,
usedLimitWarningLevel3: 90,
marginCall: 0
        }
     }
}
```
{% endtab %}

{% tab title="Thông tin chi tiết Output" %}
<table><thead><tr><th width="177">Tên trường</th><th width="132">Kiểu dữ liệu</th><th>Mô tả</th></tr></thead><tbody><tr><td>account</td><td>string</td><td>Số tài khoản phái sinh</td></tr><tr><td>accountbalance</td><td>number</td><td>Tổng số dư tiền</td></tr><tr><td>fee</td><td>number</td><td>Phí</td></tr><tr><td>commission</td><td>number</td><td>Thuế</td></tr><tr><td>interest</td><td>number</td><td>Lãi</td></tr><tr><td>Loan</td><td>number</td><td>Nợ</td></tr><tr><td>deliveryamount</td><td>number</td><td>Giá trị chuyển giao</td></tr><tr><td>floatingpl</td><td>number</td><td>Lãi lỗ tạm tính</td></tr><tr><td>totalpl</td><td>number</td><td>Lãi lỗ vị thế</td></tr><tr><td>marginable</td><td>number</td><td>Số dư tối thiếu tiền</td></tr><tr><td>depositable</td><td>number</td><td>Tiền có thể ký quỹ</td></tr><tr><td>rccall</td><td>number</td><td></td></tr><tr><td>withdrawable</td><td>number</td><td>Tiền có thể rút</td></tr><tr><td>noncashdrawablerccall</td><td>number</td><td>Giá trị chứng khoán có thể rút</td></tr><tr><td>internalassets</td><td>list</td><td><p>Bao gồm:</p><ul><li>Cash</li><li>Validnoncash</li><li>totalvalue:</li><li>maxvalidnoncash</li><li>cashwithdrawable</li><li>Ee</li></ul></td></tr><tr><td>exchangeassets</td><td>list</td><td><p>Bao gồm:</p><ul><li>Cash</li><li>Validnoncash</li><li>totalvalue:</li><li>maxvalidnoncash</li><li>cashwithdrawable</li><li>Ee</li></ul></td></tr><tr><td>internalmargin</td><td>list</td><td><p>Bao gồm:</p><ul><li>initialmargin</li><li>deliverymargin</li><li>marginreq</li><li>accountratio</li><li>usedlimitwarninglevel1</li><li>usedlimitwarninglevel2</li><li>usedlimitwarninglevel3</li><li>margincall</li></ul></td></tr><tr><td>exchangemargin</td><td>list</td><td><p>Bao gồm:</p><ul><li>marginreq</li><li>accountratio</li><li>usedlimitwarninglevel1</li><li>usedlimitwarninglevel2</li><li>usedlimitwarninglevel3</li><li>margincall</li></ul></td></tr></tbody></table>
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```
{
    account: "0901357",
}
```
{% endtab %}

{% tab title="Output" %}
```
{
message: "Account is not exist”,
status: 400,
data: null
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="ppmmraccount" %}
{% swagger-description %}
Truy vấn sức mua của tài khoản Margin
{% endswagger-description %}

{% swagger-parameter in="query" name="account" type="string" required="true" %}
Số tài khoản truy vấn
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
    account: "0901356",
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
message: "Success",
status: 200,
data: {
collateralAsset: 8404515731,
callLMW: 0,
liability: 1900,
eeOrigin: 7459367581,
forceLMV: 0,
equity: 8404513831,
ee: 7459367581,
callMargin: 0,
cashBalance: 7459369481,
purchasingPower: 7459367581,
callForcesell: 0,
lmv: 945146250,
marginCall: 0,
withdrawal: 7459367581,
collateralA: 0,
action: "",
marginRatio: 1,
debt: 0,
accruedInterest: 0,
holdRight: 0,
preLoan: 0,
fees: 1900,
buyUnmatch: 0,
ap: 0,
apT1: 0,
sellUnmatch: 0,
cia: 0,
ar: 0,
arT1: 0,
ppCredit: 7459367581,
creditLimit: 0,
totalAssets: 9615302981,
marginCallLMVSold: 0,
lmvNonMarginable: 1210787250,
eeCredit: 7459367581,
totalEquity: 9615301081,
eE90: 8288186201,
eE80: 9324209476,
eE70: 10656239401,
eE60: 12432279302,
eE50: 14918735162
      }
}
```
{% endtab %}

{% tab title="Thông tin chi tiết Output" %}
<table><thead><tr><th width="200">Tên trường</th><th width="139">Kiểu dữ liệu</th><th>Mô tả</th></tr></thead><tbody><tr><td>collateralAsset</td><td>number</td><td>Tổng tài sản đảm bảo</td></tr><tr><td>callLMW</td><td>number</td><td>Tỷ lệ ký quỹ duy trì (double)</td></tr><tr><td>liability</td><td>number</td><td>Tổng nợ</td></tr><tr><td>eeOrigin</td><td>number</td><td>Hạn mức thực hiện quyền tối thiếu</td></tr><tr><td>forceLMV</td><td>number</td><td>Tỷ lệ ký quỹ xử lý (double)</td></tr><tr><td>equity</td><td>number</td><td>Tài sản đảm bảo thực có</td></tr><tr><td>ee</td><td>number</td><td>Sức mua tối thiểu</td></tr><tr><td>callMargin</td><td>number</td><td>Tài sản thực có cần duy trì</td></tr><tr><td>cashBalance</td><td>number</td><td>Số dư tiền</td></tr><tr><td>purchasingPower</td><td>number</td><td>Sức mua</td></tr><tr><td>callForcesell</td><td>number</td><td>Tài sản thực có chạm cảnh báo xử lý</td></tr><tr><td>lmv</td><td>number</td><td>Stock Market Value (margin)</td></tr><tr><td>marginCall</td><td>number</td><td>Tỷ lệ tài khoản</td></tr><tr><td>withdrawal</td><td>number</td><td>Số tiền được rút</td></tr><tr><td>collateralA</td><td>number</td><td>Tài sản đảm bảo khác</td></tr><tr><td>action</td><td>string</td><td>Trạng thái xử lý (text)</td></tr><tr><td>marginRation</td><td>number</td><td>Tỷ lệ tài khoản (double)</td></tr><tr><td>debt</td><td>number</td><td>Nợ</td></tr><tr><td>accruedInterest</td><td>number</td><td></td></tr><tr><td>holdRight</td><td>number</td><td>Right subcription</td></tr><tr><td>preLoan</td><td>number</td><td>Nợ sắp giải ngân</td></tr><tr><td>fees</td><td>number</td><td>Phí</td></tr><tr><td>buyUnmatch</td><td>number</td><td>Tiền mua chờ khớp</td></tr><tr><td>ap</td><td>number</td><td>Tiền mua đã khớp</td></tr><tr><td>apT1</td><td>number</td><td>Tiền mua T1</td></tr><tr><td>sellUnmatch</td><td>number</td><td>Tiên bán chờ khớp</td></tr><tr><td>cia</td><td>number</td><td>Tiền bán đã ứng</td></tr><tr><td>ar</td><td>number</td><td>Tiền bán đã khớp</td></tr><tr><td>arT1</td><td>number</td><td>Tiền bán T1</td></tr><tr><td>ppCredit</td><td>number</td><td>Sức mua gia tăng tối đa</td></tr><tr><td>creditLimit</td><td>number</td><td>Hạn mức gia tăng</td></tr><tr><td>totalAssets</td><td>number</td><td>Tổng tài sản</td></tr><tr><td>MarginCallMVSold</td><td>number</td><td>Giá LMV bán hết để call margin</td></tr><tr><td>lmvNonMarginable</td><td>number</td><td>GTCK ngoài danh mục</td></tr><tr><td>eeCredit</td><td>number</td><td>SM gia tăng tối thiếu</td></tr><tr><td>totalEquity</td><td>number</td><td>Tổng đài sản thực có</td></tr><tr><td>eE90</td><td>number</td><td>SM theo tỷ lệ ký quỹ 90</td></tr><tr><td>eE80</td><td>number</td><td>SM theo tỷ lệ ký quỹ 80</td></tr><tr><td>eE70</td><td>number</td><td>SM theo tỷ lệ ký quỹ 70</td></tr><tr><td>eE60</td><td>number</td><td>SM theo tỷ lệ ký quỹ 60</td></tr><tr><td>eE50</td><td>number</td><td>SM theo tỷ lệ ký quỹ 50</td></tr></tbody></table>
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="stockPosition" %}
{% swagger-description %}
Truy vấn vị thế của tài khoản cơ sở
{% endswagger-description %}

{% swagger-parameter in="query" name="account" type="string" required="true" %}
Số tài khoản cơ sở muốn truy vấn
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
account: "0901351",
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
    message: "Success",
    status: 200,
    data: {
        account": "0901351,
        totalMarketValue: 0,
        stockPositions: [
            {
marketID: "VN",
instrumentID: "SSI",
onHand: 50300,
block: 0,
bonus: 7425,
buyT0: 0,
buyT1: 0,
buyT2: 0,
sellT0: 0,
sellT1: 0,
sellT2: 0,
avgPrice: 18505,
mortgage: 0,
sellableQty: 50300,
holdForTrade: 0,
marketPrice: 0
}
        ]
    }
}
```
{% endtab %}

{% tab title="Thông tin chi tiết Output" %}
<table><thead><tr><th width="185">Tên trường</th><th width="137">Kiểu dữ liệu</th><th>Mô tả</th></tr></thead><tbody><tr><td>totalMarketValue</td><td>number</td><td><p>Tổng giá trị thị trường danh mục</p><p>= sum(maketprice * onhand)</p></td></tr><tr><td>stockPositions</td><td>list</td><td>Danh mục đầu tư của tài khoản</td></tr><tr><td>marketID</td><td>string</td><td>Mã sàn</td></tr><tr><td>instrumentID</td><td>string</td><td>Mã CK</td></tr><tr><td>onHand</td><td>number</td><td>Tổng KL đang lắm giữ</td></tr><tr><td>block</td><td>number</td><td>Phong tỏa</td></tr><tr><td>bonus</td><td>number</td><td>CP quyền</td></tr><tr><td>buyT0</td><td>number</td><td>Mua khớp thanh toán ngày T0</td></tr><tr><td>buyT1</td><td>number</td><td>Mua khớp thanh toán ngày T1</td></tr><tr><td>buyT2</td><td>number</td><td>Mua khớp thanh toán ngày T2</td></tr><tr><td>sellT0</td><td>number</td><td>Bán khớp thanh toán ngày T0</td></tr><tr><td>sellT1</td><td>number</td><td>Bán khớp thanh toán ngày T1</td></tr><tr><td>sellT2</td><td>number</td><td>Bán khớp thanh toán ngày T2</td></tr><tr><td>avgPrice</td><td>number</td><td>Giá vốn TB</td></tr><tr><td>mortgage</td><td>number</td><td>Chứng khoán cầm cố</td></tr><tr><td>holdForTrade</td><td>number</td><td>CK hạn chế chuyển nhượng</td></tr><tr><td>marketPrice</td><td>number</td><td>Giá trị trường</td></tr></tbody></table>
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
account: "0901352"
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
    message: "Account is not exist.",
    status: 400,
    data: null
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="derivPosition" %}
{% swagger-description %}
Truy vấn vị thế của tài khoản phái sinh
{% endswagger-description %}

{% swagger-parameter in="query" name="account" type="string" required="true" %}
Số tài khoản phái sinh
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
account: "0901358",
querySummary: true
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
message: "Success",
status: 200,
data: {
       account: "0901358",
       openPosition: [
       {
           marketID: "VNFE",
           instrumentID: "VN30F2106",
           longQty: 8,
           shortQty: 0,
           net: 8,
           bidAvgPrice: 0,
           askAvgPrice: 0,
           tradePrice: 1452.7,
           marketPrice: 1452.7,
           floatingPL: 0,
           tradingPL: 0
          }   ],
        closePosition: [ ]
    }
}
```
{% endtab %}

{% tab title="Thông tin chi tiết Output" %}
<table><thead><tr><th width="153">Tên trường</th><th width="122">Kiểu dữ liệu</th><th>Mô tả</th></tr></thead><tbody><tr><td>marketID</td><td>string</td><td>Mã sàn</td></tr><tr><td>instrumentID</td><td>string</td><td>Mã chứng khoán</td></tr><tr><td>longQty</td><td>number</td><td>Vị thế mở</td></tr><tr><td>shortQty</td><td>number</td><td>Vị thế đóng</td></tr><tr><td>net</td><td>number</td><td>Net</td></tr><tr><td>bidAvgPrice</td><td>number</td><td>Giá mua trung bình</td></tr><tr><td>askAvgPrice</td><td>number</td><td>Giá bán trung bình</td></tr><tr><td>tradePrice</td><td>number</td><td>Giá khớp</td></tr><tr><td>marketPrice</td><td>number</td><td>Giá thị trường</td></tr><tr><td>floatingPL</td><td>number</td><td>Lãi/ Lỗ tạm tính</td></tr><tr><td>tradingPL</td><td>number</td><td>Lãi/ Lỗ đã chốt</td></tr></tbody></table>
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
account: "",
querySummary: true
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
    message: "'Account' must not be empty ",
    status: 400,
    data: null
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="https://fc-tradeapi.ssi.com.vn/api/v2/Trading/" summary="maxBuyQty" %}
{% swagger-description %}
Truy vấn số lượng mua tối đa
{% endswagger-description %}

{% swagger-parameter in="query" name="account" type="string" required="true" %}
Số tài khoản muốn truy vấn bao gồm Cơ sở và Phái sinh
{% endswagger-parameter %}

{% swagger-parameter in="query" name="instrumentID" type="string" required="true" %}
Mã chứng khoán
{% endswagger-parameter %}

{% swagger-parameter in="query" name="price" type="number" required="true" %}
Giá
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
{% tabs %}
{% tab title="Input" %}
```json
{
account: "0041691",
instrumentD: “SSI”,
price:17
}
```
{% endtab %}

{% tab title="Output" %}
```json
{
    message: "Success",
    status: 200,
    data: {
        account: "0041691",
        maxBuyQty: 8241440,
        marginRatio: "50%",
        purchasingPower: 99292902171
    }
}
```
{% endtab %}

{% tab title="Thông tin chi tiết Output" %}
| Tên trường | Kiểu dữ liệu | Mô tả |
| ---------- | ------------ | ----- |
| account    |              |       |
|            |              |       |
|            |              |       |
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Không thành công" %}

{% endswagger-response %}
{% endswagger %}

{% swagger src="../../.gitbook/assets/openapi.json" path="maxBuyQty" method="get" %}
[openapi.json](../../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../../.gitbook/assets/openapi.json" path="maxSellQty" method="get" %}
[openapi.json](../../.gitbook/assets/openapi.json)
{% endswagger %}
