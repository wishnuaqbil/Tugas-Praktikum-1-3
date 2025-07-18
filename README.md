
# 📘 Tugas Praktikum 1–3

**👤 Nama**: Wishnu Aqbil Ramadani  
**🆔 NIM**: 312310591  
**🏫 Kelas**: TI.23.A6  
**📚 Mata Kuliah**: Pemrograman Web 2

---

## 🧪 Praktikum 1: PHP Framework (CodeIgniter)

### 🎯 Tujuan
1. ✅ Memahami konsep dasar Framework.
2. ✅ Memahami konsep dasar MVC.
3. ✅ Membuat program sederhana menggunakan Framework CodeIgniter4.

---

### ⚙️ Instalasi CodeIgniter 4
1. ⬇️ Unduh dari website resmi CodeIgniter.
2. 📂 Ekstrak ke direktori `htdocs/Lab11_php_ci/`.
3. ✏️ Ganti nama folder menjadi `ci4`.
4. 🌐 Akses di browser: `http://localhost/Lab11_php_ci/ci4/public/`.

---

### 🧠 Membuat Controller & View

**Contoh Controller:**
```php
public function about()
{
    return view('about', [
        'title'   => 'Halaman About',
        'content' => 'Ini adalah halaman about.'
    ]);
}
```

**Contoh View (`about.php`):**
```php
<h1><?= $title; ?></h1>
<p><?= $content; ?></p>
```

---

### 🧩 Layout Template

**Buat File:**
- `app/Views/template/header.php`
- `app/Views/template/footer.php`

**Panggil di View:**
```php
<?= $this->include('template/header'); ?>
<?= $this->include('template/footer'); ?>
```

---

## 🧪 Praktikum 2: CRUD (Create, Read, Update, Delete)

### 🎯 Tujuan
- ✅ Memahami konsep dasar Model.
- ✅ Membuat sistem CRUD menggunakan CodeIgniter4.

---

### 📄 Model (`ArtikelModel.php`)
```php
class ArtikelModel extends Model
{
    protected $table = 'artikel';
    protected $allowedFields = ['judul', 'isi', 'slug', 'gambar'];
}
```

---

### 🧠 Controller (`Artikel.php`)
```php
public function index()
{
    $model = new ArtikelModel();
    $artikel = $model->findAll();
    return view('artikel/index', compact('artikel'));
}
```

---

### 🖼️ View (`index.php`)
```php
<?php foreach ($artikel as $row): ?>
  <h2><?= $row['judul']; ?></h2>
  <p><?= substr($row['isi'], 0, 100); ?></p>
<?php endforeach; ?>
```

---

### 🌐 Tambahan Routing (`Routes.php`)
```php
$routes->get('/artikel/(:any)', 'Artikel::view/$1');
```

---

## 🧪 Praktikum 3: View Layout & View Cell

### 🎯 Tujuan
- ✅ Menggunakan Layout untuk struktur HTML yang konsisten.
- ✅ Menggunakan View Cell untuk komponen dinamis seperti sidebar/widget.

---

### 🧩 Contoh View Cell

**File: `app/Views/widget/recent_post.php`**
```php
<ul>
  <li>Post Terbaru 1</li>
  <li>Post Terbaru 2</li>
</ul>
```

**Panggil di Template Layout:**
```php
<?= view_cell('\App\Libraries\Widget::recentPosts') ?>
```

---

### 📝 Catatan:
- 🔗 Gunakan `base_url()` untuk semua link atau gambar.
- ⚠️ Pastikan file `Routes.php` sudah diatur dengan benar.
- 🔒 Tambahkan validasi dan keamanan sesuai kebutuhan proyek.

---
