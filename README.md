# 📊 Feature Engineering with Google Play Store Dataset

[![TR](https://img.shields.io/badge/Lang-Türkçe-red)](#türkçe)
[![EN](https://img.shields.io/badge/Lang-English-blue)](#english)

---

## 🇹🇷 Türkçe

### Proje Özeti
Bu proje, Kaggle'da bulunan Google Play Store veri seti üzerinden detaylı **Özellik Mühendisliği (Feature Engineering)** ve **Keşifçi Veri Analizi (EDA)** aşamalarını içermektedir. Saf veri üzerinde temizleme, dönüştürme ve yeni özellikler üretme gibi kritik veri ön işleme (preprocessing) adımları uygulanmış ve ardından bu veriler üzerinden çeşitli çıkarımlar elde edilmiştir.

### Kullanılan Teknolojiler
* **Python (Jupyter Notebook)**
* **Pandas & NumPy:** Veri temizleme, dönüştürme, özellik mühendisliği (Feature Engineering) ve gruplama (groupby).
* **Matplotlib & Seaborn:** Dağılım ve karşılaştırma grafiklerinin (KDE plot, Bar plot, Count plot vb.) oluşturulması.

### Neler Yapıldı?

#### 1. Veri Temizleme ve Dönüştürme (Data Cleaning & Transformation)
* **`Reviews` (İncelemeler):** İçerisindeki geçersiz/nümerik olmayan ("3.0M" vb.) string karakterleri tespit edilip temizlendi ve tam sayı (`integer`) tipine çevrildi.
* **`Size` (Boyut):** Dosya boyutlarını ifade eden "M" (Megabayt) ve "k" (Kilobayt) harfleri nümerik formata uygun hale getirildi; "Varies with device" ibareleri null (NaN) değerlere çevrilerek sütun `float` tipine dönüştürüldü.
* **`Installs` (Yüklemeler) & `Price` (Fiyat):** İçerdikleri virgül (`,`), artı (`+`) ve dolar (`$`) işaretlerinden arındırılarak ilgili sayısal veri tiplerine (`int` ve `float`) çevrildi.
* **`Android Ver` (Android Sürümü):** Sürüm isimlerindeki "and up" ve "Varies with device" gibi gereksiz metinler ve aralıklı "-" değerler temizlendi.
* **Tekrar Eden (Duplicate) Veriler:** Veri setindeki aynı uygulamayı (`App` sütunu) gösteren tekrar eden satırlar veri setinden kaldırıldı.

#### 2. Özellik Mühendisliği (Feature Engineering)
* **Tarihsel Veri Üretimi:** String halinde olan `Last Updated` (Son Güncellenme) sütunu `datetime` objesine dönüştürüldü. Bu kısımdan `Day` (Gün), `Month` (Ay) ve `Year` (Yıl) olmak üzere 3 yeni anlamlı sütun (özellik) üretildi.
* **Hedef Odaklı Kodlama (Target / Mean Encoding):** Kategorik `Genres` (Türler) sütunu, kendi türündeki ortalama yüklenme (Installs) sayıları alınarak `Genres Encoded` adı altında yeni bir sayısal sütuna dönüştürüldü.

#### 3. Keşifçi Veri Analizi ve Görselleştirme (EDA)
* Numerik özellikler **KDE Plot** ile, kategorik özellikler ise (`Type`, `Content Rating`) **Countplot** ile görselleştirildi.
* Yüklenme sayılarına göre en popüler **İlk 10 Kategori** bar grafiğiyle çizdirildi.
* Belirlenen popüler kategorilerdeki (GAME, COMMUNICATION, TOOLS, PRODUCTIVITY, SOCIAL) en çok yüklenen **İlk 5 Uygulama** alt alanlarda (subplots) karşılaştırıldı.
* 5.0 tam puana sahip olan uygulamalar özel olarak ayrıştırılıp incelendi.

### Nasıl Çalıştırılır?
1. Repoyu bilgisayarınıza indirin:
   ```bash
   git clone https://github.com/elifduman23/Feature-Engineering-GooglePlayStore.csv.git
   ```
2. Terminal üzerinden jupyter notebook'u başlatın:
   ```bash
   jupyter notebook
   ```
3. Açılan sayfada `.ipynb` uzantılı dosyayı çalıştırın.

---

## 🇬🇧 English

### Project Overview
This project involves comprehensive **Feature Engineering** and **Exploratory Data Analysis (EDA)** using the Google Play Store dataset from Kaggle. Critical data preprocessing steps such as data cleaning, transformation, and creating new features were applied to the raw dataset to extract meaningful insights.

### Technologies Used
* **Python (Jupyter Notebook)**
* **Pandas & NumPy:** Data cleaning, type conversion, feature engineering, and aggregation (groupby).
* **Matplotlib & Seaborn:** Generating distribution and comparative visualizations (KDE plots, Bar plots, Count plots, etc.).

### What Was Done?

#### 1. Data Cleaning & Transformation
* **`Reviews` Column:** Identified and removed non-numeric string values (e.g., "3.0M" or error rows) and converted the entire column to `integer`.
* **`Size` Column:** Replaced string abbreviations "M" (Megabytes) and "k" (Kilobytes) with proper zeroes, replaced "Varies with device" with NaN, and cast the column to `float`.
* **`Installs` & `Price` Columns:** Stripped out commas (`,`), plus signs (`+`), and dollar signs (`$`), then cast them to their respective numerical types (`int` and `float`).
* **`Android Ver` Column:** Cleaned up version strings by removing redundant texts like "and up", "Varies with device", and version ranges (e.g., values containing "-").
* **Duplicate Handling:** Removed duplicate records across the dataset based on the `App` column.

#### 2. Feature Engineering
* **Date Feature Extraction:** Converted the `Last Updated` string column into Python `datetime` objects. Extracted 3 brand new numerical features: `Day`, `Month`, and `Year`.
* **Target / Mean Encoding:** Created a new numerical feature called `Genres Encoded` by mapping the categorical `Genres` column to its mean `Installs` value.

#### 3. Exploratory Data Analysis & Visualization
* Visualized numerical feature distributions using **KDE Plots** and categorical features (`Type`, `Content Rating`) using **Countplots**.
* Graphed the **Top 10 Categories** by total installs using bar plots.
* Compared the **Top 5 Apps** by installs within specific major categories (GAME, COMMUNICATION, TOOLS, PRODUCTIVITY, SOCIAL) using subplots.
* Isolated and analyzed applications with a perfect 5.0 Rating.

### How to Run
1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/elifduman23/Feature-Engineering-GooglePlayStore.csv.git
   ```
2. Launch Jupyter Notebook from your terminal:
   ```bash
   jupyter notebook
   ```
3. Open and run the provided `.ipynb` file.
