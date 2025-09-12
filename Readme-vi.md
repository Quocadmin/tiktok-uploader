Repo bạn mô tả là **TikTok-Uploader**, một công cụ Python để **tự động đăng video lên TikTok** bằng Selenium.

---

### Công dụng chính

* **Tự động upload video TikTok** qua **CLI hoặc Python API**.
* Hỗ trợ: mô tả, hashtag, mention, comment, duet, stitch.
* Có thể **schedule video** (20 phút – 10 ngày sau).
* Hỗ trợ **custom cover image**.
* Gắn **product link** vào video (nếu tài khoản đủ điều kiện).
* Cho phép **proxy**, **browser selection**, **headless mode**.
* Quản lý auth bằng **cookies / sessionid** (thay vì login trực tiếp).

---

### Cách hoạt động

* **Auth**: lấy cookies (sessionid) từ trình duyệt thật → bot dùng lại trên Selenium → TikTok nghĩ là bạn đang login bình thường.
* **Upload**: mô phỏng thao tác trên web TikTok bằng WebDriver, kèm các option (cover, product\_id, schedule, proxy).
* **Xử lý lỗi**: video fail upload sẽ trả về trong list → có thể retry.

---

### Cách cài đặt & chạy ⚡

1. **Cài Python 3 + Chrome**.
2. **Cài từ PyPI (recommended)**:

   ```bash
   pip install tiktok-uploader
   ```

   Hoặc build từ source:

   ```bash
   git clone https://github.com/wkaisertexas/tiktok-uploader
   cd tiktok-uploader
   uv run tiktok-uploader
   ```
3. **CLI Example**

   ```bash
   tiktok-uploader -v video.mp4 -d "This is my description" -c cookies.txt
   ```
4. **Python API Example**

   ```python
   from tiktok_uploader.upload import upload_video
   upload_video("video.mp4", description="test", cookies="cookies.txt")
   ```

---

### Điểm mạnh

* Dễ dùng cho **content creator / marketer** muốn lên lịch đăng video.
* Cho phép **automation nhiều tài khoản** (qua cookie/sessionid).
* Không cần viết code nhiều, chỉ CLI là đủ.

### Hạn chế 🚨

* Dựa trên **Selenium browser automation**, dễ bị TikTok phát hiện nếu spam.
* Repo cảnh báo: upload quá nhiều có thể bị chặn tạm thời (không chính thức “ban”).
* Cần tự quản lý **cookies/sessionid** → expiry → phải refresh định kỳ.

---

### Ứng dụng thực tế

* **Cá nhân / Influencer**: tự động đăng video hàng ngày.
* **Marketing team**: lên lịch nhiều video, account khác nhau.
* **E-commerce**: đăng video có gắn product link để bán hàng.

Nguồn: [GitHub - tiktok-uploader](https://github.com/wkaisertexas/tiktok-uploader).
