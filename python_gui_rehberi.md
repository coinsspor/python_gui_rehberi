<![CDATA[# 🐍 Python ile Masaüstü Uygulama Geliştirme Rehberi

**Tkinter ile Adım Adım GUI Programlama**

> 📚 Lise Düzeyi - Başlangıç Seviyesi  
> 🏫 Alanya Mesleki ve Teknik Anadolu Lisesi - Bilişim Teknolojileri Bölümü  
> 📅 2025-2026 Eğitim Yılı

---

## 📋 İçindekiler

- [Bölüm 1: Giriş ve Kurulum](#bölüm-1-giriş-ve-kurulum)
- [Bölüm 2: İlk Penceremiz](#bölüm-2-ilk-penceremiz)
- [Bölüm 3: Label - Yazı Gösterme](#bölüm-3-label---yazı-gösterme)
- [Bölüm 4: Button - Butonlar](#bölüm-4-button---butonlar)
- [Bölüm 5: Entry - Metin Kutusu](#bölüm-5-entry---metin-kutusu)
- [Bölüm 6: Combobox - Açılır Liste](#bölüm-6-combobox---açılır-liste)
- [Bölüm 7: Listbox - Liste Kutusu](#bölüm-7-listbox---liste-kutusu)
- [Bölüm 8: Yerleştirme Yöneticileri](#bölüm-8-yerleştirme-yöneticileri)
- [Bölüm 9: Messagebox - Mesaj Kutuları](#bölüm-9-messagebox---mesaj-kutuları)
- [Bölüm 10: Mini Proje - Basit Hesap Makinesi](#bölüm-10-mini-proje---basit-hesap-makinesi)
- [Bölüm 11: Faydalı Bilgiler ve Ek Kütüphane Kurulumu](#bölüm-11-faydalı-bilgiler-ve-ek-kütüphane-kurulumu)

---

## Bölüm 1: Giriş ve Kurulum

### 1.1 Masaüstü Uygulama Nedir?

Masaüstü uygulaması, bilgisayarınızda doğrudan çalıştırdığınız programlardır. Örneğin Not Defteri, Hesap Makinesi, Paint gibi programlar birer masaüstü uygulamasıdır. Bu uygulamaların ortak özelliği pencereleri, butonları, metin kutuları gibi görsel öğeler (**GUI** - Graphical User Interface) içermeleridir.

Python ile masaüstü uygulaması geliştirmek için **Tkinter** kütüphanesini kullanacağız. Tkinter, Python ile birlikte gelen hazır bir kütüphanedir, yani ekstra bir şey yüklemenize gerek yoktur.

### 1.2 Gerekli Yazılımların Kurulumu

#### Adım 1: Python Kurulumu

1. [python.org](https://www.python.org) adresine gidin.
2. **Downloads** bölümünden en son sürümü indirin (örneğin Python 3.12).
3. Kurulum sırasında **"Add Python to PATH"** kutucuğunu mutlaka işaretleyin!
4. **"Install Now"** butonuna tıklayın ve kurulumun bitmesini bekleyin.

> ⚠️ **DİKKAT!** Kurulum sırasında "Add Python to PATH" seçeneğini işaretlemeyi unutmayın! Bu seçeneği işaretlemezseniz Python komutlarını komut satırından çalıştıramazsınız.

#### Adım 2: Kurulumu Doğrulama

Komut Satırını (CMD) açın ve aşağıdaki komutu yazın:

```bash
python --version
```

Ekranda `Python 3.12.x` gibi bir çıktı görüyorsanız kurulum başarılıdır.

#### Adım 3: Tkinter Kontrolü

Tkinter Python ile birlikte gelir. Kontrol etmek için CMD'de şu komutu yazın:

```bash
python -c "import tkinter; print('Tkinter hazır!')"
```

`Tkinter hazır!` yazısı çıkarsa her şey tamamdır.

#### Adım 4: Kod Editörü (Opsiyonel)

Python kodlarını yazmak için **IDLE** (Python ile birlikte gelir) kullanabilirsiniz. Daha gelişmiş bir editör isterseniz [Visual Studio Code (VS Code)](https://code.visualstudio.com) indirebilirsiniz.

> 💡 **İPUCU:** Python kurulumunda IDLE adında bir editör de gelir. Başlangıç için IDLE gayet yeterlidir. Başlat menüsünden "IDLE" aratarak bulabilirsiniz.

---

## Bölüm 2: İlk Penceremiz

### 2.1 Boş Bir Pencere Oluşturma

İlk programımızda ekranda boş bir pencere oluşturacağız. Bu, tüm GUI uygulamalarının temelini oluşturur.

```python
# ilk_pencere.py
import tkinter as tk

# Ana pencereyi oluştur
pencere = tk.Tk()

# Pencerenin başlığını ayarla
pencere.title("İlk Programım")

# Pencerenin boyutunu ayarla (genişlik x yükseklik)
pencere.geometry("400x300")

# Pencereyi çalıştır (ana döngü)
pencere.mainloop()
```

#### Kodun Açıklaması

- **`import tkinter as tk`**: Tkinter kütüphanesini projemize dahil ediyoruz. `tk` kısaltmasını kullanarak daha kısa kod yazıyoruz.
- **`tk.Tk()`**: Ana pencere nesnesini oluşturuyoruz. Her uygulamada bir tane ana pencere olmalıdır.
- **`pencere.title()`**: Pencerenin üst kısmındaki başlık yazısını ayarlar.
- **`pencere.geometry('400x300')`**: Pencere boyutunu 400 piksel genişlik, 300 piksel yükseklik olarak ayarlar.
- **`pencere.mainloop()`**: Pencereyi açık tutar ve kullanıcı etkileşimlerini dinler. Bu satır olmadan pencere hemen kapanır!

> 💡 **İPUCU:** `mainloop()` fonksiyonu programın kalbidir. Bu fonksiyon çalışmaya devam ettiği sürece pencere açık kalır ve buton tıklamaları, klavye girişleri gibi olayları dinler.

### 2.2 Pencere Özellikleri

Penceremize daha fazla özellik ekleyebiliriz:

```python
import tkinter as tk

pencere = tk.Tk()
pencere.title("Özellikli Pencere")
pencere.geometry("500x400")

# Pencere arka plan rengini değiştir
pencere.configure(bg="lightblue")

# Pencerenin minimum boyutunu ayarla
pencere.minsize(300, 200)

# Pencerenin maximum boyutunu ayarla
pencere.maxsize(800, 600)

# Pencereyi yeniden boyutlandırmayı kapat
# pencere.resizable(False, False)

pencere.mainloop()
```

---

## Bölüm 3: Label - Yazı Gösterme

### 3.1 Basit Etiket (Label)

Label, pencere üzerinde yazı göstermek için kullanılan en temel widget'tır (görsel öğe). Kullanıcı Label'a müdahale edemez, sadece okuyabilir.

```python
import tkinter as tk

pencere = tk.Tk()
pencere.title("Label Örneği")
pencere.geometry("400x200")

# Basit bir etiket oluştur
etiket = tk.Label(pencere, text="Merhaba Dünya!")
etiket.pack()  # Etiketi pencereye yerleştir

# Biçimlendirilmiş etiket
etiket2 = tk.Label(
    pencere,
    text="Renkli Yazı",
    font=("Arial", 20, "bold"),
    fg="blue",        # Yazı rengi (foreground)
    bg="yellow"       # Arka plan rengi (background)
)
etiket2.pack()

pencere.mainloop()
```

### Label Özellikleri Tablosu

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `text` | Gösterilecek yazı | `text="Merhaba"` |
| `font` | Yazı tipi ve boyutu | `font=("Arial", 14)` |
| `fg` | Yazı rengi | `fg="red"` |
| `bg` | Arka plan rengi | `bg="yellow"` |
| `width` | Genişlik (karakter) | `width=20` |
| `height` | Yükseklik (satır) | `height=2` |
| `anchor` | Yazı hizalama | `anchor="w"` (sol) |
| `relief` | Çerçeve stili | `relief="groove"` |

---

## Bölüm 4: Button - Butonlar

### 4.1 Basit Buton

Buton (Button), kullanıcının tıkladığında bir işlem yapmasını sağlayan görsel öğedir. Butonlara tıklandığında bir fonksiyon çalıştırılır.

```python
import tkinter as tk

pencere = tk.Tk()
pencere.title("Buton Örneği")
pencere.geometry("400x200")

# Butona tıklandığında çalışacak fonksiyon
def merhaba_de():
    etiket.config(text="Butona Basıldı!")

# Etiket oluştur
etiket = tk.Label(pencere, text="Henüz basılmadı", font=("Arial", 14))
etiket.pack(pady=20)

# Buton oluştur
buton = tk.Button(
    pencere,
    text="Tıkla Bana!",
    command=merhaba_de,    # Tıklandığında çalışacak fonksiyon
    font=("Arial", 12),
    bg="green",
    fg="white",
    width=15,
    height=2
)
buton.pack(pady=10)

pencere.mainloop()
```

#### Kodun Açıklaması

- **`def merhaba_de()`**: Butona tıklandığında çalışacak fonksiyonu tanımlıyoruz.
- **`command=merhaba_de`**: Butona hangi fonksiyonun bağlanacağını belirtiyoruz. Dikkat: Parantez yazmıyoruz! `merhaba_de` yazıyoruz, `merhaba_de()` değil.
- **`etiket.config(text=...)`**: Etiketin yazısını değiştirmek için `config()` metodunu kullanıyoruz.
- **`pack(pady=20)`**: Yerleştirme sırasında yukarıdan ve aşağıdan 20 piksel boşluk bırakır.

> ⚠️ **ÖNEMLİ HATA!** `command` parametresine fonksiyon yazarken parantez kullanmayın! `command=merhaba_de` doğru, `command=merhaba_de()` yanlıştır. Parantez koyarsanız fonksiyon program başlarken hemen çalışır, butona tıkladığınızda çalışmaz.

### 4.2 Sayaç Uygulaması

Şimdi butonlarla biraz daha ilginç bir örnek yapalım. Bir sayaç uygulaması yapacağız:

```python
import tkinter as tk

pencere = tk.Tk()
pencere.title("Sayaç Uygulaması")
pencere.geometry("300x200")

sayac = 0

def artir():
    global sayac
    sayac += 1
    etiket.config(text=str(sayac))

def azalt():
    global sayac
    sayac -= 1
    etiket.config(text=str(sayac))

def sifirla():
    global sayac
    sayac = 0
    etiket.config(text="0")

# Sayaç etiketi
etiket = tk.Label(pencere, text="0", font=("Arial", 40, "bold"))
etiket.pack(pady=20)

# Butonlar için bir çerçeve (frame)
buton_cerceve = tk.Frame(pencere)
buton_cerceve.pack()

tk.Button(buton_cerceve, text="-", command=azalt,
          font=("Arial", 14), width=5).pack(side="left", padx=5)
tk.Button(buton_cerceve, text="Sıfırla", command=sifirla,
          font=("Arial", 14), width=8).pack(side="left", padx=5)
tk.Button(buton_cerceve, text="+", command=artir,
          font=("Arial", 14), width=5).pack(side="left", padx=5)

pencere.mainloop()
```

> 💡 **YENİ KAVRAM: Frame** — Frame (çerçeve), widget'ları gruplamak için kullanılır. Yukarıdaki örnekte 3 butonu yan yana koymak için bir Frame kullandık. Frame görünmez bir kutu gibi düşünülebilir.

---

## Bölüm 5: Entry - Metin Kutusu

### 5.1 Basit Metin Kutusu

Entry widget'ı kullanıcıdan tek satırlık metin girişi almak için kullanılır. Form uygulamalarının vazgeçilmez öğesidir.

```python
import tkinter as tk

pencere = tk.Tk()
pencere.title("Metin Kutusu Örneği")
pencere.geometry("400x200")

# Etiket
tk.Label(pencere, text="Adınızı yazın:", font=("Arial", 12)).pack(pady=5)

# Metin kutusu
isim_kutusu = tk.Entry(pencere, font=("Arial", 14), width=25)
isim_kutusu.pack(pady=5)

def selamla():
    isim = isim_kutusu.get()  # Kutudaki yazıyı al
    if isim:
        sonuc.config(text=f"Merhaba {isim}!")
    else:
        sonuc.config(text="Lütfen isminizi yazın!")

tk.Button(pencere, text="Selamla", command=selamla,
          font=("Arial", 12)).pack(pady=10)

sonuc = tk.Label(pencere, text="", font=("Arial", 14), fg="blue")
sonuc.pack()

pencere.mainloop()
```

### Entry Temel Metodları

| Metod | Açıklama |
|-------|----------|
| `.get()` | Kutudaki yazıyı okur ve döndürür |
| `.delete(0, END)` | Kutudaki tüm yazıyı siler |
| `.insert(0, "metin")` | Kutuya yazı ekler (0 = başa ekle) |
| `.config(state="disabled")` | Kutuyu salt okunur yapar |
| `.config(show="*")` | Şifre kutusu yapar (karakterleri gizler) |

### 5.2 Giriş Formu Uygulaması

Şimdi birden fazla metin kutusu kullanarak basit bir öğrenci kayıt formu yapalım:

```python
import tkinter as tk
from tkinter import messagebox

pencere = tk.Tk()
pencere.title("Öğrenci Kayıt Formu")
pencere.geometry("400x350")

# Başlık
tk.Label(pencere, text="ÖĞRENCİ KAYIT FORMU",
         font=("Arial", 16, "bold"), fg="navy").pack(pady=10)

# Ad alanı
tk.Label(pencere, text="Ad:", font=("Arial", 11)).pack(anchor="w", padx=40)
ad_kutusu = tk.Entry(pencere, font=("Arial", 12), width=30)
ad_kutusu.pack(padx=40, pady=2)

# Soyad alanı
tk.Label(pencere, text="Soyad:", font=("Arial", 11)).pack(anchor="w", padx=40)
soyad_kutusu = tk.Entry(pencere, font=("Arial", 12), width=30)
soyad_kutusu.pack(padx=40, pady=2)

# Numara alanı
tk.Label(pencere, text="Okul No:", font=("Arial", 11)).pack(anchor="w", padx=40)
no_kutusu = tk.Entry(pencere, font=("Arial", 12), width=30)
no_kutusu.pack(padx=40, pady=2)

def kaydet():
    ad = ad_kutusu.get()
    soyad = soyad_kutusu.get()
    no = no_kutusu.get()
    if ad and soyad and no:
        messagebox.showinfo("Başarılı",
            f"{ad} {soyad} (No: {no}) kaydedildi!")
    else:
        messagebox.showwarning("Uyarı",
            "Tüm alanları doldurun!")

def temizle():
    ad_kutusu.delete(0, tk.END)
    soyad_kutusu.delete(0, tk.END)
    no_kutusu.delete(0, tk.END)

# Butonlar
buton_frame = tk.Frame(pencere)
buton_frame.pack(pady=15)
tk.Button(buton_frame, text="Kaydet", command=kaydet,
          font=("Arial", 11), bg="green", fg="white",
          width=10).pack(side="left", padx=5)
tk.Button(buton_frame, text="Temizle", command=temizle,
          font=("Arial", 11), bg="orange", fg="white",
          width=10).pack(side="left", padx=5)

pencere.mainloop()
```

> 💡 **YENİ KAVRAM: messagebox** — `messagebox` modülü, kullanıcıya bilgi, uyarı veya hata mesajları göstermek için kullanılır. Kullanmak için `from tkinter import messagebox` yazmak gerekir.

---

## Bölüm 6: Combobox - Açılır Liste

### 6.1 Basit Combobox

Combobox (açılır liste), kullanıcıya önceden belirlenmiş seçenekler arasından seçim yaptırmak için kullanılır. Tkinter'ın `ttk` modülünden gelir.

```python
import tkinter as tk
from tkinter import ttk  # ttk modülünü içe aktar

pencere = tk.Tk()
pencere.title("Combobox Örneği")
pencere.geometry("400x250")

tk.Label(pencere, text="Şehrinizi seçin:",
         font=("Arial", 12)).pack(pady=10)

# Combobox oluştur
sehirler = ["İstanbul", "Ankara", "İzmir", "Antalya",
            "Bursa", "Adana", "Trabzon"]

sehir_combo = ttk.Combobox(
    pencere,
    values=sehirler,
    font=("Arial", 12),
    width=25,
    state="readonly"  # Sadece listeden seçim yapılabilir
)
sehir_combo.pack(pady=5)
sehir_combo.set("Bir şehir seçin")  # Varsayılan yazı

def secim_goster():
    secilen = sehir_combo.get()
    sonuc.config(text=f"Seçiminiz: {secilen}")

tk.Button(pencere, text="Seçimi Göster",
          command=secim_goster,
          font=("Arial", 11)).pack(pady=10)

sonuc = tk.Label(pencere, text="", font=("Arial", 14), fg="green")
sonuc.pack()

pencere.mainloop()
```

### Combobox Özellikleri

| Özellik / Metod | Açıklama |
|-----------------|----------|
| `values=[...]` | Seçeneklerin listesi |
| `state="readonly"` | Kullanıcı sadece listeden seçer, yazamaz |
| `.get()` | Seçili değeri okur |
| `.set("değer")` | Varsayılan veya yeni değer atar |
| `.current(index)` | Belirtilen index'teki seçeneği seçer |
| `<<ComboboxSelected>>` | Seçim değişince tetiklenen olay |

### 6.2 Olay Bağlama (Event Binding)

Combobox'ta seçim değiştiğinde otomatik işlem yapmak için `bind()` metodunu kullanabiliriz:

```python
import tkinter as tk
from tkinter import ttk

pencere = tk.Tk()
pencere.title("Otomatik Seçim")
pencere.geometry("400x200")

renkler = ["Kırmızı", "Mavi", "Yeşil", "Sarı", "Turuncu"]
renk_kodlari = {
    "Kırmızı": "red", "Mavi": "blue",
    "Yeşil": "green", "Sarı": "yellow", "Turuncu": "orange"
}

tk.Label(pencere, text="Bir renk seçin:",
         font=("Arial", 12)).pack(pady=10)

renk_combo = ttk.Combobox(pencere, values=renkler,
                          state="readonly", font=("Arial", 12))
renk_combo.pack()

sonuc = tk.Label(pencere, text="Renk Kutusu",
                 font=("Arial", 16, "bold"),
                 width=20, height=3, relief="groove")
sonuc.pack(pady=15)

def renk_degisti(event):  # event parametresi gerekli!
    secilen = renk_combo.get()
    kod = renk_kodlari[secilen]
    sonuc.config(bg=kod, text=secilen)

# Seçim değişince fonksiyonu çağır
renk_combo.bind("<<ComboboxSelected>>", renk_degisti)

pencere.mainloop()
```

> 💡 **YENİ KAVRAM: bind()** — `bind()` metodu, bir olaya (event) fonksiyon bağlamak için kullanılır. Combobox'ta seçim değişince `<<ComboboxSelected>>` olayı tetiklenir. Bağlanan fonksiyonun mutlaka `event` parametresi alması gerekir.

---

## Bölüm 7: Listbox - Liste Kutusu

### 7.1 Basit Listbox

Listbox, birden fazla öğeyi liste halinde gösteren ve kullanıcının seçim yapabileceği bir widget'tır. Combobox'tan farkı, tüm seçeneklerin aynı anda görünür olmasıdır.

```python
import tkinter as tk

pencere = tk.Tk()
pencere.title("Listbox Örneği")
pencere.geometry("400x350")

tk.Label(pencere, text="Meyve Listesi:",
         font=("Arial", 12, "bold")).pack(pady=5)

# Listbox oluştur
liste = tk.Listbox(
    pencere,
    font=("Arial", 12),
    width=25,
    height=8,
    selectmode=tk.SINGLE  # Tek seçim modu
)
liste.pack(pady=5)

# Listeye öğe ekle
meyveler = ["Elma", "Armut", "Muz", "Çilek",
            "Portakal", "Karpuz", "Üzüm", "Kiraz"]

for meyve in meyveler:
    liste.insert(tk.END, meyve)  # Listenin sonuna ekle

def secileni_goster():
    secim = liste.curselection()  # Seçili index'leri al
    if secim:
        index = secim[0]
        deger = liste.get(index)  # Index'teki değeri al
        sonuc.config(text=f"Seçilen: {deger}")
    else:
        sonuc.config(text="Bir öğe seçin!")

tk.Button(pencere, text="Seçimi Göster",
          command=secileni_goster,
          font=("Arial", 11)).pack(pady=5)

sonuc = tk.Label(pencere, text="", font=("Arial", 13), fg="purple")
sonuc.pack()

pencere.mainloop()
```

### Listbox Temel Metodları

| Metod | Açıklama |
|-------|----------|
| `.insert(END, "öğe")` | Listenin sonuna yeni öğe ekler |
| `.insert(0, "öğe")` | Listenin başına öğe ekler |
| `.delete(index)` | Belirtilen index'teki öğeyi siler |
| `.delete(0, END)` | Tüm öğeleri siler |
| `.get(index)` | Belirtilen index'teki değeri döndürür |
| `.curselection()` | Seçili öğelerin index'lerini döndürür |
| `.size()` | Listedeki öğe sayısını döndürür |
| `selectmode=MULTIPLE` | Birden fazla seçime izin verir |

### 7.2 Dinamik Liste - Öğe Ekleme ve Silme

Kullanıcının listeye öğe ekleyip çıkarabildiği daha gelişmiş bir örnek:

```python
import tkinter as tk
from tkinter import messagebox

pencere = tk.Tk()
pencere.title("Yapılacaklar Listesi")
pencere.geometry("420x400")

tk.Label(pencere, text="YAPILACAKLAR LİSTESİ",
         font=("Arial", 16, "bold"), fg="navy").pack(pady=10)

# Ekleme alanı
ekleme_frame = tk.Frame(pencere)
ekleme_frame.pack(pady=5)

giris = tk.Entry(ekleme_frame, font=("Arial", 12), width=25)
giris.pack(side="left", padx=5)

def ekle():
    yazi = giris.get().strip()
    if yazi:
        liste.insert(tk.END, yazi)
        giris.delete(0, tk.END)  # Kutuyu temizle
    else:
        messagebox.showwarning("Uyarı", "Bir şey yazın!")

tk.Button(ekleme_frame, text="Ekle", command=ekle,
          font=("Arial", 11), bg="#4CAF50",
          fg="white").pack(side="left", padx=5)

# Liste
liste = tk.Listbox(pencere, font=("Arial", 12),
                   width=35, height=10)
liste.pack(pady=10)

def sil():
    secim = liste.curselection()
    if secim:
        liste.delete(secim[0])
    else:
        messagebox.showwarning("Uyarı",
            "Silmek için bir öğe seçin!")

def tumu_sil():
    if liste.size() > 0:
        cevap = messagebox.askyesno("Onay",
            "Tüm öğeleri silmek istiyor musunuz?")
        if cevap:
            liste.delete(0, tk.END)

# Silme butonları
sil_frame = tk.Frame(pencere)
sil_frame.pack()
tk.Button(sil_frame, text="Seçili Sil", command=sil,
          font=("Arial", 11), bg="#f44336",
          fg="white", width=12).pack(side="left", padx=5)
tk.Button(sil_frame, text="Tümünü Sil", command=tumu_sil,
          font=("Arial", 11), bg="#ff9800",
          fg="white", width=12).pack(side="left", padx=5)

pencere.mainloop()
```

---

## Bölüm 8: Yerleştirme Yöneticileri

Widget'ları pencereye yerleştirmek için 3 yöntem vardır. Bu bölümde hepsini öğreneceksiniz.

### 8.1 pack() - Basit Yerleştirme

`pack()`, widget'ları sırasıyla yukarıdan aşağıya (veya yana) dizer. En kolay yerleştirme yöntemidir.

```python
# pack() örnekleri
etiket.pack()                    # Yukarıdan aşağıya dizer
etiket.pack(side="left")         # Sola yaslar
etiket.pack(side="right")        # Sağa yaslar
etiket.pack(pady=10)             # Yukarıda-aşağıda boşluk
etiket.pack(padx=10)             # Solda-sağda boşluk
etiket.pack(fill="x")            # Yatayda tüm alanı doldur
etiket.pack(expand=True)         # Boş alanı paylaş
etiket.pack(anchor="w")          # Sola dayalı yerleştir
```

### 8.2 grid() - Tablo Yerleştirme

`grid()`, widget'ları satır ve sütun numaralarıyla bir tablo gibi yerleştirir. Form tasarımlarında çok kullanışlıdır.

```python
import tkinter as tk

pencere = tk.Tk()
pencere.title("Grid Örneği - Giriş Formu")
pencere.geometry("400x200")

# Satır 0
tk.Label(pencere, text="Kullanıcı Adı:",
         font=("Arial", 11)).grid(row=0, column=0,
                                   padx=10, pady=10, sticky="e")
kullanici = tk.Entry(pencere, font=("Arial", 11), width=20)
kullanici.grid(row=0, column=1, padx=10, pady=10)

# Satır 1
tk.Label(pencere, text="Şifre:",
         font=("Arial", 11)).grid(row=1, column=0,
                                   padx=10, pady=10, sticky="e")
sifre = tk.Entry(pencere, font=("Arial", 11),
                 width=20, show="*")
sifre.grid(row=1, column=1, padx=10, pady=10)

# Satır 2 - Buton 2 sütunu kaplayan
tk.Button(pencere, text="Giriş Yap",
          font=("Arial", 11), bg="navy", fg="white",
          width=20).grid(row=2, column=0,
                         columnspan=2, pady=15)

pencere.mainloop()
```

### grid() Parametreleri

| Parametre | Açıklama |
|-----------|----------|
| `row` | Satır numarası (0'dan başlar) |
| `column` | Sütun numarası (0'dan başlar) |
| `padx, pady` | Dış boşluklar (piksel) |
| `sticky` | Hizalama: n(kuzey), s(güney), e(doğu), w(batı) |
| `columnspan` | Kaç sütun kaplayacağı |
| `rowspan` | Kaç satır kaplayacağı |

> ⚠️ **DİKKAT!** Aynı pencere veya frame içinde `pack()` ve `grid()`'i karıştırmayın! Ya hep `pack()`, ya da hep `grid()` kullanın. Karıştırmak programın hata vermesine neden olur.

### 8.3 place() - Koordinat ile Yerleştirme

`place()`, widget'ları piksel koordinatlarıyla tam istediğiniz yere yerleştirir:

```python
etiket.place(x=50, y=100)         # Piksel ile
etiket.place(relx=0.5, rely=0.5,  # Oransal (% olarak)
             anchor="center")      # Merkeze hizala
```

---

## Bölüm 9: Messagebox - Mesaj Kutuları

`messagebox` modülü, kullanıcıya çeşitli mesaj pencereleri göstermek için kullanılır.

```python
from tkinter import messagebox

# Bilgi mesajı
messagebox.showinfo("Başlık", "Bu bir bilgi mesajıdır.")

# Uyarı mesajı
messagebox.showwarning("Uyarı", "Dikkatli olun!")

# Hata mesajı
messagebox.showerror("Hata", "Bir hata oluştu!")

# Evet/Hayır sorusu (True veya False döndürür)
cevap = messagebox.askyesno("Soru", "Devam etmek istiyor musunuz?")
if cevap:
    print("Evet seçildi")
else:
    print("Hayır seçildi")

# Tamam/İptal sorusu
sonuc = messagebox.askokcancel("Onay", "Silmek istediğinize emin misiniz?")
```

---

## Bölüm 10: Mini Proje - Basit Hesap Makinesi

Şimdi öğrendiğimiz tüm bilgileri kullanarak basit bir hesap makinesi yapacağız. Bu projede butonlar, metin kutuları, etiketler ve combobox kullanacağız.

```python
import tkinter as tk
from tkinter import ttk, messagebox

pencere = tk.Tk()
pencere.title("Basit Hesap Makinesi")
pencere.geometry("380x300")
pencere.configure(bg="#f0f0f0")

# Başlık
tk.Label(pencere, text="HESAP MAKİNESİ",
         font=("Arial", 18, "bold"),
         bg="#f0f0f0", fg="#333").pack(pady=10)

# Giriş alanı
giris_frame = tk.Frame(pencere, bg="#f0f0f0")
giris_frame.pack(pady=5)

tk.Label(giris_frame, text="1. Sayı:",
         font=("Arial", 11), bg="#f0f0f0").grid(
         row=0, column=0, padx=5, pady=5, sticky="e")
sayi1 = tk.Entry(giris_frame, font=("Arial", 12), width=12)
sayi1.grid(row=0, column=1, padx=5, pady=5)

tk.Label(giris_frame, text="2. Sayı:",
         font=("Arial", 11), bg="#f0f0f0").grid(
         row=1, column=0, padx=5, pady=5, sticky="e")
sayi2 = tk.Entry(giris_frame, font=("Arial", 12), width=12)
sayi2.grid(row=1, column=1, padx=5, pady=5)

# İşlem seçimi
tk.Label(giris_frame, text="İşlem:",
         font=("Arial", 11), bg="#f0f0f0").grid(
         row=2, column=0, padx=5, pady=5, sticky="e")
islem = ttk.Combobox(giris_frame,
    values=["Toplama (+)", "Çıkarma (-)",
            "Çarpma (x)", "Bölme (/)"],
    state="readonly", font=("Arial", 11), width=14)
islem.grid(row=2, column=1, padx=5, pady=5)
islem.set("Toplama (+)")

def hesapla():
    try:
        s1 = float(sayi1.get())
        s2 = float(sayi2.get())
        secilen = islem.get()

        if "Toplama" in secilen:
            sonuc_deger = s1 + s2
        elif "Çıkarma" in secilen:
            sonuc_deger = s1 - s2
        elif "Çarpma" in secilen:
            sonuc_deger = s1 * s2
        elif "Bölme" in secilen:
            if s2 == 0:
                messagebox.showerror("Hata",
                    "Sıfıra bölme yapılamaz!")
                return
            sonuc_deger = s1 / s2

        # Tam sayı ise tam göster
        if sonuc_deger == int(sonuc_deger):
            sonuc_deger = int(sonuc_deger)

        sonuc.config(text=f"Sonuç: {sonuc_deger}")
    except ValueError:
        messagebox.showerror("Hata",
            "Lütfen geçerli sayılar girin!")

def temizle():
    sayi1.delete(0, tk.END)
    sayi2.delete(0, tk.END)
    islem.set("Toplama (+)")
    sonuc.config(text="Sonuç: -")

# Butonlar
buton_frame = tk.Frame(pencere, bg="#f0f0f0")
buton_frame.pack(pady=10)

tk.Button(buton_frame, text="Hesapla",
          command=hesapla, font=("Arial", 12, "bold"),
          bg="#4CAF50", fg="white",
          width=10).pack(side="left", padx=5)
tk.Button(buton_frame, text="Temizle",
          command=temizle, font=("Arial", 12),
          bg="#f44336", fg="white",
          width=10).pack(side="left", padx=5)

# Sonuç etiketi
sonuc = tk.Label(pencere, text="Sonuç: -",
                 font=("Arial", 18, "bold"),
                 bg="#f0f0f0", fg="#1565C0")
sonuc.pack(pady=10)

pencere.mainloop()
```

---

## Bölüm 11: Faydalı Bilgiler ve Ek Kütüphane Kurulumu

### 11.1 Ek Kütüphane: CustomTkinter

Tkinter'ın varsayılan görünümü biraz eski moda kalabilir. Daha modern görünümlü uygulamalar için **CustomTkinter** kütüphanesini kullanabilirsiniz.

**Kurulum:**

```bash
pip install customtkinter
```

**Örnek:**

```python
import customtkinter as ctk

# Tema ayarı ("dark", "light", "system")
ctk.set_appearance_mode("dark")
ctk.set_default_color_theme("blue")

pencere = ctk.CTk()
pencere.title("Modern Uygulama")
pencere.geometry("400x300")

ctk.CTkLabel(pencere, text="Modern Görünüm!",
             font=("Arial", 20)).pack(pady=20)

ctk.CTkButton(pencere, text="Modern Buton",
              font=("Arial", 14)).pack(pady=10)

ctk.CTkEntry(pencere, placeholder_text="Bir şey yazın...",
             font=("Arial", 12), width=250).pack(pady=10)

pencere.mainloop()
```

### 11.2 Ek Kütüphane: ttkbootstrap

Bir diğer modern görünüm seçeneği **ttkbootstrap** kütüphanesidir:

```bash
pip install ttkbootstrap
```

### 11.3 Sık Yapılan Hatalar ve Çözümleri

| Hata | Çözüm |
|------|-------|
| Pencere hemen kapanıyor | `mainloop()` yazılmamış. Kodun sonuna `pencere.mainloop()` ekleyin. |
| `command=fonksiyon()` çalışmıyor | Parantezi kaldırın: `command=fonksiyon` (parantezsiz). |
| `pack()` ve `grid()` birlikte hata | Aynı container içinde sadece birini kullanın. |
| Entry'den sayı alınamıyor | `get()` string döndürür. `int()` veya `float()` ile dönüştürün. |
| Türkçe karakter sorunu | Dosya başına `# -*- coding: utf-8 -*-` ekleyin. |
| `ModuleNotFoundError` | `pip install kütüphane_adı` ile kütüphaneyi yükleyin. |
| Widget görünmüyor | `pack()`, `grid()` veya `place()` çağrılmamış olabilir. |

### 11.4 Widget Hiyerarşisi Özeti

| Widget | Görevi | Kullanım |
|--------|--------|----------|
| `Tk()` | Ana pencere | Her uygulamada 1 tane |
| `Label` | Yazı gösterme | Bilgi, başlık gösterme |
| `Button` | Tıklanan buton | İşlem başlatma |
| `Entry` | Tek satırlık giriş | Form alanları |
| `Text` | Çok satırlık giriş | Yazı editörü |
| `Combobox` | Açılır liste | Seçeneklerden seçim |
| `Listbox` | Liste kutusu | Birden fazla öğe listeleme |
| `Frame` | Gruplama kutusu | Widget'ları organize etme |
| `Checkbutton` | Onay kutusu | Evet/hayır seçimi |
| `Radiobutton` | Tek seçim butonu | Grup içinden 1 seçim |
| `Scale` | Kaydırıcı | Sayısal değer ayarlama |
| `Canvas` | Çizim alanı | Şekil, grafik çizme |

---

> 📝 Bu doküman, Python ile masaüstü uygulama geliştirme konusunda başlangıç seviyesinde bilgi vermek amacıyla hazırlanmıştır. Bol bol pratik yaparak öğrenmeye devam edin!
]]>