
import random

print('--- Welcome to Roll Dice Simulator ---')

input('\n[ Tap Enter to Start ]')

# Initializing the stock
stok_dadu = 10
poin=0
ask = 'y' # Start the loop automatically after the enter tap

while ask.lower() == 'y':
    try:
        print(f"\nRemaining stock: {stok_dadu}")
        dadu = int(input('How many times do you want to roll? '))

        if dadu > stok_dadu:
            print(f'Too many! You only have {stok_dadu} left.')
            continue

        if dadu <= 0:
            print('Please enter a number greater than 0.')
            continue

        # Rolling the dice
        result=[]
        for _ in range(dadu):

            roll= random.randint(1,6)
            result.append(roll)

            if roll==6:
                poin+=5
                print('yeyy, u got extra 5 point!')

        print(f'Your rolls: {result}')
        print(f'Your poin total is {poin}')

        if stok_dadu==0:
            print('Oh Noo! is noone dice left!')
            input('\n wanna add some stcok? (y/n) :')


        if stok_dadu <= 0:
            print("\nYou're out of dice! Game over.")
            break

        ask = input('\nWanna roll again? (y/n): ')

    except ValueError:
        print("Oops! Please enter a valid number.")

print("\nThanks for playing!") 
