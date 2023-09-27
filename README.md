# ES Bank

> A következő feladatban bankszámlákat kezelő objektumot kell előállítania. Az egyes műveletekhez készítsen függvényt, valamit oldja meg, hogy a minta alapján több objektum is előállítható legyen.

## Első feladatsor

1. A következő feladatban egy bankszámlát kell létrehoznia az ügyfél adataiból, melyet paraméterként kap.  A bankszámla számát önnek kell generálnia. A hazai számlaszámok háromszor 8 számjegyből állnak. Melyek kezül az első csoport első három jegye adott: `111` Példa számlaszám: `11126453-57832575-23468325` A következőképpen néz ki egy bankszámla:

    ```js
    {
        firstName: "",
        middleName: "", 
        lastName: "", 
        identity: "", 
        address: {zip:,city:}, 
        acc_id: , 
        transactions: []
    }
    ```

2. A számla `transactions` tömbjéhez adjuk hozzá a a betétet tanusító "bizonylatot" Egy bizonylat egy olyan objektun, amely tartalmazza a betett összeget, a dátumot, valamint, hogy a tranzakció `"deposit"` volt. példa tranzakció:

    ```js
    {
        type: "withdraw", 
        amount: 3200, 
        date: "2021-11-16T10:00:00"
    }
    ```

3. Az előző feladat mintájára pénzt kivenni szeretnénk. Figyeljen, hogy a kivétel tényét a `"withdraw"` típus jelzi és nem a negatív összeg!
4. Kérdezze le a bankszámla egyenlegét. Ezt a tranzakciók megfelelő előjeles összegzésével tudja megtenni.
5. Végezzen átutalást a két számla között. Figyeljen, hogy az egyik számlán ez pénz kivételt, a másikon pedig elhelyezést jelent.

## Második feladatsor

> Kiegészítő és segéd függvények külön és az adott objektumokhoz írhatóak.

1. Alakítsuk át a számla adatait, úgy hogy a tulajdonoshoz kapcsolódó adatokat ne tartalmazzák a továbbiakban, valamint bővítsük létrehozás dátumával `open_date` néven és a létrehozás pillanatának időpontját tárolja, valamint az `open_balance`-al, amely a kezdő egyenleget tárolja. Amennyiben a függvény nem kap kezdő egyenleget akkor ezt vegyük 0-nak. Továbbá legyen egy pénznemet jelölő mező és egy hitelkeretet jelző mezőnk, szintén megadás hiányában 0-nak veendő.
2. Amennyiben korábban különálló függvényként hoztad létre a tranzakciót, akkor oldd meg, hogy ez a függvény legyen a bankszámla része és bővítsd megjegyzés mezővel. A függvénynek egyen visszatérési értéke amely a sikerességet jelzi. Akkor sikeres egy tranzakció, ha két azonos pnznemű számla között történik az utálás, valamint a levonással még nem éri el a keretet az adott számla.
3. Legyen egy olyan zárt objektumunk `TRANSACTION_TYPE` néven, amely két értéket tárol: A `WITHDRAW` értéke legyen `withdraw`, valamint ezen minta alapján a deposit.
4. Hozz létre egy `NATIONALITY` nevű zárt objektumot, amely a következő mintában tárolja az adatokat: `HUN` kulcs értéke `magyar`. Tartalmazza az objektum, francia, német, olasz és spanyol állampolgárságot.
5. Hozz létre egy `CURRENCY` nevű zárt objektumot amely a következő mintában tárolja az adatokat: `HUF`: magyar forint, ez alapján legyenek felvéve a következő pénznemek: euró, amerikai és ausztrál dollár, valamint svájci frank.
6. Készítsünk egy függvényt, amely egy olyan objektumot hoz létre, amely egy nevet tud tárolni részletekben (`firstName`, `middleName` és `lastName`)
7. Készíts függvényt amely egy string paraméter alapján előállít egy olyan objektumot amely egy címet tárol.
    - A cím tartalmazza az irányítószámot, várost, utca nevét, jellegét, valamit egy házszámot.
    - Jelenleg nem foglalkozunk a több szóból álló utca névvel valamint az emelet/ajtó számokkal.
    - példa string: `"1144 Budapest, Kerepesi út 124."`
8. Készíts olyan factory-t amely előállítja azt az obejktumot, ami a lakcímet és a levelezési címet tartalmazza. Ezeket paraméterként kapja, amennyiben csak a lakcímhez tartozó paraméter van megadva gondoskodj róla, hogy a levelezési cím is ugyanazt kapja.
9. Hozz létre egy zárt objectumot `IDENTITY_TYPE` néven amely az idazolványok típusait tárolja.
    - `ID` értéke: Személyazonosító igazolvány
    - `DL` értéke: Vezetői engedély
    - `PP` értéke: Útlevél
10. Készíts függvényt amely létrehoz egy objektumot, amely tárolja egy igazolvány adatait: típusát, számát és lejárati dátumát.
11. Hozzunk létre egy függvényt amely egy személyt hoz létre a következő adatokkal, amelyek az előző feladatok függvényiből, objektumaiból állnak elő:
    - `name`
    - `addresses`
    - `identity`
    - `nationality`
    - `accounts`: Üres tömbként inicializáld
12. Készítsd el a következő függvényeket a személyt tartalmazó objektumhoz:
    - `findAccount()`, számlaszám alapján keresse meg a számlát és adja vissza. Ha nincs a feltételnek megfelelő számla akkor `null` értékkel térjen vissza.
    - `addAccount()`
    - `closeAccount()`, számlaszám alapján töröl egy számlát. Csak akkor törölhető, ha az egyenlege legalább 0.
    - `addIdentity()`, csak olyan igazolványt fogadj el ami még nem járt le.
    - `removeIdentity()`
13. Hozz létre egy bankot objektumot létrehozó függvényt, amely a követekző mezőkkel és tagfüggvényekkel:
    - `name`
    - `address`
    - `clients`, tömbként tartalmazza az összes ügyfelet
    - `nationality`
    - `findAccount()`
    - `addClient()`
    - `removeClient()`, csak olyan ügyfelet lehet eltávolítani akinek nincs tartozása.
    - `getAccounts()`, egy olyan függgvény amely lapozással adja vissza a bankban található összes számlát. Az első paraméter tartalmazza a lapon található elemek számát, második paraméter pedig az oldalszámot.
    - `numberOfClient()`
    - `numberOfAccounts()`
    - `totalOfTransactions()`
14. Hozd létre a következő két bankot:
    1. Kelekótyaföldi Kereskedelmi Bank (KKB)
        - 1111 Budapest, Bástya utca 9.
        - magyar nemzetiségű
    2. Nemzeti Beruházási és Hitel Bank (NBHB)
        - 2000 Szentendre, Tölgy utca 136.
        - magyar nemzetiségű
15. Mindkét bank rendelkezzen 4-4 ügyféllel, melyk közül legalább 1-1 magyar legyen. Valamint legalább 2 ügyfél aki legalább 2db számlával rendelkezik, amelyek különböző pénzneműek.
16. Végezzen átutalást a két bank ügyfele között. Legyen olyan utalás is amely sikertelen.
