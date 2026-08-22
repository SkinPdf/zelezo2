# Železo — webová verze

Aplikace na plánování a záznam posilování. Běží v prohlížeči, instaluje se na plochu, funguje offline. Žádný Apple účet, žádné certifikáty, žádné vypršení po sedmi dnech.

## Nasazení přes GitHub a Netlify

Nahraj **obsah** téhle složky do repozitáře na GitHubu — jednotlivé soubory, ne složku samotnou, jinak appka skončí na adrese s podsložkou.

V Netlify pak **Add new site → Import an existing project → GitHub**, vyber repozitář a nech pole *Build command* i *Publish directory* prázdná. Není co kompilovat.

Od té chvíle se každá změna v repozitáři nasadí sama.

### Rychlé vyzkoušení na počítači

```bash
python3 -m http.server 8000
```

Otevři `http://localhost:8000`. Service worker a instalace na plochu vyžadují HTTPS nebo localhost — proto nestačí soubor otevřít poklepáním.

## Instalace na iPhone

1. Otevři adresu v **Safari** (ne v Chromu — na iOS umí instalovat jen Safari).
2. Klepni na ikonu sdílení dole uprostřed.
3. Sjeď na **Přidat na plochu**.
4. Potvrď **Přidat**.

Objeví se ikona činky. Otevře se na celou obrazovku bez adresního řádku a funguje i v letadlovém režimu.

Na Androidu je to obdobné přes nabídku Chromu → Přidat na plochu.

**Důležité:** appku spouštěj z té ikony na ploše, ne přes Safari. Data se ukládají zvlášť pro každý způsob otevření.

## Balíček rutin

Soubor `rutiny-vrsek-tela.json` obsahuje tříddenní program se zaměřením na ramena, paže, předloktí, prsa a šířku zad, s třetím dnem na zadek a břicho. Načteš ho v aplikaci přes ozubené kolečko → **Načíst soubor**.

Import je slučovací: přidá jen chybějící cviky a rutiny, historii tréninků nechá být. Když balíček načteš dvakrát, cviky se neduplikují — druhá sada rutin jen dostane číslo za názvem.

Balíček zavádí dvě nové svalové partie, **Krk** a **Předloktí**.

## Kde jsou data

V úložišti prohlížeče na tvém telefonu. Nikde jinde. Nikdo jiný je nevidí, protože se nikam neodesílají.

Znamená to ale, že **záloha je na tobě**. V kalendáři vpravo nahoře je ozubené kolečko → *Stáhnout zálohu*. Uloží se JSON soubor, který jde stejným tlačítkem načíst zpět — třeba na novém telefonu. Doporučuju to udělat jednou za měsíc.

Data zmizí, když smažeš appku z plochy nebo v Safari vymažeš data webu. Restart telefonu ani aktualizace iOS jim neublíží.

## Jak se to používá

**Kalendář** se otevírá na dnešku. Barevné tečky značí tréninky: plná = odcvičeno, obrys = plánováno. Karta pod kalendářem ukazuje, co tě čeká, a spouští trénink.

**Rutiny** — dole je týdenní rozvrh, kde nastavíš, co se cvičí který den. Kalendář to promítne dopředu i dozadu. Jednotlivý den jde přebít přes *Změnit rutinu*. Níž jsou šablony (PPL, Upper/Lower, Full body), které si můžeš vzít a upravit.

**Cviky** — 38 předdefinovaných, filtr podle partie, hledání. Vlastní cvik přidáš tlačítkem, smažeš podržením prstu.

**Trénink** — u každé série je šedě, co jsi dal minule, a políčka jsou předvyplněná. Odškrtnutím se spustí pauza. Ikona kalkulačky u cviku ukáže, jaké kotouče naložit. Když jsi minule zvládl všechny série na horní hranici, appka sama nabídne o 2,5 kg víc.

**Progres** — odhadované 1RM podle Epleyho vzorce, takže 80 kg × 5 a 70 kg × 10 jde porovnat. Dál týdenní objem, série na partii proti doporučenému rozsahu, rekordy a upozornění na stagnaci.

**Sdílecí karty** — před tréninkem pozvánka pro parťáka, po tréninku výsledek do skupiny. Vygeneruje se skutečný PNG a otevře systémové sdílení.

## Co webová verze neumí

- Pauza nepípne, když je obrazovka zhasnutá — appka musí být vepředu. Obrazovku se snaží držet rozsvícenou, dokud je otevřená.
- Místo haptiky jen vibrace, a jen na Androidu. iOS to webu nedovolí.

## Sdílení s kamarády

Pošli jim odkaz. Nic neinstalují, nepotřebují počítač, a data mají každý svoje — nemíchají se, protože nic neopouští jejich telefon.
