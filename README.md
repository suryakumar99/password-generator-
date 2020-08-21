# password-generator-
def passwordGenerator(passLen, passType):
    DIGITS = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9'] 
    LOCASE_CHARACTERS = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 
                        'i', 'j', 'k', 'm', 'n', 'o', 'p', 'q', 
                        'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 
                        'z'] 

    UPCASE_CHARACTERS = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 
                        'I', 'J', 'K', 'M', 'N', 'O', 'p', 'Q', 
                        'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 
                        'Z'] 

    SYMBOLS = ['@', '#', '$', '%', '=', ':', '?', '.', '/', '|', '~', '>', 
            '*', '(', ')'] 

    COMBINED_LIST = DIGITS + UPCASE_CHARACTERS + LOCASE_CHARACTERS + SYMBOLS 

    digit = random.choice(DIGITS) 
    upper = random.choice(UPCASE_CHARACTERS) 
    lower = random.choice(LOCASE_CHARACTERS) 
    symbol = random.choice(SYMBOLS) 
    
    tempPass = ""
    if(passType == "H"):
        tempPass = digit + upper + symbol  + lower 
    elif(passType == "M"):
            tempPass = digit + symbol
  curPassLen = len(tempPass)
    for length in range(passLen -  curPassLen): 
        tempPass = tempPass + random.choice(COMBINED_LIST) 

    tempPass_list = list(tempPass) 
    random.shuffle(tempPass_list) 


    password = "" 
    for char in tempPass_list: 
            password = password + char

    print("Password: ",password) 


def main():
    passLen = 15
    print("Type ( H for Hard, M for Medium and E for Easy)")
    print("Enter type pasword type: ")
    passType = input().strip()
    
    if(passType == "E"):
        passLen = 5
    elif(passType == "M"):
        passLen = 10
    passwordGenerator(passLen, passType)

if __name__ == "__main__":
    main()
