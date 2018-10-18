# black-jack-project
################################################################################
# Name = Black_Jack_0
# Subject = create Black jack
# Creators = Antoine Ganse and Pacôme Boucherat
################################################################################
import random

#parametres de départ : couleurs des cartes et valeur en fonction
#du numéro (/!\ onmodifiera la valeur de l'AS à therme)
colors=["Club","Diamonds","Spades","Heart"]
value={"2":2,"3":3,"4":4,"5":5,"6":6,"7":7,"8":8,
       "9":9,"10":10,"Knave":10,"Queen":10,"King":10,"Ace":1}


######## 2.1 : Initialisation
#2.1.1
def paquet():
    """
###############################################################
# Name = paquet
# Arguments = None
# Effect = create a deck
###############################################################
"""
    deck_seul=[]
    for i in colors:
        for j in value:
            deck_seul.append(j+" of "+i)
    return(deck_seul)

#2.1.2
def valeur_carte(carte):
    """
###############################################################
# Name = valeur_carte
# Arguments = name of a card
# Effect = return the card's value
###############################################################
"""
    a=carte.split()[0] #reupére la classe (1 ou 2 ou ... Roi ou as) de la carte
    return(value[a])

#2.1.3
def initPioche(n):
    """
###############################################################
# Name = initPioche
# Arguments = number of player(s)
# Effect = set the number of deck use in the game in function
#          the number of player(s) (as deck as player(s))
###############################################################
"""
    all_deck=[]
    for i in range (n):
        all_deck.append(paquet())
    return(all_deck)

#2.1.4
def piocheCarte(p,x=1):
    """
###############################################################
# Name = piocheCarte
# Arguments = la liste des cartes dans la pioche et la valeur
#             optionelle x initialement fixé a 1, mais qui
#             prend la valeur rentré (si y en a une)
# Effect = pioche une carte dans la pioche (elle disparait donc
#          de la pioche)
###############################################################
"""
    lst_p=[]
    for i in range(x):
        b= random.randint(0,51)
        lst_p.append(p.pop(b))
    return(lst_p)
