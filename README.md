# Họ tên: Vũ Việt Anh
# Lớp: K58KTP.K01
# MSSV: K225480106082
# MÔN HỌC: PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG - TEE0419

# Bài Làm
# 1. Viết phần mềm trên công cụ Mit App inventor
- Tạo Project mới trong MIT App Inventor
- Click nút `+ new project`
- Đặt tên project là: `BaiTapLon_MITApp`
<img width="1919" height="903" alt="image" src="https://github.com/user-attachments/assets/ae5ce733-24da-4444-b98a-506a3490f568" />

- Thiết kế Screen1 (About - Giới thiệu bản thân)
<img width="1915" height="905" alt="image" src="https://github.com/user-attachments/assets/b7d9f66e-659a-417d-90f4-ef1460ad7563" />

- Tạo Screen2 (Giải Toán)
<img width="1917" height="905" alt="image" src="https://github.com/user-attachments/assets/d46979dd-d9e3-4288-835b-87c68028d683" />

- Tạo Screen3 (WebView)
<img width="1154" height="910" alt="image" src="https://github.com/user-attachments/assets/405bdcf5-deb9-4f6d-bf97-84b03c20b156" />

- Lập trình Blocks cho Screen1
  + Quay về Screen1
  + Vào chế độ Blocks
  + Lập trình nút "Giải Toán" (Button1)
  + Lập trình nút "Xem Web" (Button2)
<img width="1152" height="907" alt="image" src="https://github.com/user-attachments/assets/646960a3-815a-402d-ad75-66bff86eaf76" />

- Blocks cho Screen2 (Giải PT bậc 1: ax + b = 0)
  + Chuyển sang Screen2 Blocks
  + Kéo block xử lý khi bấm nút Tính
  + Tạo biến a và b
  + Lấy giá trị từ TextBox
  + Logic giải toán (dùng if/else)
<img width="1154" height="907" alt="image" src="https://github.com/user-attachments/assets/6941aa74-8747-4c78-a1d9-dcc431f21636" />

- Lưu project + Build APK
- Build APK để có file cài vào điện thoại
- Sẽ có 2 lựa chọn:
  + `Download .apk now` → tải về máy tính
  + scan QR code bằng điện thoại để cài trực tiếp
<img width="1152" height="899" alt="image" src="https://github.com/user-attachments/assets/91ae5e26-1a8f-4902-8d05-d8f1ffa27e0f" />

## 1.1. Thanh công cụ có gì? Kéo thả + thay đổi thuộc tính làm như thế nào, để làm gì?
### - Thanh công cụ (Palette) bên trái gồm các nhóm: User Interface, Layout, Media, Drawing, Sensors, Social, Storage, Connectivity...
### - Mỗi nhóm chứa các component như: Button, Label, TextBox, Image, WebViewer...
### - Kéo thả: Giữ chuột vào component trong Palette → kéo thả vào màn hình Viewer ở giữa → component xuất hiện trên màn hình điện thoại giả lập
### - Thay đổi thuộc tính: Click vào component trên Viewer → bên phải hiện panel Properties → chỉnh Text, FontSize, Color, Width, Height...
### - Để làm gì: Thiết kế giao diện trực quan mà không cần viết code XML

## 1.2. Block — Bản chất việc kéo thả block là gì?
### - Mỗi block là 1 đoạn lệnh được hình ảnh hoá thành khối ghép hình
### - Kéo thả block = lắp ghép các lệnh lại với nhau như xếp hình Lego
### - Block có hình dạng khớp nhau → chỉ ghép được đúng chỗ, tránh sai cú pháp

## 1.3.
| Tiêu chí | Block (MIT App Inventor) | Viết Code (Android Studio) |
|----------|--------------------------|----------------------------|
| **Ưu điểm** | Không cần nhớ cú pháp, không sai lỗi chính tả, dễ học, trực quan | Linh hoạt hơn, làm được mọi thứ phức tạp |
| **Nhược điểm** | Khó làm app phức tạp, block nhiều thì rối, khó tái sử dụng | Phải học ngôn ngữ lập trình, dễ sai cú pháp |

## 1.4. Copy paste block — Backpack là gì?
### - Backpack là tính năng trong MIT App Inventor cho phép copy block từ Screen này sang Screen khác
### - Cách dùng: Chuột phải vào block → "Add to Backpack" → chuyển sang Screen khác → mở Backpack → kéo block ra dùng
### - Tác dụng: Tái sử dụng code giữa các màn hình khác nhau

- Xuất file .aia: Click `Projects` → Export selected project (.aia)
<img width="1906" height="792" alt="image" src="https://github.com/user-attachments/assets/61e06e25-06cd-4586-9066-5badfe58796d" />

# 2. Viết app sử dụng Android Studio

## 2.1. AndroidManifest.xml mô tả gì?
### - Là file khai báo tổng quan của app: tên app, icon, theme, danh sách Activity
### - Khai báo quyền (permission) app cần:
```
<uses-permission android:name="android.permission.INTERNET"/>
```
### - Để làm gì: Android OS đọc file này trước khi cài app, biết app cần quyền gì để hỏi người dùng cho phép

## 2.2. Vòng đời của 1 ứng dụng Android?
```
onCreate() → onStart() → onResume() → [App đang chạy]
     ↓
onPause() → onStop() → onDestroy()
```
### - onCreate: Khởi tạo lần đầu, setup giao diện
### - onStart: App hiển thị lên màn hình
### - onResume: App ở foreground, người dùng tương tác được
### - onPause: App bị che khuất một phần
### - onStop: App không còn hiển thị
### - onDestroy: App bị đóng hoàn toàn

## 2.3. Code tự sinh sau khi tạo 1 project: có sẵn hàm onCreate: tại sao?
### - Vì onCreate là bước bắt buộc đầu tiên trong vòng đời Android
### - Android OS gọi onCreate khi Activity được tạo lần đầu
### - Đây là nơi bắt buộc phải gọi setContentView() để gắn layout vào Activity
### - Nếu không có onCreate → app không biết hiển thị giao diện nào

## 2.4. App cần check xem có quyền để do-st? : code ntn? ý nghĩa?
```
if (ContextCompat.checkSelfPermission(this, Manifest.permission.CAMERA)
        != PackageManager.PERMISSION_GRANTED) {
    // Chưa có quyền → xin quyền
    ActivityCompat.requestPermissions(this,
        new String[]{Manifest.permission.CAMERA}, 100);
} else {
    // Đã có quyền → dùng camera
}
```
### - Ý nghĩa: Android 6.0+ yêu cầu xin quyền lúc runtime (không chỉ khai báo trong Manifest)
### - Bảo vệ người dùng khỏi app dùng quyền mà không biết

## 2.5. Thuộc tính text, hoặc các thuộc tính khác: giá trị hardcode => lưu vào nới khác, tham chiếu tới nó: cú pháp của việc tham chiếu là gì?
### - Thay vì hardcode: `android:text="Xin chào"`
### - Lưu vào `res/values/strings.xml`:
```
<string name="loi_chao">Xin chào</string>
```

### - Tham chiếu trong XML:
```
android:text="@string/loi_chao"
```

### - Tham chiếu trong Java:
```
getString(R.string.loi_chao)
```

## 2.6. Ưu điểm của việc tham chiếu này?
### - Thay đổi 1 chỗ → cập nhật toàn bộ app
### - OS hỗ trợ auto theo LOCATION, LANGUAGE, THEME:
  + Tạo `res/values-vi/strings.xml` → tiếng Việt
  + Tạo `res/values-en/strings.xml` → tiếng Anh
  + Tạo `res/values-night/` → Dark mode
  + Android tự động chọn đúng file theo cài đặt điện thoại
### - Giúp app làm được: Đa ngôn ngữ, đa theme, đa vùng mà không cần code thêm

## 2.7. Đối tượng chứa: gộp các đối tượng con lại: cùng 1 quy luật sắp xếp để hiển thị các đối tượng con nằm kề nhau theo chiều dọc | hoặc ngang, gravity?
### - LinearLayout: Sắp xếp con theo 1 chiều
```
android:orientation="vertical"   <!-- chiều dọc -->
android:orientation="horizontal"  <!-- chiều ngang -->
android:gravity="center"          <!-- căn giữa các con -->
```
### - gravity: Căn vị trí các con bên trong (center, top, bottom, start, end)
### - layout_gravity: Con tự căn mình trong cha

## 2.8. Hiển thị text mong muốn text hiển thị phù hợp với thiết lập LOCATION, LANGUAGE, THEME của người dùng thì làm ntn? (tránh hardcode)
### - Sai (hardcode):
```
tvTitle.setText("Xin chào");
```
### - Đúng (dùng resource):
```
tvTitle.setText(getString(R.string.loi_chao));
```
### - Khi điện thoại đổi ngôn ngữ → Android tự lấy đúng string từ đúng file values

## 2.9. Event (sự kiện) người dùng tác động vào app: CLICK vào button, click vào text,... với 1 sự kiện nào đó, muốn chạy 1 đoạn code để do-st thì LAYTOUT cần làm gì? CODE viết như nào (2 cách)
### - Layout cần: Đặt `id` cho button
```
<Button android:id="@+id/btnTinh" .../>
```
### - Cách 1 — setOnClickListener trong Java:
```
Button btn = findViewById(R.id.btnTinh);
btn.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        // xử lý
    }
});
// Hoặc lambda:
btn.setOnClickListener(v -> { /* xử lý */ });
```
### - Cách 2 — onClick trong XML:
```
<Button android:onClick="xuLyClick" .../>
```

```
public void xuLyClick(View v) {
    // xử lý
}
```

## 3. Assets khi sử dụng Window Explorer để copy các files + folder vào trong Assets thì khi compiler: mọi file này đều đi theo app, nằm trong app trong app có thể truy cập được đến các file này cú pháp truy cập vào là gì? Lợi ích của việc app có sẵn các files (offline cũng có)?
### - Cú pháp truy cập:
```
InputStream is = getAssets().open("tudien.json");
```
### - Lợi ích:
  + File đi kèm theo app, không cần server
  + Offline vẫn dùng được → không cần internet
  + Ứng dụng: App hướng dẫn nấu ăn, từ điển, bản đồ offline...

# - Bắt đầu Android Studio
  + tải tại: `https://developer.android.com/studio`
  + Mở Android Studio
  + Chọn `New Project`
  + Chọn template: `Empty Views Activity`
<img width="1919" height="1025" alt="image" src="https://github.com/user-attachments/assets/acda3f7e-bb5a-4a6b-9189-5ecf453dadbc" />

- Tạo thư mục Assets
  + Tìm thư mục main → chuột phải vào main
  + Chọn New → Directory
  + Gõ tên: `assets`
<img width="1913" height="1032" alt="image" src="https://github.com/user-attachments/assets/c02c01c0-ee36-44f3-a3b4-77d38594a392" />

- Tạo file dữ liệu JSON trong Assets
  + Chuột phải vào thư mục assets
  + Chọn New → File
  + Đặt tên: `tudien.json`
```
[
  {"tu": "Hello", "nghia": "Xin chào"},
  {"tu": "Goodbye", "nghia": "Tạm biệt"},
  {"tu": "Thank you", "nghia": "Cảm ơn"},
  {"tu": "Sorry", "nghia": "Xin lỗi"},
  {"tu": "Yes", "nghia": "Có / Vâng"},
  {"tu": "No", "nghia": "Không"},
  {"tu": "Water", "nghia": "Nước"},
  {"tu": "Food", "nghia": "Thức ăn"},
  {"tu": "Friend", "nghia": "Bạn bè"},
  {"tu": "School", "nghia": "Trường học"}
]
```
<img width="1911" height="1031" alt="image" src="https://github.com/user-attachments/assets/49876b10-43fe-4024-91c9-5c92c7a3951f" />

- Thiết kế giao diện activity_main.xml
- Mở file layout:
  + mở: app → res → layout → activity_main.xml
  + Double click vào activity_main.xml
  + Click tab Code (góc trên phải) để xem XML
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp"
    android:background="#F0F4F8">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="📖 Từ Điển Anh - Việt"
        android:textSize="22sp"
        android:textStyle="bold"
        android:textColor="#1A237E"
        android:gravity="center"
        android:padding="16dp"/>

    <EditText
        android:id="@+id/edtSearch"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Nhập từ cần tìm..."
        android:padding="12dp"
        android:layout_marginBottom="8dp"/>

    <Button
        android:id="@+id/btnSearch"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Tìm kiếm"
        android:backgroundTint="#1A237E"
        android:textColor="#FFFFFF"/>

    <TextView
        android:id="@+id/tvResult"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Kết quả sẽ hiển thị ở đây"
        android:textSize="18sp"
        android:padding="16dp"
        android:layout_marginTop="16dp"
        android:gravity="center"
        android:textColor="#333333"/>

    <ListView
        android:id="@+id/listView"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:layout_marginTop="8dp"/>

</LinearLayout>
```
<img width="1915" height="1029" alt="image" src="https://github.com/user-attachments/assets/a921c9ba-6955-4dd4-bcf8-e9d5c2d0226a" />

- Mở file MainActivity.java:
  + app → src → main → java → com.sinhvien.app1assets → MainActivity.java
```
package com.sinhvien.app1assets;

import android.os.Bundle;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ListView;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;
import org.json.JSONArray;
import org.json.JSONObject;
import java.io.InputStream;
import java.util.ArrayList;

public class MainActivity extends AppCompatActivity {

    EditText edtSearch;
    Button btnSearch;
    TextView tvResult;
    ListView listView;
    JSONArray jsonArray;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        edtSearch = findViewById(R.id.edtSearch);
        btnSearch = findViewById(R.id.btnSearch);
        tvResult  = findViewById(R.id.tvResult);
        listView  = findViewById(R.id.listView);

        // Đọc file tudien.json từ Assets
        try {
            InputStream is = getAssets().open("tudien.json");
            int size = is.available();
            byte[] buffer = new byte[size];
            is.read(buffer);
            is.close();
            String json = new String(buffer, "UTF-8");
            jsonArray = new JSONArray(json);

            // Hiển thị toàn bộ từ điển lên ListView
            hienThiTatCa();
        } catch (Exception e) {
            tvResult.setText("Lỗi đọc file: " + e.getMessage());
        }

        // Xử lý nút tìm kiếm
        btnSearch.setOnClickListener(v -> {
            String keyword = edtSearch.getText().toString().trim().toLowerCase();
            timKiem(keyword);
        });
    }

    void hienThiTatCa() throws Exception {
        ArrayList<String> danhSach = new ArrayList<>();
        for (int i = 0; i < jsonArray.length(); i++) {
            JSONObject obj = jsonArray.getJSONObject(i);
            danhSach.add(obj.getString("tu") + " → " + obj.getString("nghia"));
        }
        ArrayAdapter<String> adapter = new ArrayAdapter<>(this,
                android.R.layout.simple_list_item_1, danhSach);
        listView.setAdapter(adapter);
        tvResult.setText("Tổng số từ: " + jsonArray.length());
    }

    void timKiem(String keyword) {
        try {
            ArrayList<String> ketQua = new ArrayList<>();
            for (int i = 0; i < jsonArray.length(); i++) {
                JSONObject obj = jsonArray.getJSONObject(i);
                String tu = obj.getString("tu").toLowerCase();
                if (tu.contains(keyword)) {
                    ketQua.add(obj.getString("tu") + " → " + obj.getString("nghia"));
                }
            }
            if (ketQua.isEmpty()) {
                tvResult.setText("Không tìm thấy từ: " + keyword);
            } else {
                tvResult.setText("Tìm thấy " + ketQua.size() + " kết quả:");
            }
            ArrayAdapter<String> adapter = new ArrayAdapter<>(this,
                    android.R.layout.simple_list_item_1, ketQua);
            listView.setAdapter(adapter);
        } catch (Exception e) {
            tvResult.setText("Lỗi: " + e.getMessage());
        }
    }
}
```
<img width="1919" height="1032" alt="image" src="https://github.com/user-attachments/assets/5107de2d-c10e-42de-9915-8e7d6d34dc7b" />

- Chạy thử app trên máy ảo
  + Kiểm tra máy ảo
  + Click nút ▶ (Run) màu xanh lá
- Chờ emulator khởi động
- App mở ra thấy:
  + Tiêu đề `Từ Điển Anh - Việt`
  + Ô tìm kiếm
  + Nút `Tìm kiếm`
  + Danh sách 10 từ hiển thị bên dưới
<img width="901" height="1003" alt="image" src="https://github.com/user-attachments/assets/76ea8880-6647-4061-abe4-92e68a890060" />

- Tạo App2 (3 Activity + API)
<img width="894" height="636" alt="image" src="https://github.com/user-attachments/assets/8a547fb5-3272-420f-be8e-cdf22f96da91" />

<img width="1919" height="1001" alt="image" src="https://github.com/user-attachments/assets/b3553b5e-c917-4555-9f28-263e8284c26e" />

```
package com.sinhvien.app2;

import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    Button btnGiaiToan, btnXemWeb;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        btnGiaiToan = findViewById(R.id.btnGiaiToan);
        btnXemWeb = findViewById(R.id.btnXemWeb);

        btnGiaiToan.setOnClickListener(v -> {
            startActivity(new Intent(this, GiaiToanActivity.class));
        });

        btnXemWeb.setOnClickListener(v -> {
            startActivity(new Intent(this, WebActivity.class));
        });
    }
}
```

- Tạo GiaiToanActivity
  + app → src → main → java → com.sinhvien.app2
  + Chuột phải chọn New → Java Class
  + Đặt: `GiaiToanActivity`
```
package com.sinhvien.app2;

import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;

public class GiaiToanActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_giai_toan);
    }
}
```
<img width="1568" height="608" alt="image" src="https://github.com/user-attachments/assets/093cb9af-b392-4a7b-8b22-ee74399eb372" />

- Tạo WebActivity
  + Chuột phải vào com.sinhvien.app2
  + New → Java Class
  + Đặt tên: `WebActivity`
```
package com.sinhvien.app2;

import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;

public class WebActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_web);
    }
}
```
<img width="1919" height="1031" alt="image" src="https://github.com/user-attachments/assets/b3af4d5b-7c34-4837-b889-4b612797cc64" />

- Tạo layout cho GiaiToanActivity
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="24dp"
    android:background="#FFF8E1">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="🧮 Giải PT bậc 1: ax + b = 0"
        android:textSize="20sp"
        android:textStyle="bold"
        android:gravity="center"
        android:textColor="#E65100"
        android:layout_marginBottom="24dp"/>

    <EditText
        android:id="@+id/edtA"
        android:layout_width="250dp"
        android:layout_height="wrap_content"
        android:hint="Nhập a"
        android:inputType="numberDecimal|numberSigned"
        android:gravity="center"
        android:layout_marginBottom="12dp"/>

    <EditText
        android:id="@+id/edtB"
        android:layout_width="250dp"
        android:layout_height="wrap_content"
        android:hint="Nhập b"
        android:inputType="numberDecimal|numberSigned"
        android:gravity="center"
        android:layout_marginBottom="20dp"/>

    <Button
        android:id="@+id/btnTinh"
        android:layout_width="250dp"
        android:layout_height="wrap_content"
        android:text="Tính kết quả"
        android:backgroundTint="#E65100"
        android:textColor="#FFFFFF"/>

    <TextView
        android:id="@+id/tvKetQua"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Kết quả: "
        android:textSize="18sp"
        android:gravity="center"
        android:layout_marginTop="24dp"
        android:textColor="#333333"/>

</LinearLayout>
```
<img width="1919" height="1036" alt="image" src="https://github.com/user-attachments/assets/1d523077-e86a-4f5d-a34a-d9f2070d4e71" />

- Tạo layout WebActivity
-  Tạo activity_web.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <WebView
        android:id="@+id/webView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

</LinearLayout>
```
<img width="1919" height="1032" alt="image" src="https://github.com/user-attachments/assets/5c5db188-0c6e-4ee8-bc17-f243d1bc5f44" />

- Đăng ký 3 Activity trong AndroidManifest.xml
  + app → src → main → AndroidManifest.xml
```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <uses-permission android:name="android.permission.INTERNET"/>

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.App2"
        android:usesCleartextTraffic="true">

        <activity android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN"/>
                <category android:name="android.intent.category.LAUNCHER"/>
            </intent-filter>
        </activity>

        <activity android:name=".GiaiToanActivity"
            android:exported="false"/>

        <activity android:name=".WebActivity"
            android:exported="false"/>

    </application>

</manifest>
```
<img width="1916" height="1027" alt="image" src="https://github.com/user-attachments/assets/9bc03e78-a13f-42a9-af8f-c40ec8602040" />

- Code GiaiToanActivity.java
```
package com.sinhvien.app2;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;
import org.json.JSONObject;
import java.io.InputStream;
import java.io.OutputStream;
import java.net.HttpURLConnection;
import java.net.URL;

public class GiaiToanActivity extends AppCompatActivity {

    EditText edtA, edtB;
    Button btnTinh;
    TextView tvKetQua;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_giai_toan);

        edtA = findViewById(R.id.edtA);
        edtB = findViewById(R.id.edtB);
        btnTinh = findViewById(R.id.btnTinh);
        tvKetQua = findViewById(R.id.tvKetQua);

        btnTinh.setOnClickListener(v -> giaiToan());
    }

    void giaiToan() {
        try {
            double a = Double.parseDouble(edtA.getText().toString());
            double b = Double.parseDouble(edtB.getText().toString());

            String ketluan;
            double nghiem = 0;

            if (a == 0) {
                if (b == 0) {
                    ketluan = "Vô số nghiệm";
                } else {
                    ketluan = "Vô nghiệm";
                }
                tvKetQua.setText("Kết quả: " + ketluan);
            } else {
                nghiem = -b / a;
                ketluan = "Có nghiệm";
                tvKetQua.setText("Kết quả: x = " + nghiem);
            }

            String finalKetluan = ketluan;
            double finalNghiem = nghiem;

            // Gọi API gửi kết quả lên server
            new Thread(() -> {
                try {
                    JSONObject input = new JSONObject();
                    input.put("a", a);
                    input.put("b", b);

                    JSONObject output = new JSONObject();
                    output.put("ketluan", finalKetluan);
                    output.put("nghiem", finalNghiem);

                    JSONObject body = new JSONObject();
                    body.put("app_by", "K225480106082");
                    body.put("input", input);
                    body.put("output", output);

                    URL url = new URL("https://k58kmt.tdh.io.vn/api");
                    HttpURLConnection conn = (HttpURLConnection) url.openConnection();
                    conn.setRequestMethod("POST");
                    conn.setRequestProperty("Content-Type", "application/json");
                    conn.setDoOutput(true);

                    // Gửi dữ liệu
                    OutputStream os = conn.getOutputStream();
                    os.write(body.toString().getBytes("UTF-8"));
                    os.flush();
                    os.close();

                    // Đọc response trả về
                    InputStream is = conn.getInputStream();
                    byte[] buffer = new byte[1024];
                    int len = is.read(buffer);
                    String response = new String(buffer, 0, len, "UTF-8").trim();
                    is.close();

                    JSONObject resJson = new JSONObject(response);
                    int ok = resJson.getInt("ok");
                    int stt = resJson.getInt("stt");

                    // Cập nhật UI trên main thread
                    runOnUiThread(() -> {
                        tvKetQua.append("\n✅ Đã gửi server! STT: " + stt);
                    });

                } catch (Exception e) {
                    runOnUiThread(() -> {
                        tvKetQua.append("\n⚠️ Gửi API thất bại: " + e.getMessage());
                    });
                }
            }).start();

        } catch (NumberFormatException e) {
            tvKetQua.setText("⚠️ Vui lòng nhập số hợp lệ!");
        }
    }
}
```

- Code WebActivity.java
```
package com.sinhvien.app2;

import android.os.Bundle;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.webkit.WebViewClient;
import androidx.appcompat.app.AppCompatActivity;

public class WebActivity extends AppCompatActivity {

    WebView webView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_web);

        webView = findViewById(R.id.webView);

        WebSettings settings = webView.getSettings();
        settings.setJavaScriptEnabled(true);

        webView.setWebViewClient(new WebViewClient());
        webView.loadUrl("https://k58kmt.tdh.io.vn?masv=K225480106082");
    }

    @Override
    public void onBackPressed() {
        if (webView.canGoBack()) {
            webView.goBack();
        } else {
            super.onBackPressed();
        }
    }
}
```

- Click ▶ Run để chạy thử app
<img width="1512" height="809" alt="image" src="https://github.com/user-attachments/assets/5250baef-91b3-431a-a131-c35c987d26ec" />

- Build thành công. Emulator đang khởi động -> Thấy `BUILD SUCCESSFUL` Emulator bên phải đang màn hình đen là đang khởi động.
- App2 đã chạy hoàn hảo, hiện đầy đủ:
  + Tên, MSSV, Lớp
  + Nút Giải Toán
  + Nút Xem Web
<img width="836" height="844" alt="image" src="https://github.com/user-attachments/assets/7e92b854-fcf5-499e-b215-d6a95388d519" />

<img width="836" height="833" alt="image" src="https://github.com/user-attachments/assets/222683bb-668e-4f81-ae18-a31c19615599" />

<img width="835" height="842" alt="image" src="https://github.com/user-attachments/assets/bf8316b8-844b-41d2-a531-c5b9739965cf" />

- Lỗi khi hiển thị gửi API thất bại
<img width="839" height="837" alt="image" src="https://github.com/user-attachments/assets/bc2329a7-8b1e-4c75-bdd9-c6fb4d0affc9" />

- Trang web: `https://k58kmt.tdh.io.vn/?masv=K225480106082` lỗi chưa thể truy cập được
<img width="838" height="837" alt="image" src="https://github.com/user-attachments/assets/266d34e3-19cc-43ae-95e5-a610565aa5be" />



