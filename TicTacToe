from sys import exit

cells = ["_" for x in range(1,10)]

def print_matrix():
    print("---------")
    print("| " + cells[0] + " " + cells[1] + " " + cells[2] + " |")
    print("| " + cells[3] + " " + cells[4] + " " + cells[5] + " |")
    print("| " + cells[6] + " " + cells[7] + " " + cells[8] + " |")
    print("---------")

print_matrix()


def if_x_wins(s):
    s = "".join(s)
    if s[:3] == "XXX" or s[3:6] == "XXX" or s[6:] == "XXX" or (s[0] + s[3] + s[6]) == "XXX" or (s[1] + s[4] + s[7]) == "XXX" or (s[2] + s[5] + s[8]) == "XXX" or (s[0] + s[4] + s[8]) == "XXX" or (s[2] + s[4] + s[6]) == "XXX":
        return True
    return False


def if_o_wins(s):
    s = "".join(s)
    if s[:3] == "OOO" or s[3:6] == "OOO" or s[6:] == "OOO" or (s[0] + s[3] + s[6]) == "OOO" or (s[1] + s[4] + s[7]) == "OOO" or (s[2] + s[5] + s[8]) == "OOO" or (s[0] + s[4] + s[8]) == "OOO" or (s[2] + s[4] + s[6]) == "OOO":
        return True
    return False 


def check_coo(x, y):
    if x not in "1234567890" or y not in "1234567890":
        print("You should enter numbers!")
        return False
    else:
        x = int(x)
        y = int(y)
    
    if x not in range(1,4) or y not in range(1,4):
        print("Coordinates should be from 1 to 3!")
        return False
    
    return True


def get_cell_indx(x, y):
    
    x = int(x)
    y = int(y)
    
    if x == 1 and y == 1:
        return 6
    elif x == 1 and y == 2:
        return 3
    elif x == 1 and y == 3:
        return 0
    elif x == 2 and y == 1:
        return 7
    elif x == 2 and y == 2:
        return 4
    elif x == 2 and y == 3:
        return 1
    elif x == 3 and y == 1:
        return 8
    elif x == 3 and y == 2:
        return 5
    elif x == 3 and y == 3:
        return 2


def is_cell_empty(n):
    if cells[n] == "_":
        return True
    return False


sign = "O"
def switch_sign():
    global sign
    if sign == "X":
        sign = "O"
        return "O"
    elif sign == "O":
        sign = "X"
        return "X"
    


while "_" in cells:
    
    x = -1
    y = -1
    coo_ok = False
    while coo_ok != True:
        x, y = input("Enter coordinates").split()
        coo_ok = check_coo(x, y)
        
        if coo_ok != True:
            continue   

        if is_cell_empty(get_cell_indx(x, y)) != True:
            print("This cell is occupied! Choose another one!")
            coo_ok = False
            continue

    cells[get_cell_indx(x, y)] = switch_sign()
    print_matrix()
    
    if abs(cells.count("X") - cells.count("O")) > 1 or (if_x_wins(cells) == True and if_o_wins(cells) == True):
        print("Impossible")
        break

    elif if_x_wins(cells) == True:
        print("X wins")
        break
        
    elif if_o_wins(cells) == True:
        print("O wins")
        break

if not if_x_wins(cells) and not if_o_wins(cells):
    print("Draw")
