# Python-Project2
#Created email slicer in Python.

print("Welcome to Email Slicer.\nHere, you can enter 'n' number of emails.")
print("If you want to enter less than 'n' just type 'end' when email address will be asked.")

print("")
l = []
i = int(input("No. of email address you want to insert: "))
if i<=0:
    print("Sorry! number should neither zero nor negative.\nRerun the code again!!")
else:
    n= i
    while i > 0 :
        a= input("Enter email address: ")
        if ("@" not in a or (a.index(".") - a.index("@"))<2) and a != "end":  # Checking if separator is '@' or not and domain is present or not.
            print("Please enter a valid email")
            print("")
            continue
        elif a=="end":
            break
        else:
            l.append(a)                  #Storing all emails in a list.
            i = i-1
            print(" ")
    v = len(l)
    j= 0
    while j>=0 and j<v:
        b= l[j].index("@")               # getting index of '@' and separate the username and domain on basis of that.
        print("Username of",j+1,"email-->","\'"+(l[j])[0:b]+"\'")
        print("Domain of",j+1,"email-->","\'"+((l[j])[b+1 :]).upper()+"\'")
        j = j+1
        print("")
