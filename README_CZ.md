# LaskaKit TPS61169 Boost LED driver s konstantním proudem

Kompaktní DC-DC měnič určený pro napájení [výkonových LED](https://www.laskakit.cz/vyhledavani/?string=LED) z nízkého napětí nebo [LED vláken](https://www.laskakit.cz/vyhledavani/?string=LED%20vl%C3%A1kno). Modul využívá integrovaný obvod **TPS61169**, který zvyšuje vstupní napětí a zároveň **udržuje konstantní proud protékající LED**. Zátěž na výstupu musí být na vyšší napětí než je vstupní napětí, aby regulace proudu fungovala správně.

Na rozdíl od běžných boost měničů **nereguluje výstupní napětí, ale proud**. Napětí na výstupu se automaticky přizpůsobí (zvyší než je na vstupu) tak, aby LED odebíraly nastavený proud.

Typické použití:

- napájení výkonových LED
- LED vlákna
- série více LED z Li-ion / 5 V zdroje
- podsvícení panelů

Integrovaný měnič může dosahovat účinnosti až **90 %** v závislosti na vstupním napětí a zatížení.

---

# Klíčové vlastnosti

- boost LED driver s konstantním proudem  
- vstupní napětí **2.7 – 5.5 V**  
- výstupní napětí až **≈38 V**  
- nastavitelný LED proud až **≈400 mA** pomocí DIP přepínače 
- ochrana proti přerušení LED (open-LED protection)  
- soft-start a tepelná ochrana  
- spínací frekvence cca **1.2 MHz**

---

# Elektrické limity (velmi důležité)

Tyto hodnoty jsou limity čipu – při návrhu aplikace je nutné počítat s rezervou.

## Vstupní napětí

**2.7 V – 5.5 V**

Typické zdroje:

- Li-ion článek
- 3×AA
- (USB) 5 V

---

## Výstupní napětí

- automaticky řízené, pro správnou funkčnost musí být zátěž na vyšší napětí
- maximálně cca **38 V**

Napětí není pevné – měnič ho zvýší jen tak vysoko, aby LED teklo nastavený proud.

---

## Výstupní proud

Typicky:

**25 – 400 mA**

Proud je nastaven rezistorem na pinu FB. Pro jednoduchou změnu protékajícího proudu jsme použili DIP přepínač.

---

## Maximální výkon

Reálný výkon je omezen:

- proudem spínače (~1.2 A)
- účinností
- vstupním napětím

Typické **orientační** hodnoty:

| Vin | ILED | Vout max (přibližně) |
|----|----|----|
| 5 V | 100 mA | ~30 V |
| 5 V | 200 mA | ~20 V |
| 5 V | 400 mA | ~10 V |

⚠ **Maximální proud a maximální napětí nelze dosáhnout současně.**

---

# Zapojení

Typické zapojení:

- Na výstup připoj například LED vlákno
- Nastav DIP přepínačem potřebný proud
- Na vstup připoj vhodný zdroj energie - 3xAA baterie, Li-Ion akumulátor, DC adaptér
- Uprav svítivost LED vlákna DIP přepínačem tak, aby vyhovoval tvé potřebě (proud můžeš měnit během svícení)
- Pokud odpojíš LED vlákno z měniče, ale na vstupu je napětí, může se aktivovat ochrana proti přepětí. Po opětovném připojení LED vlákna bude (nejspíše) potřebné odpojit a znovu připojit vstupní napětí (restart)

---

# Na co si dát pozor

## 1. Není to zdroj napětí

Tento modul **není klasický boost měnič**.

Bez LED může výstupní napětí vystoupat až do aktivace přepěťové ochrany na výstupu

Používej jej pouze s LED nebo jinou zátěží určenou pro **konstantní proud**.

## 2. Nepřekračuj výkon

Velmi častá chyba:

400 mA × 30 V = 12 W

To už tento driver **nezvládne**.

Při vyšším rozdílu napětí musí být proud menší. Viz. Typické orientační hodnoty

## 3. Neodpojuj výstup při připojeném vstupu

Jak jsme zmínili výše, při odpojení výstupu a připojeném vstupu se může aktivovat přepěťová ochrana čipu. To může způsobit vypnutí čipu. Pokud opětovně připojíš LED vlákno, může se stát, že LED vlákno nebude svítit. Je potřeba "restartovat" čip a to provedeš odpojením a připojením vstupního napětí při připojené zátěži

---

# Modul koupíš na https://www.laskakit.cz/laskakit-tps61169-boost-led-driver-s-konstantnim-proudem/
