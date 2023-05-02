Download Link: https://assignmentchef.com/product/solved-comp1210-activity8b-comparable-interface
<br>
By the end of this activity you should be able to do the following:

<ul>

 <li>Implement interfaces</li>

 <li>Overload methods</li>

</ul>

<strong>Directions: </strong>

Don’t forget to add your Javadoc comments for your classes, constructor, and methods in this activity.

<strong>Part 1: Customer.java </strong>

<ul>

 <li>Open a new Java file in jGRASP and create a class called Customer. Create three instance variables:</li>

</ul>

o String object for the customer’s name  o String object for the customer’s location (town) o double to store the customer’s balance

<ul>

 <li>Create a constructor for the Customer class that takes the Customer’s name as a parameter. <strong>Set the location variable to an empty string and the balance to zero</strong>. You do not have to include the comments.</li>

</ul>

public Customer(String nameIn) {

____________ = nameIn; // sets name to parameter input

____________ = “”; // sets location to empty string

____________ = 0; // sets balance to 0

}




<ul>

 <li>Create methods that set the customer’s location, change the customer balance by an amount specified by a double parameter, get the location, and get the balance. That is, provide <u>method bodies</u> for the <u>method headers</u>  Be sure to compile the completed methods before using them in interactions.</li>

</ul>

public void setLocation(String locationIn) // sets location variable public void changeBalance(double amount) // add amount to balance public String getLocation() // returns variable for location public double getBalance() // returns variable for balance




<ul>

 <li>Try the following example in the interactions pane (you can leave out the comments):</li>

</ul>

Ï¼ÏÏCustomer cstmr = <strong>new</strong> Customer(<strong>“Lane, Jane”</strong>);

Ï¼ÏÏcstmr.changeBalance(30); <em>// add $30 to balance </em>

Ï¼ÏÏcstmr.getBalance()

ÏÏÏÏ30.0

Ï¼ÏÏcstmr.changeBalance(-5); <em>// take $5 off balance </em>

Ï¼ÏÏcstmr.getBalance()

ÏÏÏÏ25.0

Ï¼ÏÏcstmr.setLocation(<strong>“Boston, MA”</strong>);

Ï¼ÏÏcstmr.getLocation()

ÏÏÏÏBoston, MA




Suppose you want to be able to set the customer location with city and state in a single String or by entering city and state in two separate String parameters.  <strong><u>Overload</u></strong> the setLocation method so that it takes two String parameters (<u>do not delete the original setLocation method;</u> <u>rather create a second method</u>).







<ul>

 <li>Now when the setLocation method is included in your code, the compiler will check to see whether you have one String parameter or two String parameters. It will then <strong><u>bind the</u> <u>method call</u></strong> with the appropriate <u>d<strong>eclaration</strong></u> of the setLocation method. Try entering the following code into the interactions pane (recompile your program first):</li>

</ul>




Ï¼ÏÏCustomer cstmr = <strong>new</strong> Customer(<strong>“Lane, Jane”</strong>);

Ï¼ÏÏcstmr.setLocation(<strong>“Boston, MA”</strong>)

Ï¼ÏÏcstmr.getLocation()

ÏÏÏÏBoston, MA

Ï¼ÏÏcstmr.setLocation(<strong>“Omaha”</strong>, <strong>“NE”</strong>)

Ï¼ÏÏcstmr.getLocation()

ÏÏÏÏOmaha, NEÏÏÏ




<ul>

 <li>Create a toString method that shows the customer’s name, their location, and their balance (you do not have to format balance, but do include the dollar sign).</li>

</ul>




Ï¼ÏÏCustomer cstmr = <strong>new</strong> Customer(<strong>“Lane, Jane”</strong>);

Ï¼ÏÏcstmr.setLocation(<strong>“Boston, MA”</strong>)

Ï¼ÏÏcstmr.changeBalance(5)

Ï¼ÏÏcstmr

ÏÏÏÏLane, Jane

ÏÏÏÏBoston, MA

<h1>ÏÏÏÏ$5.0ÏÏÏÏÏÏ</h1>




<ul>

 <li>Suppose that you wanted to be able to compare Customer objects based on some attribute. You can <strong><u>implement</u></strong> the Comparable <strong><u>interface</u></strong> in your customer class by indicating this in the class header as shown below.</li>

</ul>

public class Customer implements Comparable&lt;Customer&gt;

By adding this to the Customer header as shown above, your Customer class will now need to implement a compareTo mehod as described below.

The Comparable interface has a method called compareTo which compares an object of this class to another object to another compatible object indicated by the generic parameter based on some value. Suppose you want to sort Customer objects based on their balance, which is a double, then the compareTo method can be defined as follows:

<strong>Part 2: CustomerTest.java – Testing with JUnit the Comparable Interface </strong>

<ul>

 <li>Create a jGRASP project and add the Customer.java file. Now create the test file for the Customer by clicking on the Create/Edit test file button  .  Be sure to comment out the following statement:  import static org.junit.Assert.*;</li>

 <li>Now begin adding test methods for to test each of the Customer methods created in Part 1. After each test method is added to CustomerTest.java, be sure to run the test file.</li>

</ul>

Now add the following test method to test the compareTo method.  Note that three test methods are needed to ensure that the conditions in the compareTo method are covered.