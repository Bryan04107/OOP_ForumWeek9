# OOP-Week-9
Q1a. Distinguish between a class and an instantiation of a class. <br />
A1a. A class is a template/blueprint for an object whereas the instance is the object created with it.

Q1b. By giving two examples, explain how the principles of inheritance can be incorporated into the design of this administration program. <br />
A1b. There could be a product class in which it will contain the different information’s for each product and a worker class where data of the personnel can be kept.

Q1c. Describe how the use of libraries can facilitate the development of programs like this company’s administration program. <br />
A1c. The use of libraries allows the use of prewritten codes which could greatly reduce workload as there is no need to create everything from scratch.

Q2c. Complete the constructor public SalesPerson(String id), from the SalesPerson class. <br />
A2c.
```
public SalesPerson(String id){
    this.id = id;
    this.salesHistory = new Sales[100];
}
```

Q2b. Explain why accessor methods are necessary for the SalesPerson class. <br />
A2b. Because the variable in SalesPerson is private which could be accessed from other class via the use of accessor methods.

Q2ci. Construct unified modelling language (UML) diagrams to clearly show the relationship between the SalesPerson and Sales classes.
Note: There is no need to include mutator or accessor methods or a constructor. <br />
A2ci. <br />
![1ca625de-c5ff-4366-82c1-d51217d38701](https://github.com/Bryan04107/OOP_ForumWeek9/assets/106388697/61a5ac51-b8f3-4dc2-9def-4be6b649b89a)


Q2cii. Outline a negative effect that a future change in the design of the Sales object might have on this suite of programs. <br />
A2cii. There are no mutator methods which may cause problems in the future if something needs to be changed.

Q2d. State the output after running this code. <br />
A2d. The code wouldn’t run as the method getSalesHistory(int) doesn’t exist. If fixed on Q2e the output should be.
102
2
2550.4
5000.0

Q2e. Construct the method calcTotalSales(), in the SalesPerson class that calculates the total value of the sales for a specific SalesPerson object. <br />
A2e.
```
public double calcTotalSales(){
    double total = 0.0;
    for(int i = 0; i < count; i++)
    {
        total += salesHistory[i].getValue() * salesHistory[i].getQuantity();
    }
    return total;
}
```

Q2f. By making use of any previously written methods, construct the method highest(), that returns the ID of the salesperson whose sales have the largest total value <br />
A2f.    
```
SalesPerson[] salesPeople;
public Driver()
{
    salesPeople = new SalesPerson[100];
}
public String highest() {
    double HighestSales = 0;
    String ID = "";
    for (int i = 0; i < salesPeople.length; i++) {
        double TempSales = salesPeople[i].calcTotalSales();
        if (TempSales > HighestSales) {
            HighestSales = TempSales;
            ID = salesPeople[i].getId();
        }
    }
    return ID;
}
```

Q2g. Construct the method addSales(Sales s, String id), in the Driver class, that will add a new Sales object s, to the salesperson with a specified ID.
Note: You can assume that the ID is a valid one. <br />
A2g.
```
public void addSales(Sales s, String id) {
    for (int i = 0; i < salesPeople.length; i++) {
        if (salesPeople[i].getId().equals(id)) {
            salesPeople[i].setSalesHistory(s);
            break;
        }
    }
}
```

Q2h. A further class in this suite of programs is the Payroll class. This class is run at the end of each month to calculate each salesperson’s salary, which is based on the sales that have been made during that month. Suggest changes that must be made to the SalesPerson class and/or the Sales class to allow these calculations to be made. <br />
A2h. The addition of a date variable to keep track of when a month has passed, which would then allow calculation of the monthly salesperson’s salary using another new method.

Q2i. Discuss the use of polymorphism that occurs in this suite of programs. <br />
A2i. The example of polymorphism is in the SalesPerson class as there are 2 different constructors with different parameters.

