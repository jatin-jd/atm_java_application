import java.util.*;
class ATMachine {
    public int anothertransaction;
    private int p=1234;
    private float cash=12000;
    int ch;
    int newp,newc,n,pass,nnewp;
    float newu,nnewu,amount,total;
    Scanner i= new Scanner(System.in);
    public void atm()
    {
    System.out.println("Please select an option ");
    System.out.println("1. Deposite");
    System.out.println("2. WIDRAWL ");
    System.out.println("3. Change PASSWORD");
    System.out.println("press 4 for EXIT ...");
  
    System.out.println("CHOICE is =  ");
      n=i.nextInt();
    switch(n)
    {
        case 1:
            deposite();
            break;
        case 2:
            widrawl();
            break;
        case 3:
            password();
            break;
        case 4:
            exit();
            break;
        default:
        {
            System.out.println("enter correct option please ...");
            System.out.println("thank you ");
        }
    }
}

    private void password()
    {
        
        Scanner i=new Scanner(System.in);
        System.out.println("enter your password ");
        pass=i.nextInt();
        if(pass==this.p)
        {
            System.out.println("enter NEW  PASSWORD");
            newp=i.nextInt();
            System.out.println("re enter your password :");
            nnewp=i.nextInt();
            if(nnewp==newp)
            {
            System.out.println("your password is successfully changed .");
            System.out.println("do you want to continue ??");
            anothertransaction();
        }
            else
            {
            System.out.println("both password is not matched");
            System.out.println("Retry Later ...");
            }
        }
        else 
        {
            System.out.println("password is wrong");
        }
    }
    private void deposite()
{
    Scanner i=new Scanner(System.in);
    System.out.println("enter the password ");
    pass=i.nextInt();
    if(pass==this.p)
    {
    System.out.println("Please enter amount you would wish to deposit: ");
    newu=i.nextFloat();
    cash=newu+cash;
    System.out.println("You have deposited " + newu + " new balance is " + cash + "\n");
      System.out.println("thanks for using atm service....");
        System.out.println("have a nice day.....");
         anothertransaction();
}
    else {
        System.out.println("password is wrong .....");
        anothertransaction();
    }
}
    private void widrawl()
    {
      Scanner i = new Scanner(System.in);
      System.out.println("enter the password ");
     pass=i.nextInt();
     if(pass==this.p)
     {
         System.out.println("enter the amount");
         amount=i.nextInt();
         if (amount > cash || amount == 0) {
                    System.out.println("You have insufficient funds\n\n");
                    System.out.println("your current balance is "+cash);
                    anothertransaction();
         }
         else
         {
         cash=cash-amount;
         System.out.println("take your cash please");
          System.out.println("You have withdrawn " + amount + " and your new balance is " + cash + "\n");
         System.out.println("thanks for using atm service ");
         System .out.println("enjoy your life");
          anothertransaction();
     }
     }
    else
     {
         System.out.println("your password is wrong ....");
     }}
    private void exit()
    {
      Scanner i = new Scanner(System.in);
      System.out.println("exit...");
      System.out.println("thank you for using atm ......");
      System.out.println("Have a nice day .........");
    }
    public void anothertransaction() {
        System.out.println("Do you want another transaction?\n\nPress 1 for another transaction\n2 To exit");
        anothertransaction=i.nextInt();
        switch(anothertransaction) {
            case 1:
                atm(); // call transaction method
                break;
            case 2:
                exit();
                break;
            default:
                System.out.println("Invalid choice\n\n");
                anothertransaction();
                break;
        }   
    }
    
    public static void main(String [] args)
{
    ATMachine a = new ATMachine();
    a.atm();
}
}
