# 23810310433-NGUYEN-HONG-PHONG-BagistoHeadless
23810310433-NGUYEN HONG PHONG-BagistoHeadless
CÂU 1:  So sánh Payload giữa REST API và GraphQL
REST API (lấy tất cả dữ liệu)
REST thường trả về toàn bộ dữ liệu của resource.
Ví dụ khi lấy danh sách sản phẩm, API có thể trả về nhiều trường như:
id
name
description
price
created_at
updated_at
images
category
inventory
 Vì trả về nhiều dữ liệu không cần thiết nên payload lớn hơn, tốn băng thông và thời gian tải.
GraphQL (chỉ lấy trường cần thiết)
GraphQL cho phép client chỉ định chính xác các trường cần lấy.
Ví dụ chỉ cần:
name
price
Query:
{
  products {
    name
    price
  }
}
Server chỉ trả về đúng các trường này → payload nhỏ hơn, tối ưu băng thông và tăng tốc độ tải dữ liệu.
Kết luận
REST API	GraphQL
Trả toàn bộ dữ liệu	Chỉ trả trường được yêu cầu
Payload lớn hơn	Payload nhỏ hơn
Có thể dư thừa dữ liệu	Tối ưu băng thông

CÂU 2:  Thay đổi giá sản phẩm dùng Query hay Mutation?
Nếu muốn thay đổi giá sản phẩm qua GraphQL, ta phải dùng:
Mutation
Giải thích
Trong GraphQL có 2 loại hành động chính:
Query
Dùng để lấy dữ liệu từ server.
Không làm thay đổi dữ liệu trong database.
Ví dụ:
query {
  products {
    name
    price
  }
}
Mutation
Dùng để tạo, cập nhật hoặc xóa dữ liệu.
Có thể thay đổi trạng thái của database.
Ví dụ cập nhật giá:
mutation {
  updateProductPrice(id: 1, price: 500) {
    id
    name
    price
  }
}
Kết luận
Lấy dữ liệu nên dùng Query
Thay đổi dữ liệu (update price) thì dùng Mutation
Vì việc cập nhật giá sản phẩm làm thay đổi dữ liệu trong hệ thống, nên phải sử dụng Mutation.
