## Hello There,

This is code for [Python Classes and Inheritance](https://www.coursera.org/learn/python-classes-inheritance/home/welcome) Courser's course Final Project **Wheel Of Fortune**

```python
VOWEL_COST = 250
LETTERS = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
VOWELS = 'AEIOU'

class WOFPlayer():
    def __init__(self, initName):
        self.name = initName
        self.prizeMoney = 0
        self.prizes = []
    def goBankrupt(self):
        self.prizeMoney = 0
    def addPrize(self, prize):
        self.prizes.append(prize)
    def addMoney(self,amt):
        self.prizeMoney = self.prizeMoney + amt
    def __str__(self):
        return "{} ($ {})".format(self.name,self.prizeMoney)
    
class WOFHumanPlayer(WOFPlayer):
    def getMove(category, obscuredPhrase, guessed):
        input_prompt = input(self.name + "has $"+ str(self.prizeMoney)+ "/n" + ", Category:" + category + "/n" + ", Phrases:" + "/n" + obscuredPhrase + "/n" + ", Guessed:" + guessed + "/n" + "Guess a letter, phrase, or type 'exit' or 'pass':") 
        print(input_prompt) 
    
    

class WOFComputerPlayer(WOFPlayer):
    SORTED_FREQUENCIES = 'ZQXJKVBPYGFWMUCLDRHSNIOATE'
    prizemoney = 0
    def __init__(self, name, difficulty):
        self.name = name
        self.difficulty = difficulty
        self.prizeMoney = 0
        self.prizes = []

    def smartCoinFlip(self):
        if random.randint(1, 10) > self.difficulty:
            return True
        else: 
            return False

    def getPossibleLetters(self, guessed):
        possible_letters = []
        for char in LETTERS:
            if char in VOWELS and self.prizeMoney < 250:
                continue
            if char not in guessed:
                possible_letters.append(char)
        return possible_letters

    def getMove(self, category, obscuredPhrase, guessed):
        list = self.getPossibleLetters(guessed)
        smartCoinResult=self.smartCoinFlip()
        if list == []:
            return 'pass'
        else:
            if smartCoinResult==True:
                for l in self.SORTED_FREQUENCIES:
                    if l in list:
                        return l
            elif smartCoinResult==False:
                return random.choice(list)

```

### Issues..?
[Report Issue](https://github.com/RajasekharGuptha/Python-Classes-and-Inheritance-Coursera/issues)

### Contact

[Mail](mailto:rajasekharmuppidi4@gmail.com)
