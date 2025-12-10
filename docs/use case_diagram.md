```mermaid
flowchart RL

%% :performing_arts: بازیگران
Guest([🧳 مهمان])
Receptionist([:woman::briefcase: پذیرش])
Manager([:man::briefcase: مدیر هتل])

%% 🧩 Use Cases اصلی
subgraph رزرو
    UC1([جستجوی هتل])
    UC1a([فیلتر بر اساس تاریخ و مکان])
    UC1b([مشاهده جزئیات اتاق‌ها])
    UC2([رزرو اتاق])
    UC2a([ورود اطلاعات مهمان])
    UC2b([پرداخت آنلاین])
    UC2c([دریافت تأییدیه رزرو])
end

subgraph اقامت
    UC3([ورود به هتل (چک‌این)])
    UC4([درخواست خدمات اتاق])
    UC5([خروج از هتل (چک‌اوت)])
end

subgraph مدیریت پذیرش
    UC6([مشاهده رزروهای فعال])
    UC6a([تأیید ورود مهمان])
    UC6b([لغو یا تغییر رزرو])
end

subgraph مدیریت سیستم
    UC7([مدیریت اتاق‌ها])
    UC7a([افزودن/ویرایش اطلاعات اتاق])
    UC7b([تنظیم ظرفیت و قیمت])
    UC8([گزارش‌گیری مالی])
    UC8a([گزارش رزروها])
    UC8b([گزارش درآمد])
end

%% :link: ارتباطات بازیگران با Use Caseهای اصلی
Guest --> UC1
Guest --> UC2
Guest --> UC3
Guest --> UC4
Guest --> UC5

Receptionist --> UC6
Receptionist --> UC3
Receptionist --> UC5

Manager --> UC7
Manager --> UC8

%% :link: ارتباطات زیرمجموعه‌ها با Use Case اصلی
UC1 --> UC1a & UC1b
UC2 --> UC2a & UC2b & UC2c
UC6 --> UC6a & UC6b
UC7 --> UC7a & UC7b
UC8 --> UC8a & UC8b

%% :art: ظاهر و استایل‌ها
style Guest fill:#FFF9C4,stroke:#FBC02D,stroke-width:2px
style Receptionist fill:#FFF9C4,stroke:#FBC02D,stroke-width:2px
style Manager fill:#FFF9C4,stroke:#FBC02D,stroke-width:2px

style UC1 fill:#E3F2FD,stroke:#2196F3,stroke-width:2px
style UC2 fill:#E3F2FD,stroke:#2196F3,stroke-width:2px
style UC3 fill:#E3F2FD,stroke:#2196F3,stroke-width:2px
style UC4 fill:#E3F2FD,stroke:#2196F3,stroke-width:2px
style UC5 fill:#E3F2FD,stroke:#2196F3,stroke-width:2px
style UC6 fill:#E3F2FD,stroke:#2196F3,stroke-width:2px
style UC7 fill:#E3F2FD,stroke:#2196F3,stroke-width:2px
style UC8 fill:#E3F2FD,stroke:#2196F3,stroke-width:2px

%% استایل گروه‌ها (Subgraphs)
style رزرو fill:#F1F8E9,stroke:#B2DFDB,stroke-dasharray: 5 5
style اقامت fill:#F1F8E9,stroke:#B2DFDB,stroke-dasharray: 5 5
```
style مدیریت_پذیرش fill:#F1F8E9,stroke:#B2DFDB,stroke-dasharray: 5 5
style مدیریت_سیستم fill:#F1F8E9,stroke:#B2DFDB,stroke-dasharray: 5 5
```
