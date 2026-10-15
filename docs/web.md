# Veřejný web a vydávání

Veřejný [Svět](https://mujlinux.cloud/) obsluhuje Nginx na linuxovém VPS. Tablet sbírá data, počítač připravuje vydání a na VPS se přenáší pouze výsledná statická stránka. Pro čtení přehledu nemusí být počítač zapnutý.

## Co se přenáší

Výstupní balíček povoluje jen čtecí HTML. Databáze, interní ovládání, přihlašovací údaje a provozní logy nejsou součástí veřejné stránky. Kontrola před přenosem odmítá interní adresy, soukromé cesty, nepovolené skripty a externí závislosti stránky.

Nové vydání se nahraje odděleně a teprve po kontrole přepne na aktuální. Předchozí vydání zůstává dostupné pro návrat. Po přenosu se načte celé tělo odpovědi a jeho SHA-256 se porovná s připraveným HTML. Samotné HTTP 200 by shodu neprokázalo.

## HTTPS a provozní kontrola

HTTPS používá certifikát Let's Encrypt. Při nasazení 14. října 2026 bylo ověřené HTTPS pro hlavní doménu a varianty `www` a `svet`, přesměrování a shoda obsahu. Automatické obnovování je nastavené; zkušební obnova certifikátu ještě nebyla ověřena.

Veřejný web a domácí tablet se kontrolují zvlášť. Výpadek přenosu k tabletu neznamená, že selhalo veřejné vydání. Čas nahrání stránky také není časem poslední kontroly zpráv.

[Zpět na projekt](../README.md) · [Metoda výběru zpráv](methodology.md)
