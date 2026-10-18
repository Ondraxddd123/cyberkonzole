# NEON//TERMINAL

## Spuštění
1. Nainstaluj Node.js 18 nebo novější.
2. Otevři terminál v této složce.
3. Spusť `node server.js`.
4. Otevři `http://localhost:3000`.

## Demo příkazy
- Admin: `/logadmin 1test34`
- Běžný uživatel: `/login userpass123`
- Po přihlášení povinně: `/nick TvojePrezdivka`
- `/baninfo` — vlastní ban ID
- Admin: `/users`, `/bans`, `/events`, `/ban ID`, `/unban ID`, `/infoweb`
- `/logout`, `/logoutadmin`, `/help`

## Změna hesel
Linux/macOS:
`ADMIN_PASSWORD='silne-admin-heslo' USER_PASSWORD='silne-uzivatelske-heslo' node server.js`

PowerShell:
`$env:ADMIN_PASSWORD='silne-admin-heslo'; $env:USER_PASSWORD='silne-uzivatelske-heslo'; node server.js`

Data se ukládají do `data/db.json`, které server vytvoří při prvním spuštění. Hesla se do událostí nezapisují. Běžné přihlášení používá společné heslo a vytvoří novou identitu; pro veřejný web s trvalými účty je potřeba doplnit individuální účty a bezpečné obnovení hesla.

**Veřejné nasazení:** Nepoužívej obyčejné HTTP pro přihlašování přes internet. Dej aplikaci za HTTPS proxy/hosting, změň výchozí hesla a nastav `COOKIE_SECURE=true`. Toto je funkční startovací projekt, ne auditovaná produkční aplikace. Admin uvidí nick, ID, bany a auditní události, nikoli hesla.
