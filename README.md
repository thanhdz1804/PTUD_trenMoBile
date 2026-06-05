# MÔN: PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG - TEE0419

# BÀI TẬP LỚN:

## 1. Viết phần mềm trên công cụ Mit App inventor
   (tập trung vào quy trình tạo ra phần mềm)
   app có 3 screen:
   + about về bản thân+nút gọi sang 2 screen còn lại
   + giải 1 bài toán đơn giản
   + sử dụng webview: hiển thị 1 trang web có sẵn, hỗ trợ giao diện điện thoại
   mô tả: thanh công cụ có gì? kéo thả + thay đổi thuộc tính: làm ntn, để làm gì?
          block: mô tả bản chất việc kéo thả block ntn?
                 ưu điểm gì so với viết code? nhược điểm?
                 copy paste block ? (backpack)
     
## 2. Viết app sử dụng Android Studio
   + Android manifest.xml  => mô tả gì? app cần quyền để do-st: khai báo ntn? để làm gì?
   + vòng đời của 1 ứng dụng android.
     code tự sinh sau khi tạo 1 project: có sẵn hàm onCreate: tại sao???
   + Code: java language. 
     app cần check xem có quyền để do-st? : code ntn? ý nghĩa?
     giao diện: (res/layout) mô tả bằng file XML + UI Design review
        + thuộc tính text, hoặc các thuộc tính khác: giá trị hardcode => lưu vào nới khác, tham chiếu tới nó:
          cú pháp của việc tham chiếu là gì?
          ưu điểm của việc tham chiếu này?
          OS hỗ trợ auto việc lấy giá trị tham chiếu theo LOCATION, LANGUAGE, THEME
          việc hỗ trợ auto này giúp app làm được điều gì?	
        + đối tượng chứa: gộp các đối tượng con lại: cùng 1 quy luật sắp xếp để hiển thị 
          các đối tượng con nằm kề nhau theo chiều dọc | hoặc ngang, gravity
     code tương tác với layout: vd hiển thị text
          mong muốn text hiển thị phù hợp với thiết lập LOCATION, LANGUAGE, THEME của người dùng
          thì làm ntn? (tránh hardcode)
     event (sự kiện) người dùng tác động vào app: CLICK vào button, click vào text,...
          với 1 sự kiện nào đó, muốn chạy 1 đoạn code để do-st
          thì LAYTOUT cần làm gì?
              CODE viết như nào (2 cách)
---------------------------
     trong app có các thư mục đặc biệt: Assets
     khi sử dụng Window Explorer để copy các files + folder vào trong Assets
     thì khi compiler: mọi file này đều đi theo app, nằm trong app
     trong app có thể truy cập được đến các file này
     cú pháp truy cập vào là gì?
     lợi ích của việc app có sẵn các files (offline cũng có)?
     ứng dụng: app hướng dẫn việc X

==> tạo app1 sử dụng cơ chế Dữ liệu chuẩn bị trước trong Assets
         format dữ liệu: tuỳ ý, nội dung tuỳ ý
         công cụ để hiển thị dữ liệu: tuỳ ý
         có cần phải tiền xử lý trước khi hiển thị ko: tuỳ ý.
         SV TỰ ĐẶT RA VẤN ĐỀ => TỰ GIẢI QUYẾT VẤN ĐỀ
         MÔ TẢ ĐƯỢC DỮ LIỆU CÓ ĐẶC THÙ GÌ
                    DÙNG THUẬT TOÁN NÀO ĐỂ XỬ LÝ DỮ LIỆU (NẾU CẦN)
                    DÙNG ĐỐI TƯỢNG NÀO ĐỂ HIỂN THỊ DỮ LIỆU.
                    (ĐỘ SÁNG TẠO LÀ KO GIỚI HẠN)
------------------------
APP2 (android studio):  tạo app tương đương với Mit App inventor
  app có 3 activity
  + activity1: about: about+nút gọi sang 2 activity còn lại
  + activity2: giải toán đơn giản (tuỳ ý). mỗi khi giải xong bài toán: gọi api tại https://k58kmt.tdh.io.vn/api
    để gửi bài toán lên đó
    {app_by:mã số sv, input: {a:1,b:2,c:3,name:"hello tắc kè"},output:{ketluan:"vô nghiệm", abc:"xyz", nghiem:3.14}}
    nhận lại json: {ok:1, stt:1234}
  + activity3: 
    dùng web-view để truy cập từ 
    1 trang web https://k58kmt.tdh.io.vn?masv=mã sv của bạn
=======================
    vết để lại: mô tả quá trình làm bài tập ra file .md => upload github
    kèm hình ảnh minh hoạ quá trình làm.

    print ra giấy đóng quyển, nộp bm.

# PHẦN 1 — MIT APP INVENTOR

# 1. Giới thiệu bài làm

Trong phần này thực hiện xây dựng ứng dụng bằng MIT App Inventor gồm 3 Screen:

- Screen About bản thân
- Screen giải bài toán đơn giản
- Screen sử dụng WebView để hiển thị website

Ứng dụng được xây dựng bằng phương pháp kéo thả giao diện và lập trình block.

---

# 2. Truy cập MIT App Inventor

## Bước 1: Mở website

Truy cập:

```text
https://appinventor.mit.edu/
```

Sau đó chọn:

```text
Create Apps!
```

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f6dabaa6-103b-41c3-b80b-d6c27bfa8383" />

---

# 2. Thiết kế Screen 1 — About

## Mục tiêu

Screen này dùng để:
- Giới thiệu bản thân
- Chứa nút chuyển sang Screen giải toán
- Chứa nút chuyển sang Screen WebView

---

## Bước 1: Kéo thả Label

Trong mục Palette chọn:

```text
User Interface → Label
```

Kéo vào Viewer.

Đổi thuộc tính:
- Text
- FontSize
- TextColor
- Width

Ví dụ:

```text
Họ tên: Thân Nhân Thành
MSSV: K225480106059
```

📸 Chụp ảnh:
- Kéo Label
- Bảng Properties
- Kết quả hiển thị

---

## Bước 2: Thêm Button chuyển Screen

Kéo 2 Button vào giao diện.

Đổi Text:
- Mở màn hình giải toán
- Mở WebView

📸 Chụp ảnh:
- Button trong Viewer
- Thuộc tính Text

---

## Bước 3: Viết Block chuyển màn hình

Chuyển sang tab:

```text
Blocks
```

Tạo block:

```text
when Button1.Click
open another screen screenName "Screen2"
```

Tương tự cho Screen3.

📸 Chụp ảnh:
- Các block kéo thả
- Block hoàn chỉnh

---

# 5. Thiết kế Screen 2 — Giải toán đơn giản

## Ý tưởng

Ứng dụng nhập:
- a
- b

Sau đó tính:
- Tổng
- Hiệu
- Tích
- Thương

---

## Bước 1: Thêm TextBox

Kéo:
- 2 TextBox
- 1 Button
- 1 Label kết quả

📸 Chụp ảnh:
- Các thành phần giao diện

---

## Bước 2: Đổi thuộc tính

Ví dụ:

TextBox1 Hint:

```text
Nhập số a
```

TextBox2 Hint:

```text
Nhập số b
```

Button Text:

```text
Tính toán
```

📸 Chụp ảnh:
- Properties từng thành phần

---

## Bước 3: Viết Block xử lý

Trong Blocks:

- Lấy dữ liệu TextBox
- Chuyển sang number
- Tính toán
- Hiển thị kết quả

Ví dụ:

```text
set Label1.Text to join
```

📸 Chụp ảnh:
- Block xử lý phép tính
- Kết quả chạy thử

---

# 6. Thiết kế Screen 3 — WebView

## Mục tiêu

Hiển thị website hỗ trợ giao diện điện thoại.

---

## Bước 1: Kéo WebViewer

Chọn:

```text
User Interface → WebViewer
```

📸 Chụp ảnh:
- WebViewer trong Viewer

---

## Bước 2: Đặt URL

Trong Properties:

```text
HomeUrl
```

Ví dụ:

```text
https://k58kmt.tdh.io.vn
```

📸 Chụp ảnh:
- Thuộc tính HomeUrl
- Kết quả hiển thị website

---

# 7. Giải thích về Block

## Bản chất của block

Block là phương pháp lập trình trực quan bằng kéo thả thay vì viết code thủ công.

Người dùng chỉ cần:
- Kéo block
- Ghép block
- Tạo logic xử lý

---

## Ưu điểm

- Dễ học
- Dễ làm quen
- Hạn chế lỗi cú pháp
- Tạo ứng dụng nhanh

---

## Nhược điểm

- Khó xây dựng hệ thống lớn
- Khó tối ưu
- Ít linh hoạt hơn viết code

---

## Backpack

Backpack dùng để:
- Copy block
- Lưu block
- Paste block sang nơi khác

📸 Chụp ảnh:
- Backpack
- Copy block

---

# 8. Chạy thử ứng dụng

Chọn:

```text
Connect → AI Companion
```

Dùng điện thoại quét QR để chạy app.

📸 Chụp ảnh:
- QR Code
- App chạy trên điện thoại

---

# PHẦN 2 — ANDROID STUDIO

# 1. Cài đặt Android Studio

## Bước 1: Tải Android Studio

Tải tại:

```text
https://developer.android.com/studio
```

📸 Chụp ảnh:
- Trang tải Android Studio

---

## Bước 2: Cài đặt

Cài:
- Android SDK
- Emulator
- SDK Platform

📸 Chụp ảnh:
- Quá trình cài đặt

---

# 2. Tạo Project Android Studio

## Bước 1: New Project

Chọn:

```text
Empty Views Activity
```

📸 Chụp ảnh:
- Giao diện tạo project

---

## Bước 2: Đặt tên project

Ví dụ:

```text
MobileAppAndroid
```

Language:
```text
Java
```

📸 Chụp ảnh:
- Thông tin project

---

# 3. AndroidManifest.xml

## Chức năng

File này dùng để:
- Khai báo Activity
- Khai báo quyền
- Cấu hình ứng dụng

---

## Ví dụ cấp quyền Internet

```xml
<uses-permission android:name="android.permission.INTERNET"/>
```

📸 Chụp ảnh:
- File AndroidManifest.xml

---

# 4. Giải thích vòng đời Android

## Các hàm chính

- onCreate()
- onStart()
- onResume()
- onPause()
- onStop()
- onDestroy()

---

## Ý nghĩa onCreate()

Đây là hàm được gọi khi Activity được tạo lần đầu.

Dùng để:
- Khởi tạo giao diện
- Ánh xạ View
- Khởi tạo dữ liệu

📸 Chụp ảnh:
- Hàm onCreate()

---

# 5. Thiết kế giao diện XML

## File layout

Đường dẫn:

```text
res/layout/activity_main.xml
```

---

## Ví dụ TextView

```xml
<TextView
    android:text="Xin chào"/>
```

---

## Dùng string resource

Không nên hardcode trực tiếp.

Ví dụ:

```xml
android:text="@string/app_name"
```

📸 Chụp ảnh:
- File strings.xml
- Tham chiếu @string

---

## Ưu điểm

- Hỗ trợ đa ngôn ngữ
- Hỗ trợ theme
- Dễ bảo trì

---

# 6. Event trong Android

## Cách 1 — setOnClickListener

```java
button.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {

    }
});
```

📸 Chụp ảnh:
- Code xử lý sự kiện

---

## Cách 2 — android:onClick

Trong XML:

```xml
android:onClick="xuLyNut"
```

Trong Java:

```java
public void xuLyNut(View view){

}
```

📸 Chụp ảnh:
- XML event
- Hàm Java

---

# 7. Assets trong Android

## Thư mục Assets

Dùng để:
- Chứa file dữ liệu
- File txt
- JSON
- HTML
- Hình ảnh

---

## Truy cập Assets

Ví dụ:

```java
InputStream inputStream = getAssets().open("data.txt");
```

📸 Chụp ảnh:
- Thư mục assets
- File dữ liệu

---

# 8. APP1 — Dữ liệu Offline bằng Assets

## Ý tưởng

Tạo ứng dụng đọc dữ liệu có sẵn từ file trong Assets.

Ví dụ:
- Danh sách sản phẩm
- Danh sách món ăn
- Hướng dẫn học tập

---

## Các bước

### Bước 1:
Tạo file dữ liệu.

Ví dụ:

```text
products.txt
```

📸 Chụp ảnh:
- File dữ liệu

---

### Bước 2:
Copy vào thư mục assets.

📸 Chụp ảnh:
- File trong assets

---

### Bước 3:
Đọc file bằng Java.

📸 Chụp ảnh:
- Code đọc file

---

### Bước 4:
Hiển thị dữ liệu.

Có thể dùng:
- TextView
- RecyclerView
- ListView

📸 Chụp ảnh:
- Kết quả hiển thị

---

# 9. APP2 — 3 Activity

## Activity1

- Giới thiệu bản thân
- Chuyển Activity

📸 Chụp ảnh:
- Activity1

---

## Activity2

- Giải toán
- Gọi API gửi dữ liệu

Ví dụ JSON:

```json
{
  "app_by":"K225480106059",
  "input":{
    "a":1,
    "b":2
  },
  "output":{
    "tong":3
  }
}
```

📸 Chụp ảnh:
- Code API
- Kết quả trả về

---

## Activity3

Dùng WebView truy cập:

```text
https://k58kmt.tdh.io.vn?masv=K225480106059
```

📸 Chụp ảnh:
- WebView
- Website hiển thị

---


# 11. Kết luận

Sau khi thực hiện bài tập:
- Hiểu cách xây dựng ứng dụng bằng MIT App Inventor
- Hiểu cấu trúc Android Studio
- Biết xử lý giao diện và sự kiện
- Biết sử dụng Assets
- Biết dùng WebView và API

Bài tập giúp làm quen với quy trình phát triển ứng dụng di động từ cơ bản đến thực tế.

    
