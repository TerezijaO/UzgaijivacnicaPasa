Terezija Obradović



Ekonomski fakultet u Osijeku

Kolegij: Razvoj poslovnih aplikacija
01.06.2023. 
 
Sadržaj
1.	Uvod	1
1.1	Svrha aplikacije	1
1.2	Korisnici aplikacije	1
1.3	Koristi (benefiti) od aplikacije	1
2.	Zahtjevi	1
2.1	Funkcijski zahtjevi	1
2.2	Sistemski, hardverski i mrežni zahtjevi	1
2.3	Sigurnost	1
2.4	Korisnički zahtjevi	1
2.5	Slučajevi (scenariji) korištenja (use-case dijagrami)	2
2.5.1. Slučaj korištenja 1: Pregled pasa	2
2.5.2.	Slučaj korištenja 2: Dodavanje novog Psa	3
2.5.3.	Slučaj korištenja 3: Uređivanje pasa	3
2.5.4.	Slučaj korištenja 4: Brisanje Pasa	3
2.6.	Dijagrami klasa	4
3.	Dizajn korisničkog sučelja	5
3.5.	Glavni principi dizajna korišteni u aplikaciji	5
3.6.	Wireframe-ovi i Mockup-i	6




 
1.	Uvod
1.1	Svrha aplikacije 
Ova aplikacija služi za pregledavanje pasa koji su na prodaju. Ona podržava unos uređivanje, brisanje, pretragu I popis svih pasa u bazi. Aplikacija također omogućuje brisanje I prikaz detalja pojedinog psa. Svaki unos podataka kroz aplikaciju uključuje provjeru valjanosti te je za brisanje podataka potrebna posebna potvrda korisnika.

1.2	Korisnici aplikacije
Aplikaciji mogu pristupiti svi korisnici koji imaju internet I internet preglednik te žele pristupiti svim bitnim informacijama o psima koje namjeravaju kupiti na jednom centraliziranom mjestu.
1.3	Koristi (benefiti) od aplikacije
<Koje koristi u smislu promjena u odnosu na postojeće stanje u tvrtci ili instituciji će ova aplikacija donijeti – što će automatizirati, što će se raditi brže, hoće li donijeti neke nove uvide (izvješća) u podatke, hoće li pridonijeti većoj dostupnosti informacija i kako to može povećati uspješnost poslovanja (očekuje li se smanjenje nekih troškova i kojih, ili povećanje prihoda i kojih)>

Stvoriti će se jedna centralna baza podataka o fpsoma dostupna svima. Kada korisnici budu htjeli potražiti informacije o psima, neće više morati pretraživati putem Googla I koristiti više izvora za dobivanje informacija o pojedinom psu, jer će kroz aplikaciju moći dobiti sve potrebne infrmacije na jednom mjestu. Aplikacija će biti dostupna putem interneta zahvaljujući tome, korisnik ima mogućnost korištenja aplikacije u bilo koje vrijeme.   
2.	Zahtjevi
2.1	Funkcijski zahtjevi
Aplikacija mora omogućiti spremanje uređivanje, pretraživanje, traženje I pretraživanje pasa u bazi podataka.
2.2	Sistemski, hardverski i mrežni zahtjevi
Budući da će aplikacija biti razvijena u ASP.NET Core MCV-U, ona treba biti smještena na Microsoft Web poslužitelju(eng.server). Sljedeće hardverske aplikacije: Minimum četvero jezgreni processor radnog takta 2.2 GHz, minimum 32 GB RAM memorije, Minimum 1TB diskovnog prostora, Operativni sustav Windows server 2019



2.2.1. web server
Koristit će se windows azure za hostanje aplikacije. Windows azure može hostati bilo koju ASP.NET Core MCV aplikaciju uključujući I naši predloženu aplikaciju u ovom dokumentu.
Skaliranje je vrlo jednostavno jer je Micosoft odgovoran za dodavanje resursa na poslužitelju za vrijeme visokog prometa. Troškovi su minimalni, oni ovise o količini podataka koji se prikazuju posjetiteljima, te održavanje hardware nije uključeno u njih. 

2.2.2. Baza podataka
Koristi se SQL server baza podataka unutar WA, za temeljnu bezu podataka aplikacije. Što se tiče web poslužitelja, ona osigurava visoku dostupnost hostinga za bazu podataka s dobrim omjerom vrijednosti za uloženi novac. To posebno ima smisla ako je I web aplikacija hostana na Windows azureu.

2.3	Sigurnost
U razvoju aplikacije razviti će se sigurna identifikacija I zaštićena autentifikacija gdje korisnička imena I lozinke ne smiju biti spremljena u obična tekstualna polja ili datoteke, a osobni podaci korisnika kao što su adresa, tel brojevi I brojevi krednitnih kartica neće biti dostupni anonimnom pristupu. 
2.4	Korisnički zahtjevi
<Ovdje navesti detaljni popis korisničkih zahtjeva – preporučeno u tablici, i to po vrstama korisnika - koje će vrste korisnika biti omogućene, što od operacija treba moći svaka vrsta korisnika napraviti, tj. tko će moći unositi, tko ispravljati, tko brisati, gdje će se spremati podaci, koja su izvješća potrebna, itd.>

Tablica. Korisnički zahtjevi

Rb.	Zahtjev	Vrsta korisnika (user / admin)
1.	Prikaz svih pasa	Anonimni korisnik
2.	Pretraga pasa po vrsti	Anonimni korisnik
3.	Unos psa	Registrirani korisnik
4.	Uređivanje psa	Regsitrirani korisnik
5.  	Brisanje psa	Aministrator 
6.	Provjera valjanosti podataka kod unosa ureiđivanja	Registrirani korisnik

7.	Potvrda s pitanjem “Jeste li sigurni ?” prije brisanja psa	Admimitrator
8.	Prikaz detalja pojedinog psa	Anonimni korisnik
9. 	Početna stranica dolaska na aplikaciju mora sadržavati osnovne informacije o svrsi aplikacije. 	Anonimni korisnik

2.5	Slučajevi (scenariji) korištenja (use-case dijagrami) 
Sljedeći slučajevi korištenja opisuju scenarije u kojima korisnici web aplikacije koriste predloženu aplikaciju za upravljanje psima. U tim slučajevima korištenja su uključene osnovne operacije, stoga ih ne treba smatrati konačnim. Kako napreduje razvoj dodatna funkcionalnost može biti dodana prema odluci SCRUM mastera.

2.5.1. Slučaj korištenja 1: Pregled filmova	
Kada posjetitelj stranice pregledava pse koji se nalaze u web aplikaciji, odvijaju se sljedeći koraci:
1.	Posjetitelj dolazi na početnu stranicu web mjesta kao anonimni korisnik ili klikne na link Početna stranica u izborniku ako se nalazio na drugoj stranici na istom web mjestu.
2.	Početna stranica prikazuje osnovni opis web aplikacije i sadrži gumbe za prikaz, pretraživanje i dodavanje novih pasa. 
3.	Prikaz osnovnih informacija o razvojnom timu moguće je dobiti putem stranica O nama i Kontakt.
4.	Ako anonimni korisnik želi vidjeti sve pse u bazi, mora kliknuti na link Popis pasa u glavnom izborniku ili gumb prikaži na Početnoj stranici.
5.	Web aplikacija prikazuje popis pasa. Za svakog psa se prikazuje Ime psa, Datum rođenja psa, vrsta psa te Cijena.
6.	Ako anonimni korisnik želi pretraživati pse u bazi po Vrsti i Imenu, mora kliknuti na link Tražilica pasa u glavnom izborniku.
7.	 Ako anonimni korisnik želi vidjeti detalje Psa, mora kliknuti na link Detalji za odabranog psa.
8.	Web aplikacija prikazuje detalje odabranog psa –Ime psa, Datum rođenja psa, Vrstu psa te Cijenu.
2.5.2.	Slučaj korištenja 2: Dodavanje novog Psa
Svi korisnici trebaju moći dodati novog Psa. Kada korisnik dodaje novog Psa, sljedeći koraci se odvijaju:
1.	Korisnik klikne na gumb Unos na Početnoj stranici ili na link Novi pas na stranicama Popis pasa ili Tražilica pasa.
2.	Korisnik upisuje podatke o novom Psu.
3.	Korisnik klikne na gumb Spremi.
4.	Ako su upisani podaci ispravni, web aplikacija sprema Psa u bazu i vraća korisnika na stranicu Popis pasa.
2.5.3.	 Slučaj korištenja 3: Uređivanje psa

Kada korisnik uređuje Psa, sljedeći koraci se odvijaju:
1.	Korisnik klikne na link Uredi u popisu pasa na stranicama Popis pasa ili  Tražilica pasa.
2.	Korisnik mijenja postojeće podatke o psu.
3.	Korisnik klikne gumb Spremi promjene.
4.	Ako su upisani podaci točni, web aplikacija sprema promjene u bazi i prikazuje stranicu za Popis pasa.

2.5.4.	Slučaj korištenja 4: Brisanje Psa
Kad korisnik briše Pse iz baze podataka web aplikacije, sljedeći koraci se odvijaju:

1.	Korisnik klikne na link Obriši u popisu pasa na stranicama Popis pasa ili  Tražilica pasa.
2.	Web aplikacija zahtijeva potvrdu o brisanju psa.
3.	Ako korisnik potvrđuje brisanje, Pas je uklonjen iz baze.
4.	Web aplikacija prikazuje stranicu Popis pasa.



 
Slika 1: Dijagram slučajeva korištenja


2.6.	Dijagrami klasa 

Klasa Pas je potrebna kako bi se u aplikaciji evidentirali matični podaci za svakog psa. Svojstva koja opisuju nekog psa su: ID (identifikator psa), Name (ime psa, tekstualni podatak), Tipe (vrsta, tekstualni podatak), Price (cijena, decimalni broj), DateofBirth (datum rođenja, datumskog tipa). 
Kako bi se podaci o psima mogli spremiti u bazu podataka, potrebno je napraviti klasu DogsDBContext koja koristi klasu Pas kao model za izradu tablice u bazi pomoću Entity frameworka pa zbog toga i nasljeđuje klasu DbContext. Nakon toga treba pristupiti razvoju kontrolera PasController koji mora naslijediti baznu klasu Controller s pripadajućim metodama za manipulaciju nad bazom.  












 


 

Slika 2: Dijagram klasa


3.	Dizajn korisničkog sučelja
3.5.	Glavni principi dizajna korišteni u aplikaciji



















3.6.	Wireframe-ovi i Mockup-i































Slika 3. Mockup početne stranice

Slika 3 prikazuje elemente početne stranice, odnosno prve stranice koja se učitava u internet pregledniku kada korisnik upiše link web aplikacije. Početna stranica povezana je s prvim i drugim korakom prvog slučaja korištenja. Vidljivo je da ona sadrži na vrhu horizontalnu traku izbornika, zatim ispod toga sliku, a ispod slike u tri stupca glavne operacije koje se mogu izvršiti u aplikaciji, i to putem dugmadi koje vode na posebne poglede za svaku operaciju: Prikaži, Pretraživanje i Unos.








































Slika 4. Mockup stranice s popisom pasa


Slika 4 prikazuje elemente stranice “Popis pasa”. Stranica “Popis pasa povezana je s prvim slučajem korištenja I služi za prikaz svih pasa u bazi.
Popis pasa prikazivat će se u obliku jednostavne tablice sa svim poljima o svakom psu, s tim da se iza svakog retka nalaze linkovi na posebne stranice  za operacije “Uredi”, “Detalji” i “Obriši” koje se odnose na određenog psa u tom retku. 




















































Slika 5. Mockup stranice za pretraživanje psa


Slika 5 prikazuje elemente stranice “Tražilica pasa”. Stranica “Tražilica pasa” povezana je s prvim slučajem korištenja i služi za pretraživanje pasa po Vrsti i Imenu u bazi. Filter za pretraživanje po vrsti je napravljen kao combo box s ponuđenim vrstama pasa iz baze, a filter po nazivu psa je prikazan kao textbox u koji korisnik upisuje dio imena psa ili cijelo ime psa. Pretraživanje se aktivira nakon što korisnik klikne na dugme “Traži”, i tada se na istoj stranici ispod prikazuju samo oni psi koji udovoljavaju traženim kriterijima. Filtrirani psi se prikazuju u obliku iste tablice kao i kod popisa svih pasa.















































Slika 6. Mockup stranice “O nama”

Sliak 6 prikazuje elemente stranice koja sadrži informacije o razvojnom timu. Opis je pružen u prvom slučaju korištenja.
















































Slika 8. Mockup stranice za dodavanje novog psa


Slika 8 prikazuje elemente stranice koja se koristi za unos novog Psa u bazi. Sva polja, prikazana kroz elemente, je potrebno ispuniti kako bi Pas bio uspješno spremljen u bazu. Detaljan opis pružen je u drugom slučaju korištenja. Osim unosa i spremanja pasa korisnik ima prikazan i link na povratak na popis svih pasa.















































Slika 9. Mockup stranice za uredivanje psa


Slika 9 prikazuje elemente stranice koja se koristi za izmjene postojećeg psa u bazi. Detaljan opis pružen je u trećem slučaju korištenja. Obrazac ima isti oblik kao i za unos novog psa, kako bi korisniku omogućio lakše snalaženje u aplikaciji, kao i dugme za spremanje promjena i ispod toga link na povratak na popis svih pasa.
















































Slika 10. Mockup stranice za brisanje psa


Slika 10 prikazuje elemente stranice koja se koristi za korisnikovu potvrdu brisanja postojećeg psa u bazi. Detaljan opis pružen je u četvrtom slučaju korištenja. Korisnik ima mogućnost brisanja ili povratka na popis svih pasa.













































Slika 11. Mockup stranice za detalje psa


Slika 11 prikazuje elemente stranice koja se koristi za prikaz detalja pojedinačnog psa u bazi. Opis je pružen u zadnjem koraku prvog slučaja korištenja. Korisnik ima mogućnost klika na link za uređivanje psa ili povratka na popis pasa.






