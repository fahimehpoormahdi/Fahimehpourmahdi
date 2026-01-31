
``` mermaid
flowchart TD
    start@{shape: sm-circ, label: "شروع"} --> role{نقش کاربر؟}

    %% مسیر مهمان (User/Guest)
    role -- "مهمان" --> ULogin["ورود / ثبت‌نام کاربر"]
    ULogin --> UPanel["پنل کاربری"]
    UPanel --> SearchHotel@{shape: lean-r, label: "جستجوی هتل‌ها"}
    SearchHotel --> ViewHotel["مشاهده جزئیات هتل"]
    ViewHotel --> SelectRoom["انتخاب اتاق"]
    SelectRoom --> ConfirmBooking["تایید رزرو"]
    ConfirmBooking --> PayOnline@{shape: lean-r, label:"پرداخت آنلاین"}
    PayOnline --> CheckIn["ورود به هتل (Check-in)"]
    CheckIn --> RateHotel["ثبت نظر و امتیاز"]
    RateHotel --> fin@{shape: dbl-circ, label: "پایان"}

    %% مسیر مدیر هتل (Hotel Manager)
    role -- "مدیر هتل" --> MLogin["ورود مدیر هتل"]
    MLogin --> MPanel["پنل مدیریت هتل"]
    MPanel --> ManageRooms["مدیریت اتاق‌ها"]
    ManageRooms --> ViewBookings["مشاهده رزروها"]
    ViewBookings --> ConfirmStay["تایید اقامت"]
    ConfirmStay --> GenerateReport["گزارش فروش و اقامت"]
    GenerateReport --> fin

    %% مسیر ادمین سیستم (System Admin)
    role -- "ادمین سیستم" --> ALogin["ورود ادمین"]
    ALogin --> APanel["پنل مدیریت سیستم"]
    APanel --> ManageUsers@{shape: rect, label:"مدیریت کاربران"}
    APanel --> MonitorTrans@{shape: cyl, label:"مانیتورینگ تراکنش‌ها"}
    MonitorTrans --> fin

    %% استایل‌ها
    style start fill:#ecf6fb,stroke:#4682b4,stroke-width:3px
    style fin fill:#f9e79f,stroke:#b7950b,stroke-width:3px
    style role fill:#dfe3e6,stroke:#566573,stroke-width:2px
    style ConfirmBooking fill:#d5f5e3,stroke:#145a32
    style RateHotel fill:#fdebd0,stroke:#b9770e
    style ManageRooms fill:#f2f3f4,stroke:#707b7c

    %% توضیحات مسیرها
    subgraph توضیحات [ ]
      direction TB
      شرح1["🟩 مسیر مهمان: رزرو و پرداخت"]
      شرح2["🟦 مسیر مدیر هتل: مدیریت اتاق‌ها و رزروها"]
      شرح3["🟨 مسیر ادمین: مانیتورینگ و کنترل سیستم"]
    end

``` 
