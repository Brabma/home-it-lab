# Záchrana denní zálohy

## Situace

Tablet drží nasbíraná data jen několik dní, potom je maže. Každý den se proto záloha uzavřeného dne stahuje na počítač. Záloha za 11. října 2026 se po Wi-Fi přerušila a na počítači zůstal jen neúplný soubor.

## Postup

Neúplný soubor zůstal stranou, nic se nepřepisovalo ani nemazalo. Nový přenos proběhl po kabelu (USB) a než nahradil běžnou zálohu, prošel těmito kontrolami:

1. Kontrolní součet souboru na tabletu se shoduje se součtem na počítači.
2. Soubor jde celý rozbalit a končí závěrečným záznamem.
3. Počet záznamů odpovídá.
4. Databáze obnovená ze zálohy projde kontrolou neporušenosti.
5. Nechybí žádná ze čtvrthodinových dávek.

## Výsledek

| Údaj | Hodnota |
|---|---:|
| Záznamů za 11. 10. 2026 UTC | 188 521 |
| Dávek (96 v každé ze dvou řad) | 192 ze 192 |
| Velikost zálohy | 76 MB |
| Velikost obnovené databáze | 342 MB |
| Kontrola databáze | v pořádku |

Stejným způsobem se zálohuje i provoz: 52 souborů včetně pěti databází, každá prošla kontrolou zvlášť.

## Kontrola obnovitelnosti

- Stažený soubor ještě není záloha. Zálohou je až ve chvíli, kdy z něj jde data obnovit.
- Neúplný pokus se nemaže, dokud není hotová ověřená náhrada.
- Pro velké přenosy se vyplatí druhá cesta, tady kabel.
