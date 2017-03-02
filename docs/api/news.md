## Tổng quan
Domain API: https://365ok.co/ <br/>
Giao thức: HTTP POST (Form-Data), HTTP GET <br/>
Kết quả trả về: 
+ Status:200 => Thành công <br/>
+ Status: != 200 => Thông báo lỗi qua field message. <br/>

* Mô tả chung:<br/>
'page' => Kiểu int là số trang <br/>
'limit' => Số bản ghi hiển thị trên mỗi trang<br/>
'q' => Chuỗi tìm kiếm theo tên ...<br/>
'status' => Trạng thái ...<br/>


-----------------------
### 1. News(Tin tức)

*Mô tả: Lấy ra danh sách tin tức - danh sách tin tức theo danh mục

* Tham số truyền vào: GET

* Link : /api/news
```php
[             'category_id' => 'string',
             'name' => 'string',
             'status' => 'int',
             'idnot' => 'int',
             'q' => 'string',
             'page' => 'int,1',
             'limit' => 'int,20',
        ]
```

* Trả về: Object Json
```json
{
  "data": {
  },
  "status": 200,
  "message": "success"
}
```


-----------------------
### 2. Detail_News(Chi tiết tin tức)

*Mô tả: Lấy ra chi tiết tin tức và danh sách sản phẩm đi kèm

* Tham số truyền vào: GET

* Link : /api/news/{id:[0-9]+}
```php
[          
        ]
```

* Trả về: Object Json
```json
{
  "data": {
  },
  "status": 200,
  "message": "success"
}
```