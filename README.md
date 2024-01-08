# url-dinamis-ci

# Membuat Dinamic Base URL dan Clean URL pada CodeIgniter 3.X
Di tulisan ini saya akan berbagi cara membuat Base URL yang bersih dan dinamis pada CodeIgniter 3.X.

Berikut penjelasannya:

# Setting Dinamic Base URL

Secara umum, kita harus membuat base url secara manual seperti contoh:

**$config['base_url']=http://localhost/namaproject;**
. Namun, dengan Base URL yang dinamis akan memudahkan kita untuk tidak setting secara manual alias otomatis. :) Caranya teman-teman membuka root

application/config/config.php
. Lalu gantilah kode

**$config['base_url']**

seperti di bawah ini:

**$config['base_url'] = ((isset($_SERVER['HTTPS']) && $_SERVER['HTTPS'] == "on") ? "https" : "http");
$config['base_url'] .= "://".$_SERVER['HTTP_HOST'];
$config['base_url'] .= str_replace(basename($_SERVER['SCRIPT_NAME']),"",$_SERVER['SCRIPT_NAME']);**
