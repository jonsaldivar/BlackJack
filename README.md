# BlackJack
Game of blackjack

/*
*Jonathan Saldivar
*ITSE 1302-011
*Black Jack
*Player logic in java for Black Jack
*/

 
import java.util.ArrayList; 
import java.util.Scanner; 
 
public class Player { 
 
   static int intTotalNumberOfPlayers = 0; 
   private ArrayList<Card> aryHand = new ArrayList<Card>(); 
   int intCurrentBet = 0; 
   int intMoney = 3000; 
   String strName = "no one"; 
 
 
     public Player() { 
         name(++intTotalNumberOfPlayers); 
     } 
     
     public Player(String pstrName) { 
         name(pstrName); 
     } 
 
     public void name(int intPlayerNumber) { 
         name("Player " + intPlayerNumber); 
     } 
 
     public void name(String pstrName) { 
         strName = pstrName; 
     } 
 
     public String name() { 
         return strName; 
     } 
 
 
     //Sets the value for the player. 
  
     public void setMoney(int pintMoney) { 
         intMoney = pintMoney; 
     } 

     
     // Get the current money the player has.
     
     public int getMoney() { 
         return intMoney; 
     } 
 

     public void setBet(int intBet) { 
         intCurrentBet = intBet;  
     } 
 
 
     public boolean hasMoney() { 
         return (getMoney() > 0); 
     } 
 
     public void inputBet() { 
         int intBet = 0; 
         setBet(0); 
         Scanner objScanner = new Scanner(System.in); 
         do { 
             System.out.println(toString()); 
             System.out.print("Enter your bet: "); 
             intBet = objScanner.nextInt(); 
         } while(intBet > getMoney() || intBet < 1); 
         setBet(intBet); 
     } 
 

     public int getBet() { 
         return intCurrentBet; 
     } 
 
     public int getTotalFaceValue() { 
         int intFaceValueTotal = 0; 
         int intCurrentCard = 0; 
         Card objCard = null; 
         boolean hasAce = false; 
         while(intCurrentCard < aryHand.size()){ 
             objCard = aryHand.get(intCurrentCard); 
             intFaceValueTotal += objCard.getFaceValue(); 
             if(objCard.getFace() == 1) { 
                 hasAce = true; 
             } 
             intCurrentCard++; 
         } 
 
 
         if(hasAce && intFaceValueTotal <= 11) { 
             intFaceValueTotal += 10; 
         } 
 
 
         return intFaceValueTotal; 
     } 
 

     public void addCard(Card objCard) { 
         aryHand.add(objCard); 
     } 
 
     public void clearHand() { 
         aryHand.clear(); 
     } 
  
     public void printHand() { 
         System.out.println(aryHand + " Total: " + getTotalFaceValue()); 
     } 
  
     public void printMoney() { 
         System.out.println("Total: $" + getMoney() + "\tBet: $" + getBet()); 
     } 
 
     public int getNumberOfCards() { 
         return aryHand.size(); 
     } 
 
     public String toString() { 
         return "\n" + name() + ": " + aryHand + " Total: " + getTotalFaceValue() + "\n" + 
             "Total: $" + getMoney() + "\tBet: $" + getBet();  
     } 
 } 
