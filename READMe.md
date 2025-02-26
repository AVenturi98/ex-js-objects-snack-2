🏆 Code Question 1
    const hamburger = { name: "Cheese Burger", weight: 250 };
    const secondBurger = hamburger;
    secondBurger.name = 'Double Cheese Burger';
    secondBurger.weight = 500;
    ​
    console.log(hamburger.name); // ?
    console.log(secondBurger.name ); // ?

Senza lanciare il codice, riesci a prevedere cosa viene stampato in console?
Quanti oggetti sono stati creati in memoria durante l'esecuzione di questo codice?

# Il valore di hamburger e secondHambuger avranno lo stesso valore "Double Cheese Burger" dato dalla modifica di secondHambuger, in quanto essendo un <reference>, la copia farà solo riferimento al valore della chiave hamburger. Perciò modificando il valore di secondHambuger modificheremo il valore di hambuger.