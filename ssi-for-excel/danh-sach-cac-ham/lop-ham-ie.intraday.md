---
description: >-
  Tập hợp các hàm lấy thông tin giao dịch ứng với mỗi lần khớp của mã chứng
  khoán
---

# Lớp hàm IE.Intraday

{% hint style="info" %}
**Lưu ý:** Để sử dụng hàm IE.Intraday khách hàng cần kết nối realtime như sau:
{% endhint %}

* Nhấn vào icon Kết nối realtime:

<figure><img src="../../.gitbook/assets/Ket noi Realtime 1.png" alt=""><figcaption></figcaption></figure>

* Icon chuyển sang Ngắt kết nối realtime là đang kết nối realtime thành công.



## **Cú pháp**

```
=IE.Intraday.[Trường thông tin]("Mã CK hoặc Mã Index",Số thứ tự)
```

**Trong đó:**

* **Mã CK:** là mã của những chứng khoán niêm yết
* **Mã Index:** là tên Index tương ứng, ví dụ: VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30, …&#x20;
* **Trường thông tin**: tên trường tương ứng với một thông tin nhất định của mã chứng khoán
* **Số thứ tự:** là số thứ tự của lần khớp. Số thứ tự được tính từ 1, tương ứng với lần khớp gần nhất của mã hoặc lần tổng hợp gần nhất của Index

## Ví dụ&#x20;

**Giả sử từ đầu ngày đến giờ, Mã SSI đã có tất cả 10 lần khớp lệnh. Nếu muốn xem giá của lần khớp thứ 8 ta dùng công thức:**

```
=IE.Intraday.LastPrice("SSI",8)
```

Bạn cũng có thể ghi mã chứng khoán ở một ô(ví dụ A1), ghi số thứ tự ở một ô (ví dụ A2) và dùng công thức sau:

```
=IE.Intraday.LastPrice(A1,A2)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán,số thứ tự mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.&#x20;
{% endhint %}

## IE.Intraday.Change

Lấy giá thay đổi trong ngày của 1 mã hoặc index theo số thứ tự khớp tính từ lần khớp cuối

**Cú pháp**

```
=IE.Intraday.Change("Mã CK hoặc Mã Index",Số thứ tự)
```

Hàm IE.Intraday.Change có các tham số sau :

* **Mã chứng khoán:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... )
* **Số thứ tự**: Thứ tự lần khớp (1, 2,... tương ứng với lần khớp gần nhất, gần nhì,...)

**Trả về:**

Giá thay đổi của 1 mã hoặc index trong ngày theo số thứ tự khớp tính từ lần khớp cuối

**Ví dụ**

Để lấy giá thay đổi của mã SSI tương ứng với lần khớp thứ 10 tính từ lần khớp cuối, ta dùng công thức sau:

```
=IE.Intraday.Change("SSI",10)
```

**Kết quả:**

<mark style="color:green;">Object:</mark> giá thay đổi trả về theo đơn vị đồng, ví dụ **650**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1), ghi số thứ tự ở một ô (ví dụ A2), và dùng công thức sau:

```
=IE.Intraday.Change(A1,A2)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán, số thứ tự mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.&#x20;
{% endhint %}

Tham số thứ tự cũng có thể sử dụng hàm lấy số dòng hoặc số cột để thay thế, trong trường hợp bạn muốn lấy thông tin của nhiều lần khớp. Bạn có thể dùng công thức sau, với giả sử ô A1 chứa mã, và bạn sử dụng công thức cho ô A2 trở đi:

```
=IE.Intraday.Change(A$1, ROW()-1)
```

## IE.Intraday.LastPrice

Lấy giá khớp lệnh trong ngày của 1 mã hoặc index theo số thứ tự khớp tính từ lần khớp cuối

**Cú pháp**

```
=IE.Intraday.LastPrice("Mã CK hoặc Mã Index",Số thứ tự)
```

Hàm IE.Intraday.LastPrice có các tham số sau :

* **Mã chứng khoán:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,...)
* **Số thứ tự**: Thứ tự lần khớp (1, 2,... tương ứng với lần khớp gần nhất, gần nhì,...)

**Trả về:**

Giá khớp của 1 mã hoặc index trong ngày theo số thứ tự khớp tính từ lần khớp cuối

**Ví dụ**

Để lấy giá thay đổi của mã SSI tương ứng với lần khớp thứ 10 tính từ lần khớp cuối, ta dùng công thức sau:

```
=IE.Intraday.LastPrice("SSI",10)
```

**Kết quả:**

<mark style="color:green;">Object:</mark> giá khớp trả về theo đơn vị đồng, ví dụ **21750**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1), ghi số thứ tự ở một ô (ví dụ A2) và dùng công thức sau:

```
=IE.Intraday.LastPrice(A1,A2)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán, số thứ tự mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.&#x20;
{% endhint %}

Tham số thứ tự cũng có thể sử dụng hàm lấy số dòng hoặc số cột để thay thế, trong trường hợp bạn muốn lấy thông tin của nhiều lần khớp. Bạn có thể dùng công thức sau, với giả sử ô A1 chứa mã, và bạn sử dụng công thức cho ô A2 trở đi:

```
=IE.Intraday.LastPrice(A$1, ROW()-1)
```

## IE.Intraday.LastVol

Lấy khối lượng khớp lệnh trong ngày của 1 mã hoặc index theo số thứ tự khớp tính từ lần khớp cuối

**Cú pháp**

```
=IE.Intraday.LastVol("Mã CK hoặc Mã Index",Số thứ tự)
```

Hàm IE.Intraday.LastVol có các tham số sau :

* **Mã chứng khoán:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... )
* **Số thứ tự**: Thứ tự lần khớp (1, 2,... tương ứng với lần khớp gần nhất, gần nhì,...)

**Trả về:**

Khối lượng khớp của 1 mã hoặc index trong ngày theo số thứ tự khớp tính từ lần khớp cuối

**Ví dụ**

Để lấy khối lượng khớp của mã SSI tương ứng với lần khớp thứ 10 tính từ lần khớp cuối, ta dùng công thức sau:

```
=IE.Intraday.LastVol("SSI",10)
```

**Kết quả:**

<mark style="color:green;">Object:</mark> khối lượng khớp, ví dụ **600**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1), ghi số thứ tự ở một ô (ví dụ A2) và dùng công thức sau:

```
=IE.Intraday.LastVol(A1,A2)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán, số thứ tự mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.&#x20;
{% endhint %}

Tham số thứ tự cũng có thể sử dụng hàm lấy số dòng hoặc số cột để thay thế, trong trường hợp bạn muốn lấy thông tin của nhiều lần khớp. Bạn có thể dùng công thức sau, với giả sử ô A1 chứa mã, và bạn sử dụng công thức cho ô A2 trở đi:

```
=IE.Intraday.LastVol(A$1, ROW()-1)
```

## IE.Intraday.RatioChange

Lấy tỉ lệ giá thay đổi trong ngày của 1 mã hoặc index theo số thứ tự khớp tính từ lần khớp cuối

**Cú pháp**

```
=IE.Intraday.RatioChange("Mã CK hoặc Mã Index",Số thứ tự)
```

Hàm IE.Intraday.RatioChange có các tham số sau :

* **Mã chứng khoán:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... )
* **Số thứ tự**: Thứ tự lần khớp (1, 2,... tương ứng với lần khớp gần nhất, gần nhì,...)

**Trả về:**

Tỷ lệ giá thay đổi của 1 mã hoặc index trong ngày theo số thứ tự khớp tính từ lần khớp cuối

**Ví dụ**

Để lấy tỷ lệ giá thay đổi của mã SSI tương ứng với lần khớp thứ 10 tính từ lần khớp cuối, ta dùng công thức sau:

```
=IE.Intraday.RatioChange("SSI",10)
```

**Kết quả:**

<mark style="color:green;">Object:</mark> tỷ lệ giá thay đổi, ví dụ **3.08**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1), ghi số thứ tự ở một ô (ví dụ A2) và dùng công thức sau:

```
=IE.Intraday.RatioChange(A1,A2)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán, số thứ tự mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.&#x20;
{% endhint %}

Tham số thứ tự cũng có thể sử dụng hàm lấy số dòng hoặc số cột để thay thế, trong trường hợp bạn muốn lấy thông tin của nhiều lần khớp. Bạn có thể dùng công thức sau, với giả sử ô A1 chứa mã, và bạn sử dụng công thức cho ô A2 trở đi:

```
=IE.Intraday.RatioChange(A$1, ROW()-1)
```

## IE.Intraday.Time

Lấy thời gian khớp lệnh trong ngày của 1 mã hoặc index theo số thứ tự khớp tính từ lần khớp cuối

**Cú pháp**

```
=IE.Intraday.Time("Mã CK hoặc Mã Index",Số thứ tự)
```

Hàm IE.Intraday.Time có các tham số sau :

* **Mã chứng khoán:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... )
* **Số thứ tự**: Thứ tự lần khớp (1, 2,... tương ứng với lần khớp gần nhất, gần nhì,...)

**Trả về:**

Thời gian khớp lệnh của 1 mã hoặc index trong ngày theo số thứ tự khớp tính từ lần khớp cuối

**Ví dụ**

Để lấy thời gian khớp lệnh của mã SSI tương ứng với lần khớp thứ 10 tính từ lần khớp cuối, ta dùng công thức sau:

```
=IE.Intraday.Time("SSI",10)
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thời gian khớp lệnh trả về theo định dạng hh:mm:ss, ví dụ **11:09:30**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1), ghi số thứ tự ở một ô (ví dụ A2) và dùng công thức sau:

```
=IE.Intraday.Time(A1,A2)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán, số thứ tự mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.&#x20;
{% endhint %}

Tham số thứ tự cũng có thể sử dụng hàm lấy số dòng hoặc số cột để thay thế, trong trường hợp bạn muốn lấy thông tin của nhiều lần khớp. Bạn có thể dùng công thức sau, với giả sử ô A1 chứa mã, và bạn sử dụng công thức cho ô A2 trở đi:

```
=IE.Intraday.Time(A$1, ROW()-1)
```

## IE.Intraday.TotalVol

Lấy tổng khối lượng khớp trong ngày của 1 mã hoặc index theo số thứ tự khớp tính từ lần khớp cuối

**Cú pháp**

```
=IE.Intraday.TotalVol("Mã CK hoặc Mã Index",Số thứ tự)
```

Hàm IE.Intraday.TotalVol có các tham số sau :

* **Mã chứng khoán:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... )
* **Số thứ tự**: Thứ tự lần khớp (1, 2,... tương ứng với lần khớp gần nhất, gần nhì,...)

**Trả về:**

Tổng khối lượng khớp của 1 mã hoặc index trong ngày theo số thứ tự khớp tính từ lần khớp cuối

**Ví dụ**

Để lấy tổng khối lượng khớp của mã SSI tương ứng với lần khớp thứ 10 tính từ lần khớp cuối, ta dùng công thức sau:

```
=IE.Intraday.TotalVol("SSI",10)
```

**Kết quả:**

<mark style="color:green;">Object:</mark> tổng khối lượng khớp, ví dụ 13567800

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1), ghi số thứ tự ở một ô (ví dụ A2) và dùng công thức sau:

```
=IE.Intraday.TotalVol(A1,A2)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán, số thứ tự mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.&#x20;
{% endhint %}

Tham số thứ tự cũng có thể sử dụng hàm lấy số dòng hoặc số cột để thay thế, trong trường hợp bạn muốn lấy thông tin của nhiều lần khớp. Bạn có thể dùng công thức sau, với giả sử ô A1 chứa mã, và bạn sử dụng công thức cho ô A2 trở đi:

```
=IE.Intraday.TotalVol(A$1, ROW()-1)
```

## IE.Intraday.TradingDate

Lấy ngày khớp lệnh trong ngày của 1 mã hoặc index

**Cú pháp**

```
=IE.Intraday.TradingDate("Mã CK hoặc Mã Index",Số thứ tự)
```

Hàm IE.Intraday.TradingDate có các tham số sau :

* **Mã chứng khoán:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... )
* **Số thứ tự**: Thứ tự lần khớp (1, 2,... tương ứng với lần khớp gần nhất, gần nhì,...)

**Trả về:**

Ngày khớp lệnh của 1 mã hoặc index trong ngày theo số thứ tự khớp tính từ lần khớp cuối

**Ví dụ**

Để lấy ngày khớp lệnh của mã SSI tương ứng với lần khớp thứ 10 tính từ lần khớp cuối, ta dùng công thức sau:

```
=IE.Intraday.TradingDate("SSI",10)
```

**Kết quả:**

<mark style="color:green;">Object:</mark> ngày khớp lệnh trả về theo định dạng dd/mm/yyyy, ví dụ **21/04/2023**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1), ghi số thứ tự ở một ô (ví dụ A2) và dùng công thức sau:

```
=IE.Intraday.TradingDate(A1,A2)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán, số thứ tự mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.&#x20;
{% endhint %}

Tham số thứ tự cũng có thể sử dụng hàm lấy số dòng hoặc số cột để thay thế, trong trường hợp bạn muốn lấy thông tin của nhiều lần khớp. Bạn có thể dùng công thức sau, với giả sử ô A1 chứa mã, và bạn sử dụng công thức cho ô A2 trở đi:

```
=IE.Intraday.TradingDate(A$1, ROW()-1)
```
