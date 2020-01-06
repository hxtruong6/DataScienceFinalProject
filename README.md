# Data Science Final Project

![alt text](https://devcrew.io/wp-content/uploads/2017/03/feature-1.jpg "Title")

## Thành viên nhóm

-   Nguyễn Thanh Tuấn 1612744
-   Hoàng Xuân Trường 1612899

## Tệp 
- __Slide__ :https://docs.google.com/presentation/d/1Nq5LlfNVe-uooOjxUx5RLwBN-Aha2yDpy-C7NqmzX9Y/edit?usp=sharing

## Ý tưởng:

-   Dự đoán giá laptop, tablet từ các thông tin cấu thành (hãng, CPU, ram, gpu,...)
    -   Input: các thông tin của mấy tính: hãng, CPU, ram, ...
    -   Output: Giá sản phẩm.

## Ứng dụng:

-   Người dùng: Gợi ý giá sản phẩm cho người dùng khi người dùng muốn mua 1 sản phẩm laptop, tablet với cấu hình mong muốn.
-   *Model dự đoán giá này có gì đặc biệt:*

> Model sẽ giúp người dùng tự build sản phẩm từ những linh kiện khác nhau nên người dùng không cần phải tra cứu từng linh kiện để lắp ráp. Người dùng có thể tự tìm kiếm các link kiện nhưng đó là với người dùng có kiến thức nhất định về các cấu hình máy (loại nào, hãng nào, thế hệ nào,..). Vì vậy, mô hình sẽ tốt cho *(a)* tiết kiệm thời gian tìm kiếm từng thành phần cấu hình laptop một cách chi tiết nhưng vẫn có thể có chi phí tối ưu và *(b)* dễ sử dụng với những người dùng có không có kiến thức chi tiết về cấu hình laptop đã có sẵn trong bộ dữ liệu
    

## Dữ liệu:

-   Lấy từ 2 nguồn: Bestbuy và Amazon
-   API: Không lấy được đủ thông tin -> request_html và selenium
-   Check tính hợp lệ của dữ liệu:
    -   https://www.amazon.com/robots.txt
    -   https://www.bestbuy.com/robots.txt
-   Dữ liệu hiện tại:
    -   Bestbuy: hơn 1000 items
    -   Amazon: hơn 5000 items
-   Vấn đề hiện tại:
    -   Chọn thuộc tính phù hợp
    -   Thuộc tính sản phẩm 2 nguồn khác nhau, format khác nhau, cần đồng bộ (khó ghép lại) -> giải quyết: ????
    -   Dữ liệu rác: Thuộc tính không chuẩn, thiếu

### CrThông tin dữ liệu

Một số thông tin cơ bản được crawl:

-   Price: giá của laptop
-   Screen size: kích thước của màn hình
-   RAM: bộ nhớ RAM
-   Brand Name: hãng laptop
-   Item Weigth: Khối lượng
-   Operating System: Hệ điều hành của máy
-   Color: màu của sản phẩm
-   Processor Brand: hãng sản xuất CPU (Intel, AMD, Mediatek,..)
-   Processor Count: số lượng nhân
-   Computer Memory Type: Loại RAM (DDR3, DDR4,...)
-   ...

Tất cả thuộc tính của dữ liệu:
![Screenshot from 2020-01-06 22-00-24](https://user-images.githubusercontent.com/24609363/71826679-077aae00-30d1-11ea-8243-37746325929d.png)

Một giá trị mẫu của 1 dòng:
![Screenshot from 2020-01-06 22-02-53](https://user-images.githubusercontent.com/24609363/71826678-06e21780-30d1-11ea-8f0c-dbbdb1c53bb2.png)

### Preprocessing
Dữ liệu được chọn là __Amazon__ (bỏ qua __Bestbuy__ để tránh nhiễu).

Tuy vậy, vẫn thiếu rất nhiều trường thuộc tính và tỷ lệ % thiếu cao:
![Screenshot from 2020-01-06 21-57-01](https://user-images.githubusercontent.com/24609363/71826682-077aae00-30d1-11ea-90e8-3476f8f8be8b.png)

Chọn một số thuộc tính được để tiền xử lý. Các thuộc tính khác do tỷ lệ thiếu quá cao nên sẽ bị bỏ qua. Các thuộc tính tiêu biểu:
- Giá
- Kích thước màn hình
- Độ phân giải
- Ram
- Chip xử lý
- Bộ nhớ
- Kích thước máy
- Khối lượng
- ...

~ 27 thuộc tính

#### Thuộc tính thiếu

Các thuộc tính thiếu được thay thế bởi các giá trị trung bình, 0, tần suất xuất hiện,... tùy vào trường nào đang xét sẽ có các giá trị được chọn phù hợp nhất với thuộc tính đó. 

#### Dataset

-   Dữ liệu chưa được clean và preproccessing (file `*.csv`) nằm trong thư mục `/dataset/Amazon` cho dữ liệu của Amazon và `/dataset/BestBuy` cho dữ liệu của trang web Bestbuy.
- Dữ liệu đã qua xử lý nằm ở thư mục `preprocessing` file `preprocessing.ipynb`

### Model 
### Testing & evuluation
