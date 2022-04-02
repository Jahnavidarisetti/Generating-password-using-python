# Generating-password-using-python
import random
import array

# maximum password length is necessary
max_len = 14

# declaring arrays of the characters necessary for the password

LOWER_CASE_CHARACTERS = ['a', 'b','c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']

UPPER_CASE_CHARACTERS = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']

DIGITS = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']

SYMBOLS = ['`', '~', '!', '@', '#', '$', '%', '^', '&', '*', '(', ')', '_', '-', '=', '+', '[', ']', '{', '}', ':', ';', '/', '|', '<', '>']

# join all the characters listed above to form the array 

COMBINED_LIST = UPPER_CASE_CHARACTERS + LOWER_CASE_CHARACTERS + DIGITS + SYMBOLS

# select atleast one character from each set listed above

upper = random.choice(UPPER_CASE_CHARACTERS)
lower = random.choice(LOWER_CASE_CHARACTERS)
digit = random.choice(DIGITS)
symbol = random.choice(SYMBOLS)

# join all the random characters selected above but the password length is only 4

temp_pass = upper + lower + digit + symbol

# code for 14 characters length of password

for x in range(max_len - 4):
 temp_pass = temp_pass + random.choice(COMBINED_LIST)
 
# change temporary password to an array to prevent the password from predicting

temp_pass_list = array.array('u', temp_pass)
random.shuffle(temp_pass_list)

password = ""
for x in temp_pass_list:
 password = password + x
 
 # print the password
 
 print(password)

