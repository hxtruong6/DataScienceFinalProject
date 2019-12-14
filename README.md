# Data Science Final Project

![alt text](https://devcrew.io/wp-content/uploads/2017/03/feature-1.jpg "Title")

## Thành viên nhóm

-   Nguyễn Thanh Tuấn 1612
-   Hoàng Xuân Trường 1612899

## Ý tưởng:

-   Dự đoán giá laptop, tablet từ các thông tin cấu thành (hãng, CPU, ram, gpu,...)
    -   Input: các thông tin của mấy tính: hãng, CPU, ram, ...
    -   Output: Giá sản phẩm.

## Ứng dụng:

-   Người dùng: Gợi ý giá sản phẩm cho người dùng khi người dùng muốn mua 1 sản phẩm laptop, tablet với cấu hình mong muốn.

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

### Thông tin dữ liệu

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

### Dataset

-   Dữ liệu chưa được clean và preproccessing
-   File `*.csv`
-   Nằm trong thư mục `/dataset/Amazon` cho dữ liệu của Amazon và `/dataset/BestBuy` cho dữ liệu của trang web Bestbuy
