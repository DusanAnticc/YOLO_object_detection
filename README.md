# Probrojavanje objekata na pokretnoj traci

#### Tim
- Loreana Oluić SW-60/2018
- Nemanja Milutinović SW-64/2018
- Dušan Antić SW-81/2019

#### Asistent
- Vidaković Dragan

# O projektu

### Definicija problema:
Detekcija, prebrojavanje i klasifikacija artikala na pokretnoj traci kase u marketu ("Banana","Apple","Sandwich","Carrot","Bottle") na slici i videu.

### YOLO (You only look once)
Yolo je savremeni sistem za detekciju objekata u realnom vremenu na videu ili slici. Za razliku od prethodnih sistema koji su koristili klasifikatore tako što su primenjivali model na delove slike i vršili ocenjivanje a najviše ocenjene regije posmatrali kao detekcije, yolo primenjuje neuronsku mrezu na citavu sliku koja deli sliku u regije i predviđa granične okvire i verovatnosti za svaku regiju. 
U poređenju sa modelima kao sto su R-CNN i Fast R-CNN radi 1000 i 100 puta brže, respektivno.

Algoritam radi prateći tri tehnike:
- Rezidualni blokovi - Slika je podeljena u mrežu gdje je svaka ćelija iste dimenzije. Svaka ćelija će detektovati objekat koji se pojavljuje u njoj.
- Bounding box regresija - Bounding box je kontura koja ograničava objekat na slici. Sadrži širinu, visinu, klasu i centar konture.
- Intersection over union - YOLO koristi IOU da bi napravio okvir oko objekta na slici. Svaka ćelija predviđa okvir I postotak sigurnosti u predviđanje, YOLO se trudi da predvidjeni okvir I stvarni okvir budu jednaki.

### Darknet
[Darknet](https://github.com/pjreddie/darknet "Darknet") je neuronska mreža otvorenog koda napisana u programskom jeziku C i CUDA što je čini izuzetno brzom. Podržava rad i na CPU i na GPU .

# Instalacija i zahtevi
U osnovi ovog projekta nalazi se darknet projekat dostupan na linku : [https://github.com/AlexeyAB/darknet](https://github.com/AlexeyAB/darknet)
Zahtevi neophodni za pokretanje ovog projekta opisani su na linku : [https://github.com/AlexeyAB/darknet#requirements-for-windows-linux-and-macos](https://github.com/AlexeyAB/darknet#requirements-for-windows-linux-and-macos)

Instalacija projekta opisana je na sledećim linkovima: 
- Windows - [https://github.com/AlexeyAB/darknet#how-to-compile-on-windows-using-vcpkg](https://github.com/AlexeyAB/darknet#how-to-compile-on-windows-using-vcpkg)
- Linux/macOS - [https://github.com/AlexeyAB/darknet#how-to-compile-on-linux-using-make](https://github.com/AlexeyAB/darknet#how-to-compile-on-linux-using-make)

# Podaci
Za potrebe treniranja neuronske mreže koristili smo slike namirnica (banana, jabuka, sendviča, šargarepe I flaše) koje smo pronašli na internetu I ručno labelirali. Za našu mrežu koristili smo ukupno 177 slika koje smo podelili u trening I testni skup.

# Trening
Podatke za treniranje smo prikupili sami i uz pomoc alata za labeliranje označili svaku sliku, nad tim podacima smo trenirali našu neuronsku mrezu i kao rezultat dobili mrežu koja prepoznaje testne slike

# Korisni linkovi
- [https://github.com/AlexeyAB/darknet](https://github.com/AlexeyAB/darknet)
- [https://github.com/pjreddie/darknet](https://github.com/pjreddie/darknet)
- https://www.youtube.com/watch?v=hTCmL3S4Obw
- [https://github.com/tzutalin/labelImg](https://github.com/tzutalin/labelImg)
