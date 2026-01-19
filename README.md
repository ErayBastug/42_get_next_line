# 42_get_next_line

Bu proje, bir dosya tanımlayıcısından (`file descriptor`) **satır satır okuma** işlemi yapan bir C fonksiyonunu içerir.

## Özellikler
- `read()` kullanarak dosyadan veri okur
- Her çağrıda bir satır döndürür
- Satır sonlarını (`\n`) korur
- Bellek yönetimi yapılmıştır (memory leak yok)
- `BUFFER_SIZE` değerinden bağımsız çalışır

## Kullanım
```c
int fd = open("dosya.txt", O_RDONLY);
char *line;

while ((line = get_next_line(fd)) != NULL)
{
    printf("%s", line);
    free(line);
}
close(fd);
