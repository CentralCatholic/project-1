# CS 0401 Intermediate Programming
## Assignment 1
## Topics: Review of expressions, conditions, loops and I/O

---------------------------

After passing your OWLs and NEWTs (with a grade of "Outstanding" in "Defence Against the Dark Arts") but discovering that there are currently no openings for Aurors, you decide to bide your time by running a small food cart in Hogsmeade, called "Dumbledore's Delicious Delicacies" (or DDD for short, named in honor of your great cousin [twice removed] Albus).  Since your cart is small you have a very limited menu, consisting only of Cauldron Cakes, Chocolate Frogs and Butterbeer.  However, since these are all popular items you hope to earn enough Galleons to get by while you wait for an Auror position to become available.

Your prices are as follows:

| Item                     | Price    |
| ------------------------ | -------- |
| Cauldron Cakes (1 cake)  | 10 Knuts |
| Cauldron Cakes (6 cakes) | 55 Knuts |
| Chocolate Frog           | 20 Knuts |
| Butterbeer (Small)       | 50 Knuts |
| Butterbeer (Large)       | 75 Knuts |

For your best customers, you have a secret password that enables them to get discounts on your products.   In another homage to your cousin, you nickname this group "Dumbledore's Army".  Customers who know the password (they get two tries to guess it) gets the following discounted prices: 

| Item                     | Discount                                 |
| ------------------------ | ---------------------------------------- |
| Cauldron Cakes (1 cake)  | No discount                              |
| Cauldron Cakes (6 cakes) | 50 Knuts (5 knut discount)               |
| Chocolate Frog           | 15 Knuts (5 knut discount)               |
| Butterbeer (either size) | 50 Knuts (upgrade to large is free)      |
| Overall                  | 10% off over and above any other discount if the overall order (after existing discounts) is 10 sickles or more, rounded to the nearest knut |

To accommodate the occasional muggle who may drop by, or to remind the absent-minded 3rd years of the currency, you also post the following sign on your cart:

> **Note 1:** We appreciate exact change!

> **Note 2:** The operator does not have more than 20 galleons in the cart at a time!

> **Note 3:** Recall our currency options:
>
> ​	29 Knuts == 1 Sickle
>
> ​	17 Sickles == 1 Galleon == 493 Knuts

# Assignment

Your assignment is to write a Java program that will simulate transactions between you and some of your customers.  The program should:

1. Ask if there is another customer to be waited on.  If so, continue; if not, quit the program.

2. Ask the customer for the secret password (pick any password that you would like – don't worry about encryption).  If the customer knows the password, show him/her the discounted prices; otherwise show the customer the regular price list.  Allow only two attempts for the password.

3. Allow the customer to order items from the menu.  This process must be iterative, with the customer possibly changing his / her order until finalizing it prior to checking out.  For simplicity (to allow the line to move more quickly), purchases will be restricted in the following ways:

   1. Purchase of Cauldron Cakes will always be made by number of cakes.  If a customer wishes to buy a bag, he / she should specify 6 cakes and your program should automatically detect that as a bag of 6.  Furthermore, for any number of cakes, K, you should automatically count as many whole bags as you can before charging by the cake.  For example, if a customer asks for 19 Cauldron Cakes, this should be 3 bags plus 1 single cake.
   2. Discount passwords will be sent to customers either via owl or perhaps floo powder transmissions.  In any case, customers will not be given the password during store transactions – they must already know the password when they are waited on.

   For an idea of how a customer transaction might proceed, see my sample output in `a1out.txt`. 

4. Tabulate the total (don't forget the 10% overall discount if it applies) and show the itemized bill (with unit and subtotal prices for each item) on the display. See the example output in `a1out.txt`.

5. Ask the customer for some money, input the amount, and give the customer his/her change (by showing it on the display).  Note that the customer could pay in Knuts, Sickles or Galleons, but to keep things simple you will accept only one type of currency per transaction (so a customer could NOT give you 5 Sickles and 10 Knuts, for example).  For change, you will always give the minimum number of coins back (so you give larger currency before smaller currency).  For example, if a customer's total bill is 300 Knuts and he/she pays with 1 Galleon, then the change would be 193 Knuts.  However, your program must return this change as 6 Sickles and 19 Knuts.

6. Do not allow the customer to underpay (i.e. do not accept an amount less than the total).  See the example output in a1out.txt.

7. Go back to (1) and do it all again

For some example runs, see file `a1out.txt`

# Important Notes:

* Clearly there are a few places in your program where loops are required.  We discussed (or will discuss) several different looping constructs in lecture – choose one that is appropriate for the task at hand (more than one correct answer is possible).
* You will also need to do some math to calculate totals and discounts and to convert currency.  Think carefully about how you can do these things in relatively simple ways.
* Be careful about handling special cases with regard to input.  If the value the user enters is invalid (ex: negative number of items) your program should handle it in some reasonable way.  However, you can assume that the type of the data the user enters will be valid (i.e. if you are expecting a number the user will not enter a non-numeric string).  Some special cases are demonstrated in the example run that will be put online.
* Use the Scanner class for your input.  We will see later how we can get input into our programs in other ways as well.
* Format your code nicely (indenting, etc) and be sure to use comments to explain your code where appropriate.  Minimally you should have your name, course, section and a brief explanation at the beginning of your program. You should also have brief comments wherever the meaning of the code is not obvious.
* Your output should also be nicely formatted (make the user wants to run your program).  In particular, your itemized bill must be presented in a nice, readable way.  For some help with formatted output see `ex6.java`, `ex6b.java` and Section 3.10 of your Gaddis text.  See file a1out.txt for some example output.
* If you are interested in doing some extra credit, you can enhance your program in many ways.  Here are some examples:
  * If adding an extra Cauldron Cake would either be the same or a lower price for the customer, recommend that he or she add another cake.  Think about when / if this could occur.
  * Show after the total the user's overall savings for being in Dumbledore's Army (i.e. for knowing the password).  In other words, for a customer who knows the password you should calculate the bill both with and without the discounts, and the difference is the amount the Dumbledore's Army member saved.
  * Add some graphical output to your program using JOptionPane.  You should NOT use this for input, however, since a Scanner class is required.

Be sure to look at the `a1out.txt` file for ideas about the look and feel of your program.  Your program DOES NOT have to look exactly like the sample run, but it should have the same functionality and should be well-formatted.
