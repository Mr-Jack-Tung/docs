---
description: Các hàm lấy thông tin từ bảng cân đối kế toán
---

# Lớp hàm IE.BalanceSheet

## **Mô tả**

Các hàm thuộc nhóm này cho phép lấy 3 loại thông tin từ bảng CĐKT:

* **Thông tin về bảng CĐKT mới nhất:** Quý/Năm có bảng CĐKT mới nhất (Year/Quarter), năm tài chính cuối có bảng CĐKT năm
* **Chỉ tiêu tổng hợp mới nhất**: Một số hạng mục từ bảng CĐKT quý cuối  hoặc năm gần nhất&#x20;
* **Toàn bộ Bảng CĐKT**: Bảng CĐKT của các năm hoặc quý đã nộp báo cáo                                                                         &#x20;

## Nhóm hàm lấy thông tin về bảng cân đối kế toán mới nhất&#x20;

**Cú pháp**                                                                           &#x20;

Biểu thức lấy năm của bảng CĐKT mới nhất của mã chứng khoán:

```
=IE.BalanceSheet.Year("Mã CK")
```

Biểu thức lấy quý và năm của bảng CĐKT mới nhất của mã chứng khoán:&#x20;

```
=IE.BalanceSheet.Quarter("Mã CK")
```

**Trong đó:**

* **Mã CK:** là mã cổ phiếu niêm yết                                                                           &#x20;

## Nhóm hàm lấy các chỉ tiêu tổng hợp mới nhất từ bảng cân đối kế toán

**Cú pháp**

Biểu thức lấy một chỉ tiêu tổng hợp mới nhất từ bảng CĐKT**:**&#x20;

```
=FA.BalanceSheet.[Chỉ tiêu bảng CĐKT]("Mã CK", Năm báo cáo, Quý báo cáo) 
```

**Trong đó:**

* **Mã CK:** là mã cổ phiếu niêm yết
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm
* **Chỉ tiêu bảng CĐKT:** là một chỉ tiêu tương ứng trong bảng CĐKT

**Ví dụ**

Để lấy tổng tài sản ngắn hạn năm 2022 quý 2 của mã SSI ta dùng công thức:&#x20;

```
=FA.BalanceSheet.CurrentAssets("SSI",2022,2) 
```

Các chỉ tiêu chính được sử dụng để tính toán các chỉ số tài chính, các chỉ tiêu còn lại chỉ có ý nghĩa thuyết minh và không được sử dụng trong các tính toán. Bên cạnh các chỉ tiêu có sẵn trong bảng CĐKT, chúng tôi cũng tổ hợp 1 số chỉ tiêu không có sẵn trong các báo cáo tài chính theo chuẩn VAS, nhưng có trong các báo cáo tài chính theo chuẩn IAS, như nợ phải trả lãi, tài sản sinh lãi, ...&#x20;

## Hàm lấy toàn bộ bảng cân đối kế toán

**Cú pháp**

Biểu thức lấy toàn bộ một hay nhiều bảng CĐKT:&#x20;

```
=IE.BalanceSheet.Reports("Mã CK", Năm, Quý, Số lượng báo cáo) 
```

**Trong đó:**

* **Mã CK:** là mã cổ phiếu niêm yết&#x20;
* **Năm:** là năm tương ứng với bảng CĐKT&#x20;
* **Quý:** là quý tương ứng với báo cáo. Nếu Quý bằng 5 thì bảng CĐKT là bảng CĐKT năm&#x20;
* **Số lượng báo cáo:** là số bảng CĐKT muốn lấy ra tính từ bảng CĐKT ứng với các tham số Năm và Quý.&#x20;

**Ví dụ**

Để lấy 4 bảng CĐKT theo quý, tính từ quý 2/2021 trở về trước của mã SSI, ta dùng công thức:&#x20;

<pre><code><strong>=IE.BalanceSheet.Reports("SSI", 2021, 2, 4)
</strong></code></pre>

{% hint style="info" %}
**Lưu ý**: do các loại hình doanh nghiệp khác nhau, nên có 1 số chỉ tiêu chỉ có ở loại hình doanh nghiệp này, mà không có ở các loại hình doanh nghiệp khác
{% endhint %}

## IE.BalanceSheet.Cash

Hiển thị số dư tiền mặt trên bảng cân đối kế toán của doanh nghiệp

**Cú pháp**

```
=IE.BalanceSheet.Cash("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> số dư tiền mặt trên bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn biết công ty SSI có bao nhiều tiền mặt ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.BalanceSheet.Cash("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.Cash(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.BalanceSheet.CurrentAssets

Hiển thị số dư tổng tài sản ngắn hạn trên bảng cân đối kế toán của doanh nghiệp

**Cú pháp**

```
=IE.BalanceSheet.CurrentAssets("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> số dư tổng tài sản ngắn hạn trên bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn biết công ty SSI có số dư tổng tài sản ngắn hạn ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.BalanceSheet.CurrentAssets("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.CurrentAssets(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.BalanceSheet.CurrentLiabilities

Hiển thị số dư tổng nợ ngắn hạn trên bảng cân đối kế toán của doanh nghiệp

**Cú pháp:**

```
=IE.BalanceSheet.CurrentLiabilities("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> số dư tổng nợ ngắn hạn trên bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn biết công ty SSI có số dư tổng nợ ngắn hạn ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.BalanceSheet.CurrentLiabilities("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.CurrentLiabilities(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.BalanceSheet.FixedAssets

Hiển thị số dư tổng tài sản cố định trên bảng cân đối kế toán của doanh nghiệp

**Cú pháp**

```
=IE.BalanceSheet.CurrentLiabilities("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> số dư tổng nợ ngắn hạn trên bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn biết công ty SSI có số dư tổng nợ ngắn hạn ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.BalanceSheet.CurrentLiabilities("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.CurrentLiabilities(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.BalanceSheet.HolderEquity

Hiển thị số dư vốn chủ sở hữu trên bảng cân đối kế toán của doanh nghiệp

**Cú pháp**

```
=IE.BalanceSheet.HolderEquity("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> số dư vốn chủ sở hữu trên bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn biết công ty SSI có số dư vốn chủ sở hữu ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.BalanceSheet.HolderEquity("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.HolderEquity(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.BalanceSheet.Inventory

Hiển thị số dư hàng tồn kho trên bảng cân đối kế toán của doanh nghiệp

**Cú pháp**

```
=IE.BalanceSheet.Inventory("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> số dư hàng tồn kho trên bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn biết công ty SSI có số dư hàng tồn kho ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.BalanceSheet.Inventory("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.Inventory(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.BalanceSheet.LongTermAssets

Hiển thị số dư tổng tài sản dài hạn trên bảng cân đối kế toán của doanh nghiệp

**Cú pháp**

```
=IE.BalanceSheet.LongTermAssets("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> số dư tổng tài sản dài hạn trên bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn biết công ty SSI có số dư tổng tài sản dài hạn ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.BalanceSheet.LongTermAssets("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.LongTermAssets(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.BalanceSheet.LongTermLiabilities

Hiển thị số dư tổng nợ dài hạn trên bảng cân đối kế toán của doanh nghiệp

**Cú pháp**

```
=IE.BalanceSheet.LongTermLiabilities("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> số dư tổng nợ dài hạn trên bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn biết công ty SSI có số dư tổng nợ dài hạn ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.BalanceSheet.LongTermLiabilities("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.LongTermLiabilities(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.BalanceSheet.Quarter

Lấy quý và năm có báo cáo bảng cân đối kế toán gần nhất

**Cú pháp**

```
=IE.BalanceSheet.Quarter("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> Hiển thị quý và năm có báo cáo bảng cân đối kế toán gần nhất của doanh nghiệp

**Ví dụ**

Bạn muốn biết quý và năm có báo cáo bảng cân đối kế toán gần nhất của công ty SSI, bạn dùng công thức

```
=IE.BalanceSheet.Quarter("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.BalanceSheet.Quarter(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

**Kết quả:**

Q4/2022

## IE.BalanceSheet.Reports

Hiển thị bảng cân đối kế toán của doanh nghiệp

**Cú pháp**

```
=IE.BalanceSheet.Reports("Mã chứng khoán",Năm báo cáo, Quý báo cáo,Số lượng báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm cuối cùng hiển thị báo cáo
* **Quý báo cáo:** Quý cuối cùng hiển thị báo cáo. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm
* **Số lượng báo cáo:** Số lượng báo cáo lấy về

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn hiển thị bảng cân đối kế toán của công ty SSI từ quý 2 năm 2022 trở về với số lượng 3 báo cáo , bạn dùng công thức

```
=IE.BalanceSheet.Reports("SSI",2022,2,3)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3), số lượng báo cáo lấy về ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.Reports(A1,A2,A3,A4)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo, số lượng báo cáo lấy về mà không cần gõ lại công thức

## IE.BalanceSheet.TotalAssets

Hiển thị số dư tổng tài sản trên bảng cân đối kế toán của doanh nghiệp

**Cú pháp**

```
=IE.BalanceSheet.TotalAssets("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> số dư tổng tài sản trên bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn biết công ty SSI có số dư tổng tài sản ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.BalanceSheet.TotalAssets("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.TotalAssets(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.BalanceSheet.TotalLiabilities

Hiển thị số dư tổng nợ trên bảng cân đối kế toán của doanh nghiệp

**Cú pháp**

```
=IE.BalanceSheet.TotalLiabilities("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> số dư tổng nợ trên bảng cân đối kế toán của doanh nghiệp

**Ví dụ**

Bạn muốn biết công ty SSI có số dư tổng nợ ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.BalanceSheet.TotalLiabilities("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.BalanceSheet.TotalLiabilities(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.BalanceSheet.Year

Lấy năm có báo cáo bảng cân đối kế toán gần nhất

**Cú pháp**

```
=IE.BalanceSheet.Year("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> năm có báo cáo bảng cân đối kế toán gần nhất

**Ví dụ**

Bạn muốn biết năm gần nhất có bảng cân đối kế toán của công ty SSI, bạn dùng công thức

```
=IE.BalanceSheet.Year("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.BalanceSheet.Year(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

**Kết quả:**

2022
