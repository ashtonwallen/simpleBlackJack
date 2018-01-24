import random

def update_game_info():
    print("player score is %d:" % (count_cards(player_cards)))
    print("Player Hand: %s" % player_cards)
    print("dealer score is %d:" % (count_cards(dealer_cards)))
    print("Dealer Hand: %s\n" % dealer_cards)


def first_deal():

    print("Dealer draws first card")
    dealer_cards.append(game_deck.pop(0))
    print("Player is dealt two cards\n")
    player_cards.append(game_deck.pop(0))
    player_cards.append(game_deck.pop(0))
    update_game_info()





def player_move():
    move = ''

    while ((move != ('s' or 'S')) and (count_cards(player_cards) <= 20)):
        move = input("'H'it or 'S'tay \n")

        if move not in ('H', 'h', 's', 'S'):
            print("Invalid Input")
        elif move in ('H', 'h'):
            player_cards.append(game_deck.pop(0))
            update_game_info()

    if (count_cards(player_cards) > 21):
        return True
    else:
        return False

def dealer_move():
    print("Dealer is taking his turn...\n")
    while(count_cards(dealer_cards) < 17):
        dealer_cards.append(game_deck.pop(0))

    update_game_info()

def get_winner():
    if count_cards(player_cards) > 21:
        print("Bust! You lose!")
    elif (count_cards(dealer_cards) > 21):
        print("Dealer bust, you win!\n")
    elif (count_cards(dealer_cards) > count_cards(player_cards)):
        print("Dealer wins!\n")
    elif (count_cards(dealer_cards) < count_cards(player_cards)):
        print("You Win!\n")
    else:
        print("Its a tie! \n")



def count_cards(current_hand):
    hasAce = False
    card_count = 0

    for i in range(len(current_hand)):
        if current_hand[i] is "A":
            hasAce = True
        elif current_hand[i] in ("K", "Q", "J"):
            card_count += 10
        else:
            card_count += int(current_hand[i])

    if hasAce:
        if (card_count + 11 > 21):
            card_count += 1
        else:
            card_count += 11

    return card_count


game_deck = ['A', 'Q', 'K', 'J', '1', '2', '3', '4', '5', '6', '7', '8', '9', '10']
player_cards = []
dealer_cards = []


random.shuffle(game_deck)
first_deal()

if not player_move():
    dealer_move()

get_winner()
input("Press any key to continue...")