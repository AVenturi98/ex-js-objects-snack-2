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

🏆 Code Question 2
    const hamburger = { 
        name: "Cheese Burger", 
        weight: 250,
        ingredients: ["Cheese", "Meat", "Bread", "Tomato"]
    };
    ​
    const secondBurger = {...hamburger};
    secondBurger.ingredients[0] = "Salad";
    ​
    console.log(hamburger.ingredients[0]); // ?
    console.log(secondBurger.ingredients[0]); // ?

P.S.: Ricordati che gli Array, come gli oggetti, sono dei Reference Type (Tipi di Riferimento)!
Senza lanciare il codice, riesci a prevedere cosa viene stampato in console?
Quanti oggetti sono stati creati in memoria durante l'esecuzione di questo codice?

# Stessa questione. Il valore di hambuger verrà modificato in insieme a secondHambuger in quanto questo metodo di copia degli oggetti sia un <Reference Type>. Perciò farà solo riferimento al valore di hambuger e non creerà una vera e propria copia indipendente.

🏆 Code Question 3
    const hamburger = { 
    	name: "Cheese Burger", 
    	weight: 250,
    	maker: {
    		name: "Anonymous Chef",
    		restaurant: {
    			name: "Hyur's Burgers",
    			address: "Main Street, 123",
    			isOpen: true,
    		},
    		age: 29
    	}
    };

    const secondBurger = structuredClone(hamburger);
    const thirdBurger = structuredClone(hamburger);
    const hamburger = { 
        name: "Cheese Burger", 
        weight: 250,
        maker: {
            name: "Anonymous Chef",
            restaurant: {
                name: "Hyur's Burgers",
                address: "Main Street, 123",
                isOpen: true,
            },
            age: 29
        }
    };
​
const secondBurger = structuredClone(hamburger);
const thirdBurger = structuredClone(hamburger);
Quanti oggetti sono stati creati in memoria durante l'esecuzione di questo codice?

# Gli oggetti creati in questione saranno 3, uno per ogni variabile dichiarata. Con il metodo structuredClone() si potrà ottenere una <Deep Copy> del valore hambuger, dando la possibilità di ottenere anche oggetti complessi ma senza poter copiare delle funzioni.

🏆 Code Question 4
    const chef = {
        name: "Chef Hyur",
        age: 29,
        makeBurger: (num = 1) => {
            console.log(`Ecco ${num} hamburger per te!`);
        },
    }
    ​
    const restaurant = {
        name: "Hyur's Burgers",
        address: {
            street: 'Main Street',
            number: 123,
        },
        openingDate: new Date(2025, 3, 11),
        isOpen: false,
    };
Qual è il metodo migliore per clonare l’oggetto chef, e perché?
Qual è il metodo migliore per clonare l’oggetto restaurant, e perché?

# L'oggetto "chef" al suo interno contiene una funzione, perciò l'unica maniera per riottenere una funzione è con il metodo <Spread>, anche se faremo una copia 'superficiale' all'oggetto stesso.
# L'oggetto "restaurant" avendo al suo interno dei valori più complessi come il metodo Date(), converrà usare una <Shallow Copy> in questa maniera:
# (const restaurant2 = JSON.parse(JSON.stringify(restaurant)));