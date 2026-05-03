# powerbi-retail-sales-analysis

# Pərakəndə Satışın Analitikası (Retail Data Analytics Project)
Bu layihə pərakəndə satış zəncirinin fəaliyyətini analiz etmək, biznesin ümumi vəziyyətini qiymətləndirmək, müştəri və tədarükçü davranışlarını optimallaşdırmaq məqsədilə hazırlanmış Power BI hesabatıdır. Layihə çərçivəsində məlumatların ETL proseslərindən vizuallaşdırılmasına qədər bütün mərhələlər tətbiq olunmuşdur.
##  Layihənin Mərhələləri və Görülən İşlər
### 1. Məlumatların Təmizlənməsi və ETL (Power Query)
* **Məlumatların Oxunması:** `Customers`, `Employees`, `Freight`, `Orders`, `Products` və `Suppliers` cədvəlləri Power Query mühitinə daxil edilmişdir.
* **Şərti Sütunların Yaradılması (Price Range):** `Product` cədvəlində məhsulların qiymətlərinə görə şərti sütun yaradılmışdır:
  * **Low value:** Qiyməti < 50
  * **Medium value:** Qiyməti 50 - 100 arası
  * **High value:** Qiyməti > 100
### 2. Məlumat Modeli (Data Modeling & DAX)
* **Ulduz Sxemi (Star Schema):** Bütün cədvəllər arasında düzgün əlaqələr (1-to-many) qurularaq optimal data model yaradılmışdır.
* **Təqvim Cədvəli (Date Table):** DAX vasitəsilə yeni `Date` cədvəli yaradılmış və daxilinə `Year`, `Month`, `MonthName`, `Day` sütunları əlavə edilmişdir.
* **Hesablanmış Sütunlar (Calculated Columns):**
  * `Unit Profit` = `Unit Price` - `Unit Cost`
  * DAX vasitəsilə `Profitability Range` sütunu:
    * **Low:** Profit < 20
    * **Medium:** Profit 20 - 40 arası
    * **High:** Profit > 40
* **Xüsusi Ölçülər (Measures Table):** Bütün biznes göstəricilərini hesablamaq üçün ayrıca ölçü cədvəli yaradılmış və aşağıdakı DAX measure-ları tətbiq edilmişdir:
  * `Sales`, `Cost`, `Profit`, `Profit %`, `# of orders`, `# of customers`
  * Zaman fərqliliklərini analiz etmək üçün: `Sales LY`, `Sales LY%`, `Sales LM`, `Sales LM%`
##  Hesabat Səhifələri və Vizuallar

Hesabat ümumilikdə dinamik naviqasiyaya və interaktivliyə malik 3 əsas və 2 köməkçi səhifədən ibarətdir:

### 1. Overview (Ümumi Baxış)
 * Kartlar: Satış, Mənfəət, Mənfəət %, Sifariş sayı və Müştəri sayı;
 * Trend Analizi (Line & Clustered Column Chart): Zaman oxu üzrə Satış və Mənfəət %-nin müqayisəsi;
 * Müştəri Analizi (Bar Chart): Şirkətlər üzrə Satış və Mənfəət %;
 * İşçi Performansı (Column Chart): Əməkdaşların reallaşdırdığı satış həcmi;
 * Kateqoriya Analizi (Pie Chart): Məhsul kateqoriyalarına görə satışın payı;
 * Regional Analiz (Bar Chart): Ölkələr üzrə satış göstəriciləri;
 * Filtrlər:İl (`Year`) və Ay adı (`Month Name`) üzrə slicer-lər;
### 2. Product Wise (Məhsul üzrə Analiz)
 * Məhsul kateqoriyaları və məhsul adları üzrə satış və mənfəətliliyin dərin analizi;
 * Təchizatçı Ölkələri: Supplier Country üzrə satış həcmləri;
 * Məhsul Detalları (Table): Məhsul adı, Satış, Mənfəət, Mənfəət %, Miqdar və Sifariş sayı;
 * Qiymət və mənfəət diapazonuna görə (`Price Range`, `Profitability Range`) satışların paylanması;
### 3. Customer & Suppliers (Müştəri və Tədarükçülər)
 * Müştəri və tədarükçülərə dair qrafiklər, slicer-lər və kartlar əlavə olunmuşdur;
 * Bookmark Funksionallığı: Eyni sahədə həm Müştəri (`Customer Sales`), həm də Tədarükçü (`Suppliers Sales`) satışlarını göstərən dinamik keçid düyməsi qurulmuşdur.
##  Qabaqcıl Power BI Funksiyaları
* **Dinamik Tooltip Səhifəsi:** Xəritə üzərində şəhər və ölkə bölgüsünə görə satışları göstərən interaktiv tooltip yaradılmış və aidiyyatı vizuallara bağlanmışdır. Seçilmiş şəhər və ölkə dərhal dinamik olaraq əks olunur.
* **Drillthrough Səhifəsi:** Müştəri (`Customer`) və ya Məhsul adına (`Product Name`) sağ klikləyərək keçid edilən xüsusi səhifədir. Bu səhifədə həmin müştəri və ya məhsul üzrə satışın keçən il və keçən ayla müqayisəsi həm rəqəm, həm də faizlə dinamik şəkildə nümayiş etdirilir.
## İstifadə Olunan Texnologiyalar
* **Power BI Desktop**
* **Power Query (ETL)**
* **DAX (Time Intelligence, Conditional logic)**

<img width="1600" height="827" alt="image (12)" src="https://github.com/user-attachments/assets/e7733a37-a84a-4696-ac5c-0b7229bd7195" />

<img width="1600" height="827" alt="image (11)" src="https://github.com/user-attachments/assets/70c6e706-72ca-4cb0-b8e4-0f23109c61d9" />

<img width="1600" height="825" alt="image (16)" src="https://github.com/user-attachments/assets/2978f376-f547-473a-9f7c-a5dbdd662fcb" />

<img width="1600" height="825" alt="image (15)" src="https://github.com/user-attachments/assets/2d762643-d4cb-45fc-8454-c16449b05585" />

<img width="1600" height="827" alt="image (14)" src="https://github.com/user-attachments/assets/51c74681-7dfd-491a-bfd7-4ba7cec5a021" />

https://github.com/user-attachments/assets/a87b36e0-744a-4bac-a99a-00e0b3af9eed







