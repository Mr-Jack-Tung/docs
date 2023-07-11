---
description: Các hàm lấy danh sách và thông tin mã chứng khoán
---

# Lớp hàm IE.Stock

Các hàm thuộc lớp này chia làm hai loại, nhóm hàm lấy giá trị đơn, và nhóm hàm lấy giá trị dạng bảng.

Các hàm lấy thông tin mã chứng khoán (trừ thông tin hồ sơ công ty, thông tin chi tiết công ty, sự kiện, thông tin niêm yết, công ty con, công ty liên kết, công ty cùng ngành, lãnh đạo, cổ đông, tin tức), trả về giá trị đơn.&#x20;

Các hàm lấy danh sách mã chứng khoán theo sàn hoặc theo ngành, cũng như thông tin hồ sơ công ty, thông tin chi tiết công ty, sự kiện, thông tin niêm yết, công ty con, công ty liên kết, công ty cùng ngành, lãnh đạo, cổ đông, tin tức trả về giá trị dạng bảng.

## Nhóm hàm trả về giá trị đơn

**Mô tả:**

Tập hợp các hàm lấy thông tin mã chứng khoán (tên doanh nghiệp, tài sản, vốn chủ sở hữu, cổ tức …)

**Cú pháp**:&#x20;

Biểu thức lấy dữ liệu đơn có dạng:&#x20;

```
=IE.Stock.[Trường thông tin]("Mã CK")
```

**Trong đó:**

* **Mã CK:** là mã chứng khoán niêm yết&#x20;
* **Trường thông tin**: là tên trường tương ứng với thông tin nhất định về cổ phiếu

**Ví dụ:**

Nếu muốn lấy tên công ty ứng với mã SSI, ta dùng công thức:&#x20;

```
=IE.Stock.Name("SSI")
```

## **Nhóm hàm trả về giá trị dạng bảng**

**Mô tả:**

Bao gồm các hàm lấy danh sách mã chứng khoán theo sàn hoặc theo ngành, cũng như thông tin hồ sơ công ty, thông tin chi tiết công ty, sự kiện, thông tin niêm yết, công ty con, công ty liên kết, công ty cùng ngành, lãnh đạo, cổ đông, tin tức

**Cú pháp:**&#x20;

Biểu thức lấy danh sách các mã cổ phiếu của 1 sàn:&#x20;

```
=IE.Stock.SymbolsByExchange("Mã sàn")
```

Trong đó:&#x20;

* **Mã sàn**: là tên sàn giao dịch chứng khoán nơi mã cổ phiếu được niêm yết. Mã sàn có thể nhận các giá trị sau: "HSX", "HNX", "UPCOM"

Biểu thức lấy thông tin ban lãnh đạo của mã chứng khoán:&#x20;

```
=IE.Stock.ShareHolders("Mã CK")
```

**Trong đó:**&#x20;

* **Mã CK**: là mã chứng khoán niêm yết

## IE.Stock.Affilited

Lấy thông tin các công ty liên kết của mã chứng khoán

**Cú pháp**

```
=IE.Stock.Affilited("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin các công ty liên kết

**Ví dụ**

Bạn muốn biết thông tin các công ty liên kết của công ty SSI, bạn dùng công thức

```
=IE.Stock.Affilited("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.Affilited(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

## IE.Stock.Asset

Lấy thông tin tài sản của mã chứng khoán

**Cú pháp**

```
=IE.Stock.Asset("Mã chứng khoán",Năm)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm:** Năm hiển thị thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin tài sản

**Ví dụ**

Bạn muốn biết thông tin tài sản của công ty SSI năm 2022, bạn dùng công thức

```
=IE.Stock.Asset("SSI",2022)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm ở một ô(ví dụ A2) và dùng công thức

```
=IE.Stock.Asset(A1,A2)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm mà không cần gõ lại công thức

## IE.Stock.BasicInfo

Lấy thông tin hồ sơ cơ bản của công ty chứng khoán

**Cú pháp**

```
=IE.Stock.BasicInfo("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin hồ sơ cơ bản

**Ví dụ**

Bạn muốn biết thông tin hồ sơ cơ bản của công ty SSI, bạn dùng công thức

```
=IE.Stock.BasicInfo("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.BasicInfo(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

## IE.Stock.CashDividend

Lấy thông tin cổ tức của mã chứng khoán

**Cú pháp**

```
=IE.Stock.CashDividend("Mã chứng khoán",Năm)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm:** Năm hiển thị thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin cổ tức

**Ví dụ**

Bạn muốn biết thông tin cổ tức của công ty SSI năm 2022, bạn dùng công thức

```
=IE.Stock.CashDividend("SSI",2022)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm ở một ô(ví dụ A2) và dùng công thức

```
=IE.Stock.CashDividend(A1,A2)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm mà không cần gõ lại công thức

## IE.Stock.CompanyProfile

Lấy thông tin giới thiệu về công ty của mã chứng khoán

**Cú pháp**

```
=IE.Stock.CompanyProfile("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin giới thiệu về công ty

**Ví dụ**

Bạn muốn biết thông tin giới thiệu về công ty SSI, bạn dùng công thức

```
=IE.Stock.CompanyProfile("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.CompanyProfile(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

## IE.Stock.Detail

Lấy thông tin chi tiết của mã chứng khoán

**Cú pháp**

```
=IE.Stock.Detail("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin chi tiết

**Ví dụ**

Bạn muốn biết thông tin chi tiết của công ty SSI, bạn dùng công thức

```
=IE.Stock.Detail("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.Detail(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

## IE.Stock.Equity

Lấy thông tin vốn chủ sở hữu của mã chứng khoán

**Cú pháp**

```
=IE.Stock.Equity("Mã chứng khoán",Năm)
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin
* **Năm:** Năm hiển thị thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin vốn chủ sở hữu

**Ví dụ**

Bạn muốn biết thông tin vốn chủ sở hữu của công ty SSI năm 2022, bạn dùng công thức

```
=IE.Stock.Equity("SSI",2022)
```

Hoặc gõ SSI ở một ô( ví dụ A1), năm ở một ô(ví dụ A2) và dùng công thức

```
=IE.Stock.Equity(A1,A2)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, năm mà không cần gõ lại công thức

## IE.Stock.Leaderships

Lấy thông tin ban lãnh đạo của mã chứng khoán

**Cú pháp**

```
=IE.Stock.Leaderships("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin ban lãnh đạo

**Ví dụ**

Bạn muốn biết thông tin ban lãnh đạo của công ty SSI, bạn dùng công thức

```
=IE.Stock.Leaderships("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.Leaderships(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

## IE.Stock.ListingInfo

Lấy thông tin niêm yết của mã chứng khoán

**Cú pháp**

```
=IE.Stock.ListingInfo("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin niêm yết

**Ví dụ**

Bạn muốn biết thông tin niêm yết của công ty SSI, bạn dùng công thức

```
=IE.Stock.ListingInfo("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.ListingInfo(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

## IE.Stock.Name

Lấy tên công ty ứng với mã chứng khoán

**Cú pháp**

```
=IE.Stock.Name("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin tên công ty ứng với mã chứng khoán

**Ví dụ**

Bạn muốn biết thông tin tên công ty ứng với mã chứng khoán SSI, bạn dùng công thức

```
=IE.Stock.Name("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.Name(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

## IE.Stock.News

Lấy thông tin tin tức của mã chứng khoán

**Cú pháp**

```
=IE.Stock.News("Mã CK", "Từ ngày", "Đến ngày")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin
* **Từ ngày**: Từ ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Đến ngày:** Đến ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin tin tức của mã chứng khoán

**Ví dụ**

Bạn muốn lấy thông tin tin tức của mã chứng khoán SSI từ ngày 11/04/2023 đến ngày 21/04/2023, bạn dùng công thức

```
=IE.Stock.News("SSI","11/04/2023","21/04/2023")
```

Hoặc gõ SSI ở một ô( ví dụ A1), từ ngày ở 1 ô(ví dụ A2), đến ngày ở 1 ô(ví dụ A3) và dùng công thức

```
=IE.Stock.News(A1,A2,A3)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, từ ngày, đến ngày mà không cần gõ lại công thức

## IE.Stock.Peers

Lấy thông tin các công ty cùng ngành của mã chứng khoán

**Cú pháp**

```
=IE.Stock.Peers("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin các công ty cùng ngành của mã chứng khoán

**Ví dụ**

Bạn muốn biết thông tin các công ty cùng ngành của mã SSI, bạn dùng công thức

```
=IE.Stock.Peers("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.Peers(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

## IE.Stock.ShareHolders

Lấy thông tin ban lãnh đạo của mã chứng khoán

**Cú pháp**

```
=IE.Stock.ShareHolders("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin ban lãnh đạo

**Ví dụ**

Bạn muốn biết thông tin ban lãnh đạo của công ty SSI, bạn dùng công thức

```
=IE.Stock.ShareHolders("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.ShareHolders(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

## IE.Stock.Subsidiaries

Lấy thông tin các công ty con của mã chứng khoán

**Cú pháp**

```
=IE.Stock.Subsidiaries("Mã chứng khoán")
```

**Trong đó:**

* **Mã chứng khoán:** Mã chứng khoán của cổ phiếu cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin các công ty con

**Ví dụ**

Bạn muốn biết thông tin các công ty con của công ty SSI, bạn dùng công thức

```
=IE.Stock.Subsidiaries("SSI")
```

Hoặc gõ SSI ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.Subsidiaries(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán mà không cần gõ lại công thức

## IE.Stock.SymbolsByExchange

Lấy danh sách các mã chứng khoán

**Cú pháp**

```
=IE.Stock.SymbolsByExchange("Sàn")
```

**Trong đó:**

* **Sàn:** Sàn cần lấy thông tin

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> danh sách các mã chứng khoán của sàn

**Ví dụ**

Bạn muốn biết danh sách các mã chứng khoán của sàn HNX, bạn dùng công thức

```
=IE.Stock.SymbolsByExchange("HNX")
```

Hoặc gõ HNX ở một ô( ví dụ A1) và dùng công thức

```
=IE.Stock.SymbolsByExchange(A1)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi sàn mà không cần gõ lại công thức

## IE.Stock.CoporateActions

Lấy thông tin sự kiện của mã chứng khoán

**Cú pháp**

```
=IE.Stock.CoporateActions("Mã CK", "Từ ngày", "Đến ngày",Loại ngày)
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin
* **Từ ngày**: Từ ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Đến ngày:** Đến ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Loại ngày:** 1: Ngày giao dịch không hưởng quyền, 2: Ngày công bố

**Giá trị trả về:**

<mark style="color:green;">Object:</mark> thông tin sự kiện của mã chứng khoán

**Ví dụ**

Bạn muốn lấy thông tin ngày giao dịch không hưởng quyền của công ty SSI từ ngày 11/04/2023 đến ngày 21/04/2023, bạn dùng công thức

```
=IE.Stock.CoporateActions("SSI","11/04/2023","21/04/2023",1)
```

Hoặc gõ SSI ở một ô( ví dụ A1), từ ngày ở 1 ô(ví dụ A2), đến ngày ở 1 ô(ví dụ A3), loại ngày ở 1 ô(ví dụ A4) và dùng công thức

```
=IE.Stock.CoporateActions(A1,A2,A3,A4)
```

Với cách thứ 2, bạn sẽ dễ dàng thay đổi mã chứng khoán, từ ngày, đến ngày, loại ngày mà không cần gõ lại công thức
