---
description: >-
  Tập hợp các hàm lấy thông tin liên quan đến giao dịch của mã cổ phiếu ở thời
  điểm hiện tại
---

# Lớp hàm IE.Quote

## **Cú pháp**

```
=IE.Intraday.[Trường thông tin]("Mã CK hoặc Mã Index",Số thứ tự)
```

**Trong đó:**

* **Mã CK:** là mã của những chứng khoán niêm yết
* **Mã Index:** là tên Index tương ứng, ví dụ: VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30, …&#x20;
* **Trường thông tin**: tên trường tương ứng với một thông tin nhất định của mã chứng khoán

## Ví dụ

Nếu muốn lấy giá bán tốt nhất hiện tại của mã SSI, nhập biểu thức:&#x20;

```
=FA.Quote.AskPrice1("SSI")
```

Bạn cũng có thể ghi mã chứng khoán ở một ô (cell), ví dụ A1, và dùng công thức sau:

```
=FA.Intraday.AskPrice1(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.AskPrice1

Lấy giá đặt bán tốt nhất của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.AskPrice1("Mã CK")
```

Hàm IE.Quote.AskPrice1 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Giá đặt bán tốt nhất của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy giá đặt bán tốt nhất của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.AskPrice1("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> giá đặt bán tốt nhất của mã tại thời điểm hiện tại, ví dụ **21800**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.AskPrice1(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.&#x20;
{% endhint %}

## IE.Quote.AskPrice2

Lấy giá đặt bán tốt nhì của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.AskPrice2("Mã CK")
```

Hàm IE.Quote.AskPrice2 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Giá đặt bán tốt nhì của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy giá đặt bán tốt nhì của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.AskPrice2("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> giá đặt bán tốt nhì của mã tại thời điểm hiện tại, ví dụ **21800**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.AskPrice2(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.AskPrice3

Lấy giá đặt bán tốt thứ ba của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.AskPrice3("Mã CK")
```

Hàm IE.Quote.AskPrice3 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Giá đặt bán tốt thứ ba của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy giá đặt bán tốt thứ ba của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.AskPrice3("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> giá đặt bán tốt thứ ba của mã tại thời điểm hiện tại, ví dụ **21800**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.AskPrice3(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.AskVol1

Lấy khối lượng đặt bán tương ứng giá đặt bán tốt nhất của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.AskVol1("Mã CK")
```

Hàm IE.Quote.AskVol1 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Khối lượng đặt bán tương ứng giá đặt bán tốt nhất của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy khối lượng đặt bán tương ứng giá đặt bán tốt nhất của mã tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.AskVol1("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> khối lượng đặt bán tương ứng giá đặt bán tốt nhất của mã tại thời điểm hiện tại, ví dụ **301000**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.AskVol1(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.AskVol2

Lấy khối lượng đặt bán tương ứng giá đặt bán tốt nhì của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.AskVol2("Mã CK")
```

Hàm IE.Quote.AskVol2 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Khối lượng đặt bán tương ứng giá đặt bán tốt nhì của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy khối lượng đặt bán tương ứng giá đặt bán tốt nhì của mã tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.AskVol2("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> khối lượng đặt bán tương ứng giá đặt bán tốt nhì của mã tại thời điểm hiện tại, ví dụ **301000**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.AskVol2(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.AskVol3

Lấy khối lượng đặt bán tương ứng giá đặt bán tốt thứ ba của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.AskVol3("Mã CK")
```

Hàm IE.Quote.AskVol3 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Khối lượng đặt bán tương ứng giá đặt bán tốt thứ ba của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy khối lượng đặt bán tương ứng giá đặt bán tốt thứ ba của mã tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.AskVol3("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> khối lượng đặt bán tương ứng giá đặt bán tốt thứ ba của mã tại thời điểm hiện tại, ví dụ **301000**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.AskVol3(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.AvgPrice

Lấy giá khớp trung bình trong ngày của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.AvgPrice("Mã CK")
```

Hàm IE.Quote.AvgPrice có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Giá khớp trung bình trong ngày của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy giá khớp trung bình trong ngày của mã tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.AvgPrice("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> giá khớp trung bình trong ngày của mã tại thời điểm hiện tại, ví dụ **21766.59**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.AvgPrice(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.BidPrice1

Lấy giá đặt mua tốt nhất của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.BidPrice1("Mã CK")
```

Hàm IE.Quote.BidPrice1 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Giá đặt mua tốt nhất của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy giá đặt mua tốt nhất của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.BidPrice1("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> giá đặt mua tốt nhất của mã tại thời điểm hiện tại, ví dụ **21800**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.BidPrice1(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.BidPrice2

Lấy giá đặt mua tốt nhì của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.BidPrice2("Mã CK")
```

Hàm IE.Quote.BidPrice2 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Giá đặt mua tốt nhì của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy giá đặt mua tốt nhì của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.BidPrice2("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> giá đặt mua tốt nhì của mã tại thời điểm hiện tại, ví dụ **21800**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.BidPrice2(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.BidPrice3

Lấy giá đặt mua tốt thứ ba của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.BidPrice3("Mã CK")
```

Hàm IE.Quote.BidPrice3 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Giá đặt mua tốt thứ ba của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy giá đặt mua tốt thứ ba của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.BidPrice3("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> giá đặt mua tốt thứ ba của mã tại thời điểm hiện tại, ví dụ **21800**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.BidPrice3(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.BidPVol1

Lấy khối lượng đặt mua tương ứng giá đặt mua tốt nhất của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.BidPVol1("Mã CK")
```

Hàm IE.Quote.BidPVol1 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Khối lượng đặt mua tương ứng giá đặt mua tốt nhất của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy khối lượng đặt mua tương ứng giá đặt mua tốt nhất của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.BidPVol1("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> khối lượng đặt mua tương ứng giá đặt mua tốt nhất của mã tại thời điểm hiện tại, ví dụ **301000**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.BidPVol1(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.BidPVol2

Lấy khối lượng đặt mua tương ứng giá đặt mua tốt nhì của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.BidPVol2("Mã CK")
```

Hàm IE.Quote.BidPVol2 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Khối lượng đặt mua tương ứng giá đặt mua tốt nhì của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy khối lượng đặt mua tương ứng giá đặt mua tốt nhì của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.BidPVol2("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> khối lượng đặt mua tương ứng giá đặt mua tốt nhì của mã tại thời điểm hiện tại, ví dụ **301000**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.BidPVol2(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.BidPVol3

Lấy khối lượng đặt mua tương ứng giá đặt mua tốt thứ ba của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.BidPVol3("Mã CK")
```

Hàm IE.Quote.BidPVol3 có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Khối lượng đặt mua tương ứng giá đặt mua tốt thứ ba của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy khối lượng đặt mua tương ứng giá đặt mua tốt thứ ba của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.BidPVol3("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> khối lượng đặt mua tương ứng giá đặt mua tốt thứ ba của mã tại thời điểm hiện tại, ví dụ **301000**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.BidPVol3(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.Change

Lấy thông tin thay đổi của giá khớp gần nhất so với giá tham chiếu

**Cú pháp**

```
=IE.Quote.Change("Mã CK")
```

Hàm IE.Quote.Change có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Thông tin thay đổi của giá khớp gần nhất so với giá tham chiếu

**Ví dụ**

Để lấy thông tin thay đổi của giá khớp gần nhất so với giá tham chiếu của mã SSI, ta dùng công thức sau:

```
=IE.Quote.Change("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin thay đổi của giá khớp gần nhất so với giá tham chiếu, ví dụ **800**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.Change(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.EstMatchedPrice

Lấy giá khớp dự kiến trong ngày của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.EstMatchedPrice("Mã CK")
```

Hàm IE.Quote.EstMatchedPrice có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Thông tin giá khớp dự kiến trong ngày của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy thông tin giá khớp dự kiến trong ngày của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.EstMatchedPrice("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin giá khớp dự kiến trong ngày của mã tại thời điểm hiện tại, ví dụ **21650**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.EstMatchedPrice(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.High

Lấy giá khớp cao nhất trong ngày của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.High("Mã CK")
```

Hàm IE.Quote.High có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về**

Thông tin giá khớp cao nhất trong ngày của mã tại thời điểm hiện tại

**Ví dụ:**

Để lấy thông tin giá khớp cao nhất trong ngày của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.High("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin giá khớp cao nhất trong ngày của mã tại thời điểm hiện tại, ví dụ **21650**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.High(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.IndexValue

Lấy chỉ số index tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.IndexValue("Mã Index")
```

Hàm IE.Quote.IndexValue có các tham số sau :

* **Mã Index:** Mã index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... ) cần lấy thông tin

**Trả về:**

Thông tin chỉ số index tại thời điểm hiện tại

**Ví dụ**

Để lấy thông tin chỉ số VNINDEX tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.IndexValue("VNINDEX")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin chỉ số index tại thời điểm hiện tại, ví dụ **1042.91**

Bạn cũng có thể ghi VNINDEX ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.IndexValue(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã index mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã index, thì ở ô đó cần chứa index. Trong trường hợp này mã index không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.LastPrice

Lấy giá khớp gần nhất trong ngày của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.LastPrice("Mã CK")
```

Hàm IE.Quote.LastPrice có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Thông tin giá khớp gần nhất trong ngày của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy thông tin giá khớp gần nhất trong ngày của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.LastPrice("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin giá khớp gần nhất trong ngày của mã tại thời điểm hiện tại, ví dụ **21650**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.High(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.LastVol

Lấy khối lượng khớp gần nhất trong ngày của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.LastVol("Mã CK")
```

Hàm IE.Quote.LastVol có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Thông tin khối lượng khớp gần nhất trong ngày của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy thông tin khối lượng khớp gần nhất trong ngày của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.LastVol("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin khối lượng khớp gần nhất trong ngày của mã tại thời điểm hiện tại, ví dụ **21650**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.LastVol(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.Low

Lấy giá khớp thấp nhất trong ngày của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.Low("Mã CK")
```

Hàm IE.Quote.Low có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Thông tin giá khớp thấp nhất trong ngày của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy thông tin giá khớp thấp nhất trong ngày của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.Low("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin giá khớp thấp nhất trong ngày của mã tại thời điểm hiện tại, ví dụ **21650**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.Low(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.PriceCeiling

Lấy giá trần trong ngày của mã

**Cú pháp**

```
=IE.Quote.PriceCeiling("Mã CK")
```

Hàm IE.Quote.PriceCeiling có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Thông tin giá trần trong ngày của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy thông tin giá trần trong ngày của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.PriceCeiling("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin giá trần trong ngày của mã tại thời điểm hiện tại, ví dụ **21650**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.PriceCeiling(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.PriceFloor

Lấy giá sàn trong ngày của mã

**Cú pháp**

```
=IE.Quote.PriceFloor("Mã CK")
```

Hàm IE.Quote.PriceFloor có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Thông tin giá sàn trong ngày của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy thông tin giá sàn trong ngày của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.PriceFloor("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin giá sàn trong ngày của mã tại thời điểm hiện tại, ví dụ **21650**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.PriceFloor(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.PriceRef

Lấy giá tham chiếu trong ngày của mã

**Cú pháp**

```
=IE.Quote.PriceRef("Mã CK")
```

Hàm IE.Quote.PriceRef có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Thông tin giá tham chiếu trong ngày của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy thông tin giá tham chiếu trong ngày của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.PriceRef("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin giá tham chiếu trong ngày của mã tại thời điểm hiện tại, ví dụ **21650**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.PriceRef(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.PriorIndexValue

Lấy chỉ số index ngày hôm trước

**Cú pháp**

```
=IE.Quote.PriorIndexValue("Mã Index")
```

Hàm IE.Quote.PriorIndexValue có các tham số sau :

* **Mã Index:** Mã index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... ) cần lấy thông tin

**Trả về:**

Thông tin chỉ số index ngày hôm trước

**Ví dụ**

Để lấy thông tin chỉ số VNINDEX ngày hôm trước, ta dùng công thức sau:

```
=IE.Quote.PriorIndexValue("VNINDEX")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin chỉ số index ngày hôm trước, ví dụ **1042.91**

Bạn cũng có thể ghi VNINDEX ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.PriorIndexValue(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã index mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã index, thì ở ô đó cần chứa index. Trong trường hợp này mã index không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.Time

Lấy thời gian khớp gần nhất trong ngày của mã index

**Cú pháp**

```
=IE.Quote.Time("Mã Index")
```

Hàm IE.Quote.Time có các tham số sau :

* **Mã Index:** Mã index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... ) cần lấy thông tin

**Trả về:**

Thông tin thời gian khớp gần nhất trong ngày của mã index

**Ví dụ**

Để lấy thông tin thời gian khớp gần nhất trong ngày của mã index, ta dùng công thức sau:

```
=IE.Quote.Time("VNINDEX")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin thời gian khớp gần nhất trong ngày của mã index, ví dụ **1042.91**

Bạn cũng có thể ghi VNINDEX ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.Time(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã index mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã index, thì ở ô đó cần chứa index. Trong trường hợp này mã index không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.TotalQtty

Lấy khối lượng khớp trong ngày của mã index

**Cú pháp**

```
=IE.Quote.TotalQtty("Mã Index")
```

Hàm IE.Quote.TotalQtty có các tham số sau :

* **Mã Index:** Mã index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... ) cần lấy thông tin

**Trả về:**

Thông tin khối lượng khớp trong ngày của mã index

**Ví dụ**

Để lấy thông tin khối lượng khớp trong ngày của mã index, ta dùng công thức sau:

```
=IE.Quote.TotalQtty("VNINDEX")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin khối lượng khớp trong ngày của mã index, ví dụ **553030161**

Bạn cũng có thể ghi VNINDEX ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.TotalQtty(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã index mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã index, thì ở ô đó cần chứa index. Trong trường hợp này mã index không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.TotalTrade

Lấy số lượng lệnh khớp trong ngày của mã index

**Cú pháp**

```
=IE.Quote.TotalTrade("Mã Index")
```

Hàm IE.Quote.TotalTrade có các tham số sau :

* **Mã Index:** Mã index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... ) cần lấy thông tin

**Trả về:**

Thông tin số lượng lệnh khớp trong ngày của mã index

**Ví dụ**

Để lấy thông tin số lượng lệnh khớp trong ngày của mã index, ta dùng công thức sau:

```
=IE.Quote.TotalTrade("VNINDEX")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin số lượng lệnh khớp trong ngày của mã index, ví dụ **1042.91**

Bạn cũng có thể ghi VNINDEX ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.TotalTrade(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã index mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã index, thì ở ô đó cần chứa index. Trong trường hợp này mã index không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.TotalValue

Lấy giá trị khớp trong ngày của mã index

**Cú pháp**

```
=IE.Quote.TotalValue("Mã Index")
```

Hàm IE.Quote.TotalValue có các tham số sau :

* **Mã Index:** Mã index (VNINDEX, HNXINDEX, UPCOM, VN30, HNX30,... ) cần lấy thông tin

**Trả về:**

Thông tin giá trị khớp trong ngày của mã index

**Ví dụ**

Để lấy thông tin giá trị khớp trong ngày của mã index, ta dùng công thức sau:

```
=IE.Quote.TotalValue("VNINDEX")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin giá trị khớp trong ngày của mã index, ví dụ **1042.91**

Bạn cũng có thể ghi VNINDEX ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.TotalValue(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã index mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã index, thì ở ô đó cần chứa index. Trong trường hợp này mã index không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.TradingSession

Lấy thông tin phiên giao dịch của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.TradingSession("Mã CK")
```

Hàm IE.Quote.TradingSession có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Thông tin phiên giao dịch của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy thông tin phiên giao dịch của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.TradingSession("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin phiên giao dịch của mã tại thời điểm hiện tại, ví dụ **LO**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.TradingSession(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}

## IE.Quote.Volumn

Lấy tổng khối lượng khớp trong ngày của mã tại thời điểm hiện tại

**Cú pháp**

```
=IE.Quote.Volumn("Mã CK")
```

Hàm IE.Quote.Volumn có các tham số sau :

* **Mã CK:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Trả về:**

Thông tin tổng khối lượng khớp trong ngày của mã tại thời điểm hiện tại

**Ví dụ**

Để lấy thông tin tổng khối lượng khớp trong ngày của mã SSI tại thời điểm hiện tại, ta dùng công thức sau:

```
=IE.Quote.Volumn("SSI")
```

**Kết quả:**

<mark style="color:green;">Object:</mark> thông tin tổng khối lượng khớp trong ngày của mã tại thời điểm hiện tại, ví dụ **21650**

Bạn cũng có thể ghi mã SSI ở một ô (ví dụ A1) và dùng công thức sau:

```
=IE.Quote.Volumn(A1)
```

Ưu điểm của phương pháp này là bạn có thể thay đổi mã chứng khoán mà không cần sửa công thức.

{% hint style="info" %}
**Lưu ý**: Nếu bạn truyền ô vào thay vì mã chứng khoán, thì ở ô đó cần chứa mã chứng khoán. Trong trường hợp này mã chứng khoán không cần nằm giữa 2 dấu nháy đôi.
{% endhint %}
