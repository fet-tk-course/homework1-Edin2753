# Izvjestaj za zadacu br. 1

## Objašnjenje koda

### 1. Struktura klasa i odnosi
- `Osoba` je interfejs koji definira osnovne metode za prikaz informacija (`info`) i titule (`titula`).  
- `Inzenjer` je osnovna klasa koja implementira `Osoba` i dodaje svojstva: ime, prezime, profesija, godine iskustva i lista ekspertiza.  
- `SoftverskiInzenjer` i `InzenjerElektrotehnike` su izvedene klase koje proširuju `Inzenjer` i dodaju specifične atribute (`brojProjekata` ili `brojCertifikata`) te metodu `uspjesnost()`.  

### 2. Korištene funkcionalne operacije
- `fold` u funkciji `grupisiPoEkspertizi` akumulira inženjere u mapu po njihovim ekspertizama.  
- `reduce` u funkciji `najiskusnijiPoTipu` pronalazi najiskusnijeg inženjera po profesiji.  
- `aggregate` je ručno implementirana generička funkcija koja računa ukupan broj projekata i certifikata.  

### 3. Poređenje fold, reduce i aggregate
- `fold` = fleksibilno akumuliranje sa početnom vrijednošću; idealno za kreiranje novih kolekcija.  
- `reduce` = koristi prvi element kao početni akumulator; idealno za pronalaženje maksimuma/minimuma ili kombiniranje elemenata.  
- `aggregate` = funkcija prilagođena za specifične izračune; slična `fold`, ali ručno implementirana.  

### 4. Način pokretanja programa
- U funkciji `main` definira se lista inženjera.  
- Opcija 1, 2, 3 ili 4 određuje što se prikazuje: osoblje, funkcije, sve ili provjera grešaka.  
- Program ispisuje osoblje, grupiranje po ekspertizama, najiskusnijeg po tipu i ukupan broj projekata i certifikata.  
- Također demonstrira hvatanje grešaka pri neispravnom unosu (negativne godine ili prazna lista ekspertiza).

## Fold, Reduce i Aggregate u Kotlinu

Ovo je sažetak razlika i primjena funkcija **fold**, **reduce** i **aggregate** u programskom jeziku Kotlin.  

### 1. fold

**Opis:**  
Funkcija `fold` prolazi kroz listu i akumulira rezultat, počevši od početne vrijednosti koju zadaješ.

**Prednosti:**  
- Može akumulirati u bilo koji tip rezultata (`R`).  
- Fleksibilna za kreiranje novih kolekcija, sabiranje ili kombiniranje elemenata.  

**Kada koristiti:**  
- Za građenje novih kolekcija.  
- Za zbir, proizvod ili akumuliranje vrijednosti sa inicijalnim “seedom”.  

### 2. reduce

**Opis:**  
Funkcija `reduce` prolazi kroz listu i koristi **prvi element** kao početni akumulator, vraćajući jedan element.

**Prednosti:**  
- Jednostavna za pronalaženje maksimuma, minimuma ili kombinaciju elemenata.  

**Kada koristiti:**  
- Kad trebaš izračunati **jedan konačan rezultat** iz liste, npr. maksimum ili zbir elemenata bez posebnog početnog akumulatora.  


### 3. aggregate

**Opis:**  
`aggregate` je generička funkcija koja prima listu, početni akumulator i lambda funkciju koja određuje kako akumulirati elemente.

**Prednosti:**  
- Fleksibilna i može raditi s bilo kojim tipom akumulatora ili elemenata.  
- Omogućava prilagođene izračune i logiku.  

**Kada koristiti:**  
- Kad želiš napraviti **prilagođene izračune po elementima ili po ključevima**, npr. sabiranje projekata i certifikata različitih tipova.  

##Prikaz rezultata

Kod je napravljen tako da:  
- opcija 1 prikazuje osoblje,  
- opcija 2 prikazuje rezultate funkcija,  
- opcija 3 prikazuje sve,  
- opcija 4 prikazuje greške.  

Radi jednostavnosti ovdje su prikazane samo **opcija 3 i opcija 4**.  
Ako želite vidjeti rezultate pojedinačno, u kodu možete promijeniti varijablu `opcija` i pogledati komentare koji objašnjavaju kako funkcioniše.

---

### Prikaz opcije 3

--- Osoblje ---
Marko Markovic – Softverski inženjer – 6 godina – Projekti: 10 – Ekspertize: [Kotlin, Java]  
Ana Anic – Softverski inženjer – 7 godina – Projekti: 8 – Ekspertize: [Kotlin, Git]  
Luka Lukic – Softverski inženjer – 8 godina – Projekti: 12 – Ekspertize: [C++, Java]  
Ivan Ivanovic – Softverski inženjer – 4 godina – Projekti: 5 – Ekspertize: [JavaScript, HTML]  
Petra Petrovic – Softverski inženjer – 9 godina – Projekti: 7 – Ekspertize: [Python, Kotlin]  
Petar Petrovic – Inženjer elektrotehnike – 8 godina – Certifikati: 4 – Ekspertize: [PLC, CNC]  
Jelena Jelic – Inženjer elektrotehnike – 6 godina – Certifikati: 3 – Ekspertize: [Elektronika, PLC]  
Milan Milic – Inženjer elektrotehnike – 9 godina – Certifikati: 5 – Ekspertize: [Robotika, Energetika]  
Nikola Nikolic – Inženjer elektrotehnike – 7 godina – Certifikati: 2 – Ekspertize: [Elektro, PLC]  
Ivana Ivanovic – Inženjer elektrotehnike – 4 godina – Certifikati: 1 – Ekspertize: [Elektronika, PLC]  

--- Grupisanje po ekspertizama (fold) ---
Kotlin: [Marko Markovic, Ana Anic, Petra Petrovic]  
Java: [Marko Markovic, Luka Lukic]  
Git: [Ana Anic]  
C++: [Luka Lukic]  
Python: [Petra Petrovic]  
PLC: [Petar Petrovic, Jelena Jelic, Nikola Nikolic]  
CNC: [Petar Petrovic]  
Elektronika: [Jelena Jelic]  
Robotika: [Milan Milic]  
Energetika: [Milan Milic]  
Elektro: [Nikola Nikolic]  

--- Najiskusniji po tipu (reduce) ---
Najiskusniji Softverski inženjer: Petra Petrovic – 9 godina  
Najiskusniji Inženjer elektrotehnike: Milan Milic – 9 godina  

--- Ukupan broj projekata i certifikata (aggregate) ---
Ukupan broj projekata i certifikata u kompaniji: 57  

### Prikaz opcije 4

Greška (negativne godine): Broj godina iskustva ne može biti negativan  
Greška (prazna lista ekspertiza): Lista ekspertiza ne može biti prazna


##Koristenje AI alata

AI alat je korišten isključivo u svrhu **boljeg razumijevanja novih funkcionalnih operacija** te **davanja sugestija za organizaciju i izgled koda**.  
Sav kod je **napisan od strane studenta**, dok su svi dijelovi u kojima je AI pružio pomoć **označeni komentarima unutar koda**.  

AI je dodatno korišten za **ispravljanje gramatičkih grešaka**, kao i pri **izradi ovog `README_user.md` dokumenta**.