CREATE OR REPLACE TABLE rakamin-kf-analytics-448115.Kimia_Farma.tabel_analisis AS
WITH 
-- Menghitung persentase laba
price_with_gross_margin AS (
  SELECT
    p.product_id,
    p.product_name,
    p.price AS actual_price,
    CASE
      WHEN p.price <= 50000 THEN 0.10
      WHEN p.price > 50000 AND p.price <= 100000 THEN 0.15
      WHEN p.price > 100000 AND p.price <= 300000 THEN 0.20
      WHEN p.price > 300000 AND p.price <= 500000 THEN 0.25
      ELSE 0.30
    END AS persentase_gross_laba
  FROM rakamin-kf-analytics-448115.Kimia_Farma.kf_product p
),

-- Menggabungkan tabel transaksi dengan produk
transaction_with_product AS (
  SELECT
    t.transaction_id,
    t.date,
    t.branch_id,
    t.customer_name,
    t.product_id,
    p.product_name,
    p.persentase_gross_laba,
    p.actual_price,
    t.discount_percentage,
    (t.price * (1 - t.discount_percentage / 100)) AS nett_sales,
    ((t.price * (1 - t.discount_percentage / 100)) * p.persentase_gross_laba) AS nett_profit,
    t.rating AS rating_transaksi
  FROM rakamin-kf-analytics-448115.Kimia_Farma.kf_final_transaction t
  JOIN price_with_gross_margin p
    ON t.product_id = p.product_id
),

-- Menggabungkan dengan tabel cabang
transaction_with_branch AS (
  SELECT
    tp.transaction_id,
    tp.date,
    tp.branch_id,
    b.branch_name,
    b.kota,
    b.provinsi,
    b.rating AS rating_cabang,
    tp.customer_name,
    tp.product_id,
    tp.product_name,
    tp.actual_price,
    tp.discount_percentage,
    tp.persentase_gross_laba,
    tp.nett_sales,
    tp.nett_profit,
    tp.rating_transaksi
  FROM transaction_with_product tp
  JOIN rakamin-kf-analytics-448115.Kimia_Farma.kf_kantor_cabang b
    ON tp.branch_id = b.branch_id
)

-- Membuat tabel final
SELECT * FROM transaction_with_branch;
