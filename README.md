# IshTop — saytni internetga chiqarish

Papkadagi fayllar: `index.html` (sayt), `robots.txt`, `sitemap.xml`.

## 1. Domenni almashtiring
`SIZNING-DOMEN.uz` o'rniga o'z domeningizni yozing (3 ta faylda):

    sed -i 's|SIZNING-DOMEN.uz|sizning-saytingiz.uz|g' index.html robots.txt sitemap.xml

## 2. Bepul joylash (Google Firebase Hosting)
1. https://firebase.google.com saytida Google hisobingiz bilan loyiha yarating.
2. Kompyuterda: `npm install -g firebase-tools`, keyin `firebase login`.
3. Shu papkada: `firebase init hosting`. Public papka sifatida `.` (nuqta) yozing, single-page app savoliga `No` deng, `index.html` ni ustiga yozmang.
4. `firebase deploy`. Sayt `loyiha-nomi.web.app` manzilida ochiladi.
5. O'z domeningizni Firebase konsolida «Add custom domain» orqali ulang.

Muqobil: Netlify yoki GitHub Pages ham shu papkani xuddi shunday joylaydi.

## 3. Google qidiruvida chiqishi uchun
1. https://search.google.com/search-console ga kiring va saytingizni qo'shing (domen yoki URL bo'yicha).
2. Egalikni tasdiqlang (Google bergan kodni `index.html` `<head>` qismiga qo'shing).
3. «Sitemaps» bo'limida `sitemap.xml` manzilini yuboring.
4. «URL tekshiruvi»da bosh sahifani kiritib, «Indekslashni so'rash» ni bosing.
Indekslanish bir necha kundan bir necha haftagacha davom etadi.

## 4. Chiqarishdan oldin muhim
- `index.html` boshidagi `var DEMO=true;` namunaviy e'lonlarni ko'rsatadi. Ular uydirma, ochiq saytda `false` qiling yoki haqiqiy e'lonlar bilan almashtiring.
- Foydalanuvchi e'lonlari hozir faqat o'z brauzerida saqlanadi. Hammaga umumiy ko'rinishi uchun server va ma'lumotlar bazasi kerak (masalan, Firebase Firestore va kirish tizimi).
