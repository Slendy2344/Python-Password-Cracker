# Python-Password-Cracker
import itertools 
import time
import string

chars = string.printable.strip()
attempts = 0

#----------------------------

password = input("Input a password to crack: ")
start_t = time.perf_counter()

for length in range(1, len(password) + 1):
    for guess_tuple in itertools.product(chars, repeat=length):
        attempts += 1 
        guess = ''.join(guess_tuple)
        if guess == password:
            break 


end_t = time.perf_counter()
total_t = end_t - start_t
print(f"Password was cracked in {total_t} second with {attempts} total attempts.")
print(f"Your password was: {guess}")

