# Proteus Arduino Bağlama ve 7 Segment Display Kullanımı (Proteus #7)


🔗 [Web Siteme Bakmak İçin Tıkla](https://www.hakkiharmankaya.com/)

Bu projede, **Arduino Uno** kullanarak **7 segment display** üzerinde 0’dan 9’a kadar sayılar görüntülenecektir. Simülasyon ortamı olarak Proteus kullanılmaktadır. Hem bağlantılar hem de Arduino kodu örneği aşağıda yer almaktadır.

---

## 🧰 Gerekli Malzemeler

- Arduino Uno  
- 1 adet 7 Segment Display (Common Anode veya Common Cathode)  
- 7 adet 330Ω direnç  
- Proteus simülasyon yazılımı  

---

## 📘 Temel Bilgi

Bir 7 segment display, `a` ila `g` harfleriyle adlandırılmış 7 adet LED segmentinden oluşur. Hangi segmentlerin yandığına göre sayılar gösterilir.

---

## 🛠️ Devre Bağlantıları

**Proteus’ta Devre Kurulumu:**

1. Proteus’ta "P" tuşuna basarak `Arduino`, `7 Segment Display`, ve `Resistor` bileşenlerini ekle.
2. Arduino pinlerinden 7 segment display’e bağlantı yap:
   - D2 → Segment a  
   - D3 → Segment b  
   - D4 → Segment c  
   - D5 → Segment d  
   - D6 → Segment e  
   - D7 → Segment f  
   - D8 → Segment g  
3. Her bağlantı arasına 330Ω direnç ekle.
4. **Common Cathode** display kullanıyorsan ortak bacağı GND’ye,  
   **Common Anode** kullanıyorsan ortak bacağı VCC’ye bağla.

---

## 💻 Arduino Kodu

Aşağıdaki kod yalnızca `0` rakamını gösterir. Diğer rakamlar için `one()`, `two()` gibi fonksiyonlar oluşturulabilir.

```cpp
void setup() {
  pinMode(2,OUTPUT);
  pinMode(3,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(7,OUTPUT);
  pinMode(8,OUTPUT);
}

void loop() {
  zero(); // 0 rakamını göster
}

void zero() {
  digitalWrite(2,HIGH); // a
  digitalWrite(3,HIGH); // b
  digitalWrite(4,HIGH); // c
  digitalWrite(5,HIGH); // d
  digitalWrite(6,HIGH); // e
  digitalWrite(7,HIGH); // f
  digitalWrite(8,LOW);  // g (kapalı)
}
```

---

## ▶️ Simülasyonu Başlatma

1. Arduino üzerine `.hex` dosyasını yüklemek için:
   - Arduino’ya sağ tıkla → "Edit Properties"  
   - HEX dosyasını seçerek yükle  
2. "Run" butonuna basarak simülasyonu başlat.

---

## 🔍 Çalışma Prensibi

Arduino, 7 segment display’in her bir segmentini dijital sinyallerle kontrol eder. Kod tarafında her bir rakam için uygun segmentler **HIGH/LOW** durumuna getirilir. Böylece rakamlar sırasıyla gösterilebilir.

---

Bu basit uygulama, Proteus üzerinde **Arduino + 7 Segment Display** kullanımını öğrenmek ve temel dijital gösterimlerin nasıl yapıldığını simüle etmek için ideal bir örnektir.
