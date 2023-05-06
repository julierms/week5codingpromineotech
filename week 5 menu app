//MENU APP
class Drink {
    constructor(name, flavor) {
        this.name = name;
        this.style = flavor;
    }

    describe() {
        return `This drink is a ${this.name} ${this.flavor}.`;
    }
}

class Type {
    constructor(name) {
        this.name = name;
        this.drinks = [];
    }

    addDrink(drink) {
        if (drink instanceof Drink) {
            this.drinks.push(drinks);
        } else {
            throw new Error(`You can only add an instance of Drink. Argument is not a drink: ${drink}}`);
        }
    }

    describe() {
        return `The ${this.name} type has ${this.guitars.length} guitars.`;
    }
}

class Menu {
    constructor() {
        this.types = [];
        this.selectedType = null;
    }

    start() {
        let selection = this.showMainMenuOptions();
        
        while (selection != 0) {
            switch (selection) {
                case '1':
                    this.createType();
                    break;
                case '2':
                    this.viewType();
                    break;
                case '3':
                    this.deleteType();
                    break;
                case '4':
                    this.displayTypes();
                    break;
                default:
                    selection = 0;
            }
            selection = this.showMainMenuOptions();
        }

        alert('Bye Bye!');
    }

    showMainMenuOptions() {
        return prompt(`
        0) exit
        1) enter new drink type
        2) view drink types
        3) remove drink types
        4) display all drink types
        `);
    }

    showTypeMenuOptions(typeInfo) {
        return prompt(`
        0) back
        1) enter drink
        2) remove drink
        ----------------------
        ${typeInfo}
        `);
    }

    displayTypes() {
        let typeString = '';
        for (let i = 0; i < this.types.length; i++) {
            typeString += i + ') ' + this.types[i].name + '\n';
        }
        alert(typeString);
    }

    createType() {
        let name = prompt('Enter type of drink');
        this.types.push(new Type(name));
    }

    viewType() {
        let index = prompt('Enter the index of the type of drink you wish to view:');
        if (index > -1 && index < this.types.length) {
            this.selectedType = this.types[index];
            let description = 'Type of drink: ' + this.selectedType.name + '\n';
            
            for (let i = 0; i < this.selectedType.drinks.length; i++) {
                description += i + ') ' + this.selectedType.drinks[i].name
                 + ' - ' + this.selectedType.drinks[i].style + '\n';
            }

            let selection = this.showTypeMenuOptions(description);
            switch (selection) {
                case '1':
                    this.createDrink();
                    break;
                case'2':
                    this.deleteDrink();
            }
        }
    }

    deleteType() {
        let index = prompt('Enter the index of the type of drink you wish to remove:');
        if (index > -1 && index < this.types.length) {
            this.types.splice(index, 1);
        }
    }
    

    createDrink() {
        let name = prompt('Enter name of new drink:');
        let flavor = prompt('Enter the flavor of the new drink:');
        this.selectedType.drinks.push(new Drink(name, flavor));
    }

    deleteDrink() {
        let index = prompt('Enter the index of the drink you wish to remove:');
        if (index > -1 && index < this.selectedType.drinks.length) {
            this.selectedType.drinks.splice(index, 1);
        }
    }
}

let menu = new Menu();
menu.start();