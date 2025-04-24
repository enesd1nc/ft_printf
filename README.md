# ft_printf: C Dilinde Biçimlendirilmiş Çıktı Fonksiyonu

Bu proje, C dilinde standart `printf` fonksiyonunun özelleştirilmiş bir versiyonunu sunmaktadır. `ft_printf`, çeşitli veri türlerini biçimlendirilmiş bir şekilde standart çıktıya yazdırmanıza olanak tanır. Bu, programlama sürecinizde hata ayıklama ve çıktıları düzenleme konusunda size esneklik sağlayacaktır.

## Özellikler

*   **Desteklenen Dönüşüm Belirleyiciler:**
    *   `%c`: Karakter yazdırır.
    *   `%s`: String yazdırır.
    *   `%p`: İşaretçi adresini yazdırır.
    *   `%d` ve `%i`: Ondalık (decimal) tam sayı yazdırır.
    *   `%u`: İşaretsiz ondalık tam sayı yazdırır.
    *   `%x`: İşaretsiz onaltılık (hexadecimal) tam sayıyı küçük harflerle yazdırır.
    *   `%X`: İşaretsiz onaltılık tam sayıyı büyük harflerle yazdırır.
    *   `%%`: Yüzde işareti (%) yazdırır.

# 🌟 Öğrendiğim Kazanımlar – Variadic Fonksiyonlar 🌟

## 📚 Konu: `stdarg.h` – C'de Değişken Sayıda Argüman Alan Fonksiyonlar

C dilinde bazı durumlarda fonksiyonlara kaç tane argüman verileceği önceden bilinmeyebilir. İşte tam bu noktada `stdarg.h` kütüphanesi devreye girer! Bu kütüphane sayesinde değişken sayıda argüman alan (variadic) fonksiyonlar yazabiliriz. 📦

---

## 🔧 Kullanılan Makrolar

### 📌 `va_list`
📝 Argümanları sırayla çekebilmek için tanımladığımız veri tipidir. `va_list`, argümanları dolaşmak için kullanılan bir veri yapısıdır. Fonksiyonun içinde tanımlanarak `va_start` ile başlatılır ve `va_arg` ile her bir argüman alınabilir.

```c
va_list args;
```

---

### 🚀 `va_start`
⏩ Argümanlar arasında gezinmeye başlamak için kullanılır. Bu makro, `va_list` değişkenini başlatmak ve sabit argümandan sonra gelen değişken argümanları hazırlamak için kullanılır. Kullanımı, sabit argümandan sonra gelir.

```c
va_start(args, last_fixed_param);
```

---

### 🔁 `va_arg`
🔍 Sıradaki argümanı çekmek için kullanılır. Bu makro ile `va_list`'ten bir sonraki argüman belirli bir türde alınır. Dikkat: tür doğru verilmelidir, aksi takdirde beklenmeyen davranışlar oluşabilir.

```c
va_arg(args, int);
```

---

### 🛑 `va_end`
✅ Argüman okuma işlemi bittiğinde `va_list` değişkenini sonlandırmak için kullanılır. Bellek sızıntısı olmaması ve sistem kaynaklarının düzgün yönetimi için her `va_start` çağrısı bir `va_end` ile sonlandırılmalıdır.

```c
va_end(args);
```

---

## Kurulum

1.  Projeyi klonlayın:

    ```bash
    git clone https://github.com/enesd1nc/ft_printf.git ftPrintf
    ```

2.  Projeye gidin:

    ```bash
    cd ft_printf
    ```

3.  Kitaplığı derleyin:

    ```bash
    make
    ```

4.  Oluşan `libftprintf.a` dosyasını projenize bağlayın.

## Kullanım

Fonksiyonu kullanmak için projenize `libftprintf.h` başlık dosyasını ekleyin:

```c
#include "libftprintf.h"

int main(void)
{
    // Karakter yazdırma
    ft_printf("Karakter: %c\n", 'A');  // Çıktı: Karakter: A

    // String yazdırma
    ft_printf("String: %s\n", "Merhaba Dünya!");  // Çıktı: String: Merhaba Dünya!

    // İşaretçi adresi yazdırma
    int num = 42;
    int *ptr = &num;
    ft_printf("İşaretçi adresi: %p\n", ptr);  // Çıktı: İşaretçi adresi: 0x7ffee0f869ac

    // Ondalık tam sayı yazdırma
    ft_printf("Ondalık tam sayı: %d\n", 12345);  // Çıktı: Ondalık tam sayı: 12345

    // İşaretsiz ondalık tam sayı yazdırma
    ft_printf("İşaretsiz ondalık tam sayı: %u\n", 4294967295);  // Çıktı: İşaretsiz ondalık tam sayı: 4294967295

    // Onaltılık tam sayı yazdırma (küçük harf)
    ft_printf("Onaltılık tam sayı (küçük harf): %x\n", 255);  // Çıktı: Onaltılık tam sayı (küçük harf): ff

    // Onaltılık tam sayı yazdırma (büyük harf)
    ft_printf("Onaltılık tam sayı (büyük harf): %X\n", 255);  // Çıktı: Onaltılık tam sayı (büyük harf): FF

    // Yüzde işareti yazdırma
    ft_printf("Yüzde işareti: %%\n");  // Çıktı: Yüzde işareti: %

    return 0;
}
```
