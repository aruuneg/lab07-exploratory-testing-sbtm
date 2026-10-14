\# Лаборатори №7: Exploratory Testing (SBTM)



\## Оюутны мэдээлэл



\- Нэр: ANAR BATBOLD

\- Код: B170910823

\- Хичээл: F.CSA313 Программ хангамжийн чанарын баталгаа ба тест



\---



\# Туршилтын орчин



\## Node.js



```text

v24.19.0

```



\## Аппликейшн



```text

Reading List Application

```



URL:



```text

http://localhost:3000

```



\---



\# Charter Summary



Судлах хүрээ:



\- Ном нэмэх

\- Ном хайх

\- Ном устгах

\- Статистик

\- REST API



Ашигласан турууд:



\- Couch Potato Tour

\- Data Tour

\- Saboteur Tour



Туршилтын зорилго нь өгөгдлийн баталгаажуулалт, статистикийн үнэн зөв байдал, хайлтын ажиллагаа болон хэрэглэгчийн интерфейсийн доголдлыг илрүүлэх байв.



\---



\# Session Information



| Үзүүлэлт | Утга |

|----------|----------|

| Test Type | Exploratory Testing |

| Approach | Session Based Test Management |

| Duration | 60 минут |

| Tester | ANAR BATBOLD |

| Application | Reading List |



\---



\# Судалсан хэсгүүд



\## UI



\- Add Book

\- Search

\- Delete Book

\- Statistics



\## API



\- GET /api/books

\- GET /api/stats



\---



\# Илрүүлсэн согогууд



\## Bug #1 – Empty book title can be added



\### Severity



Medium



\### Steps



1\. Гарчгийг хоосон үлдээнэ.

2\. Year оруулна.

3\. Add товч дарна.



\### Expected Result



```text

Validation error should be displayed.

Book should not be added.

```



\### Actual Result



```text

Book is added successfully.

Empty book appears in the list.

```



\### Evidence



Хоосон гарчигтай мөр жагсаалтад нэмэгдсэн.



\---



\## Bug #2 – Statistics count does not match displayed books



\### Severity



Medium



\### Steps



1\. Номын жагсаалтыг харна.

2\. API статистик шалгана.



\### API Response



```json

{

&#x20; "total": 7,

&#x20; "newest": 2024

}

```



\### Expected Result



```text

Total book count should equal displayed books.

```



\### Actual Result



```text

Displayed books and API statistics do not match.

```



\### Evidence



`/api/stats` API ба UI жагсаалтын мэдээлэл зөрсөн.



\---



\## Bug #3 – Search is case-sensitive



\### Severity



Medium



\### Steps



1\. "Clean Code" ном байгаа байх.

2\. Search талбарт:



```text

clean code

```



гэж бичнэ.



3\. Search дарна.



\### Expected Result



```text

Clean Code should be found.

```



\### Actual Result



```text

No results returned.

```



\### Evidence



Search хэрэглэгчийн жижиг үсгээр бичсэн хайлтыг олж чадаагүй.



\---



\# API Evidence



\## Statistics API



Request:



```http

GET /api/stats

```



Response:



```json

{

&#x20; "total": 7,

&#x20; "newest": 2024

}

```



\---



\# Эрсдэлийн үнэлгээ



| Асуудал | Эрсдэл |

|----------|----------|

| Empty title | Мэдээллийн чанар алдагдах |

| Incorrect statistics | Буруу тайлан, буруу тооцоолол |

| Case-sensitive search | Хайлт ашиглахад хүндрэлтэй |



\---



\# Session Assessment



Туршилтын хугацаанд үндсэн UI болон API хэсгүүдийг шалгасан. Хоосон утгууд, урт утгууд, хайлт болон статистиктай холбоотой асуудлуудыг судалсан. Системийн үндсэн ажиллагаа ажиллаж байсан боловч мэдээллийн баталгаажуулалт дутуу байсан. Search функц

