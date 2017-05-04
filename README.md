# BlackJack
Game of blackjack

/*
*Jonathan Saldivar
*ITSE 1302-011
*Project
*Black Jack game in Java
*/
 
 
package blackjack; 
 import java.util.ArrayList;  
 
 public class BlackJack { 
 
 public static void main(String [] strArgs) { 
   BlackJack objGame = new BlackJack(); 
   objGame.playRound(); 
 } 
    System.out.println ("Welcome to BlackJack!");
    
    //Dealer stops at 16. 
    
     public Player dealerLogic(Player botDealer, Deck playingDeck) { 
         return dealerLogic(botDealer, playingDeck, 16); 
     } 

     // Simple dealer logic to hard stop at a certain point. 
      
     public Player dealerLogic(Player botDealer, Deck playingDeck, int intStop) { 
         while(botDealer.getTotalFaceValue() <= intStop && 
             botDealer.getNumberOfCards() < 4) { 
             botDealer.addCard(playingDeck.getCard());         
         } 
         return botDealer; 
     } 
 

     public void playRound() { 
         //TODO: Gut this logic and add your own function calls to play your own version of BlackJack. 
 
 
         Deck playingDeck = new Deck();
         playingDeck.createDeck();
         playingDeck.shuffle(); 
         
         
    
 
         ArrayList<Player> aryPlayers = new ArrayList<Player>(); 
         aryPlayers.add(new Player()); 
         aryPlayers.add(new Player()); 
         Player botDealer = new Player("Dealer"); 
         botDealer.setMoney(0); 
         aryPlayers.add(botDealer); 
 
 
         int intCurrentPlayer = 0; 
 
 
         int intCounter = 0; 
         while(intCounter < 2) { 
             intCurrentPlayer = 0; 
             while(intCurrentPlayer < aryPlayers.size()) { 
                 aryPlayers.get(intCurrentPlayer).addCard(playingDeck.getCard()); 
                 intCurrentPlayer++; 
             } 
             intCounter++; 
         } 
 
 
         intCurrentPlayer = 0; 
         while(intCurrentPlayer < aryPlayers.size()) { 
             if(aryPlayers.get(intCurrentPlayer).hasMoney()) { 
                 System.out.println(botDealer); 
                 aryPlayers.get(intCurrentPlayer).inputBet(); 
             } 
             intCurrentPlayer++; 
         } 
 
 
         this.dealerLogic(botDealer, playingDeck); 
 
 
         System.out.println(aryPlayers); 
 
 
         if(playingDeck.shouldShuffle()) { 
             playingDeck.shuffle(); 
         } 
 
 
         /* 
         objPlayer1.addCard(playingDeck.getCard()); 
         objPlayer1.addCard(playingDeck.getCard()); 
         objPlayer1.addCard(playingDeck.getCard()); 
         objPlayer1.addCard(playingDeck.getCard()); 
         objPlayer1.printHand(); 
         */ 
     } 
 } 
