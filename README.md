# IT-infrastruktuuri projekt:
Raamatupidamis firma

### Meeskond
* Laura
* Kristjan

### Meie ülesanne
* **Kasuatjate arv:** 11
* **Ettevõtte tüüp:** Raamatupidamis firma
* **Eritingimus:** Kaugtöö on vajalik
* **Süsteem:** Windows server

Projekt on edukalt teostatud ja testitud Windows Server keskkonnas. Kõik infrastruktuuri osad on loodud ja seadistatud vastavalt etteantud stsenaariumile.

## Teostatud seadistused ja arhitektuur

1. **Active Directory domeenikontroller (AD DS):**
   * Loodud sisevõrgu domeen nimega `raamatupidamisfirma.local`.
   * Seadistatud kohalik DNS-server sisevõrgu nime lahendamiseks.

2. **Kasutajate haldus:**
   * Loodud jaotusüksus (Organizational Unit) nimega `Raamatupidajad`.
   * Lisatud 11 unikaalset kasutajakontot (`user1` - `user11`) koos paroolipoliitikaga *Password never expires* (mugavamaks sisevõrgu testimiseks).

3. **Failihaldus ja turvalisus:**
   * Loodud tsentraalne ühiskaust `C:\Firmadokumendid`.
   * Määratud võrgu- (Sharing) ja failisüsteemi (Security) õigused, mis lubavad ainult `Domain Users` grupi liikmetele täieliku ligipääsu (Full Control).

4. **Kaugtöö lahendus (Remote Desktop Services):**
   * Paigaldatud **Remote Desktop Services (RDS)** kaugtöölaua teenus kasutades *Quick Start* sessioonipõhist lahendust.
   * Kõik 11 raamatupidajat saavad kodust turvaliselt üle krüpteeritud sessiooni serveri töölauale sisse logida ja otse ühiskaustas faile töödelda.
