# BlackJack
Game of blackjack

import java.util.ArrayList;

public class Deck{

  private ArraList<Card> cards;

  public Deck(){
  this.cards = new Arraylist<Card>();
  }
  
  public void creatDeck(){
 
   for(PrSuit cardSuit : PrSuit.values()){
     for(PrValue cardvalue : PrValue.values()){
 
        this.cards.add(new Card(cardSuit,cardValue));
        }
     }
 }
 
   public String toString(){
   String cardList = "";
   int i = 0;
   for(Card aCard : this.cards){
    cardLst += "/n" + i + "-" + aCard.toString();
    i ++;
    }
    return cardList

}
