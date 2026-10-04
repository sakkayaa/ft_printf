# ft_printf

> **C ile variadic fonksiyonlar ve formatlı çıktı**  
> Standart `printf` fonksiyonunun temel format belirteçlerini yeniden uygulayan, yeniden kullanılabilir bir statik C kütüphanesi.

## Proje hakkında

`ft_printf`, değişken sayıda argüman alan (`variadic`) bir fonksiyonu C dilinde uygulama çalışmasıdır. Format metnini tarar, `%` belirteçlerini ilgili argümanlarla eşleştirir, çıktıyı standart çıktıya yazar ve yazdırılan karakter sayısını döndürür.

Proje; `stdarg.h` ile argüman yönetimi, format ayrıştırma, farklı veri türlerini yazdırma, pointer gösterimi ve çıktı uzunluğunu hesaplama konularında pratik sunar. Derleme sonunda `libftprintf.a` statik kütüphanesi oluşturulur.

## Öne çıkanlar

- **Variadic argüman yönetimi:** `va_list`, `va_start`, `va_arg` ve `va_end`
- **Format ayrıştırma:** format string’i ile argümanları sıralı eşleştirme
- **Karakter, string ve sayı çıktısı**
- **Onaltılık ve pointer gösterimi**
- **Yazdırılan karakter sayısını döndürme**
- **Statik kütüphane:** Makefile ile `libftprintf.a` üretimi

## Desteklenen format belirteçleri

| Belirteç | Açıklama |
|---|---|
| `%c` | Karakter |
| `%s` | String; null pointer için `(null)` çıktısı |
| `%p` | Pointer adresi (`0x` önekiyle) |
| `%d`, `%i` | İşaretli tam sayı |
| `%u` | İşaretsiz tam sayı |
| `%x`, `%X` | Küçük veya büyük harfli onaltılık sayı |
| `%%` | Yüzde işareti |

## Gereksinimler

- C derleyicisi (`gcc` veya uyumlu bir derleyici)
- `make`

## Derleme

Depoyu klonlayıp proje klasörüne geçin:

```bash
git clone <repository-url>
cd printf
```

Statik kütüphaneyi oluşturun:

```bash
make
```

Derleme sonunda proje klasöründe `libftprintf.a` oluşur.

## Başka bir projede kullanma

`ft_printf.h` dosyasını dahil edin ve programınızı kütüphaneyle birlikte derleyin:

```c
#include "ft_printf.h"

int main(void)
{
    int printed = ft_printf("Merhaba, %s! Sayı: %d\n", "C", 42);
    return (printed < 0);
}
```

```bash
cc -Wall -Wextra -Werror -I/path/to/printf \
  main.c /path/to/printf/libftprintf.a -o app
```

`/path/to/printf` kısmını `ft_printf.h` ve `libftprintf.a` dosyalarının bulunduğu konumla değiştirin.

## Makefile komutları

| Komut | Açıklama |
|---|---|
| `make` | `libftprintf.a` kütüphanesini oluşturur |
| `make clean` | Nesne dosyalarını siler |
| `make fclean` | Nesne dosyalarıyla birlikte kütüphaneyi siler |
| `make re` | Temiz derleme yapar |

## Öğrenme çıktıları

Bu çalışma; C’de değişken sayıda argüman alan fonksiyonları kullanma, format metnini ayrıştırma, farklı veri türlerini çıktıya dönüştürme ve modüler bir statik kütüphane hazırlama becerilerini gösterir.

## Geliştiren

**Sedef Akkaya**  
GitHub: [sakkayaa](https://github.com/sakkayaa) · LinkedIn: [Sedef Akkaya](https://www.linkedin.com/in/sedef-akkaya-0a5580228/)

---

*Formatı çöz, argümanı yazdır, çıktıyı kontrol et.*
