# PlantsTracking — публічні сторінки

Privacy Policy + Support, готові для GitHub Pages. Живий, редагований контент — не архів, онови файли тут коли зміниться домен/пошта чи текст політики.

## Як опублікувати (один раз)

1. Створи **новий, окремий, публічний** репозиторій на GitHub (не в цьому — цей приватний, а Pages з приватного репо потребує платний план). Наприклад `plantstracking-web`.
2. Скопіюй три файли з цієї папки (`index.html`, `privacy-policy.html`, `support.html`) у корінь нового репо.
3. Запуш:
   ```bash
   cd path/to/plantstracking-web
   git init
   git add index.html privacy-policy.html support.html
   git commit -m "Add privacy policy and support pages"
   git branch -M main
   git remote add origin https://github.com/<твій-акаунт>/plantstracking-web.git
   git push -u origin main
   ```
4. На GitHub: **Settings → Pages** → Source: "Deploy from a branch" → Branch: `main`, папка `/ (root)` → Save.
5. За хвилину-дві сторінка з'явиться на `https://<твій-акаунт>.github.io/plantstracking-web/privacy-policy.html` (і `/support.html`).

## Якщо хочеш свій домен (напр. plantstracking.app)

1. У тому ж репо: Settings → Pages → Custom domain → введи `plantstracking.app` (або піддомен, напр. `legal.plantstracking.app`).
2. У DNS свого домену (там, де купував домен) додай запис, який покаже GitHub:
   - Для кореневого домену — чотири `A`-записи на IP GitHub Pages (GitHub покаже їх сам у тому ж вікні).
   - Для піддомену — простіше: один `CNAME`-запис на `<твій-акаунт>.github.io`.
3. Почекай на DNS (від кількох хвилин до кількох годин), GitHub сам оформить безкоштовний HTTPS-сертифікат.

## Після публікації

Онови URL у двох місцях, щоб усе показувало вже реальну адресу, а не тимчасове посилання:
- **App Store Connect** → App Information → Privacy Policy URL / Support URL.
- **Код застосунку**: `Sources/Views/SettingsView.swift`, константи `privacyPolicyURLString`/`supportURLString` на самому початку файлу.
