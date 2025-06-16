# Naudojant AISVS

Dirbtinio intelekto saugumo patikros standartas (AISVS) apibrėžia saugumo reikalavimus moderniosioms DI programėlėms ir paslaugoms, daugiausia dėmesio skiriant aspektams, kuriuos kontroliuoja programėlių kūrėjai.

AISVS yra skirtas visiems, kurie kuria arba vertina dirbtinio intelekto programų saugumą, įskaitant kūrėjus, architektus, saugumo inžinierius ir auditorius. Šiame skyriuje pristatoma AISVS struktūra ir naudojimas, įskaitant jos patikros lygius ir numatytus naudojimo atvejus.

## Dirbtinio intelekto saugumo tikrinimo lygiai

AISVS apibrėžia tris augančio lygio saugumo patikros lygius. Kiekvienas lygis praplečia ir sudėtingina patikros procesą, leidžiant organizacijoms pritaikyti savo saugumo poziciją prie jų dirbtinio intelekto sistemų rizikos lygio.

Organizacijos gali pradėti nuo 1 lygio ir palaipsniui pereiti prie aukštesnių lygių, kai didėja saugumo brandumas ir grėsmių poveikis.

### Lygmenų apibrėžimas

Kiekvienas reikalavimas AISVS v1.0 yra priskirtas vienam iš šių lygių:

#### 1 lygio reikalavimai

1 lygis apima pačius svarbiausius ir pagrindinius saugumo reikalavimus. Jie orientuoti į bendrų atakų, kurios nepriklauso nuo kitų išankstinių sąlygų ar pažeidžiamumų, užkirtimą. Dauguma 1 lygio kontrolės priemonių yra arba paprastai įgyvendinamos, arba pakankamai svarbios, kad pateisintų pastangas.

#### 2 lygio reikalavimai

2 lygis apima sudėtingesnius arba rečiau pasitaikančius išpuolius, taip pat sluoksniuotas gynybas nuo plačiai paplitusių grėsmių. Šie reikalavimai gali apimti sudėtingesnę logiką arba būti skirti konkretiems išpuolių išankstiniams sąlygoms.

#### 3 lygio reikalavimai

3 lygis apima valdymo priemones, kurios paprastai yra sunkiau įgyvendinamos arba taikomos tam tikrose situacijose. Jos dažnai atspindi gynybos gilumo mechanizmus arba sprendimus prieš specifinius, taikinius ar didelės sudėtingumo atakas.

### Rolė (D/V)

Kiekvienas AISVS reikalavimas yra pažymėtas pagal pagrindinę auditoriją:

* D – Reikalavimai, orientuoti į kūrėjus
* V – Reikalavimai, orientuoti į tikrintojus/auditorius
* D/V – Svarbu tiek kūrėjams, tiek patikrintojams

