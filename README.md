# tugas-n8n-video-generator-drive
# Video Generator Google Drive (n8n)

**Nama:** Fachri Fadilah
**NIM:** 0110224146

Workflow n8n yang menerima link gambar dan prompt lewat n8n Form, membuat video
dari gambar tersebut dengan API video AI (Kie AI, model image-to-video), menunggu
hasilnya dengan polling loop, lalu mengunggah video hasil unduhan secara otomatis
ke folder Google Drive.

## Alur Workflow

```
Input Prompt -> Buat Task -> Tunggu 20 detik -> Cek Status -> Status Success?
                                  ^                              |-- true  -> Ambil URL Video -> Unduh Video -> Upload ke Google Drive
                                  |------------- false ----------|
```

## Node yang Digunakan

| Node | Fungsi |
|---|---|
| Input Prompt (n8n Form Trigger) | Menerima `img_url` (link gambar) dan `prompt` (deskripsi
