# Лаборатори №7: Exploratory Testing (SBTM)

## Оюутны мэдээлэл

- Нэр: ANAR BATBOLD
- Код: B170910823

## Ашигласан орчин

### Node.js

```text
v24.19.0
```

### Аппликейшн

```text
Reading List Application
```

URL:

```text
http://localhost:3000
```

---

# Session Charter Summary

Тестийн зорилго:

Reading List аппликейшний ном нэмэх, хайх, устгах болон статистикийн функцуудыг exploratory аргачлалаар шалгах.

### Сонгосон аялалууд

#### Couch Potato Tour

Хоосон утга, баталгаажуулалт дутуу нөхцөлүүдийг шалгах.

#### Data Tour

Урт текст, давхардсан өгөгдөл, хайлт болон өгөгдлийн чанартай холбоотой асуудлыг шалгах.

#### Saboteur Tour

API болон системийн логикийг эвдэх оролдлого хийх.

---

# Session Information

| Үзүүлэлт | Утга |
|----------|----------|
| Test Type | Exploratory Testing |
| Approach | Session Based Test Management |
| Duration | 60 минут |
| Tester | ANAR BATBOLD |

---

# Session Timeline

## 14:00 – 14:10

- Charter review
- Application startup
- Initial exploration of UI

## 14:10 – 14:25

### Couch Potato Tour

Шалгасан зүйлс:

- Empty input
- Invalid values
- Missing data

Илрүүлсэн асуудал:

- Empty title accepted

## 14:25 – 14:40

### Data Tour

Шалгасан зүйлс:

- Search
- Long titles
- Duplicate values

Илрүүлсэн асуудал:

- Search is case-sensitive

## 14:40 – 14:50

### Saboteur Tour

Шалгасан зүйлс:

- API endpoints
- Statistics
- Consistency checks

Илрүүлсэн асуудал:

- Statistics mismatch

## 14:50 – 15:00

- Bug reproduction
- Screenshot collection
- Evidence collection
- Report preparation

---

# Илрүүлсэн согогууд

## Bug #1 – Empty book title can be added

### Severity

Medium

### Expected

Validation error should be displayed.

### Actual

Empty title is successfully added to the list.

### Impact

Invalid data can be stored in the application.

---

## Bug #2 – Statistics total count does not match displayed books

### Severity

Medium

### Expected

Total number of books should match displayed books.

### Actual

Statistics API returned:

```json
{
  "total": 7,
  "newest": 2024
}
```

while displayed data did not match that count.

### Impact

Users receive incorrect statistical information.

---

## Bug #3 – Search is case-sensitive

### Severity

Medium

### Expected

Searching for:

```text
clean code
```

should return:

```text
Clean Code
```

### Actual

No results are displayed.

### Impact

Search functionality is less usable and does not match user expectations.

---

# API Evidence

## Statistics API

Request:

```http
GET /api/stats
```

Response:

```json
{
  "total": 7,
  "newest": 2024
}
```

Full HTTP response is stored in:

```text
evidence/api-stats.txt
```

---

# Human Observation vs Automation

Exploratory testing revealed several issues that would be difficult to identify using simple automated checks alone.

### Human Observation

Discovered:

- Empty title acceptance
- Case-sensitive search behavior
- Inconsistent statistics

These issues required visual inspection and human judgement.

### Automation

Automated tests are effective for:

- Regression checking
- Repeated validation
- API verification

However, automated tests do not easily identify usability and user-experience issues without explicitly written assertions.

---

# Tour Findings

## Couch Potato Tour

Found missing validation for empty titles.

## Data Tour

Found search behavior issue related to character casing.

## Saboteur Tour

Found inconsistency between API statistics and displayed data.

---

# Obstacles Encountered

1. Determining whether statistics inconsistency originated from the UI or API required additional investigation.
2. Search issue was not obvious until different letter casing was tested.
3. Multiple reproductions were needed to confirm reported issues.

---

# Areas Covered

## Covered

- Add Book
- Search
- Delete Book
- Statistics
- REST API

## Not Covered

- Performance
- Security
- Concurrent users
- Cross-browser compatibility

---

# Дүгнэлт

Энэхүү лабораторийн ажлаар Session Based Test Management (SBTM) аргачлалыг ашиглан Reading List аппликейшнд exploratory тест хийлээ. Туршилтын явцад Couch Potato Tour, Data Tour болон Saboteur Tour гэсэн гурван өөр аяллыг ашигласан. Couch Potato Tour-ийн үеэр оролтын баталгаажуулалт дутуу байгааг илрүүлж, хоосон гарчигтай ном нэмэгдэх боломжтойг тогтоосон. Data Tour-ийн үеэр хайлтын функц том жижиг үсэг ялгаж ажиллаж байгааг илрүүлсэн бөгөөд энэ нь хэрэглэгчийн хүлээлттэй нийцэхгүй байв. Saboteur Tour-ийн үеэр API болон хэрэглэгчийн интерфейсийн мэдээллийг харьцуулан шалгаж статистикийн мэдээллийн зөрүүг илрүүлсэн. Exploratory тестийн гол давуу тал нь урьдчилан тодорхойлсон тест кейсгүйгээр системийн бодит зан төлөвийг судлах боломж олгодог явдал байв. Хүний ажиглалт шаардсан хэрэглэгчийн туршлага болон өгөгдлийн чанартай холбоотой асуудлуудыг автомат тестээр илрүүлэхэд хүндрэлтэй байдаг болохыг ажигласан. Харин API түвшний шалгалт нь интерфейс болон өгөгдлийн хоорондын зөрүүг илрүүлэхэд үр дүнтэй байлаа. Нийтдээ гурван өөр төрлийн согог илрүүлж, бүгдийг дахин давтан үзүүлж баталгаажуулсан. Энэхүү лабораторийн ажлын үр дүнд exploratory тестийг системтэйгээр төлөвлөх, гүйцэтгэх болон олдсон согогуудыг баримтжуулах дадлага олж авлаа.

---

# Repository Structure

```text
app.js

charter.md
session-report.md

bug-1.md
bug-2.md
bug-3.md

evidence/
└── api-stats.txt

screenshots/
├── bug-1-empty-title.png
└── bug-3-search-case-sensitive.png
```