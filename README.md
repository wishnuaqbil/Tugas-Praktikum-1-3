# Tugas Praktikum 1–3

**Nama**: Wishnu Aqbil Ramadani  
**NIM**: 312310591  
**Kelas**: TI.23.A6  
**Mata Kuliah**: Pemrograman Web 2

---

## Praktikum 1: PHP Framework (CodeIgniter)

### Tujuan
1. Memahami konsep dasar Framework.
2. Memahami konsep dasar MVC.
3. Membuat program sederhana menggunakan Framework CodeIgniter4.

### Instalasi CodeIgniter 4
1. Unduh dari website resmi.
2. Ekstrak ke `htdocs/Lab11_php_ci`.
3. Ganti nama folder jadi `ci4`.
4. Jalankan di `http://localhost/Lab11_php_ci/ci4/public/`.

### Membuat Controller & View
Contoh controller:
```php
public function about()
{
    return view('about', [
        'title'   => 'Halaman About',
        'content' => 'Ini adalah halaman about.'
    ]);
}

Contoh view (about.php):

php
Copy
Edit
<h1><?= $title; ?></h1>
<p><?= $content; ?></p>
Layout Template
Buat template/header.php dan footer.php, lalu panggil di setiap view menggunakan:

php
Copy
Edit
<?= $this->include('template/header'); ?>
<?= $this->include('template/footer'); ?>
Praktikum 2: CRUD (Create, Read, Update, Delete)
Tujuan
Memahami konsep dasar Model.

Membuat sistem CRUD menggunakan CodeIgniter4.

Model (ArtikelModel.php)
php
Copy
Edit
class ArtikelModel extends Model
{
    protected $table = 'artikel';
    protected $allowedFields = ['judul', 'isi', 'slug', 'gambar'];
}
Controller (Artikel.php)
php
Copy
Edit
public function index()
{
    $model = new ArtikelModel();
    $artikel = $model->findAll();
    return view('artikel/index', compact('artikel'));
}
View (index.php)
php
Copy
Edit
<?php foreach ($artikel as $row): ?>
  <h2><?= $row['judul']; ?></h2>
  <p><?= substr($row['isi'], 0, 100); ?></p>
<?php endforeach; ?>
Tambahan Routing
Tambahkan di app/config/Routes.php:

php
Copy
Edit
$routes->get('/artikel/(:any)', 'Artikel::view/$1');
