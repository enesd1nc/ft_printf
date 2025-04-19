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

## Kurulum

1.  Projeyi klonlayın:

    ```bash
    git clone git@github.com:ehabesdev/printf.git
    ```

2.  Projeye gidin:

    ```bash
    cd printf
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
