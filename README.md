#1.Write a function in python to read the content from a text file "poem.txt" line by line and display the same on screen 

f=open("poem.txt","r")
print(f.read())
f.close()


#2.Write a function in Python to count and display the total number of words in a text file. 


fname = input("Enter file name: ")
 
num_words = 0
 
with open(fname, 'r') as f:
    for line in f:
        words = line.split()
        num_words += len(words)
print("Number of words:")
print(num_words)

#3.Write a function in Python to read lines from a text file "notes.txt". Your function should find and display the occurrence of the word "the". 
#For example: If the content of the file is: 
#"India is the fastest-growing economy. India is looking for more investments around the globe. The whole world is looking at India as a great market. Most of the Indians can foresee the heights that India is capable of reaching." 
#The output should be 5. 
 


def count_words():
    file = open("poem.txt","r")
    count = 0
    data = file.read()
    words = data.split()
    for word in words:
        if word =="the" or word =="The":
            count += 1
    print(count)
    file.close()

count_words()


#4.Write a function in Python to count the words "this" and "these" present in a text file "article.txt". [Note that the words "this" and "these" are complete words] 


def count_words():
    file = open("Q4/article.txt","r")
    count = 0
    data = file.read()
    words = data.split()
    for word in words:
        if word =="this" or word =="These":
            count += 1
    print(count)
    file.close()


#5.Write a function in Python to count words in a text file those are ending with alphabet "e". 
 
count_words()

def count_words():
    file = open("Q5/article.txt","r")
    count = 0
    data = file.read()
    words = data.split()
    for word in words:
        if word[-1] == 'e':
            count+=1
    print(count)
    file.close()

#6.Write a function in Python to count uppercase character in a text file 

    def count_letter():
    file = open("Q5/article.txt","r")
    data = file.read()
    count = 0
    for letter in data:
        if letter.isupper():
            count+=1
    print(count)
    file.close()
count_letter()

count_words()


#7.	Write a function AMCount() in Python, which should read each character of a text file STORY.TXT, should count and display the occurrence of alphabets A and M (including small cases a and m too).  
  

def AMcount():
    file = open('Q7/article.txt','r')
    data = file.read()
    counta=0
    countm=0
    for letter in data:
        if letter == 'A' or letter =='a':
            counta += 1
        elif letter == 'M' or letter =='m':
            countm += 1

    file.close()
    print('A or a:',counta)
    print('M or m:',countm)

AMcount()

#8.Write a function to search and display details of student whose rollno is
#'1005' from the binary file student.dat having structure [rollno, name, class and fees]. 

def search():
    file = open("student.dat","rb")
    try:
        while True:
            record = pickle.load(file)
            if record[0] == 1005:
                print(record)
    except EOFError:
        pass
    file.close()

# import pickle

# def create_student_data():
#     # Sample student records
#     students = [
#         (1001, "Alice", 20, "A"),
#         (1002, "Bob", 21, "B"),
#         (1003, "Charlie", 19, "C"),
#         (1004, "David", 22, "A"),
#         (1005, "Eve", 20, "B"),
#         # Add more records as needed
#     ]
    
#     # Open the file in binary write mode
#     with open("student.dat", "wb") as file:
#         # Serialize and write each student record
#         for student in students:
#             pickle.dump(student, file)

# # Call the function to create the file
# create_student_data()

#9.	Create user defined exception named as EligibleforEntrance(Exception) and NotEiligibleforEntrance(Exception). Input PCM marks from user. 
#If per<45 raise userdefined exception NotEiligibleforEntrance else EligibleforEntrance 

class EligibleforEntrance(Exception):
    pass

class NotEligibleforEntrance(Exception):
    pass

def check_eligibility(p_marks):
    if p_marks < 45:
        raise NotEligibleforEntrance("You are not eligible for entrance.")
    else:
        raise EligibleforEntrance("You are eligible for entrance.")

try:
    pcm_marks = float(input("Enter PCM marks: "))
    check_eligibility(pcm_marks)
except ValueError:
    print("Invalid input! Please enter a valid number.")
except NotEligibleforEntrance as e:
    print(e)
except EligibleforEntrance as e:
    print(e)
