---
description: Các hàm lấy thông tin từ Báo cáo kết quả kinh doanh
---

# Lớp hàm IE.IncomeStatement

## **Mô tả**

Các hàm thuộc nhóm này cho phép lấy 3 loại thông tin từ báo cáo KQKD:

* **Thông tin về báo cáo KQKD mới nhất:** Quý/Năm có báo cáo KQKD mới nhất (Year/Quarter), năm tài chính cuối có báo cáo KQKD năm
* **Chỉ tiêu tổng hợp mới nhất**: Một số hạng mục từ báo cáo KQKD quý cuối  hoặc năm gần nhất&#x20;
* **Toàn bộ báo cáo KQKD**: Báo cáo KQKD của các năm hoặc quý đã nộp báo cáo                                                                         &#x20;

## Nhóm hàm lấy thông tin về báo cáo kết quả kinh doanh mới nhất&#x20;

**Cú pháp**                                                                           &#x20;

Biểu thức lấy năm của báo cáo KQKD mới nhất của mã chứng khoán:

```
=IE.IncomeStatement.Year("Mã CK")
```

Biểu thức lấy quý và năm của báo cáo KQKD mới nhất của mã chứng khoán:&#x20;

```
=IE.IncomeStatement.Quarter("Mã CK")
```

**Trong đó:**

* **Mã CK:** là mã cổ phiếu niêm yết                                                                           &#x20;

## Nhóm hàm lấy các chỉ tiêu tổng hợp mới nhất từ báo cáo kế quả kinh doanh

**Cú pháp**

Biểu thức lấy một chỉ tiêu tổng hợp mới nhất từ báo cáo KQKD**:**&#x20;

```
=FA.IncomeStatement.[Chỉ tiêu bảng CĐKT]("Mã CK", Năm báo cáo, Quý báo cáo) 
```

**Trong đó:**

* **Mã CK:** là mã cổ phiếu niêm yết
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm
* **Chỉ tiêu báo cáo KQKD:** là một chỉ tiêu tương ứng trong báo cáo KQKD

**Ví dụ**

Để lấy giá trị lợi nhuận gộp năm 2022 quý 2 của mã SSI ta dùng công thức:&#x20;

```
=FA.IncomeStatement.GrossProfit("SSI",2022,2)
```

## Hàm lấy toàn bộ báo cáo kết quả kinh doanh

**Cú pháp**

Biểu thức lấy toàn bộ một hay nhiều báo cáo KQKD:&#x20;

```
=IE.IncomeStatement.Reports("Mã CK", Năm, Quý, Số lượng báo cáo) 
```

**Trong đó:**

* **Mã CK:** là mã cổ phiếu niêm yết&#x20;
* **Năm:** là năm tương ứng với báo cáo KQKD
* **Quý:** là quý tương ứng với báo cáo. Nếu Quý bằng 5 thì báo cáo KQKD là báo cáo KQKD năm&#x20;
* **Số lượng báo cáo:** là số báo cáo KQKD muốn lấy ra tính từ báo cáo KQKD ứng với các tham số Năm và Quý.&#x20;

**Ví dụ**

Để lấy 4 báo cáo KQKD theo quý, tính từ quý 2/2021 trở về trước của mã SSI, ta dùng công thức:&#x20;

<pre><code><strong>=IE.IncomeStatement.Reports("SSI", 2021, 2, 4)
</strong></code></pre>

{% hint style="info" %}
**Lưu ý**: do các loại hình doanh nghiệp khác nhau, nên có 1 số chỉ tiêu chỉ có ở loại hình doanh nghiệp này, mà không có ở các loại hình doanh nghiệp khác.
{% endhint %}

## IE.IncomeStatement.GrossProfit

Lấy lợi nhuận gộp trên báo cáo kết quả kinh doanh của doanh nghiệp

**Cú pháp**

```
=IE.IncomeStatement.GrossProfit("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> lợi nhuận gộp trên báo cáo kết quả kinh doanh của doanh nghiệp

**Ví dụ**

Bạn muốn biết giá trị lợi nhuận gộp của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.IncomeStatement.GrossProfit("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.IncomeStatement.GrossProfit(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.IncomeStatement.NetSales

Lấy doanh thu thuần trên báo cáo kết quả kinh doanh của doanh nghiệp

**Cú pháp**

```
=IE.IncomeStatement.NetSales("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> doanh thu thuần trên báo cáo kết quả kinh doanh của doanh nghiệp

**Ví dụ**

Bạn muốn biết giá trị doanh thu thuần của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.IncomeStatement.NetSales("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.IncomeStatement.NetSales(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.IncomeStatement.OtherProfit

Lấy lợi nhuận khác trên báo cáo kết quả kinh doanh của doanh nghiệp

**Cú pháp**

```
=IE.IncomeStatement.OtherProfit("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> lợi nhuận khác trên báo cáo kết quả kinh doanh của doanh nghiệp

**Ví dụ**

Bạn muốn biết giá trị lợi nhuận khác của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.IncomeStatement.OtherProfit("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.IncomeStatement.OtherProfit(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.IncomeStatement.ProfitAfterIncomeTaxes

Lấy lợi nhuận sau thuế trên báo cáo kết quả kinh doanh của doanh nghiệp

**Cú pháp**

```
=IE.IncomeStatement.ProfitAfterIncomeTaxes("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> lợi nhuận sau thuế trên báo cáo kết quả kinh doanh của doanh nghiệp

**Ví dụ**

Bạn muốn biết giá trị lợi nhuận sau thuế của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.IncomeStatement.ProfitAfterIncomeTaxes("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.IncomeStatement.ProfitAfterIncomeTaxes(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.IncomeStatement.ProfitBeforelIncomeTaxes

Lấy lợi nhuận trước thuế trên báo cáo kết quả kinh doanh của doanh nghiệp

**Cú pháp**

```
=IE.IncomeStatement.ProfitBeforelIncomeTaxes("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> lợi nhuận trước thuế trên báo cáo kết quả kinh doanh của doanh nghiệp

**Ví dụ**

Bạn muốn biết giá trị lợi nhuận trước thuế của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.IncomeStatement.ProfitBeforelIncomeTaxes("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.IncomeStatement.ProfitBeforelIncomeTaxes(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.IncomeStatement.ProfitFromFinancialActivities

Lấy lợi nhuận từ hoạt động tài chính trên báo cáo kết quả kinh doanh của doanh nghiệp

**Cú pháp**

```
=IE.IncomeStatement.ProfitFromFinancialActivities("Mã chứng khoán",Năm báo cáo, Quý báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm hiển thị thông tin
* **Quý báo cáo:** Quý hiển thị thông tin. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> lợi nhuận từ hoạt động tài chính trên báo cáo kết quả kinh doanh của doanh nghiệp

**Ví dụ**

Bạn muốn biết giá trị lợi nhuận từ hoạt động tài chính của công ty SSI ở thời điểm quý 4 năm 2022, bạn dùng công thức

```
=IE.IncomeStatement.ProfitFromFinancialActivities("SSI",2022,4)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3) và dùng công thức

```
=IE.IncomeStatement.ProfitFromFinancialActivities(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo mà không cần gõ lại công thức

**Kết quả:**

2.671.613.358.430

## IE.IncomeStatement.Quarter

Lấy quý và năm có báo cáo kết quả kinh doanh gần nhất

**Cú pháp**

```
=IE.IncomeStatement.Quarter("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> Hiển thị quý và năm có báo cáo kết quả kinh doanh gần nhất của doanh nghiệp

**Ví dụ**

Bạn muốn biết quý và năm có báo cáo kết quả kinh doanh gần nhất của công ty SSI, bạn dùng công thức

```
=IE.IncomeStatement.Quarter("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.IncomeStatement.Quarter(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

**Kết quả:**

Q4/2022

## IE.IncomeStatement.Reports

Hiển thị báo cáo kết quả kinh doanh của doanh nghiệp

**Cú pháp**

```
=IE.IncomeStatement.Reports("Mã chứng khoán",Năm báo cáo, Quý báo cáo,Số lượng báo cáo)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm báo cáo:** Năm cuối cùng hiển thị báo cáo
* **Quý báo cáo:** Quý cuối cùng hiển thị báo cáo. Quý I,II,III,IV tương ứng 1,2,3,4. Đặt bằng 5 nếu muốn lấy báo cáo theo năm
* **Số lượng báo cáo:** Số lượng báo cáo lấy về

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> báo cáo kết quả kinh doanh của doanh nghiệp

**Ví dụ**

Bạn muốn hiển thị báo cáo kết quả kinh doanh của công ty SSI từ quý 2 năm 2022 trở về với số lượng 3 báo cáo , bạn dùng công thức

```
=IE.IncomeStatement.Reports("SSI",2022,2,3)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm báo cáo ở một ô(ví dụ A2), quý báo cáo ở một ô(ví dụ A3), số lượng báo cáo lấy về ở một ô(ví dụ A3) và dùng công thức

```
=IE.IncomeStatement.Reports(A1,A2,A3,A4)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm báo cáo, quý báo cáo, số lượng báo cáo lấy về mà không cần gõ lại công thức

## IE.IncomeStatement.Year

Lấy năm có báo cáo kết quả kinh doanh gần nhất

**Cú pháp**

```
=IE.IncomeStatement.Year("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> năm có báo cáo kết quả kinh doanh gần nhất

**Ví dụ**

Bạn muốn biết năm gần nhất có báo cáo kết quả kinh doanh của công ty SSI, bạn dùng công thức

```
=IE.IncomeStatement.Year("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.IncomeStatement.Year(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

**Kết quả:**

2022
