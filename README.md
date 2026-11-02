# Kiyimni kiyib ko'ring (jonli virtual try-on)

Kamera orqali jonli kiyim kiydirish: kiyim rasmini tanlaysiz, u sizning ustingizda real vaqtda ko'rinadi.
Model: Decart `lucy-vton-latest` (realtime VTON). Sayt statik, GitHub Pages'da turadi.

## Qanday ishlaydi
1. `index.html` — kamera, kiyim tanlash, natija (brauzerda).
2. Token endpoint: `https://kiyim-token.vercel.app/api/token` — qisqa muddatli (120 s) client token beradi.
   Asosiy Decart kaliti faqat serverda (Vercel env `DECART_API_KEY`), brauzerga chiqmaydi.
3. Sessiya cheklovi: 180 soniya, model `lucy-vton-latest`.

## Narx
Decart: jonli sessiya $0.02/sekund → 1 daqiqa ≈ $1.20. Bir mijoz 3 daqiqa sinasa ≈ $3.60.

## Kiyim rasmini almashtirish
`garments/` papkasiga yangi rasm qo'ying (toza oq fon, kamida 512×512, kiyim yolg'iz) va
`index.html` dagi `.grid` blokiga yangi tugma qo'shing:
`<button class="item" data-img="/garments/YANGI.jpg" data-p="Substitute the current top with ...">`
