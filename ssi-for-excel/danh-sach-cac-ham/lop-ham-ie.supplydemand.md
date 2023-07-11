---
description: Tập hợp các hàm lấy thông tin thông kê thị trường theo thời gian thực
---

# Lớp hàm IE.SupplyDemand

## **Cú pháp**

```
=IE.SupplyDemand.[Trường thông tin]("Mã CK hoặc Mã Index")
```

**Trong đó:**

* **Mã CK:** là mã của những chứng khoán niêm yết
* **Mã Index:** là tên Index tương ứng, ví dụ: VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30, …&#x20;
* **Trường thông tin:** là tên trường tương ứng với một thông tin nhất định về Index hoặc thị trường phiên hiện tại"

## **Ví dụ**

Muốn xem số lượng lệnh mua chủ động của mã SSI ta dùng công thức:&#x20;

```
=IE.SupplyDemand.TotalBuyTrade("SSI") 
```

Muốn xem khối lượng lệnh khớp thỏa thuận của mã SSI ta dùng công thức:&#x20;

```
=IE.SupplyDemand.TotalPTTrade("SSI")
```

## IE.SupplyDemand.TotalBuyTrade

Lấy số lượng lệnh mua chủ động của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.SupplyDemand.TotalBuyTrade("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là số lượng lệnh mua chủ động ứng với 1 ngày giao dịch trong khoảng thời gian.

## IE.SupplyDemand.TotalBuyTradeVolume

Lấy khối lượng lệnh mua chủ động của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.SupplyDemand.TotalBuyTradeVolume("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là khối lượng lệnh mua chủ động ứng với 1 ngày giao dịch trong khoảng thời gian.

## IE.SupplyDemand.TotalMatchValue

Lấy giá trị lệnh khớp của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.SupplyDemand.TotalMatchValue("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là giá trị lệnh khớp ứng với 1 ngày giao dịch trong khoảng thời gian.

## IE.SupplyDemand.TotalPTTrade

Lấy khối lượng lệnh khớp thỏa thuận của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.SupplyDemand.TotalSellTrade("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là số lượng lệnh bán chủ động ứng với 1 ngày giao dịch trong khoảng thời gian.

## IE.SupplyDemand.TotalSellTrade

Lấy số lượng lệnh bán chủ động của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.SupplyDemand.TotalSellTrade("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là số lượng lệnh bán chủ động ứng với 1 ngày giao dịch trong khoảng thời gian.

## IE.SupplyDemand.TotalSellTradeVolume

Lấy khối lượng lệnh bán chủ động của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.SupplyDemand.TotalSellTradeVolume("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là khối lượng lệnh bán chủ động ứng với 1 ngày giao dịch trong khoảng thời gian.

## IE.SupplyDemand.TradingDate

Lấy ngày giao dịch của 1 mã hoặc index trong 1 khoảng thời gian

**Cú pháp**

```
=IE.SupplyDemand.TradingDate("Mã CK", "Ngày bắt đầu", "Ngày kết thúc")
```

**Trong đó**:

* **Mã CK:** Mã chứng khoán cần lấy thông tin hoặc index (VNINDEX, HNXINDEX, UPINDEX, VN30, HNX30,...)&#x20;
* **Ngày bắt đầu**: Ngày bắt đầu lấy dữ liệu, định dạng "dd/MM/yyyy"
* **Ngày kết thúc:** Ngày kết thúc lấy dữ liệu, định dạng "dd/MM/yyyy"

**Giá trị trả về:**

Một chuỗi các giá trị trong đó mỗi phần tử là ngày giao dịch trong khoảng thời gian.

