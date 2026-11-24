# BUG-02: Буруу JSON POST хүсэлтэд 200 OK буцдаг

Орчин: Уншлагын жагсаалт v2.0 API, curl.exe, Windows PowerShell, Node.js v24.19.0, 2026-11-24
Урьдчилсан нөхцөл: `node app.js`-ийг шинээр асаасан; апп `localhost:3000` дээр ажиллаж байна.

## Дахин гаргах алхам

1. PowerShell нээж дараах командыг ажиллуулна:

   ```powershell
   curl.exe --include --silent --show-error --request POST http://localhost:3000/api/books --header "Content-Type: application/json" --data-binary "{invalid json"
   ```

Хүлээгдэж байсан: HTTP `400` алдаа буцна.

Бодит үр дүн: `HTTP/1.1 200 OK` болон `{"result":"OK"}` буцна.

Ноцтой байдал: Major — буруу хүсэлт амжилттай мэт харагдаж, API хэрэглэгч буруу төлөвт итгэж болно.

Хавсралт: Бүтэн `curl -i` гаралт `../evidence/bug-02-curl.txt`
Олдсон аялал: Saboteur (API)
