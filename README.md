# Harshada_Jadhav_assignment

#Day 13 

Q1. 
from datetime import datetime, timedelta
dt = datetime.now()
td = timedelta(days=4)
# your calculated date
my_date = dt + td

Q2.

    import datetime
    yesterday = datetime.date.today () - datetime.timedelta (days=1) 
    PERIOD=yesterday.strftime ('%Y-%m-%d') 
    new_period=PERIOD.replace(hour=23, minute=30)
    print new_period
    
Q3.

print("Enter the marks of five subjects::")

subject_1 = float (input ())
subject_2 = float (input ())
subject_3 = float (input ())
subject_4 = float (input ())
subject_5 = float (input ())

total, average, percentage, grade = None, None, None, None

# It will calculate the Total, Average and Percentage
total = subject_1 + subject_2 + subject_3 + subject_4 + subject_5
average = total / 5.0
percentage = (total / 500.0) * 100

if average >= 90:
    grade = 'A'
elif average >= 80 and average < 90:
    grade = 'B'
elif average >= 70 and average < 80:
    grade = 'C'
elif average >= 60 and average < 70:
    grade = 'D'
else:
    grade = 'E'

# It will produce the final output
print ("\nThe Total marks is:   \t", total, "/ 500.00")
print ("\nThe Average marks is: \t", average)
print ("\nThe Percentage is:    \t", percentage, "%")
print ("\nThe Grade is:         \t", grade)


Q4.

import os
def check_file():
    x = os.listdir("path to dir")
    for i in x:
        if ["hi","bye","bedanagain","dan1","dan2","gray"] in i:
            return True
            
Q6.

import csv
professions = {}

with open("sal.csv") as data:
    for city, profession, salary in csv.reader(data):
        professions.setdefault(profession.strip(), []).append(int(salary.strip()))

for profession, salaries in sorted(professions.items()):
    print ("{}: {}".format(profession, sorted(salaries)[len(salaries//2)] ))
    
Q7.

s = "aba"
perm = list("".join(string) for string in permutations(s))# all permutations
numberOfPerm = len(perm) #number of permutations
unique = len(list(set(perm))) #number of unique permutations
list.sort(perm) # ascii sorting
format_list = [numberOfPerm, unique]
print("total: {} (unique: {}) ".format(*format_list))
print(perm)

Q8.

filename = input("filename: ")
with open(filename, "w") as f:
  f.write(input())
  
  
Q9.

from urllib.request import urlopen

url = "https://www.xyz.com/file.csv"

# Download from URL
with urlopen(url) as file:
    content = file.read().decode()

print(content)

from urllib.request import urlopen

url = "https://www.xyz.com/file.csv"
save_as = "file.csv"

# Download from URL
with urlopen(url) as file:
    content = file.read().decode()

# Save to file
with open(save_as, 'w') as download:
    download.write(content)
    
Q10.

import urllib2 as ul 

def word_counting(url, code, words):
    page = ul.urlopen(url)
    text = page.read()
    decoded = ext.decode(code)
    result = {}

    for word in words:
        count = decoded.count(word)
        counted = str(word) + ":" + " " + str(count)
        result.append(counted)

    return finale
    
Q12.

data=open('xyz.txt')
num=[]
    while 1:
        numrow=[]
        count=0
        x=data.readline()
        if x=='':
            break
        for line in data:
            if line==x:
                count+=1
        numrow.append(x)
        numrow.append(count)
        num.append(numrow)
    print(num)
    
Q13.

import os
import zipfile
def zipdir(path, ziph):
    # ziph is zipfile handle
    for root, dirs, files in os.walk(path):
        for file in files:
            ziph.write(os.path.join(root, file))
zipf = zipfile.ZipFile('Zipped_file.zip', 'w', zipfile.ZIP_DEFLATED)
zipdir('./my_folder', zipf)
zipf.close()

Q14.

import os
for filename in os.listdir():
    if filename.endswith('.txt'):
        os.unlink(filename)
        
Q15.

def run():
p("Please enter file name\n")
a = input('> ')
import glob, os
os.chdir("H:/")
for file in glob.glob(a+'.*'):
    print(file)
    
Q16.

n=int(input()) 
width = len("{0:b}".format(n)) 
for num in range(1,n+1):
    print ('  '.join(map(str,(num,oct(num).replace('0o',''),hex(num).replace('0x',''),bin(num).replace('0b','')))))
    
 Q17.
 
 class Solution(object):
   def fizzBuzz(self, n):
      """
      :type n: int
      :rtype: List[str]
      """
      result = []
      for i in range(1,n+1):
         if i% 3== 0 and i%5==0:
            result.append("FizzBuzz")
         elif i %3==0:
            result.append("Fizz")
         elif i% 5 == 0:
            result.append("Buzz")
         else:
            result.append(str(i))
      return result
ob1 = Solution()
print(ob1.fizzBuzz(30))

Q19.

functions.py

import json

class Functionalities:
    def addelement(element):
        # code goes here`
main.py

import functions
f = functions.Functionalities()
f.addelement('some element')

Q20.

#Define the class 


class Car(object): 

    def __init__(self,fuelEfficiency=0,fuelCapacity=0,fuelLevel=0,odometer=0):
        self.setCar(fuelEfficiency,fuelCapacity,fuelLevel,odometer)

    def setFuelEfficiency(self,newFuelEfficiency):
        self.setCar(fuelEfficiency = newFuelEfficiency)

    def setFuelCapacity(self,newFuelCapacity):
        self.setCar(fuelCapactity = newFuelCapacity)

    def setFuelLevel(self,newFuelLevel):
        self.setCar(fuelLevel = newFuelLevel)

    def setOdometer(self,newOdometer):
        self.setCar(odometer = newOdometer)

    def setCar(self,fuelEfficiency = None,fuelCapacity = None,fuelLevel = None,odometer = None):
        if fuelEfficiency == None:
            fuelEfficiency = self.getFuelEfficiency

        if fuelCapacity == None:
            fuelCapacity = self.getFuelCapacity

        if fuelLevel == None:
            fuelLevel = self.getFuelLevel

        if odometer == None:
            odometer = self.getOdometer

        self.fuelEfficiency = fuelEfficiency
        self.fuelCapacity = fuelCapacity
        self.fuelLevel = fuelLevel
        self.odometer = odometer

    def drive(self,miles):
        if miles < 0:
            return ("The car is not driven")

        one_gallon = miles / self.fuelEfficiency

        if one_gallon < self.fuelLevel:
            print("The car drove {} miles".format(miles))
        elif self.fuelLevel == 0:
            print("The car drove 0 miles")
        #else:
            #newMiles = milesDriven * miles
            #print("The car drove {} miles".format(newMiles))

        self.fuelLevel -= one_gallon
        self.odometer += miles   


    def getCar(self):
        #Returns a tuple that has (FE,FC,FL,OD)
        return (self.fuelEfficiency,self.fuelCapacity,self.fuelLevel,self.odometer)        


    def addFuel(self,num):
        if type(num) == str:
            return self.fuelLevel
        if num < 0:
            print("Sorry, you need to enter a postive number.")
            return self.fuelLevel

        if (self.fuelLevel + num) > self.fuelCapacity:
            return self.getFuelLevel
        if (self.fuelLevel + num) == self.fuelCapacity:
            self.fuelLevel += num
            return self.getFuelLevel
        if (self.fuelLevel + num) < self.fuelCapacity:
            self.fuelLevel += num
            return self.getFuelLevel

    def getFuelEfficiency(self):
        return self.getCar()[0]

    def getFuelCapacity(self):
        return self.getCar()[1]

    def getFuelLevel(self):
        return self.getCar()[2]

    def getOdometer(self):
        return self.getCar()[3]

    def tripRange(self):
        numOfMiles = self.fuelEfficiency * self.fuelLevel
        return numOfMiles

    def __str__(self):
        FE = self.getFuelEfficiency()
        FC = self.getFuelCapacity()
        FL = self.getFuelLevel()
        OD = self.getOdometer()

        string = '{}:{}:{}:{}'.format(FE,FC,FL,OD)
        return string
        
        
Q22.

name=input("Name on your bank account? ")
balance=float(input("Your current balance? "))

def printMenu():
    print(name,"Welcome to the Lots of Money Bank")
    print("Enter 'b'(balance), 'd'(deposit), 'w'(withdraw), or'q'(quit)")

def getTransaction():
    transaction=str(input("What would you like to do? "))
    return transaction

def withdraw(bal,amt):
    global balance
    balance=bal-amt
    if balance<0:
        balance=balance-10

def formatCurrency(amt):
    return "$%.2f" %amt

###MAIN PROGRAM###

printMenu()
command=str(getTransaction())

while command!="q":
    if (command=="b"):
        print(name,"Your current balance is",formatCurrency(balance))
        printMenu()
        command=str(getTransaction())
    elif (command=="d"):
        amount=float(input("Amount to deposit? "))
        balance=balance+amount
        printMenu()
        command=str(getTransaction())
    elif (command=="w"):
        amount=float(input("Amount to withdraw? "))
        withdraw(balance,amount)
        printMenu()
        command=str(getTransaction())
    else:
        print("Incorrect command. Please try again.")
        printMenu()
        command=str(getTransaction())

print(name,"Goodbye! See you again soon")

Q26.

import psycopg2

try:
    connection = psycopg2.connect(user="sysadmin",
                                  password="pynative@#29",
                                  host="127.0.0.1",
                                  port="5432",
                                  database="postgres_db")
    cursor = connection.cursor()
    postgreSQL_select_Query = "select * from mobile"

    cursor.execute(postgreSQL_select_Query)
    print("Selecting rows from mobile table using cursor.fetchall")
    mobile_records = cursor.fetchall()

    print("Print each row and it's columns values")
    for row in mobile_records:
        print("Id = ", row[0], )
        print("Model = ", row[1])
        print("Price  = ", row[2], "\n")

except (Exception, psycopg2.Error) as error:
    print("Error while fetching data from PostgreSQL", error)

finally:
    # closing database connection.
    if connection:
        cursor.close()
        connection.close()
        print("PostgreSQL connection is closed")
        
Q.28        
#1
public String loadJSONFromAsset() {
    String json = null;
    try {
        InputStream is = getAssets().open("Contries.json");
        int size = is.available();
        byte[] buffer = new byte[size];
        is.read(buffer);
        is.close();
        json = new String(buffer, "UTF-8");
    } catch (IOException ex) {
        ex.printStackTrace();
        return null;
    }
    return json;
}

#2

public void loadCountries(String parent, String child, ArrayList<String> listValue)
{
    try {

        JSONObject obj = new JSONObject(loadJSONFromAsset());
        JSONArray m_jArry = obj.getJSONArray(parent);;
        ArrayList<HashMap<String, String>> formList = new ArrayList<HashMap<String, String>>();

        HashMap<String, String> m_li;

      //  listValue = new ArrayList<>();

        for (int i = 0; i < m_jArry.length(); i++) {
            JSONObject jo_inside = m_jArry.getJSONObject(i);

            listValue.add(jo_inside.getString(child));
        }


    } catch (JSONException e) {

        e.printStackTrace();
    }


}

Q31.

import hashlib

md5 = hashlib.md5(b'I like PythonTect.com')

print("The Hash Value is ",md5.hexdigest())



import hashlib

password = input("Please type password")

md5 = hashlib.md5(byte(password))

print("The Hash Value of the password is ",md5.hexdigest())


Q32.

import numpy as np
s = '\x01\x05\x03\xff'
a = np.fromstring(s, dtype='uint8')

Q34.

import pandas as pd
import numpy as np

l1 = [f'10{i}' for i in range(10,30)]
l2 = [f'10{i}.{i}' for i in range(10,30)]
l3 = [f'1.0{i}.{i}' for i in range(10, 30)]
l4 = [f'1,0{i}' for i in range(10, 30)]
l5 = [f'$1,0{i}' for i in range(10, 30)]
l6 = [f'{i}%' for i in range(20)]
l7 = [f'{i}.{i}%' for i in range(20)]
l8 = [f'10{i}' if i%2 == 0 else 'asdf' for i in range(10,30)]
l9 = [f'$1,0{i}' if i%2 == 0 else 'asdf' for i in range(10,30)]

df = pd.DataFrame({'l1':l1,
                   'l2':l2,
                   'l3':l3,
                   'l4':l4,
                   'l5':l5,
                   'l6':l6,
                   'l7':l7,
                   'l8':l8,
                   'l9':l9,
    })
