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
   ArrayList<Card> tmpDeck = new ArrayList<Card>();
   Random random = new Random();
   intrandomCardIndex = 0;
   int originalSize = this.cards.size();
   
   String cardList = "";
   for(int i = 0; i originalsize;i++){
   randomCardIndex = random.next((this.cards.size()-1 - 0) + 1) + 0;
   tmpDeck.addThis.cards.get(randomCardIndex));
   this.cards.remove(randomCardIndex);
}
this.cards = tmpDeck;


public void removeCard(int i){
        this.cardsremove(i);
}

public Card getCard(int i){
return this.cards.get(i);
}

public void addCard(Card addCard){
this.cards.add(addCard);
}
public void drae(Deck comingFrom){
this.cards.add(comingFrom.getCard(0));
comingFrom.removeCard(0);
}

public String toString(){
String cardListOutput += "\n" + aCard.toString();
i++;
}
return cardListOutput;
}

public void moveAll(Deck move){
int this DeckSize = this.cards.size();
for(int i = 0; i < thisDeckSize; i++){
  this.removeCard(0);
  }
  }
  public int decksize
  return this.cards.size();
  }
  
  public int cardsValue(){
  int totalValue = 0;
  int aces = 0;
  for(Card aCard : this.cards){
  switch(aCard.getValue()){
  case TWO: totalValue += 2; break;
  case THREE: totalValue +=3; break;
  case FOUR: totalValue +=4; break;
  case FIVE: totalValue +=5; break;
  case SIX: totalValue +=6; break;
  case SEVEN: totalValue +=7; break;
  case EIGHT: totalValue +=8; break;
  case NINE: totalValue +=9; break;
  case TEN: totalValue +=10; break;
  case JOKER: totalValue +=10; break;
  case QUEEN: totalValue +=10; break;
  case KING: totalValue +=10; break;
  case ACE: totalValue +=1; break;

}
}
for(int i = 0; i < aces; i++){
totalValue+= 1;
}
else{
totalValue += 11;
}
}
return totalValue;
}
}
