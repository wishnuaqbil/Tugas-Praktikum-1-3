# Tugas Praktikum 1-3
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
