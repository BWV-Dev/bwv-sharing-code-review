# Sharing content review code


## Table of Contents

[**1. Review content (Vi)** ](#1-Review-content-vi)


<br>

## 1. Review content (VI)

### Nội dung review code thường xét theo độ ưu tiên của riêng dự án trước, sau đó mới xét tới rule của công ty

* [1.1 Tên nhánh có đúng format chưa ( tùy dự án )](#1.1)
* [1.2 Nội dung commit message viết bằng tiếng Anh và tường minh](#1.2)
* [1.3 Những file nào cần ignore thì phải kiểm tra](#1.3)
* [1.4 Trường hợp thêm mới file thì phải đồng bộ convention với các file tương tự trong dự án](#1.4)
* [1.5 Nhánh đang yêu cầu merge tới có đúng đối tượng hay không](#1.5)
* [1.6 Số lượng file commit có hợp lý không](#1.6)
* [1.7 Khi tạo một function mới, thì kiểm tra có tồn tại chưa hoặc có thể custom lại hàm sẵn có](#1.7)
* [1.8 Có thêm biến môi trường thì cần xem xét confirm](#1.8)
* [1.9 Kiểm tra file package.json và file .lock xem có thay đổi nào bất thường không](#1.9)
* [1.10 Nếu có hàm được chỉnh sửa trong file common, thì cần check phạm vị ảnh hưởng](#1.10)
* [1.11 Các thông tin bảo mật như AccessKey, SecretKey… thì không được commit](#1.11)
* [1.12 Các giá trị list, CONST thì không được để giá trị raw mà cần dùng tới các biến CONST, Enum, config…](#1.12)
* [1.13 Khi thêm thư viện mới thì nên lấy file .min (minify)](#1.13)
* [1.14 Xem có các lệnh debug, console.log dư không](#1.14)

### Nodejs/Typescript

* [1.15 Hạn chế dùng kiểu any nếu có thể xác định kiểu của object](#1.15)
* [1.16 Nếu xử lý liên quan đến collection thì nên dùng thư viện Lodash](#1.16)
* [1.17 Xử lý liên quan đến ngày tháng nên dùng thư viện moment/day.js](#1.17)
* [1.18 Xử lý liên quan đến tiền / số lớn / số chấm phẩy thì phải dùng thư viện Big.js / Math.js](#1.18)

### Common
* [1.19 Về API thì kiểm tra API search xem có tối ưu performance chưa](#1.19)
* [1.20 API insert/update/delete nhiều records cùng lúc thì phải dùng transaction/bulkUpdate/bulkInsert thay vì loop rồi xử lý từng record](#1.20)

### Coding rule khác thì tham khảo file coding rule của công ty
https://github.com/BWV-Dev/bwv-coding-rules

### Ngoài ra tùy dự án sẽ có rule khác nhau:

Ví dụ dự án team Nodejs Vuejs thì tham khảo (Mr.Phi): <br> 
https://github.com/orgs/Briswell-Ltd/projects/4/views/1?pane=issue&itemId=12515593 <br>
https://github.com/orgs/Briswell-Ltd/projects/4/views/1?pane=issue&itemId=14294336


<table>

<tr id="1.1">
<td width="5%">

**1.1**
</td>
<td width="50%">
Tên nhánh có đúng format chưa </td>
<td width="45%">

```typescript
feature/issue-#####
```

</td>
</tr>

<tr id="1.2">
<td width="5%">

**1.2**
</td>
<td width="50%">
Nội dung commit message viết bằng tiếng Anh và tường minh </td>
<td width="45%">

```typescript
Add new screen S301_1
or
Fixing bug cannot display items A B C
```

</td>
</tr>

<tr id="1.3">
<td width="5%">

**1.3**
</td>
<td width="50%">
Những file nào cần ignore thì phải kiểm tra</td>
<td width="45%">

```typescript
Không commit file dư thừa như .env , ./dist
```

</td>
</tr>

</td>
</tr>

<tr id="1.4">
<td width="5%">

**1.4**
</td>
<td width="50%">
Trường hợp thêm mới file thì phải đồng bộ convention với các file tương tự trong dự án</td>
<td width="45%">

```typescript
Ví dụ như thêm controller thì đặt tên phải giống với rule dự án
user.controller.ts
or
userController.ts
```

</td>
</tr>

<tr id="1.5">
<td width="5%">

**1.5**
</td>
<td width="50%">
Nhánh đang yêu cầu merge tới có đúng đối tượng hay không</td>
<td width="45%">

```typescript
Yêu cầu merge lên develop hay feature hay main phải chính xác
```

</td>
</tr>

<tr id="1.6">
<td width="5%">

**1.6**
</td>
<td width="50%">
Số lượng file commit có hợp lý không</td>
<td width="45%">

```typescript
Ví dụ như có repo cần commit file build hoặc ignore file build thì phải check xem đủ file chưa
```

</td>
</tr>


<tr id="1.7">
<td width="5%">

**1.7**
</td>
<td width="50%">
Khi tạo một function mới, thì kiểm tra có tồn tại chưa hoặc có thể custom lại hàm sẵn có</td>
<td width="45%">

```typescript
Một số function có thể custom để tái sử dụng thì nên suy xét thay vì tạo hàm mới làm source phình to
Nhất là những function trong file utils, common, middleware etc
```

</td>
</tr>

<tr id="1.8">
<td width="5%">

**1.8**
</td>
<td width="50%">
Có thêm biến môi trường thì cần xem xét confirm</td>
<td width="45%">

```typescript
Lưu ý khi thêm một biến môi trường mới.
Cần kiểm tra xem có cần thiết và có ảnh hưởng gì không
```

</td>
</tr>

<tr id="1.9">
<td width="5%">

**1.9**
</td>
<td width="50%">
Kiểm tra file package.json và file .lock xem có thay đổi nào bất thường không</td>
<td width="45%">

```typescript
Có trường hợp file .lock bị thay đổi linh tinh. Cần kiểm tra để chắc chắn version các package không bị sai
```

</td>
</tr>

<tr id="1.10">
<td width="5%">

**1.10**
</td>
<td width="50%">
Nếu có hàm được chỉnh sửa trong file common, thì cần check phạm vị ảnh hưởng</td>
<td width="45%">

```typescript
Hàm được dùng ở nhiều nơi, nên rất có thể bị ảnh hưởng gây bug degrade
```

</td>
</tr>

<tr id="1.11">
<td width="5%">

**1.11**
</td>
<td width="50%">
Các thông tin bảo mật như AccessKey, SecretKey… thì không được commit</td>
<td width="45%">

```typescript
Vì tính bảo mật các thông tin trên không được phép commit
```

</td>
</tr>

<tr id="1.12">
<td width="5%">

**1.12**
</td>
<td width="50%">
Các giá trị list, CONST thì không được để giá trị raw mà cần dùng tới các biến CONST, Enum, config…</td>
<td width="45%">

```typescript
Cần dùng Enum để logic được tường minh ví dụ
export declare enum Status {
    '待機中' = 1,
    '起動中' = 2,
    '正常終了' = 3,
    '異常終了' = 4,
    '中断／強制終了' = 9
}
Thay vì để status = 4
Thì nên để status = Status[異常終了]
```

</td>
</tr>

<tr id="1.13">
<td width="5%">

**1.13**
</td>
<td width="50%">
Khi thêm thư viện mới thì nên lấy file .min (minify)</td>
<td width="45%">

```typescript
Các file .min sẽ có dung lượng ít hơn
Ví dụ: jquery.min.js
```

</td>
</tr>

<tr id="1.14">
<td width="5%">

**1.14**
</td>
<td width="50%">
Xem có các lệnh debug, console.log dư không</td>
<td width="45%">

```typescript
Loại bỏ các dòng code dư thừa như console.log , debugger, các dòng code bị comment out
```

</td>
</tr>

<tr id="1.15">
<td width="5%">

**1.15**
</td>
<td width="50%">
Hạn chế dùng kiểu any nếu có thể xác định kiểu của object</td>
<td width="45%">

```typescript
// Bad 
function sum2Number(first: any, second: any){
    return first + second;
}
// Good 👍
function sum2Number(first: number, second: number){
    return first + second;
}
```

</td>
</tr>


<tr id="1.16">
<td width="5%">

**1.16**
</td>
<td width="50%">
Nếu xử lý liên quan đến collection thì nên dùng thư viện Lodash</td>
<td width="45%">

```typescript
// Bad 
function getActiveStudentFromList(studentLst: Student[]){
    return studentLst.filtler(x => x.deletedAt === null);
}

// Good 👍
function getActiveStudentFromList(studentLst: Student[]){
    return _.filter((x:Student) => x.deletedAt === null);
}
```

</td>
</tr>


<tr id="1.17">
<td width="5%">

**1.17**
</td>
<td width="50%">
Xử lý liên quan đến ngày tháng nên dùng thư viện moment/day.js</td>
<td width="45%">

```typescript
import moment from "moment";
import "moment-timezone";

// Thư viện có hỗ trợ nhiều function, tiện lợi và chính xác hơn so với xử lý bằng javascript thuần
const getCurrentTimeJp = moment.tz("Asia/Tokyo").format('YYYY/MM/DD HH:mm:ss');

```

</td>
</tr>

<tr id="1.18">
<td width="5%">

**1.18**
</td>
<td width="50%">
Xử lý liên quan đến tiền / số lớn / số chấm phẩy thì phải dùng thư viện Big.js / Math.js</td>
<td width="45%">

```typescript
// Javascript không thể xứ lý số quá lớn và số chấm phẩy một cách chính xác, cần sự hỗ trợ từ thư viện
let x = new Big(0.1);
let y = new Big(0.2);
console.log(x.add(y).toFixed()); // 0.3
```

</td>
</tr>


<tr id="1.19">
<td width="5%">

**1.19**
</td>
<td width="50%">
Về API thì kiểm tra API search xem có tối ưu performance chưa</td>
<td width="45%">

```typescript
Thường là không select tất cả các column
Không select all from table rồi sau đó filter
Đảm bảo số lượng câu query là tối thiểu
```

</td>
</tr>

<tr id="1.20">
<td width="5%">

**1.20**
</td>
<td width="50%">
API insert/update/delete nhiều records cùng lúc thì phải dùng transaction/bulkUpdate/bulkInsert thay vì loop rồi xử lý từng record</td>
<td width="45%">

```typescript
// Bad 
async function insertProducts(products) {
  products.forEach(product => await Product.create(product))
}

// Good 👍
async function insertProducts(products, transaction) {
  const transaction = await sequelize.transaction();
  try {
    const insertedProducts = await Product.bulkCreate(products, { transaction });
    await transaction.commit();
    return insertedProducts;
  } catch (error) {
    await transaction.rollback();
    throw error;
  }
}
```

</td>
</tr>

</table>
