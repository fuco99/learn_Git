# Git Basic

## 1. Git là gì ?

Git là một hệ thống quản lý phiên bản phân tán, được sử dụng để theo dõi các thay đổi trong mã nguồn và các tệp liên quan đến dự án phần mềm. Git được phát triển bởi Linus Torvalds vào năm 2005 và hiện được sử dụng rộng rãi trong việc phát triển phần mềm và quản lý mã nguồn. Git cho phép nhiều người cùng làm việc trên cùng một dự án và quản lý các phiên bản khác nhau của mã nguồn. Điều này giúp cho việc phát triển phần mềm trở nên dễ dàng hơn và linh hoạt hơn.

## 2. Github là gì ?

Github là một dịch vụ lưu trữ mã nguồn trực tuyến được xây dựng trên nền tảng Git. Nó cho phép các nhà phát triển phần mềm lưu trữ mã nguồn của mình, quản lý phiên bản và chia sẻ mã nguồn với những người khác trên toàn thế giới

Các tính năng của Github bao gồm quản lý code, quản lý dự án, báo cáo lỗi và yêu cầu tính năng, cho phép các thành viên trong nhóm phát triển tương tác với nhau. Ngoài ra, Github cung cấp một cộng đồng lớn và đa dạng các mã nguồn mở cho phép người dùng có thể học hỏi và đóng góp vào các dự án đó.

## 3. Lệnh git config 

git config là lệnh dùng để cấu hình các tùy chọn cho Git. Với lệnh này bạn có thể cấu hình username, email và các tùy chọn khác cho tài khoản Git của mình.

- Git có 2 loại config đó là `local` và `global`. `local` dành riêng cho dự án còn `global` dùng cho cả máy tính. Nếu không định nghĩa trong git config thì nó tự hiểu là bạn đang config cho `global`.

- Hiển thị các config trên `local`:

``` bash
git config --local --list
```
- Hiển thị các config trên `global`:
```bash
git config --global --list
```

- Lệnh config username và email: 

```bash
git config user.name "ten_user"

git config user.email email
```
## 4. git init

git init là lệnh giúp bạn khởi tạo một Git repository trên local và code của bạn chỉ được quản lý bởi Git khi mà code nằm chung với thư mục .git

## 5. git status

git status là một lệnh dùng để kiểm tra trạng thái của repo Git của bạn.

Khi bạn chạy lệnh `git status`, Git sẽ hiển thị cho bạn 1 số thông tin như sau:

- Các tệp đã sửa đổi và chưa được commit
- các tệp mới được thêm vào (untrack files)
- Các tệp sẵn sàng cho việc commit 
- Cho biết bạn đang ở branch nào 

## 6. Các khu vực làm việc của Git

- Local

1. **Working directory (Thư mục làm việc)**: Đây là thư mục nơi bạn thực hiện các thay đổi trên tệp trong repository của bạn. Khi bạn chỉnh sửa một tệp trong thư mục làm việc, Git sẽ không tự động lưu trữ thay đổi đó. Thay vào đó, bạn phải sử dụng lệnh git add để đưa các thay đổi này vào khu vực "staging area".
2. **Staging area (Khu vực staging)**: Đây là khu vực các tệp đã được chỉnh sửa và đã sẵn sàng commit. Khi bạn sử dụng lệnh `git add` thì toàn bộ code sẽ được đẩy vào khu vực này.
3. **Local repository**: Đây là nơi các tệp đã được commit và lưu trữ. Khi bạn sử dụng lệnh `git commit` thì toàn bộ code của bạn sẽ được đẩy vào khu vực này (tất nhiên code của bạn vẫn ở trên local).

- Remote
1. **Remote repository**: Đây là nơi lưu trữ code trên remote, sau khi sử dụng lệnh `git push` toàn bộ code trên local repository sẽ được đẩy lên remote repository.

## 7. git add 

- Thêm 1 file

```bash
git add index.html
```

- Thêm tất cả các file thay đổi: 
```bash
git add .
```

## 8. git reset

Chức năng trái ngược với lệnh `git add`. Dùng để đưa các file ở khu vực staging area về khu vực code

`git reset` cũng có thể khôi phục 1 file hay nhiều files

- Khôi phục 1 file:

```bash
git reset index.html
```

- Khôi phục tất cả file: 
```bash
git reset .
```

## 9. git commit

```bash
git commit -m "title"
```
Nếu có gắn thêm description để mô tả cho title

```bash
git commit -m "title" -m "description"
```

## 10. git push
Nếu local branch của bạn không tồn tại trên remote, chạy câu lệnh sau

```bash
git push -u origin localBranch
```

Hoặc câu lệnh này, nó sẽ giúp các bạn không cần gõ chính xác tên local branch

```bash
git push -u origin HEAD
```
## 11. git remote 

> Khi lấy một remote reop bằng câu lệnh `git clone`, mặc định repo tải về có liên kết với tên `origin` chứa địa chỉ tham chiếu đến remote repo nó tải về

Hiển thị thông tin chi tiết hơn, có thêm đường dẫn đến remote Repo

```bash
git remote -v
```

Tạo một liên kết

```bash
git remote add TenRemote url
```

Xóa một địa chỉ remote

```bash
git remote rm TenRemote
```

Đổi tên địa chỉ remote

```bash
git remote rename TenCu TenMoi
```

Xem thông tin về Remote

```bash
git remote show origin
```
## 12. .gitignore

Có những file chúng ta không muốn bị git giám sát thì chỉ cần tạo file `.gitignore` và thêm các file và folder vào file `.gitignore` này.

**`.gitignore`**

```bash
# Comment
node_modules/
.logs
```

Những trường hợp phổ biến dùng `.gitignore`

- ignore thư mục node_modules vì thư mục này rất nặng gây tốn thời gian pull và push code. Ngoài ra còn tốn tài nguyên git, ai muốn có node_modules thì chỉ cần chạy npm hoặc yarn là có ngay.
- ignore các thư mục build như `dist`. Ai muốn có các file build thì chỉ cần chạy câu lệnh build là được, không cần gửi lên git thư mục này làm gì
- ignore các file cấu hình trên máy tính cá nhân mà không muốn xuất hiện ở các máy thành viên khác

Cách viết `.gitignore`

- Comment thì dùng `#`
- Ignore file: `example.exe`
- Ignore cả thư mục: `folder/`, tất nhiên là bạn dùng `folder` cũng được nhưng nên thêm `/` để phân biệt với file
- Phủ định thì thêm `!`: `!folder/file.exe`
- Ignore tất cả các file có đuôi là `.exe`: `*.exe`
- Ignore tất cả các file có tên bắt đầu là log: `log*`
- Ignore tất cả các file có đuôi là `.exe` ở theo đường dẫn `folder/file.exe` (các file ở đường dẫn `folder/sub/file.exe` sẽ không bị ignore): `folder/**.exe`
- Ignore tất cả các file có đuôi là `.exe` ở thư mục `folder` dù cho có nằm ở sub-folder đi chăng nữa: `folder/**/**.exe`
- Ignore mọi thứ bên trong thư mục folder: `folder/**`

### Xử lý Git cache

Trong một số trường hợp bạn code một thời gian rồi, push pull các kiểu rồi, sau đó bạn mới thêm các file vào `.gitignore`, lúc này những file đó có thể không bị ignore vì nó đã bị git cache từ trước và git nó vẫn quản lý những file này. Cách giải quyết là hãy xóa những file đó ra khỏi cache

```bash
git rm -r --cached /đường-dẫn-file-hoặc-folder
```







