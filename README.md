# ES Bank

> A következő feladatban bankszámlákat kezelő objektumot kell előállítania. Az egyes műveletekhez készítsen függvényt, valamit oldja meg, hogy a minta alapján több objektum is előállítható legyen.

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
