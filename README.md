def gcd_extended(a, b):
    if a == 0:
        return b, 0, 1
    gcd, x1, y1 = gcd_extended(b % a, a)
    
    x = y1 - (b // a) * x1
    y = x1
    
    return gcd, x, y

def main():
    a = int(input("Введите натуральное число a: "))
    b = int(input("Введите натуральное число b: "))

    d, x, y = gcd_extended(a, b)

    if abs(x) >= 10**9 or abs(y) >= 10**9:
        print("Коэффициенты x и y превышают допустимые значения.")
    else:
        print(f"Наибольший общий делитель a и b: {d}")
        print(f"Коэффициенты x и y: {x}, {y}")

if name == "__main__":
    main()
