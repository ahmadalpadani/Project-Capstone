# Product Reccomendation ELT Pipeline: Extract With Airbyte, Load to Bigquery, Transform With DBT and Orchestration With Airflow

## User Case

TechGear adalah perusahaan yang menjual berbagai macam perangkat elektronik. Dalam proses bisnisnya, TechGear menggunakan website sebagai instrumen jual beli utama, website tersebut menampung berbagai macam data hasil jual beli seperti: user activity data, product transaction data, dan user behavior data.

Untuk menunjang peningkatan bisnis perusahaan TechGear, perusahaan berusaha mengembangkan sistem Product Recommendation untuk mengetahui kecocokan setiap produk dengan masing-masing pelanggan berdasarkan analisa data user behavior (cth: product views, cart additions).

## Project Goals

1. Data Ingestion - Membuat pipeline data ingestion untuk mengekstrak raw data ke dalam GCP BigQuery.
2. Data Transformation - Menggunakan DBT untuk melakukan pemodelan data dan mengubah data ke dalam star schema.
3. Data Orchestration - Menggunakan Airflow untuk melakukan otomatisasi terhadap pipeline yang telah dibetuk.
4. Data Reporting/Analytics - Menggunakan Looker Studio untuk membuat dashboard untuk tujuan pelaporan atau analisis.

## ELT Data Architecture 

![data_architecture](https://github.com/ahmadalpadani/Project-Capstone/blob/main/assets/ELT%20Archicteture.png) 

## Start Docker Compose
- git clone this code to local
- run docker compose

  ```
  docker compose up -d
  ``` 

## Make Bukcet in Google Cloud Service (CSV Files)
- Open Google Cloud Service
- Input Bucket in search text box 
- Create new Bucket 
![bucket](https://github.com/ahmadalpadani/Project-Capstone/blob/main/assets/Bucket.png) 
- Upload CSV file to the Bucket folder
![bucket_folder](https://github.com/ahmadalpadani/Project-Capstone/blob/main/assets/bucket_folder.jpg) 
- Setting CSV Bucket file to the public 

## Define source connection in Airbyte
- Open url http://localhost:8000 for Airbyte UI
- Click New Connection

### Data Source From CSV
- In Define source, choose setup new source
- Input csv in search text box then click File
- Input dataset name and choose file format csv 
- For Storage Provider choose HTTPS : Public Web and input URL : 
Product: https://storage.googleapis.com/project_capstone_alterra_2/product%20(1).csv
Cart: https://storage.googleapis.com/project_capstone_alterra_2/cart.csv
Country: https://storage.googleapis.com/project_capstone_alterra_2/country.csv
Gender: https://storage.googleapis.com/project_capstone_alterra_2/gender.csv
Purchased: https://storage.googleapis.com/project_capstone_alterra_2/purchased.csv
Review: https://storage.googleapis.com/project_capstone_alterra_2/review.csv
Tags: https://storage.googleapis.com/project_capstone_alterra_2/tags%20(1).csv
- Click set up source 