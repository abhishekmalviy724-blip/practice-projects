import pandas as pd

data = {
    "Name": ["Aman", "Riya", "Karan", "Neha", "Rahul"],
    "Math": [78, 92, 65, 88, 75],
    "Science": [82, 90, 70, 85, 80],
    "English": [75, 89, 68, 91, 77]
}

df = pd.DataFrame(data)

print("Student Dataset")
print(df)

df["Total"] = df["Math"] + df["Science"] + df["English"]
df["Average"] = df["Total"] / 3
df["Result"] = df["Average"].apply(lambda x: "Pass" if x >= 60 else "Fail")

print("\nDataset with Total, Average and Result")
print(df)

print("\nTop Scorer")
print(df.loc[df["Total"].idxmax()])

print("\nAverage Marks in Each Subject")
print(df[["Math", "Science", "English"]].mean())

print("\nStudents Scoring More Than 80 Average")
print(df[df["Average"] > 80])




import numpy as np

marks = np.array([
    [78, 85, 90, 88],
    [65, 70, 75, 80],
    [92, 95, 89, 94],
    [55, 60, 58, 62],
    [81, 79, 84, 86]
])

print("Marks Dataset")
print(marks)

print("\nTotal Marks of Each Student")
print(np.sum(marks, axis=1))

print("\nAverage Marks of Each Student")
print(np.mean(marks, axis=1))

print("\nHighest Marks in Each Subject")
print(np.max(marks, axis=0))

print("\nLowest Marks in Each Subject")
print(np.min(marks, axis=0))

print("\nOverall Average")
print(np.mean(marks))

bonus = marks + 5

print("\nMarks After Bonus")
print(bonus)

print("\nDifference")
print(bonus - marks)

print("\nStudents Passed (Average >= 60)")
print(np.mean(marks, axis=1) >= 60)


import numpy as np

a = np.array([[2, 4, 6], [8, 10, 12], [14, 16, 18]])
b = np.array([[1, 3, 5], [7, 9, 11], [13, 15, 17]])

print("Array A:")
print(a)

print("\nArray B:")
print(b)

print("\nAddition:")
print(a + b)

print("\nSubtraction:")
print(a - b)

print("\nMultiplication:")
print(a * b)

print("\nMatrix Multiplication:")
print(np.dot(a, b))

print("\nTranspose of A:")
print(a.T)

print("\nMean of A:")
print(np.mean(a))

print("\nMaximum of A:")
print(np.max(a))

print("\nMinimum of A:")
print(np.min(a))

print("\nSum of A:")
print(np.sum(a))

print("\nShape of A:")
print(a.shape)

print("\nReshaped A:")
print(a.reshape(1, 9))



# import matplotlib.pyplot as plt
# import pandas as pd
# import seaborn as sns
# a=pd.read_csv("Walmart_Sales.csv")

# b=a.nlargest(10,columns="Weekly_Sales")
# sns.barplot(data=b,x="Weekly_Sales",y="Date")
# plt.show()

# a.plot(x="Weekly_Sales",kind="bar")
# plt.show()

import seaborn as sns
import matplotlib.pyplot as plt

tips = sns.load_dataset("tips")

sns.barplot(
    data=tips,
    x="day",
    y="total_bill",
    hue="sex"
)

plt.title("Average Total Bill by Day and Gender")
plt.xlabel("Day")
plt.ylabel("Average Total Bill")
plt.show()



import pandas as pd

data = {
    "Name": ["Rahul", "Priya", "Amit"],
    "Math": [80, 95, 70],
    "Science": [75, 90, 65],
    "English": [90, 85, 75]
}

df = pd.DataFrame(data)

df["Total"] = df["Math"] + df["Science"] + df["English"]
df["Average"] = df["Total"] / 3

print(df)

print("Highest Scorer:")
print(df.loc[df["Total"].idxmax()])

df.to_csv("student_report.csv", index=False)



x = [1, 2, 3, 4, 5]
y = [10, 20, 15, 25, 30]
plt.plot(x, y, marker='o', color='blue')
plt.title("Simple Line Graph")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.grid(True)
plt.show()


a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

op = input("Enter operator (+, -, *, /): ")

if op == "+":
    print("Answer =", a + b)
elif op == "-":
    print("Answer =", a - b)
elif op == "*":
    print("Answer =", a * b)
elif op == "/":
    if b != 0:
        print("Answer =", a / b)
    else:
        print("Cannot divide by zero")
else:
    print("Invalid operator")






import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.figure(figsize=(6, 4))
plt.plot(x, y, marker="o", linewidth=2, label="y = 2x")
plt.title("Simple Line Graph")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.grid(True)
plt.legend()
plt.tight_layout()
plt.show()


import pandas as pd

# 1. Sample Data banana
data = {
    'Product': ['Laptop', 'Mouse', 'Laptop', 'Keyboard', 'Mouse', 'Keyboard'],
    'Sales': [50000, 500, 48000, 1200, 600, 1500]
}

df = pd.DataFrame(data)


aggregated_df = df.groupby('Product')['Sales'].sum().reset_index()

print("Original Data:")
print(df)
print("\nAggregated Data (Total Sales per Product):")
print(aggregated_df)






import matplotlib.pyplot as plt

plt.plot([1, 2, 3], [4, 5, 6])
plt.title("Minimal Plot")
plt.show()




import pandas as pd

data = {
    "Name": ["Amit", "Rahul", "Neha"],
    "Marks": [80, 90, 85]
}

df = pd.DataFrame(data)

print(df)

print(df[df["Marks"] > 80])

print(df["Marks"].mean())





import pandas as pd

data = {
    "Name": ["Amit", "Rahul", "Priya", "Neha"],
    "Age": [22, 25, 21, 24],
    "Salary": [30000, 45000, 35000, 40000]
}

df = pd.DataFrame(data)

print(df[df["Salary"] > 35000])

df["Bonus"] = df["Salary"] * 0.10

print(df)

print("Average Salary:", df["Salary"].mean())




import pandas as pd

a = pd.read_csv("Walmart_Sales.csv")

a.fillna(method="ffill", inplace=True)

a.to_csv("Walmart_Sales.csv", index=False)

print(a)








import pandas as pd

data = {
    "Name": ["Aman", "Priya", "Rahul"],
    "Age": [21, 22, 20],
    "City": ["Delhi", "Mumbai", "Jaipur"]
}

df = pd.DataFrame(data)

print(df)

print(df[df["Age"] > 21])
print("=== Table Generator ===")

number = int(input("Kis number ka table chahiye? "))

print("\nTable of", number)

for i in range(1, 11):
    print(number, "x", i, "=", number * i)

print("\nTable complete!")


print("=== Student Grade Calculator ===")

name = input("Student ka naam: ")

math = int(input("Math ke marks: "))
science = int(input("Science ke marks: "))
english = int(input("English ke marks: "))

total = math + science + english
percentage = total / 3

print("\nStudent:", name)
print("Total Marks:", total)
print("Percentage:", percentage)

if percentage >= 90:
    print("Grade: A+")
elif percentage >= 75:
    print("Grade: A")
elif percentage >= 60:
    print("Grade: B")
elif percentage >= 40:
    print("Grade: C")
else:
    print("Grade: Fail")
# # year=['2023', '2024', '2025']
# store_A=[30, 50, 45]
# store_B=[40, 35, 60]
# # plt.plot(year,year,store_A,color="red",marker="o",linewidth=3,label='Store A')
# # plt.plot(year,year,store_B,color="purple",marker="o",linewidth=3,label='Store B')
# # plt.grid(True)
# # plt.legend()
# # plt.show()
# df=pd.DataFrame({ 
#     'Drug_Type':['Tablet', 'Injection', 'Syrup'],
#   'Stock_Available':[10,20,30]
# })
# print(df.groupby('Drug_Type')['Stock_Available'].sum())

# df=pd.DataFrame({
#     'Disease':["Covid",'Maleria','Typhoid','Typhoid'],
#     'Patient_ID':["JDNX384","O383IXI","09283099",'09283099'],
# })
# print(df.groupby("Disease")['Patient_ID'].count())

# df=pd.DataFrame({
#   'Patient_ID'  :['P01','P02','P03','P04'],
#   'Patient_Name':['Abhi','Sanvi','Sonu','Monu']
# })
# df1=pd.DataFrame({
#   'Patient_ID'  :['P05','P06','P07','P08'],
#   'Patient_Name':['Abhi','Sanvi','Sonu','Monu']
# })
# print(pd.merge(df,df1,on='Patient_Name',how='left'))


import numpy as np
# a=np.array([1,2,3,4,5])
# print(a.ndim)
# print(a.shape)
# print(a.size)
# a=np.array([[1,2,3],
#             [4,5,6]])
# print(a)
# print(a.shape)
# print(a.size)
# print(a.ndim)
# a = np.array([[10,20,30],
#               [40,50,60]])
# print(a[0][1])
# print(a[1][2])
# print(a[0])
# print(a[0:2][:,2])
# a=np.array([[5,10,15],
#             [20,25,30],
#             [35,40,45]])
# print(a)
# print(a[1][1])
# print(a[2][2])
# print(a[0:3][:,2])
# a=np.array([[1,2,3,4],
#             [5,6,7,8],
#             [9,10,11,12],
#             [13,14,15,16]])
# # print(a)
# # print(a[1])
# # print(a[0:4][:,2])
# print(a[3])
# print(a[0:4][:,3])
# number = 7

# fact = 1
# while number>1:
#     fact*= number
#     number-=1
# print("fact", fact)


# num = 5
# fact = 1
# while num >=1:
#     fact *= num
#     num -=1
# print('fact', fact)

# while True:   
#     key = int(input('enter password'))
#     if 1 <= key <=10:
#         print('open')
#         break
#     else:
#         print("try again")


# scores = [45, 22, 10, 60, 35, 5]
# b = []

# for a in scores:
#     if a >15:
#         b.append(a)
# print(b)
        
        
# prices_in_rupees = [80, 160, 240]
# prices_in_dollars = []
# for i in prices_in_rupees:
#     prices_in_dollars.append(i/80)
# print(prices_in_dollars)
    
# orders = [150, 300, 50, 400]
# status = []
# for i in orders:
#     if i >200:
#         print('free')
#         status.append(status)
#     else:
#         print("paid")


# h = [123,344,321,200,55]
# for i in h:
#     i = i - 150
#     if i >0:
#         print('tall')
        
#     else:
#         print("short")

# a = [22,-23,3,-1,]
# a2 = []
# for i in a:
#     if i >=0:
#         print('positive')
#         a2.append(a2)
#     else:
#         print("negetive")

# num = [1,3,5,17,9,]
# res = []
# for i in num:
#     i = i + 5
#     if i >20:
#         res.append(i)
# print(res)

# data = [12,0,34,56,8,90]
# clean = []
# for i in data:
#     if i != 0:
#         print("clean data")
#         clean.append(i)
#     else:
#         print('cryupt')
# print(clean)


# num =[12,34,56,76,78,89]
# b = []
# for i  in num:
#     sq = i * i
#     if sq >=10:
#         b.append(sq)
# print(b)

# marks = [34,65,88,34,56,43,56,3,7,5,11,8,8]
# pas = 0
# for a in marks:
#     if a >=15:
#         pas = pas + 1
# print(pas)


# p = [1,2,3,4,5,6,7]
# data = []
# for i in p:
#     a = i * 100
#     data.append(a)
# print(data)


# e = [233,564,768,879,454,34,345]
# v = 0
# for i in e:
#     v = v + i
# print(v)


#Q1
# fruits = ["apple", "banana", "cherry"]
# for i in fruits:
#     print(i)
    
#Q2
# num = [1, 2, 3, 4, 5]
# for i in num:
#     print(i*2)

# #Q3
# data = [10, -5, 20, -1]
# for i in data:
#     if i >0:
#         print(i)

# #Q4
# nums = [1, 2, 3, 4, 5, 6]
# for i in nums:
#     if i %2==0:
#         print(i,'even')
#     else:
#         print(i,'odd')

# #Q5
# prices = [10, 20, 30]
# new_list = []
# for i in prices:
#     i = i + 5
#     new_list.append(i)
# print(new_list)

# #Q6
# sales = [100, 200, 300]
# total = 0
# for i in sales:
#     total = i + i
# print(total)

# #Q7
# ages = [12, 18, 25, 30, 10]
# for i in ages:
#     if  i >15 and i<25 :
#         print(i)

# #Q8
# votes = ["Yes", "No", "Yes", "Yes", "No"]
# for i  in votes:
#     if i == 'yes':
#         print(i)
#         i = i + 1


# raw_data = [10, 0, -5, 20, 0, 35]
# d = []
# for i in raw_data:
#     if i >0:
#         i = i * i
#         d.append(i)
# print(d)



# #Q1
# temps = [-5, -2, 0, 3, 8]
# for i in  temps:
#     i = i * -1
#     print(i)


# #Q2
# marks = [45, 20, 15, 60, 30]
# for i in marks:
#     if i >33:
#         print(i, 'pass')
#     else:
#         print(i, "fail")

# #Q3
# names = ["Ai", "Python", "Data", "ML"]
# for i in names:
#     if len(i)>3:
#         print(i)

# #Q4
# nums = [1, 2, 3, 4, 5, 6]
# for i in nums:
#     if i %2!=0:
#         i=i*i
# print(i)

# #Q5
# prices = [1000, 500, 2000]
# new_list = []

# for i in prices:
#     i *= 0.9
#     new_list.append(i)
# print(new_list)

# #Q6
# items = ["apple", "banana", "STOP", "cherry"]
# for i in items:
#     if i == 'STOP':
#         break
#     print(i)

# #Q
# vals = [5, 15, 25, 35, 45]
# for i  in vals:
#     if i >10 and i <40:
#         i = i + i
#     print(i)

# #Q
# list1 = [1, 2, 3] 
# list2 = [2, 3, 4]

# for i in list1:
    
# #Q
# weights = [70, 55, 90, 42, 80]
# min_val = weights[0]

# for i in weights:
#     if i >0:
#         i = i = i
#     print(i)


# raw = [10, "NA", 20, "NA", 30]
# n = []
# for i in raw:
#     if i != 'NA':
#         n.append(i)
# print(n)


# logs = ["INFO: Start", "ERROR: Disk Full", "INFO: Run", "ERROR: Memory Low"]
# errors = []
# for i in logs:
#     if "ERROR" in i:
#         errors.append(i)
#     print(i)

# prices = [10, 20, 30, 40]
# total = 0
# for i in prices:
#     total = total + i
#     avg = total / 4
# # print(total)


#Q1
# data = [10, -5, 20, -30, 40, -1]
# positives = []
# for i in data:
#     if i >0:
#         positives.append(i)
# print(positives)


# marks = [55, 30, 88, 20, 95, 40]
# for i in marks:
#     if i >80:
#         print(i, 'pass')
#     else:
#         print(i,'fail' )
        
# # raw_list = [5, 10, 5, 20, 10, 30]
# # d = []
# # for i in raw_list:
# #     if i == 10:
# #         d.append(i)
# print(d)


# m = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
# table = []
# for i in m:
#     i = i * 5
#     table.append(i)
# print(table)


# nums = [45, 22, 89, 10, 56]7
# for t in nums:
#     if t < chota_num:
#         chota_num = t
# # print("chota",chota_num)

# temps = [30, 45, 38, 50, 32]
# temp = []
# for i in temps:
#     if i >40:
#         print(i,"danger")
#     else:
#         print(i,"safe")
        

# for i in range(5,51):

# print(i)



# for i in range(5,51):

# print(i)



# for i in range(5,51):

# print(i)



# for i in range(5,51):

# print(i)


# a = [1,2,3,4,5,6,7,8,9,10,11]
# for i in a:
#     i = i * 5
# #     print(i)


# passwords = ["12345", "python789", "admin", "data_science_2026"]
# t = 8
# for i in passwords:
#     if len(i)>t:
#         print(i)
        
        
# numbers = [1, 5, 8, 10, 15, 20, 23]
# total = 0
# for i  in numbers:
#         total = total + i
# print(total, 'total')


# basket = ["apple", "banana", "mango", "apple", "orange", "apple"]
# count = 0
# for i in basket:
#     if i == 'apple':
#         count = count + 1
    
# print(count,"count")


# names = ["amit", "rahul", "sana"]
# clean_names = []

# for i in names:
#     # i.capitalize() karke use seedha append kar do
#     clean_names.append(i.capitalize()) 

# print(clean_names)
# # Output: ['Amit', 'Rahul', 'Sana']

# nums = [2, 3, 4, 5, 6]
# num = 20
# for i in nums:
#     s = i * i
#     if s > num:
#         print(s,'num')


# ages = [15, 25, 40, 12, 60, 17, 35]
# adults = []
# kids = []
# age = 18
# for i in ages:
#     if i > age:
#         adults.append(i)
#     if i <age:
#             kids.append(i)
#     print(kids,'kids')
# print(adults,'adults')


# logs = ["INFO: Start", "ERROR: Disk Full", "INFO: Working", "ERROR: Connection Lost"]
# all_errors = []
# for i  in logs:
#     if "ERROR" in i :
#         all_errors.append(i)
# print(all_errors, 'all_errors')


# x = [1, 2, 3, 4]
# y = []
# for i in x:
#     d = i * 2
#     y.append(d)
# print(y)

# hours = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
# cost = []

# for i in hours:
#     i = i * 5
#     cost.append(i)
# print(cost,'cost')

# m = [5, 10, 15, 20, 25, 30, 35, 40, 45, 50]
# expensive_hours = []
# h = 30
# for i in m:
#     if i >h:
#         expensive_hours.append(i)
#         print(expensive_hours, "expensive_hours")


# cpu_usage = [20, 45, 90, 30, 95, 40]
# t  = 80
# for i in cpu_usage:
#     if i >t:
#         print("Alert: CPU is high at {i}%")
        

   
         
# load_levels = [60, 85, 70, 92, 45, 88]
# limit = 80
# count = 0
# for i in load_levels:
#     if i > limit:
#         print("High load detected")
#         count = count + 1
# print("Total High Load Times: [count]", count)
    
    
# vactor = [10,20,30,40,50]
# n = 3
# result = []
# for i in vactor:
#     i = i* n
#     result.append(i)
# print(result, 'result')
    
# file_sizes = [120, 45, 300, 80, 150, 20]
# max_size = 100
# keep = []
# delete = []

# for i  in file_sizes:
#     if i >max_size:
#         delete.append(i)
#     if i <max_size:
#             keep.append(i)
# print(keep)
# print(delete)    


# efficiency = [70, 0, 85, 0, 90, 100, 0, 60]
# total_sum = 0
# valid_count = 0
# for i in efficiency:
#     if i > 0:
#         total_sum = total_sum + 1
#         valid_count = valid_count + 1
# average = total_sum / valid_count
# print(valid_count) 



# marks = [70, 80, 90]
# total = 0
# for i in marks:
#     total = total + i
# average = total / 3
# print(total)


# storage = [100, 200, 300, 400]
# total_storage = 0
# for i in storage:
#     if i > 250:
#         print(i,"Alert: High Storage on this server")
#         total_storage = total_storage +1
        
# print(total_storage)


# weights = [10, 20, 30]
# total_kg = 0
# total_boxes = 0
# for i in weights:
#     total_boxes= total_boxes +1
#     total_kg = total_kg +i
# print(total_kg,'total kg')
# print(total_boxes, 'total boxes')


# listt = [23,43,6,7,89,76]
# limit = 9
# v = []
# for i in listt:
#     if i > limit:
#         v.append(i)
# print(v) 


# n = 1
# while n <=21:
#     print(n,'name')
#     n = n +1
# print('end')

# m = 1 
# while m <=21:
#     print(m, 'Hello')
#     m= m +1
# print('end')


# i = 1
# while i <=100:
#     if i%3 ==0:
#         print(i)
#     i = i +1


# l =[23,34,76,89,3,56,89]
# budget = 20
# count= 0
# sum = 0
# for i in l:
#     if i>budget:
#         count = count + 1
#         sum = sum + i
# avg = sum/ count
# print('avg ', avg)



# l  = [21,34,56,78,89,67,45,23]
# l2 = 30
# safe = []
# danger = []
# for i in l :
#     if i >l2:
#         danger.append(i)
#     else:
#          safe.apped(i)
# avg = sum(danger) / len(danger)
# print(avg,'avg')


# l = [100,200,300,400,500,600]
# price = 250
# count = 0
# expensive_items = []
# for i in l:
#     if i >price:
#         count = count + 1
#         expensive_items.append(i)
# avg = sum(expensive_items) / len(expensive_items)
# print(avg, 'avg')


# salaries = [10000,20000,30000, 40000,50000,60000,70000]
# l = 50000
# low_salaries = []
# high_salaries = []
# for i in salaries:
#     if i <l:
#         low_salaries.append(i)
#     else:
#         high_salaries.append(i)
# avg = sum(low_salaries)/ len(low_salaries)
# print(avg, 'avg')

# w = [12,34,56,78]
# w1 =[87,76,45,56]
# total_stock = []
# for a in range(len(w)):
#     z =  w[a] + w1[a]
#     total_stock.append(z)
# print(total_stock,'total_stock')
    

# stock_jan  = [200,300,400,500]
# stock_feb =  [600,700,800,900]
# difference = []
# for i in range(len(stock_jan)):
#     m = stock_feb[i] - stock_jan[i]
#     difference.append(m)
# avg = sum(difference)/len(difference)
# print(avg,'avg')



# #Q1
# students = [12,17,19,16,20,19]
# li = 18
# count = 0
# for i in students:
#     if i >li:
#         count = count +1

# print(count,'count')


# price = [100,200,300,400,500]
# discount = 10
# new_list = []



# #Q1
# num =  1 
# for i in range(num,11,1):
#     print(i)



# for i in range(1,6):
#     print('abhishek')
    
# for i in range(21):
#     if i%2==0:
#         print(i)

# for i in range(10,0,-1):
#     print(i)

# n = 'PYTHON'
# for i in n:
#     print(i)


    
# n = int(input('Enter num'))
# for i in range (n,n*10+1,n):
#     print(i)
    
    
# for i in range(5,51,1):
#     if i %5==0:
#         print(i)

# for i in range(1,30):
#     if i %2==0:
#         print(i)



# for i in range(1,20):
#     if i == 3 :
#         break
#     print(i)



# for  i in range(1,6):
#     print(i)

# for i in range(1,10):
#     if i %2==0:
#         print(i)

# for i in range(1,11):
#     if i %2!=0:
#         print(i)

# for i in range(1,11):
#     if i == 7:
#          break
#     print(i)
        
        
# for i in range (1,11):
#     if i == 5:
#         continue
# #     print(i)
    

# for i in range(1,21):
#     if i % 3==0:
#          continue
#     print(i)
  

# for i in range(1,21):
#     if i == 3:
#         continue
#     if i == 15:
#         break
#     print(i)

# n = int(input("Enter a number: "))

# while n != 0:
#     if n % 2 != 0:
#         print(n)
#     n = int(input("Enter a number: "))



# while True:
#     a = int(input("Enter no:"))
#     if a ==0:
#         break
#     if a %2==0:
#         continue
#     if a >20:
#         break
#     print(a,'odd')

# while True:
#     a = int(input("Enter no:"))
#     if a == 0:
#         break
#     if a >30:
#         break
#     if a %2==0:
#         continue
#     print(a,'odd')

# n = int(input("Enter no"))
# for i in range(1,10+1):
#     print(i*n)

# for i in range(1,30):
#     if i %4==0:
#         continue
#     print(i)

# for i in range(1,21):
#     if i ==13:
#         break
#     print(i)

# for i in range(1 ,16):
#     if i%3==0:
#         continue
#     print(i)


# for i in range(1,21):
#     if i == 17:
#         break
#     if i %2==0:
#         continue
#     print(i)


# for i in  range(1,21):
#     if i > 15:
#         break
#     if i %3==0:
#         continue
#     print(i)

# for i in range(1,30):
#     if i >25:
#         break
#     if i %2!=0:
#         print(i,'odd')
#     if i %5==0:
#         print(i)
    


# for i in range(1,51):
#     if i >40:
#         break
#     if i %4==0:
#         continue
#     if i%7==0:
#         print(i,"lucky")
# #     else:
# #         print(i)


# for i in range(1,31):
#     if i >25:
#         break
#     if i %2==0:
#         print(i,"Double")
#     if i %5==0:
#         continue
#     else:
#         print(i)


# for i in range(1,41):
#     if i >35:
#         break
#     if i % 3==0:
#         print("Fizz")
#     if i %5==0:
#         print("Buzz")
#     if i %3==0 and i %5==0:
#         print("FizzBuzz")
#     else:
#         print(i)


# for i in range(1,31):
#     if i >24:
#         break
#     if i %4==0 and i %6==0:
#         print(i,"QuadHex")
#     if i %4==0:
#         print(i,"Quad")
#     if i %6==0:
#         print(i,"Hex")
#     else:
#         print(i)

# for i in range(1,61):
#     if i>45:
#         break
#     if i%6==0:
#         continue
#     if i %4==0 and i%9==0:
#         print("SoftHard")
#     if i %4==0:
#         print("Soft")
#     if i %9==0:
#         print("Hard")
#     else:
#         print(i)
        

# n =1
# n2 = []
# for i in range(n,11):
#     n2.append(i)
# print(n2)


# n = 1
# n2 = []
# for i in range(n,21):
#     if i %2==0:
#         n2.append(i)
# print(n2)

# a = 1
# a2 = []
# for i in range(a,31):
#     if i %5==0:
#         continue
#     if i %2!=0:
#         a2.append(i)
# print(a2)


# a = 1
# a2 = []
# for i in range(a, 40):
#     if i >35:
#         break
#     if i %5==0:
#         continue
#     if i %3==0 and i%7==0:
#         print("LowHigh")
#     elif i %3==0:
#         print("Low")
#     elif i %7==0:
#         print("High")
#     else:
#         a2.append(i)
# print(a2)




# n1 = []
# for i in range(n,51):
#     if i >42:
#         break
#     if i %5==0:
#         continue
#     if i %4==0 and i %6==0:
#         n1.append("QuadHex")
#     if i %4==0:
#         n1.append("Quad")
#     if i %6 == 0:
#         n1.append("Hex")
#     else:
#         n1.append(i)
# print(n1)


# for i in range(1,6):
#     for j in range(1,6):
#         print(i,j)


# odd_list = []
# even_list = []
# for i in range(1,21):
#     if i %5==0:
#         continue
#     if i %2!=0:
#         odd_list.append(i)
#     else:
#         even_list.append(i)
            
# print(odd_list,"odd list")
# print(even_list,"even list")
    

# old = [1,2,3,4,5,6]
# new = [9,8,7,6,5,4]
# newl = []
# for i in range(len(old)):
#     a = new[i] + old[i]
#     newl.append(a)
# print(newl)


# w = [23,34,56,78,45,34]
# l = 25
# k = []
# for i in w:
#     a = i - l
#     k.append(a)
# print(k)


# lll = [12,34,5,67,78,9,9]
# vvv = 19
# sss = []
# for i in lll:
#     a =((i-vvv)**2)
#     sss.append(a)
# print(sss)

# marks = [[50, 60], [70, 80], [90, 85]]
# total_marks = []
# for i in marks:
#     a = (sum(i)) + (len(marks))
#     total_marks.append(a)
# print(total_marks)


# matrix = [[23,45],[45,78],[89,67]]
# new_list = []
# for i in matrix:
#     a = (sum(i)) +(sum(i)) + (len(matrix))
#     if a >100:

#          new_list.append(a)
# print(new_list)


# qantity = [2,3,4,5]
# prices = [100,200,300,400]
# bill = []
# for i in range(len(qantity)):
#     a = prices[i] * qantity[i]
#     bill.append(a)
#     (sum(bill))+ (len(bill))
# print(bill)


# hour = [2,3,4,5,6]
# pay = [10,20,30,40,50]
# salary = []
# for i in range(len(hour)):
#     a = hour[i] * pay[i]
#     salary.append(a)
# print(salary)



# matrix = [[1,2,3,4,5], [8,7,6,5,4]]
# for i in matrix:
#     for a in i:
#         print(a)
        
        
# matrix = [[1,2,3,], [6,5,4]]
# eee = []
# for i in matrix:
#     for a in i:
#         s = a * 100
#         eee.append(s)
# print(a)

# mat = [[1, 2], [3, 4]]
# li = 5
# for i in mat:
#     for a in i:
#         if a >li:
#             print(a,'found num')

# m1 = [[1, 2], [3, 4]]
# m2 = [[10, 20], [30, 40]]
# res = []
# for i in range(len(m1)):
#     for a in range(len(m1[i])):
#         a = m1[i][a] + m2[i][a] 
#         res.append(a)
# print(res)


# mmm = [1, 0, 1, 1, 0, 0, 1, 0, 1, 1]
# count = 0
# prob = []
# for i in mmm:
#     if i == 1:
#         count = count +1
#         prob = count / len(mmm)
# print(prob)


# data = [1, 0, 5, 1, 0, 9, 1]
# eee = []
# for i in data:
#     if i ==0 :
#         eee.append(i)
# print(eee)

# age = [20, 21, 22, 150, 23]
# for i in age:
#     if i <100:
#         print(i)
#     else:
#         print(i,"outlier num")

# for i in range(1,3):
#     for a in range(1,i+1):
#         print("*",end=" ")
#     print()

# for i in range(3,0,-1):
#     for a in range(i):
#         print("*", end=" ")
#     print()

# for i in range(1,4):
#     for space in range(3 - 1):
#         print(" ", end="")
#     for star in range(i):
#         print("* ", end="")
#     print()

# for i in range(1,4):
#     for a in range(1,i+1):
#         print(a,end="")
#     print()

# for i in range(3,0,-1):
#     for a in range(i):
#         print("*",end="")
#     print()
    
# for i in range(1,4):
#     for a in range(4 +1):
#         print ("", end = " ")
#     for b in range(i):
#         print ("* ", end="")
#     print()




# for i in range(1,6):
#     for a in range(1,5):
#         print("*",end=" ")
#     print()


# a = 6
# for i in range(1,6):
#     for n in range(1,i+1):
#         print("*",end =" ")
#     print()
    

# rows = 4
# for i in range(1,rows+1):
#     for s in range(rows-i):
#         print(" ",end="")
#     for d in range(i):
#         print("* ",end ="")
#     print()
        
        
        
# for i in range(1,5):
#     print("*")
# print()

# for i in range(3):
#     for a in range(2):
#         print("*",end =" ")
#     print()


# for row in range(2):
#     for star in range(2):
#         print("*",end="")
#     print()




# for i in range(5):
#     for a in range(i+1):
#         print("8",end="")
    
#     print()


# for i in range(1,11):
#     print(i)

# for i in range(1,21):
#     if i%2!=0:
#         print(i)


# for i in range(1,51):
#     if i%3!=0 and i%5!=0:
#         print(i)


# n = 4
# for i in range(n):
#     for  j in range(i):
#         print(i, end=" ")
#     print()

# size = 3
# for i in range(size):
#     for j in range(size):
#         if i== j:
#             print(1,end=" ")
#         else:
#             print(0,end =" ")
#     print()



# A = str(input("Enter num"))
# if A == "1234":
#     print("Login Successfully")
# else:
#     print("faild")


# num = int(input("Enter num"))
# if num >0:
#     print("Positive")
# else:
#     print("Negetive")

# a = int(input("Enter num"))
# if a >90:
#     print("Grade A")
# elif a >75:
#     print("Grade B")
# elif a >50:
#     print("Grade c")
# else:
#     print("Fail")

# # for i in range(1,6):
# #     print(i)
    
# # for i in range(1,11):
# #     print(i)


# a = "PYTHON"
# for i in a:
# #     print(i)

# for i in range(1,20):
#     i = i +1
#     print(i)

# for i in range(0,21):
#     i = i + i
#     print(i)


# n = 11
# for i in range(n, 0, -1):
#     print(i)

# t = 8
# for i in range(1,t+1):
#     for a in range(i):
#         print(i, end=" ")
#     print()


# l = 5
# for i in range(l,0,-1):
#     for a in range(l,i+1):
#         print(a,end = "")
#     print()

# num = 1
# row = 5
# for i in range(1,row+1,1):
#     for a in range(i):
#         print(a,end=" ")
#     print()

# num = 0 
# row = 3
# for i in range(0,row+1,1):
#     for a in range(i):
#         print(a ,end =" ")
#     print()

# num = 5
# n = 0
# for i in range(num,0,-1):
#     for a in range(i):
#         print(a,end=" ")
#     print()


# n = 3
# for i in range(1,n+1):
#     for a in range(i):
#         print(i,end=" ")
#     print()

# b = 1
# row = 6
# for i in range(1, row+1):
#     for a in range(i):
#         print(b,end=" ")
#         b+=1
#     print()
    

# a = 1
# s = 4
# for i in range(1, s+1):
#     for h in range(s - i + 1):
#         print(a,end =" ")
#         a+=1
#     print()


# rows = 4
# for i in range(1,rows+1):
#     for a in range(1,i+1):
#         print(a,end=" ")
#     print()

# rows = 4
# for i in range(1,rows+1):
#     for a in range(1,rows-i+2):
#         print(a,end=" ")
#     print()

# num = 1
# rows = 4
# for i in range(1,rows+1):
#     for a in range(rows-i+1+1):
#         print(num,end=" ")
#         num+=1
#     print()


# for i in range(10,1,-1):
#     print(i,"Liftoff!")



# a = 6
# for i in range(1,6):
#     for f in range(i):
#         print("*",end="")
#     print()


# l = 5
# for i in range(1,5):
#     for k in range(i):
#         print("*",end="")
#     print()

# l = 5
# for i in range(5,0,-1):
#     for a in range(i):
#         print("*",end="")
#     print()


# for i in range(1,5):
#     for k in range(1,i+1):
#         print(k,end="")
#     print()
    

# for i in range(1,5):
#     for k in range(i):
#         print(i,end ="")
#     print()



# for i in range(1,6):
#     for o in range(i,10):
#         print(o,end="")
#     print()

# for i in range(5,0,-1):
#     for k in range(i):
#         print(i,end="")
#     print()

# for i in range(1,5):
#     for k in range(5 - i):
#         print("*",end="")
#     print()

# for i in range(1,4):
#     for k in range(1,4):
#         print("*",end="")
#     print()


# for i in range(1,4):
#     for k in range(1,6):
#         print("*",end="")
#     print()

#

# # Increasing part
# for i in range(1, 4):
#     for k in range(1, i+1):
#         print("*", end="")
#     print()

# # Decreasing part
# for i in range(2, 0, -1):
#     for k in range(1, i+1):
#         print("*", end="")
#     print()


# for i in range(1,4):
#     for k in range(1,i+1):
#         print(i,end="")
#     print()

# for i in range(2,0,-1):
#     for k in range(1,i+1):
#         print(i,end="")
#     print()


# for i in range(1,4):
#     for k in range(1,i+1):
#         print(i,end="")
#     print()

# for i in range(2,0,-1):
#     for k in range(1,i+1):
#         print(i,end="")
#     print()
    
    
# # Upper part
# for i in range(1,4):
#     for l in range(1,i+1):
#         print(l, end="")
#     print()

# # Lower part
# for i in range(2,0,-1):
#     for l in range(1,i+1):
#         print(l, end="")   # ✅ inner loop correct
#     print()               # ✅ parentheses laga do


# for i in range(1,5):
#     for k in range(i):
#         print(i,end="")
#         i+=1
#     print()

# for i in range(1,6):
    
#     for k in range(1,i+1):
#         print("*",end="")
#         i+=1
        
#     print()


# for i in range(1,6):
#     if i % 2 != 0:  # Odd row → stars
#         for k in range(i):
#             print("*", end="")
#     else:           # Even row → numbers
#         for k in range(1, i+1):
#             print(k, end="")
#     print()

# m = 1
# for i in range(1,5):
#     for l in range(1,i+1):
#         print(m,end=" ")
#         m+=1
#     print()


# for i in range(1,5):
#     for k in range(1,i+1):
#         print(i,end=" ")
#         i+=1
#     print()


# s = 1
# for i in range(1,6):
#     for k in range(i):
#         print(s,end=" ")
#         s+=1
#     print()


# for i in range(5,0,-1):
#     for k in range(i,6):
#         print(k,end=" ")
        
#     print()


# for i in range(1,6):
#     for k in range(1,i+1):
#         print(k,end=" ")
#     print()
    
# for i in range(4,0,-1):
#     for k in range(1,i+1):
#         print(k,end=" ")
#     print()



# for i in range(1,6):
#     if i % 2 != 0:  # Odd row → stars
#         for k in range(i):
#             print("*", end="")
#     else:           # Even row → numbers
#         for k in range(1, i+1):
#             print(k, end="")
#     print()


# for i in range(1,6):
#     for k in range(1,i+1):
#         print("*",end="")
   
#     print()
    
    
# for i  in range(1,6):
#     for k in range(1,i+1):
#         print(i,end="")
#     print()

    
# for i  in range(5,0,-1):
#     for k in range(1,i+1):
#         print(i,end="")
#     print()


# a = 1
# for i in range(1,5):
#     for k in range(1,i+1):
#         print(a,end="")
#         a+=1
#     print()



# print(not(False))


# a = "23.23"
# v = float(a)
# t = type(v)
# print(t)

# a = input("Enetre num")
# b = input("Enetre num")
# print("sum is ",a+b)

# a = 45
# b = 4
# print("remainder",a%b)



# f = "Abhishek"
# name = f[0:5]
# print(name)


# g = "sdfsdfghjklghjkl"
# a = g[1:7:3]
# print(a)

# h = "ABHISHEK MALVIY"
# s = h[-1:-8:-4]
# print(s)

# A = "ABHISHEK"
# print(A.capitalize())


# a ="Abhishek is correct"
# s = a.replace("correct","bad")
# print(s)


# c = "hy my name is abhishek\nmy college name \"is\" oui"
# print(c)

# a = input("name")
# print(f"moring",{a})




# n = "my name is abhishek"
# print(n.replace("  "," "))

# name = "Hello my name Abhishek\n\t and my college name is OUI\n and i m from indore"
# print(name)

# l = """abhishek, abhi, shek"""
# print(l.replace("abhishek", "Abhishek").replace("abhi","ABHI").replace("shek","SHEK"))


# nem = ["aaole","sdfg",3,45,23.5,"nnnnnnnn"]
# print(nem[0:5:3])


# li = ["sdfgh","sdfghj","sdfghj"]
# li.append("aaaaaaaa")
# print(li)


# a = [1,52,45,76,2,7,4]
# a.sort()
# a.insert(4,33)
# print(a)



# a = [1,52,45,76,2,7,4]
# # a.sort()
# # a.insert(4,33)
# # a.pop(0)
# print(a.pop(6))
# print(a)


# a = (1,"abhise",45,56,3,5,5,5)
# # s = a.count(3)
# # # print(type(a))
# # # s = a.index(3)
# # print(s)
# print(len(a))


# num = [1,1]
# print(sum(num))


# marks = {
#     "abhi": 45,
#     "suny": 34,
#     "budy": 67,
#     0: "abhishek"
# }

# print(marks,type(marks))
# print(marks["suny"])
# print(marks.items())
# print(marks.keys())
# print(marks.values())
# marks.update({"suny":33,"ssss":99})
# print(marks)
# print(marks.get("abhii"))



# s = {2,3,4,5,6,7}
# # print(s,type(s))
# # s.add(65478)
# print(s,type(s))

# s = {2,3,4,5,6,7}
# print(len(s))


# s = {2,3,4,5,6,7}
# print(len(s))

# s = {2,3,4,5,6,7}
# s1 = {3,4,5,7,65}
# # print(s.union(s))
# print(s.intersection(s1))


# a = {
#     "sona": "gold",
#     "chandi":"silver"
    
# }
# a1 = input("Enter words")
# print(a[a1])


# a = set()
# s = input("Enter num 1-")
# a.add(int(s))
# s = input("Enter num 1-")
# a.add(int(s))
# s = input("Enter num 1-")
# a.add(int(s))
# s = input("Enter num 1-")
# a.add(int(s))
# s = input("Enter num 1-")
# a.add(int(s))
# s = input("Enter num 1-")
# a.add(int(s))
# s = input("Enter num 1-")
# a.add(int(s))
# print(a)

# a = set()
# a.add(118)
# a.add("188")
# print(a,)


# i = 1
# while(i<6):
#     print(i,"harry")
#     i+=1

# s = ["fghj","aaaaaa","dddddd","jjjjj",12]
# i = 0
# while(i<len(s)):
#     print(s[i])
#     i+=1


# data = ["apple", 10, "banana", 25, "grapes", 40]
# i = 0
# while(i<len(data)):
#     if type(data[i]) == int:
#         print(data[i])
#     i+=1


# items = ["pen", "notebook", "eraser", "marker", "book", "highlighter"]
# i = 0
# while(i<len(items)):
#     if type(items[i]) == str and len(items[i]) > 5:
#         print(items[i])
#     i+=1


# nums = [12, 7, 9, 20, 33, 40, 55, 60]
# i = 0
# while(i<len(nums)):
#     if nums[i]%2==0:
#         print(nums[i])
#     i+=1


# data = [5, 12, 18, 22, 30, 7, 40, 15]
# i = 0
# while(i<len(data)):
#     if data[i] %2==0 and data[i]>20:
#         print(data[i])
#     i+=1

# nums = [10, 45, 23, 89, 34, 67]
# i = 0
# max_num = nums[0]
# while(i<len(nums)):
#     if nums[i] > max_num:
#         max_num = nums[i]
#         print(nums[i])
#     i+=1
# print(max_num)

# nums = [7,10, 45, 23, 89, 34, 67]
# i = 0
# min_num = nums[0]
# while(i<len(nums)):
#     if nums[i] < min_num:
#         print(nums[i])
#     i+=1
# print(min_num)


# nums = [10, 20, 30, 40]
# i = 0
# total = 0
# while(i<len(nums)):
#     total += nums[i]
#     i+=1
# print(total)


# nums = [10, 20, 30, 40]
# i = 0
# total = 0
# while(i<len(nums)):
#     total+=nums[i]
#     i+=1
# Average = total / i
# print(Average)


# h = [34,56,89]
# h = (2,3,4,5,6)
# h = {12,34,5,76}
# for i in h:
#     print(i)


# a = [21,34,45,6,76,7889,8989]
# for i in a:
#     print(i)
# else:
#     print("done")

# data = ["apple", 10, "banana", 25]
# for x in data:
#     if type(x) == str:
#         print(x)


# data = ["apple", 10, "banana", 25]
# for x in data:
#     if type(x) == int:
#         print(x)



# nums = [12, 7, 9, 20, 33, 40, 55, 60]
# for i in nums:
#     if  i%2==0:
#         print(i)
        

# nums = [12, 7, 9, 20, 33, 40, 55, 60]
# for i in nums:
#     if  i%2!=0:
#         print(i)

# nums = [12, 7, 9, 20, 33, 40, 55, 60]
# for i in nums:
#     if i >20:
#         print(i)



# nums = [12, 7, 9, 20, 33, 40, 55, 60]
# for i in nums:
#     if i%5==0:
#         print(i)


# nums = [12, 7, 9, 20, 33, 40, 55, 60]
# for i in nums:
#     if i %5==0 and i>30:
#         print(i)
        
        
# nums = [12, 7, 9, 20, 33, 40, 55, 60]
# for i in nums:
#     if i%3==0 or i%5==0:
#         print(i)



# nums = [12, 7, 9, 20, 33, 40, 55, 60]
# for i in nums:
#     if i%3==0 and i%5==0:
#         print(i)


# for i in range(1,11):
#     if i ==6:
#         break
#     print(i)
    

# for i in range(1,11):
#     if i ==6:
#         continue
#     print(i)


# for i in range(1,11):
#     if i ==6:
#         pass
#     print(i)

# n = int(input("Enter numbre"))
# for i in range(1,11):
#     print(f"{n*i}")
    

# n = int(input("Enter numbre"))
# for i in range(1,11):
#     print(f"{n*i}")
    
    

# n = int(input("Enter numbre"))
# for i in range(1,11):
#     print(f"{n*i}")
    
    
# n = int(input("Enter numbre"))
# while (n,11):
#     print(f"{n*i}")


# n = int(input("Enter num:- "))
# for i in range(1,11):
#     print(f"{n*i}")

# n = ["sdfghj","dfghj","fghj","hjkl"]
# for i in n:
#     if (i.startswith("h")):
#         print(f"hello{i}")


# n = int(input("Enter numbre"))
# for  i in range(2,n):
#     if (n%i)==0:
#         print("prime")
#         break
 
    
# n  = int(input("Enter num"))
# i = 0
# sum = 0
# while(i<=n):
#     sum+=i
#     i+=1
# print(sum)

 
# n  = int(input("Enter num"))
# i = 1
# for s in range(1,n+1):
#     i*=s
# print(f"fact{i}")


# n  = int(input("Enter num"))
# for i in range(1,n+1):
#     print(" "* (n-i),end="")
#     print("*"* (2*i-1),end="")
#     print("")


# n  = int(input("Enter num"))
# for i in range(1,n+1):
#     print(" "* (n-i),end="")
#     print("*"* (2*i-1),end="")
#     print("")

# row = 4
# for i in range(row,0,-1):
#     for k in range(i):
#         print("*",end="")
#     print()

# rows = 4
# for i in range(rows,0,-1):
#     for j in range(1,i+1):
#         print(j,end="")
#     print()


# rows =4
# for i in range(1,rows+1):
#     for j in range(i):
#         print(i,end="")
#     print()

# rows = 4
# for i in range(1,rows+1):
#     for j in range(1,i+1):
#         print(j,end="")
#     print()

# rows = 4
# for i in range(rows,0,-1):
#     for j in range(1,i+1):
#         print(i,end="")
#     print()

# rows = 4
# for i in range(rows,0,-1):
#     for j in range(1,i+1):
#         print(j,end="")
#     print()

# rows = 5
# for i in range(1,rows+1):
#     for j in range(rows - i):
#         print(" ", end="")
#     for k in range(i):
#         print("*",end="")
#     print()

# rows = 5
# for i in range(rows,0,-1):
#     for j in range(rows+1):
#         print("",end="")
#     for k in range(i):
#         print("*",end="")
#     print()


# rows = 5
# for i in range(rows,0,-1):
#     for j in range(i):
#         print("*",end="")
#     print()


# rows = 5
# for i in range(1,rows+1):
#     for j in range(rows-i):
#         print(" ",end="")
        
#     for k in range(i):
#         print("*",end="")
#     print()

# rows =5
# for i in range(rows,0,-1):
#     for j in range(rows-i):
#         print(" ",end="")
#     for k in range(i):
#         print("*",end="")
#     print()

# nums = [1, 2, 3, 4, 5, 6]
# for i in nums:
#     if i%2!=0:
#         continue
#     print(i)
        
# data = [
#     [10, 20, 30],
#     [40, 50, 60],
#     [70, 80, 90]
# ]
# for i in data:
#     for j in i:
#         if j%2==0:
#             continue
#         print(j,end=" ")
#     print()


# n = int(input("Enter num"))
# for i in range(10,0,-1):
#     print(f"{n*i}")


# data = [
#     [1, 2, 3],
#     [4, 5, 6],
#     [7, 8, 9]
# ]
# for i in data:
#     for j in i:
#         if j%2==0:
#             continue
#         print(j,end=" ")
#     print()

# data = [
#     [10, 20, 30],
#     [40, 50, 60],
#     [70, 80, 90]
# ]
# for i in data:
#     for j in i:
#         if j==50:
#             break
#         print(j,end=" ")
#     print()


# rows = 5
# for i in range(rows+1):
#     for j in range(i+1):
#         print("*",end="")
#     print()
    
    

# rows = 5
# for i in range(1,rows+1):
#     for j in range(i):
#         print(i,end="")
#     print()

# rows = 5
# for i in range(5):
#     for j in range(i+1):
#         print("8",end="")
#     print()
# for i in range(5):
#         print("*",end="")     
# print()
# for j in range(i-2):
#     print("*",end="")
#     for k in range(i-2):
#         print(" ",end="")
#     print("*")
# for k in range(i):
#     print("*",end="")
# print()


# name = "Abhishek"
# n = name[0:5]
# print(n)

# name = "Abhishek"
# n = name[-3:]
# print(n)

# name = "Abhishek"
# b = name[1:6]
# print(b)

# name = "Abhishek"
# b = name[::-1]
# print(b)

# name = "Abhishek"
# b = name[-1:-8:]


# a = "ABHISHEK"
# n = a[0:6]
# print(n)


# word = "PYTHONISTA"
# sliced = word[2:8:2]
# print(sliced)


# a = "PROGRAMMING"
# s = a[4:9]
# print(s)


# a = "DEVELOPER"
# s = a[1:8]
# print(s)


# a ="PYTHONISTA"
# s = a[8:3:-1]
# print(s)

# a = "ABHISHEK"
# s = a[1:7:2]
# print(s)

# a = "sawalakhiya"
# s = a[-3:]
# print(s)

# s = "James"
# a = s[0:5:2]
# print(a)


# word = "Python"
# a = word[-1:-5:-1]
# print(a)


# a = "ABHISHEK"
# s = a[0:6:4]
# print(s)

# d = "123456789"
# d1 = d[0:9:2]
# print(d1)



# for i in range(0,10):
#     for j in range(0,i+1):
#         print("* ",end="")
#     print()

# r = 5
# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
    
#     print()


# r = 5
# for i in range(5,0,-1):
#     for j in range(i+1):
#         print("*",end=" ")
#     print()


# n = 5
# for i in range(6,0,-1):
#     for j in range(i-1):
#         print("*",end="")
#     print()
    


# r = 4
# for i in range(5):
#     for j in range(i+1):
#         print("*",end=' ')
#     print()


# r = 5
# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()


# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()


# for i in range(6):
#     for j in range(8):
#         print("*",end="")
#     print()

# for i in range(3):
#     for j in range(5):
#         print("*",end="")
#     print()



# for i in range(3):
#     for j in range(i+1):
#         print("*",end="")
#     print()


# for i in range(3):
#     for j in range(3-i):
#         print("*",end="")
#     print()

# for i in range(3):
#     for j in range(5):
#         print("*",end="")
#     print()

# for i in range(1,4):
#     for j in range(1,i+1):
#         print(j,end="")
#     print()

# for i in range(1,4):
#     for j in range(3):
#         print(i,end="")
#     print()

# for i in range(1,5):
#     for j in range(1,i+1):
#         print(i,end="")
#     print()

# for i in range(1,5):
#     for j in range(1,i+1):
#         print(j,end="")
#     print()


# for i in range(4,0,-1):
#     for k in range(5-i):
#         print(i,end="")
#     print()

# for i in range(4):
#     for j in range(i+1):
#         print("*",end=" ")
#     print()


# for i in range(4):
#     for j in range(i+1):
#         print("A",end="")
#     print()

# for i in range(5):
#     for j in range(i+1):
#         print("*",end=" ")
#     print()


# for i in range(6,0,-1):
#     for j in range(i-1):
#         print("*",end=" ")
#     print()

# for i in range(1,5):
#     for j in range(i):
#         print(i,end=" ")
#     print()


# for i in range(1,5):
#     for j in range(1,i+1):
#         print(j,end="")
#     print()

# for i in range(1,5):
#     for j in range(i):
#         print(chr(65+j),end='')
#     print()


# for i in range(4):
#     for j in range(i+1):
#         print(chr(65+i),end="")
#     print()


# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()

# for i in range(5,0,-1):
#     for j in range(i):
#         print("*",end="")
#     print()

# for i in range(1,6):
#     for j in range(1,i+1):
#         print(j,end="")
#     print()


# for i in range(1,6):
#     for j in range(i):
#         print(i,end="")
#     print()


# for i in range(5):
#     for j in range(i+1):
#         print(chr(65+i),end="")
#     print()

# for i in range(5):
#     for j in range(i+1):
#         print(chr(97+i),end="")
#     print()


# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()
    
# for f in range(5,0,-1):
#     for j in range(f+1):
#         print("*",end="")
#     print()


# for i in range(1,5):
#     for j in range(i):
#         print(i,end="")
#         i+=1
#     print()

# for i in range(1,6):
#     for j in range(i):
#         print(chr(65+j),end="")
#     print()


# for i in range(6,0,-1):
#     for j in range(i):
#         print(chr(65+j),end="")
#     print()


# for i in range(1,5):
#     for j in range(4):
#         print(i,end=" ")
#     print()

# for i in range(3):
#     for j in range(1,5):
#         print(j,end="")
#     print()

# for i in range(4):
#     for j in range(3):
#         print(chr(65+i),end=" ")
#     print()

# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()




# for l in range(1):
#     print("*",end="")
#     print()

# for i in range(2,6):
#     for j in range(5-i):
#         print(" ",end="")
#     for k in range(i):
#         print("*",end="")
#     print()


# for i in range(1,5):
#     for j in range(i):
#         print(i,end="")
#         i+=1
#     print()


# ch = 65
# for i in range(1,5):
#     for j in range(i):
#         print(chr(ch),end="")
#         ch+=1
#     print()

# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()
    
# for k in range(6,0,-1):
#     for l in range(k):
#         print("*",end="")
#     print()





# for i in range(1):
#     print("*")



# for l in range(1):
#     print("*",end="")
#     print()

# for i in range(2,6):
#     for j in range(5-i):
#         print(" ",end="")
#     for k in range(i):
#         print("*",end="")
#     print()
    
    
    
    
    
# for m in range(1):
#     print("*",end="")
#     print()
    
# v = 5
# for i in range(5):
#     for j in range(v - i-1):
#         print(" ",end="")
#     for k in range(2*i+2):
#         print("*",end="")
#     print()


# v = [12,3,4,5,7,8,8,8]
# print(len(v))

# v = "Abhishek"
# b = v[8:0:-1]
# print(b)


# n = int(input("Enter num:"))
# count =0
# for i in range(1,n+1):
#     if n%i==0:
  
#         count+=1
# if count==2:
#     print("prime")
# else:
#     print("not")


# for i in range(1,11):
#     print(i)


# for i in range(1,51):
#     if i%2==0:
#         print(i)

# n = int(input("Enter num:"))
# for i in range(1,11):
#     print(n*i)


# for i in range(20,0,-1):
#     print(i)



# n = int(input("Enter num :"))
# for i in range(1,11):
#     print(n*i)


# n = "HELLO"
# print(n[::-1])

# s = [1,2]
# total = 0
# for i in s:
#     total= total + s
# print(total)

# for i in range(1,21):
#     if i %2==0:
#         print(i)

# l = [1,2,3,4]
# total = 0
# for i in l:
#     print(i*i)


# for i in range(4):
#     for j in range(i+1):
#         print("*",end="")
#     print()


# a = 1
# for i in range(1,6):
#     a *=i
#     print(a)
    
# a = 0
# for i in range(1,6):
#     a+=i
#     print(a)


# word = "PYTHON"
# v = ['a','i','o','e','u']
# count =0
# for i in  word:
#     if i in v:
#         count = count + 1
# print(count)


# num = int(input("Enetr num:"))
# if num %2==0:
#     print("Even")
# else:
#     print("Odd")


# name = 25
# print("I am" ,name, "years old")


# variable = 12
# print(f"Hello, {variable}!")



# age = int(input("Enter your age: "))
# if age >18:
#     print("can vote")
# else:
#     print("cannot vote")



# n = int(input("Enter num :"))
# for i in range(1,11):
#     print(n*i)
    
# for i in range(20,0,-1):
#     print(i)

# a = "Abhishek"
# for i in range(5):
#     print(a[i])
  

# a = "Abhishek"
# print(len(a))

# a = "Abhishek sawalakhiya"
# for i in a:
#     print(i)

# for i in range(1,21):
#     if i == 15:

#     print(i)

# n = int(input("Enter num: "))
# for i in range(n):
#     print("AAAA",i)

# n = int(input("Enter num: "))
# for i in range(n,0,-1):
# #     print(i)

# n = int(input("ENtre num"))
# for i in range(1,11):
#     print(n*i)
    
    
# n = int(input("Enter num: "))
# sum = 0
# for i in range(1,n+1):
#     sum+=i
# print(sum)


# n = int(input("Enter num: "))
# sum = 0
# for i in range(1,n+1):
#     sum+=i
# print(sum)



# n = int(input("Enter num: "))
# fact = 1
# for i in range(1,n+1):
#     fact*=i
# print(fact)



# n = int(input("Enter num: "))
# sum = 0
# for i in range(1,n+1):
#     if i%2==0:
#          sum+=i
# print(sum)

# n = int(input("Enter num: "))
# for i in range(1,n+1):
#     if n%i==0:
#         print(i)


# n = int(input("Enter num: "))
# sum = 0
# for i in range(1,n):
#     if n%i==0:
#         sum+=i
# if sum ==n:
#     print("p")
# else:
#     print("n")


# n = int(input("Enter num: "))
# count = 0
# for i in range(1,n+1):
#     if n%i==0:
#         count = count +1
# print(count)


# n = int(input("Enter num: "))
# for i in range(1,n+1):
#     if n%i==0:
#         print(i)


# name =  "Abhishek"
# print(name[::-1])


# l = [1,2,3,4,5,6,7,8,9,10]
# print(l[::-1])

# def abhi():
#     print("this is fun...")
# abhi()

# def aaa(a,b):
#     print(f"result {a+b}")
# aaa(1,1)
# aaa(2,2)

# def abhi(name,age):
#     print(f"your name {name} and your age {age}")
# abhi(age =20,name="abhishek")

# for i in range(1,11):
#     print(i)
    
# for i in range(2,21):
#     if i %2==0:
#         print(i)

# n = int(input("Enter num: "))
# for i in range(1,11):
#     print(n*i)


# total = 0
# for i in range(1,101):
#     total+=i
    
# print(total)

# count = 0
# for i in range(1,51):
#     if i%3==0:
#         count+=1
# print(count)

# v = [1,2,3,4,5,6,7,8,9]
# print(v[::-1])




# v = [1,2,3,4,5,6,7,8,9]
# b = []
# for i in v:
#     b.insert(0,i)
# print(b)



# n = int(input("Enter num:"))
# for i in range(1,11):
#     print(n*i)


# n = int(input(" Enter num:"))
# weight =75.5
# height = 1.75
# bmi = weight / (height ** 2)
# is_overweight = bmi > 25
# print(f"Your BMI is {bmi:.2f} and overweight: {is_overweight}")


# amount = int(input("Enter amount : "))
# discount = 0
# if amount>500:
#     discount = amount *0.1
# final_bill = amount - discount
# print(f"Final bill after discount: {final_bill}")

# prices = [100, 250, 50, 400, 150]
# total = 0
# for i in range(len(prices)):
#     total += prices[i]
# #     print(total)

# daily_sales = [150, 220, 180, 300, 90, 250, 400]
# high_sales_count = 0
# high_sales_total = 0
# for i in range(len(daily_sales)):
#     if daily_sales [i]>200:
#         high_sales_count+=1
#         high_sales_total+=daily_sales[i]
#         print(f"High sales day: {daily_sales[i]}")
#     else:
#         print(f"Low sales day: {daily_sales[i]}")

# marks = [85, 42, 90, 31, 55]
# total = 0
# avg = 0
# for i in range(len(marks)):
#     if marks[i]>40:
#         total+=marks[i]
#         print(f"Passed: {marks[i]}")
#     else:
#         print(f"Failed: {marks[i]}")



# def calculate_mean(data_list):
#     total = 0
#     for i in range(len(data_list)):
#         total += data_list[i]
#     mean = total / len(data_list)
        
#     print(f"Mean: {mean}")
        
# calculate_mean([1,2,3,4,5])
# calculate_mean([5,4,3,2,1])


# test_scores = [88, 92, 5, 75, 3, 98, 45, 12, 8]
# def find_outliers(scores):
#     outliers = []
#     for i  in range(len(scores)):
#         if scores[i]<10:
#             outliers.append(scores[i])
#             print(f"outlier found: {scores[i]}")
            
                
# find_outliers(test_scores)


# inventory = {
# #     "Laptop": {"price": 50000, "stock": 5},
# #     "Mouse": {"price": 500, "stock": 0},
# #     "Keyboard": {"price": 1200, "stock": 3}
# # }
# # for i in range(len(inventory)):
# #     if i ==0:
# #         print(f"Out of stock:")
# #     elif i>0:
# #         print(f" In stock")

# # def math_ops(a, b):
# #     sum = 0
# #     difference = 0
# #     product = 0
# #     sum = a + b
# #     difference = a - b
# #     product = a * b
# #     print(f"Sum: {sum}, Difference: {difference}, Product: {product}")
# # math_ops(10, 5)
    


# # expenses = [1200, 450, 3000, 800, 150, 2200, 600, 25000]
# # def analyze_expenses(expense_list):
# #     for i in range(len(expense_list)):
# #         if expense_list[i]>1000:
# #             avg = sum(expense_list) / len(expense_list)
# #             print(avg)
            
# # analyze_expenses(expenses)


# library = {
#     "101": {"title": "Python Basics", "status": "Available"},
#     "102": {"title": "Data Science 101", "status": "Available"},
#     "103": {"title": "Statistics", "status": "Borrowed"}
# }
# if "101" in library:
#     print(f"Book 101: {library['101']['title']} - {library['101']['status']}")
# elif "102" in library:
#     print(f"Book 102: {library['102']['title']} - {library['102']['status']}")
# else:
#     print("Book not found in library:")


# vehicle_rates = int(input(" vehical rates Car: 50, Truck: 150, aur Bus: 100:"))
# def vehicle_type(rates):
#     is_vip=False
#     if rates == is_vip:
#         print(0)
#     elif rates == 50:
#         print(0)
#     elif rates == 150:
#         print(100)
#     elif rates == 100:
#         print(200)
# vehicle_type(vehicle_rates)


# age = int(input("Enter your age: "))
# if age >= 18:
#     print("You can Vote!")
# elif age<0:
#     print("Invalid Age!")
# else:
#     print(f"Too young to vote. Wait for {18 - age} years.")


# degree = input("Enter your degree: ")
# if degree == "yss":
#     experience = int(input("Enter your "))
#     if degree == "yss" and experience>2:
#         print("You can apply for job")
#     elif experience <= 2:
#         print("Selected for Junior Role.")
#     else:
#         print("Not Eligible.")
        


# marks = int(input("Enter marks:"))
# if marks>90:
#     print("A")
# elif marks>70 and marks<=90:
#     print("B")
# elif marks>40 and marks<=70:
#     print("C")
# else:
#     print("F")

# a = [1,2,3,4,5]
# a.append(6)
# print(a)


# a =  [1,3,4,5]
# a.insert(1,2)
# print(a)


# items = ["Milk", "Bread", "Eggs", "Butter"]
# items.append("Cheese")
# print(items)


# items = ["Milk", "Bread", "Eggs", "Butter"]
# items.remove("Milk")
# print(items)


# sales = [1200, 1500, 1100, 1300, 1400, 2500, 3000]
# print(sales[5:] [-2:])
# print(sales[1:5])
# print(sales[::-1])


# raw_prices = [100, 200, 300, 400, 500]
# final_prices = []
# for price in raw_prices:
#     dicounted_price = price * 0.9
#     final_prices.append(dicounted_price)
#     print(final_prices)
    
    
    
# raw_prices = [100, 200, 300, 400, 500]
# final_prices = [price * 1.1 for price in raw_prices]
# print(final_prices)

# numbers = [1, 2, 3, 4, 5]
# doubled = [n * 2 for n in numbers]
# # print(doubled)

# results = {"Rahul": 85, "Sara": 92, "Amit": 78}
# name = input("Enter Student Name: ")
# if name in results:
#     print(f"{name} scored {results[name]} marks:")
# else:
#     print("Student not found")

# fruits = ["Apple", "Apple", "Banana", "Apple", "Banana" , "Apple"]
# count =0
# for i in fruits:
#     if i == "Apple":
#         count+=1
#         print(count)

# fruits = ["Apple", "Banana", "Orange", "Grapes"]
# for i in fruits:
#     if i =="Banana":
#         print("Banana mil gaya!")

# numbers = [1, 2, 3, 4, 5, 6]
# for i in numbers:
#     if i%2==0:
#         print(i)
        
        
# sales = [2000, 3500, 1500, 4000, 2500]
# def analyze_sales(data):
#     avg = sum(data) / len(data)
#     if avg >3000:
#         print(f"Target Achieved! 🚀 {avg}")
#     else:
#         print(f"Need more sales. 📉 {avg}")
        
        
# analyze_sales(sales)

# a = (1,2,3,4,5,6,7,7)
# print(a[2])

# days = ("Monday", "Tuesday", "Wednesday")
# print(days[1])

# student = ("Rahul", 21, "Data Science")
# print(f"Student Age: {student[1]}")


# data = [10, -5, 20, -3, 0, 15]
# for i in data:
#     if i>0:
#         print(i)

# prices = [100, 200, 300]
# new = []
# for i in prices:
#     i*=i
#     new.append(i)
# print(new)


# numbers = [45, 89, 23, 102, 67]
# def filter_num(nums):
#     filtered =[]
    
    

# sales = [1200, 4500, 800, 3200, 5000, 2100]
# high_sales = []
# for i in sales:
#     if i > 3000:
#         high_sales.append(i)
#         print(i)
        
# marks = [85, 90, 78, 92, 88]
# sum = 0
# total = 0
# for i in marks:
#     sum+=i
# avg = sum/ len(marks)
# print(avg)


# items = ["Apple", "Banana", "Apple", "Orange", "Apple", "Banana"]
# count = 0
# for i in items:
#     if i =="Apple":
#         count+=1
# print(count)



# fruites  = {"Apple": 3, "Banana": 2, "Orange": 1}
# counts = {}
# if "Apple" in fruites:
#     counts+=1
#     print(counts)
# else:
#     counts["Apple"] = 1
#     print(counts)


# cloud_users = ["AWS", "Azure", "AWS", "AWS", "Azure", "GCP"]
# def calc_probability(data, target):
#     total = 0
#     for i in data:
#         if i == target:
#             total+=1
#             probability = total / len(data)
#         print(total)
   
   
# data = [10, 15, 12, 500, 14, 600]
# new_list = []
# for i in data:
#     if i <100:
#         new_list.append(i)
# print(new_list)


# num = [1,2,3,5,6]
# num.append(6)
# print(num)


# num = [1,2,3,5,]
# num.pop(0)
# print(num)

# a = [1,2,3]
# a.extend([10,20,30])
# print(a)


# a = [1,2,3,4,5,6]
# a.append(7)
# print(a)


# listt = [1,2,3,4,5]
# listt = list(map(lambda x: x*3, listt))
# for i in listt:
#     print(i,end=" ")



# listt = [10,20,30]
# listt = list(map(lambda x: x*2, listt))
# for i in listt:
#     print(i,end=" ")


# listt = [1,2,3,4,5,6]
# listt.append(7)
# print(listt)



# listt = [1,2,3,4,5,6]
# print(listt[4])


# listt = [1,2,3,4,5,6]
# print(len(listt))

# listt = [1,2,3,4,5,6]
# listt.insert(7, 7)
# print(listt)




# student = {
#     "id": 101,
#     "name": "Rahul",
#     "marks": 85
# }
# print(student["name"])
# student["grade"] = "A"
# student["marks"] = 90
# del student["id"]
# print(student)

# a = [12,34,56,78,89]
# for i in range(len(a)):
#     print(a[i])
# for i in a:
#     print(i)

# a = [1,2,3,45]
# a.append(8)
# print(a)

# a = [1,2,3,5]
# a.insert(3,4)
# print(a)

# a = [1,2,3,45]
# a.remove(2)
# print(a)

# a = [1,2,3,45,-1,4,-76]
# for i in a:
#     if i >=0:
#         print(i,"positive")
# print("hfvjb")
# for i in a:
#     if i<0:
#         print(i)

# a = [1,2,34,5,6,7,8,9]
# sum =0 
# for i in a:
#     sum+=i
# print(sum/len(a))

# a = [10, 45, 32, 67, 89, 67]
# sum = 0
# for i in a:
#     sum+=i
# print(sum/len(a))


# a = [10, 45, 32, 67, 89, 67]
# count = 0
# for i in a:
#     if i>50:
#         count+=1
# print(count)

# a = [10, 45, 32, 67, 89, 67, 45, 32, 100]
# duplicates = []

# for i in a:
#     if a.count(i) > 1 and i not in duplicates:
#         duplicates.append(i)

# for num in duplicates:
#     print(num)


# a = [10, 45, 32, 67, 89, 67, 45, 32, 100]
# new = []
# for i in a:
#     if i not in new:
#         new.append(i)
# print(new)


# a = [10, 45, 32, 67, 89, 67, 45, 32, 100]
# new = []
# for i in a:
#     if i%2==0:
#         new.append(i)
#         print(new,"largest even number is",max(new))
#     else:
#         print("smallest odd number is",min(new))



# students = [("John", 25), ("Alice", 20), ("Bob", 23)]
# sorted_students = sorted(students, key=lambda x: x[1])
# print(sorted_students)

# multiply = lambda a, b: a * b
# print(multiply(3 , 4))

# odd = lambda x: x %2!=0
# print(odd(5))
# print(odd(4))

# num = lambda a, b, c: a if(a>b and a>c) else (b if(b>a and b>c) else c)
# print(num(10, 20, 15))


# count_vowels = lambda s: sum(1 for ch in s.lower() if ch in "aeiou")
# print(count_vowels("Hello World"))


# num = lambda b: "Even" if b%2==0 else "Odd"
# print(num(5) )
# print (num (6))

# a = {1,2,3,4,5}
# a.clear()
# print(a)

# a = {1,2,3,4}
# b = {4,5,6,7}
# d = a.union(b)
# print(d)

# a = {1,2,3,4}
# b = {4,5,6,7}
# d = a|b
# print(d) 


# A = {1, 2, 3, 4}
# B = {3, 4, 5, 6}
# n = A.union(B)
# print(n)


# A = {1, 2, 3, 4}
# B = {3, 4, 5, 6}
# n = A.intersection(B)
# print(n)


# A = {1, 2, 3, 4}
# B = {3, 4, 5, 6}
# n = A.difference(B)
# print(n)

# numbers = [1, 2, 2, 3, 4, 4, 5]
# unique_numbers = set(numbers)
# {1, 2, 3, 4, 5}
# sorted_numbers = sorted(unique_numbers)
# print(sorted_numbers)


# list1 = [1, 2, 2, 3, 4]
# list2 = [3, 4, 4, 5, 6]
# num = set(list1 and list2)
# {1,2,3,4}
# {5,6}
# new = sorted(num)
# print(num)

# sett = {1,2,3,4,5}
# sett.add(6)
# print(sett)



# sett = {1, 2, 3, 5}
# Q = [2, 4, 6, 1]
# for i in Q:
#     if i in sett:
#         print(f"{i} Yess")
#     else:
#         print(f"{i} No")


# sett = {1,2,3,5,9}
# Q = [3, 5, 7, 0]
# for i in Q:
#     if i in sett:
#         print(f"{i} YES")
#     else:
#         print(f"{i} NO")

# sett = {1, 2, 3, 5, 9}
# Q = [1, 4, 9, 10]
# for i in Q:
#     if i in sett:
#         print(f"{i} YESS")
#     else:
#         print(f"{i} NO")


# sett = {2,5}
# Q = [2, 6, 5, 8]
# for i in Q:
#     if i in sett:
#         print(f"{i} YES")
#     else:
#         print(f"{i} NO")



# sett = {5}
# Q = [1, 3, 5, 7]
# for i in Q:
#     if i in sett:
#         print(f"{i} YES")
#     else:
#         print(f"{i} NO")

# sett = {5}
# Q = [2, 5, 8, 0]
# for i in Q:
#     if i in sett:
#         print(f"{i} YES")
#     else:
#         print(f"{i} NO")

# sett = {5}
# Q = [5, 1, 9, 3]
# for i in Q:
#     if i in sett:
#         print(f"{i} YES")
#     else:
#         print(f"{i} NO")


# sett = {5,5,}
# Q = [0, 2, 5, 7, 10, 5, 3]
# for i in Q:
#     if i in sett:
#         print(f"{i} YES")
#     else:
#         print(f"{i} NO")


# sett = {1, 2, 3, 5, 7, 9, 11, 13, 15}
# Q = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]
# for i in Q:
#     if i in sett:
#         print(f"{i} YES")
#     else:
#         print(f"{i} NO")


# s1 = {1, 2, 3}
# s2 = {2, 3, 4}

# print(s1 | s2)  
# print(s1 & s2)  
# print(s1 - s2)  
# print(s1 ^ s2)  


# n = int(input("Enter Num: "))
# for i in range(1,11):
#     print(n*i)


# s1 = {1,2,3,4}
# s2 = {5,6,7,8}
# print(s1 | s2)

# a = "Python"
# print(a[0:3])


# a = {1,2,3,4}
# b = {4,5,6,7}
# s = a-b
# print(s)


# n = int(input("Enter Num"))
# if n >90:
#     print("Good")
# else:
#     print("Bad")



# r = int(input("Enter num of rows: "))
# for i in range(0 ,r):
#     for j in range(0,r - i -1):
#         print(" ",end="")
#     for k in range(0, i +1):
#         print("* ",end="")
#     print()
    
# for i in range(0,5):
#     for j in range(0,i+1):
#         print("* ",end="")
#     print()

# def ispallindrome(s):
#     return s == s[::-1]
# s = "Abhishek"
# ans = ispallindrome(s)
# if ans:
#     print("Yes")
# else:
#     print("No")

# def sss(func):
#     def wap():
#         fun = func()
#         sun = fun.upper()
#         return sun
#     return wap
# def mess():
#     return 'Thank You'
# msg = mess()
# print(msg)

# a = [1,2,3,4]
# b = [5,6,7,8]
# a.extend(b)
# print(a)



# c = 0
# while c<5:
#     print(c)
#     c+=1


# import math
# n=4.7
# f = math.floor(n)
# print(f)

# def add(x,y):
#     return x+y
# def apply(func,a,b):
#     return func(a,b)
# print(apply(add,5,7))

# a = [1,2,3,3,4,5,6]
# res = [v  ** 2 for v in a]
# print(res)

# def func(*avg):
#     for i in avg:
#         print(i)
# func('Hello', 'Wellcome', 'To', 'Abhishekt')

# l = []
# for i in range(2000,3021):
#     if (i%7==0) and (i%5!=0):
#         l.append(str(i))
# print(','. join(l))


# for i in range(1,5):
#     for j in range(i):
#         print("*",end="")
#     print()
    

# for i in range(0,6):
#     for j in range(i):
#         print("*",end=" ")
#     print()
# for k in range(6,0,-1):
#     for h in range(i):
#         print("*",end=" ")
#     print()

# for i in range(5):
#     for j in range(i ** 2):
#         print("*",end="")
#     print()

# for i in range(7):
#     for j in range(i):
#         print("*",end="")
#     print()
# for i in range(8):
#     print("*",end="")
# for i in range(8,0,-1):
#     for j in range(i):
#         print("*",end="")
#     print()


# list1 = [0,1,2,3,4,5,6,7,8,9,10]
# for i in list1:
#     if i%2==0:
#         print(i,"Evne")
#     else:
#         print(i,"Odd")


# for i in range(1,5):
#     for j in range(i):
#         print("#",end="")
#     print()


# a = {100,200,300,400,500}
# a.update({30:3000})
# print(a)


# a = {10,20,30,40,50}
# print(a)


# a = {1,2,3,4,5}
# a.add(6)
# print(a)

# a = {10,20,30,40}
# for i in a:
#     if i%3==0:
#         print(i)
 
# a =  {1,2,3,4,5,6}
# for i in range(len(a)):
#     print(i)

# s = {10, 20, 30, 40}
# s.add(50)
# s.remove(20)
# print(s)

# a ={5, 10, 15, 20, 25}
# for i in a:
#     if i%5==0:
#         print(i)

# a = {1, 2, 3}
# a.update([4, 5, 6])
# print(a)


# a = {1,2,3,4}
# b = {3,4,5,6}
# a.union(b)
# print(a)


# a = {1,2,3,4}
# b = {3,4,5,6}
# print(a.intersection(b))

# a = {10,20,30,40,50}
# for i in a:
#     if i >25:
#         print(i)

# a = {1,2,3,4,5}
# a.remove(3)
# a.add(10)
# print(a)

# a = {2,4,6,8}
# b = {1,2,3,4}
# a.difference(b)
# print(a.difference(b))

# a = {10,20,30,40}
# if 20 in a:
#         print("Found")
# else:
#         print("Not Found")

# a = {5,10,15,20,25}
# print(len(a))
# a.clear()
# print(a)

# a = {1,2,3,4,5}
# b = {4,5,6,7}
# a.union(b)
# print(a.union(b))
# print(a.intersection(b))

# a = {1:100, 2:200, 3:300}
# a[4] = 400
# print(a)

# a = {1:10, 2:20, 3:30, 4:40}
# for i in a.values():
#     if i >20:
#         print(i)

# a = {1:100, 2:200, 3:300}
# a.remove(2)
# print(a)

# a = {1:100, 2:200, 3:300}
# del a[2]
# print(a)

# a = {1:10, 2:20, 3:30}
# for i in a.values():
#     print(i)

# a = {1:10, 2:20, 3:30}
# for s,d in a.items():
#     print(s,d)

# a = {1:100, 2:200, 3:300}
# a[2] = 500
# print(a)

# a = {1:10, 2:20, 3:30, 4:40}
# for i in a.values():
#     if i >20:
#         print(i)

# a = {1:100, 2:200, 3:300}
# print(len(a))

# a = {1:10, 2:20, 3:30}
# a.clear()
# print(a)

# a = {1:100, 2:200}
# b = {3:300, 4:400}
# a.update(b)
# print(a)

# a=[10, 20, 30, 40, 50]
# for i in a:
#     if i >25:
#         print(i)

# v = [2, 4, 6, 8, 10]
# for i in v:
#     if i%4==0:
#         print(i)
        
        
# a = [5, 10, 15, 20, 25]
# count = 0
# for i in a:
#     count +=1
#     if i >12:
#         print(i)

# v= [3, 6, 9, 12, 15]
# for i in v:
#     if i%3==0 and i%6!=0:
#         print(i)

# v = [10, 15, 20, 25, 30]
# sum = 0
# for i in v:
#     sum+=i
#     print(sum)

# v =[7, 14, 21, 28, 35]
# for i in v:
#     if i%7==0 and i%14!=0:
#         print(i)

# v =[2, 4, 6, 8, 10]
# p = 1
# for i in v:
#     p *=i
#     print(p)

# v =[11, 22, 33, 44, 55]
# for i in v:
#     if i >30:
#         print(i)

# v = [5, 10, 15, 20, 25]
# count = 0
# for i in v:
#     if i %5==0:
#         count+=1
# print(count)

# v = [2, 3, 4, 5, 6]
# for i in v:
#     if i %2==0:
#         print(i,"Even")
#     else:
#         print("Odd")


# a = {100, 200, 300}
# a.update([400,500])
# print(a)

# d = {1: 100, 2: 200}
# s = {300, 400}
# s.update(d)
# print(s)

# a = {10, 20, 30, 40, 50}
# for i in a:
#     if i%10==0:
#         a.remove()
#         print(i)

# a = {10, 20, 30, 40, 50}
# for i in a:
#     if i %10==0:
#         print(i)

# a = {10,20,30,40,50}
# for i in a.copy():
#     if i%10==0:
#         a.remove(i)
# print(a)

# d = {1:10, 2:20, 3:30, 4:40}
# for i in d:
#     if i %20:
#         print(i)


# v = {5, 10, 15, 20, 25}
# count = 0

# for i in v:
#     if i > 12:
#         count += 1

# print(count)


# v = [1, 2, 3, 4, 5, 6]
# for i in v:
#     if i%2==0 and i %3!=0:
#         print(i)
        
# v =  {1,2,3,4,5,6}
# count =0
# for i  in v:
#     if i %2==0:
#         count+=1
# print(count)

# d = {1:2, 2:4, 3:6, 4:8}
# for i in d.values():
#     if i>4:
#         print(i)


# v = [10, 15, 20, 25, 30]
# for i in v:
#     if i%5==0 and i%10==0:
#         print(i)

# v = {2,4,6,8,10}
# sum = 0
# for i in v:
#     sum+=i
# print(sum)

# v = [10, 15, 20, 25, 30, 35]
# new = []
# for i in v:
#     if i%5==0 and i%3==0:
#         new.append(i)
#         print(i)

# v = {5, 10, 15, 20, 25, 30}
# new = []
# for i in v:
#     if i>15:
#         new.append(i)
# print(new)


# d = {1:10, 2:25, 3:30, 4:45}
# largest = 0
# for i in d.values():
#     if i >largest:
#         largest = i
# print(largest )

# v = [3, 6, 9, 12, 15]
# new = []
# for i in v:
   
#         new.append(i*i)
# print(new)

# v = [2, 3, 4, 5, 6, 7]
# new = []
# for i in v:
#     if i %2==0:
#         new.append(i)
# print(new)

# v = [1, 2, 3, 4, 5]
# new =  []
# for i in v:
#     new.append(i)
# print(new)

# v = [10,20,30,40,50]
# print(v[0])

# v = "Abhishek Malviy"
# print(v[0])

# v = [5, 10, 15, 20, 25, 30]
# for i in v:
#     if i %5==0 and i >15:
#         print(i)

# v = [2, 4, 6, 8, 10]
# sum = 0
# for i in v:
#     if i %2==0:
#         sum+=i
# print(sum

# b = [3, 6, 9, 12, 15]
# count = 0
# for i in b:
#     if i %3==0:
#         count+=1
# print(count)

# n = [4, 7, 10, 13, 16]
# for i in n:
#     if i %2!=0:
#         print(i)

# n =[1, 2, 3, 4, 5]
# for i in n:
#         print(i**2)


# b = [5, 10, 15, 20, 25]
# for i in b:
#     if i >12:
#         print(i)
        
# b = [2, 5, 8, 11, 14]
# for i in b:
#     if i %2==0:
#         print(i)
        
# from fastapi import FastAPI, HTTPException
# from pydantic import BaseModel
# from typing import List, Optional

# app = FastAPI(title="Netflix Clone API")


# class Movie(BaseModel):
#     id: int
#     title: str
#     genre: str
#     rating: float
#     is_original: bool = False
#     description: str


# movies_db = [
#     {"id": 1, "title": "Stranger Things", "genre": "Sci-Fi", "rating": 8.7, "is_original": True, "description": "Mysterious disappearances in a small town."},
#     {"id": 2, "title": "Inception", "genre": "Action", "rating": 8.8, "is_original": False, "description": "Dream within a dream."},
#     {"id": 3, "title": "The Crown", "genre": "Drama", "rating": 8.6, "is_original": True, "description": "Story of Queen Elizabeth II."},
#     {"id": 4, "title": "Dark", "genre": "Thriller", "rating": 8.8, "is_original": True, "description": "Time travel mystery in Germany."}
# ]

# # API 

# @app.get("/")
# def home():
#     return {"message": "Welcome to Netflix Clone Backend API"}


# @app.get("/movies", response_model=List[Movie])
# def get_all_movies():
#     return movies_db

# @app.get("/movies/{movie_id}", response_model=Movie)
# def get_movie(movie_id: int):
#     for movie in movies_db:
#         if movie["id"] == movie_id:
#             return movie
#     raise HTTPException(status_code=404, detail="Movie not found")


# @app.get("/search")
# def search_movies(genre: Optional[str] = None):
#     if genre:
#         results = [m for m in movies_db if m["genre"].lower() == genre.lower()]
#         return results
#     return movies_db

# @app.post("/add-movie", response_model=Movie)
# def add_movie(new_movie: Movie):

#     if any(m['id'] == new_movie.id for m in movies_db):
#         raise HTTPException(status_code=400, detail="ID already exists")
    
#     movies_db.append(new_movie.dict())
#     return new_movie


# b = [1,2,3,4,5]
# sum = 0
# for i in b:
#     sum+=i
# print(sum)

# b = [1,2,3,4,5,6,7]
# for i in b:
#     if i % 2 != 0:
#         print(i * i)
        
# num = [1,2,3,4,5,6,7,8,9,10,11,12]
# for i in num:
#     if i >10:
#         break
#     print(i)
    
# v  = [1, 2, 2, 3, 4, 4, 4, 5]
# count = 0
# for i in v:
#     if i == 4:
#         count+=1
# print(count)

# v = [1, 2, 2, 3, 4, 4, 4, 5]
# unique_list = []
# for i in v:
#     if i not in unique_list:
#         unique_list.append(i)
# print(unique_list)

# netflix_movies = [
#     {"title": "Stranger Things", "rating": 8.7},
#     {"title": "The Witcher", "rating": 8.1},
#     {"title": "Dark", "rating": 8.8},
#     {"title": "Money Heist", "rating": 8.3}
# ]

# if netflix_movies >=8.5:
#     print(netflix_movies)

# all_movies = ["Iron Man", "Batman", "Spider-Man", "Inception", "Joker"]
# def search_movie(movie_name):
#     if movie_name in all_movies:
#         print("YESS")
#     else:
#         print("no this not **")
        
# search_movie("Batman")
# # search_movie("Mass")

# my_watchlist = ["Inception", "Dark"]
# new = []
# def add_to_watchlist(movie_name):
#     if movie_name not in my_watchlist:
#         new.append(movie_name)
#         print("Final WAtchlist:", my_watchlist)

# add_to_watchlist("my")


# pwd = int(input("Password dalo: "))
# if pwd == 1234:
#     print("Login Success!")
# else:
#     print("Wrong Password!")

# age = int(input("Apni umar batayein: "))
# if age>18:
#     print("Ticket Price: 200")
# else:
#     print("Ticket Price: 100")

# for i in range(1,51):
#     if i %3==0:
#         print(i,"Fizz")
#     elif i %5==0:
#         print(i,"Buzz")
#     else:
#         print(i,"FizzBuzz")

# pin = int(input("Enter PIN"))
# if pin == 000

# v = [10, 15, 20, 25, 30, 35]
# count = 0
# for i in v:
#     if i %5==0 and i >20:
#         count+=1
# print(count)

# d = {1:12, 2:25, 3:18, 4:30}
# for i in d.values():
#     if i %2==0 and i%3==0:
#         print(i)

# v = [1, 2, 3, 4, 5]
# new=[]
# for i in v:
#     if i%2==0:
#         new.append(i**2)
        
#     else:
#         new.append(i**3)
# print(new)

# n = [10, 20, 30, 40, 50]
# small = n[0]
# for i in n:
#     if i <small:
#         small = i
# print(small)

# b = [2, 4, 6, 7, 9]
# for i in b:
#     if i>5:
#         print(i)

# n = [3, 5, 8, 10, 13]
# for i in n:
#     if i %2==0:
#         print(i)

# d = {1:5, 2:10, 3:15, 4:20}
# for i in d.values():
#     if i >10:
#         print(i)

# v = [10, 20, 30, 40]
# for i in v:
#     if i%10==0:
#         print(i)

# raw_data = [
#     {"name": "Rahul", "age": 25, "city": "Mumbai"},
#     {"name": "Anjali", "age": None, "city": "Delhi"},
#     {"name": "Rahul", "age": 25, "city": "Mumbai"},  
#     {"name": "Sneha", "age": 200, "city": "Indore"},  
#     {"name": None, "age": 28, "city": "Indore"}       
# ]

# cleaned_data = []
# seen_names = set()

# for person in raw_data:

#     if person["name"] in seen_names:
#         continue

#     if person["name"] is None or person["age"] is None:
#         continue
        

#     if person["age"] >= 100:
#         continue

#     cleaned_data.append(person)
#     seen_names.add(person["name"])

# print("Cleaned Data:")
# for p in cleaned_data:
#     print(p)

# raw_students = [
#     {"name": "Aman", "marks": 85},
#     {"name": "Sneha", "marks": -10}, 
#     {"name": "", "marks": 50},      
#     {"name": "Rahul", "marks": 25}, 
#     {"name": "Priya", "marks": 105}, 
#     {"name": "Vikram", "marks": 40}   
# ]


# def clean_student_data(data):
#     clean_list = []
#     for i in data:
#         if i["name"] != "":
#             if 33 <= i["marks"] <= 100:
#              clean_list.append(i)
            

    
#     return clean_list
# final_result = clean_student_data(raw_students)
# print(final_result)


# for i in range(3):
#     for j in range(3):
#         print("*",end="")
#     print()
    
# for i in range(3):
#     for j in range(i+1):
#         print("*",end="")
#     print()

# for i in range(3,0,-1):
#     for j in range(i):
#         print("*",end="")
#     print()

# for i in range(5):
#     for j in range(i):
#         print(i,end="")
#     print()

# for i in range(1,5):
#     for k in range(i):
#         print(i,end="")
#     print()

# num = 1
# for i in range(3):
#     for j in range(3):
#         print(num,end=" ")
#         num+=1
#     print()

# for i in range(3):
#     for j in range(3):
#         if (i+j) %2==0:
#             print("0",end=" ")
#         else:
#             print("1",end=" ")
#     print()

# list_a = ["Aman", "Rahul", "Sneha"]
# list_b = ["Sneha", "Vikram", "Aman"]
# for i in list_a:
#     for j in list_b:
#         if i==j:
#             print(i)

# v1 = [1, 2, 2, 3, 4, 4, 4, 5]
# v2 =[1, 2, 3, 4, 5]
# unique_list = []
# for i in v1:
#     if i not in unique_list:
#         unique_list.append(i)
# print(unique_list)

# age = int(input("Enter Age"))
# if age >18:
#     print("You can Drive")
# else:
#     print("Too Young")

# age = int(input("Enter Age "))
# if age >18:
#     print("You can drive")
# elif age >16 and age <18:
#     print("Only 2 Whiller")
# else:
#     print("Too Young")


# amount = int(input("Enter Amount"))
# if amount >1000:
#     print("20% Discount do.")
# elif amount >500 and amount <1000:
#     print("10% Discount do.")
# else:
#     print("No Discount.")

# user = input("Enter Username: ")
# if user == "Abhishek":
#     pin = int(input("Enter PIN: "))
#     if user == "Abhishek" and pin == 000:
#         print("check_balance : withdraw_money : deposit_money :")
#         bal = int(input(10000))
#         if user == "Abhishek" and pin == 000 and bal <10000:
#             print("Withdraw Successful")
#         else:
#             print("Error")
#     else:
#         print("Wrong PIN")    
# else:
#     print("Invalid User")
    
    
# 1
# print(1,2)
# no = int(input("Enter num: "))
# if no %2==0:
#     print("Even")
# else:
#     print("Odd")
# no = int(input("Enter Year: "))
# if no %4==0:
#     print("Leap")
# else:
#     print("No")
# lis = [1,2,3]
# def largest(c):
#     max=c[0]
#     for i in c:
#         if i>max:
#             max=i
#             print(max)
#     print(max)
# largest(lis)
# num = int(input("Enter Num: "))
# fact = 1
# while (num>0):
#     fact = fact*num
# print(fact)
# x = 0
# y = 1
# print(x)
# print(y)
# for i in range(0,11):
#     print(x+y)
#     sem=x
#     x=y
#     y=sem+y


# print(2/2)
# name = "Python"
# print(name == "python")
# d = {"name": "MCA", "year": 2026}
# print(d.get("age", "Not Found"))



# n = int(input("Enetr Num: "))
# if n  %2==0:
#     print("Even")
# else:
#     print("Odd")


# n = int(input("Enter Num"))
# for i in range(1,11):
#     print(n*i)
    
# s = "data science"
# n = {}
# v = {'d': 1, 'a': 2, 't': 1, 's': 1, 'c': 2, 'i': 1, 'e': 2, 'n': 1}
# for i in s:
#     if not i:
#         n.append(i)
# print(n)


# data = [100,2000,200,3000,400,5000]
# max_val = data[0]
# for num in data:
#     if num > max_val:
#         max_val = num
# print("Sabse bada number hai:", max_val)

# num = int(input("Enter Num"))
# set1 = []
# for i in range(1,1001):
#     set1.append(i)
#     print(set1)

# age = int(input("Enter Age: "))
# print(age *365)

# num = int(input("Enter  num: "))
# total = num * 50
# if num >5:
#     total-=20
# print(total)

# Digit = int(input("Enter Dig...: "))
# date = int(input("Enter Date: "))
# if Digit%2==0 and date %2==0:
#     print("Allowed")
#     if date % 2 != 0:
#         print("Allowed")
# else:
#     print("Not Allowed")
    
# PIN = int(input("Enter PIn...."))
# if PIN == 1234:
#     print("Withdraw amount...")
#     Amount = int(input("Enter Amount"))
#     if Amount <5000:
#         print("Withraw Succesfull.. Thank You")
#     else:
#         print("Insuifficient Funds")
# else:
#     print("Wrong PIN")

# Age = int(input("Enter Age.."))
# day = input("Enter Day")
# if Age <18 and day == "Tuesday":
#     print("Ticket ₹150")
  
#     if Age >18:
#         print("Ticket ₹50")
#     else:
#         print("Ticket ₹250")
# else:
#     print("Ticket ₹250")
    
    
    
# for i in range(1,11):
#     print(i)
# # for i in range(1,21):
# #     if i %2==0:
# #         print(i,"Even")
# n = int(input("Enter Num: "))
# sum = 0
# for i in range(1,n+1):
#     sum+=i
# print(sum)
# n = int(input("Enter Num: "))
# for i in range(1,11):
#     print(n*i)
# fruits = ["apple", "banana", "cherry"]
# for i in fruits:
#     print(i)


# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()

# for i in range(5,0,-1):
#     for j in range(i):
#         print("*",end="")
#     print()

# n = int(input("Enter Num :"))
# fact = 1
# while True:
#     if n>0:
#         fact*=-1
#         print(fact)

# v = "Python"
# print(v[::-1])

# v="Python"
# for i in v:  
#     print(i)

# f= "Abhishek"
# new= ""
# for i in v:
#     new.add("Malviy")
#     print(new)

# for i in range(1,51):
#     if i%3==0:
#         print(i,"Fizz")
#     elif i%5==0:
#         print(i,"Buzz")
#     elif  i%3==0 and i%5==0:
#         print(i,"FizzBuzz")
#     else:
#         print(i)

# for i in range(5):
#     for j in range(i+1):
#         print(j,end=" ")
#     print()

# n = 5
# for i in range(1,n+1):
#     for j in range(n-i):
#         print(" ",end="")
#     for k in range(i):
#         print("*",end=" ")
#     print()

# n = 5
# for i in range(1, n + 1):
#     print(" " * (n - i) + "* " * i)


# for i in range(1,11):
#     print(i)
# for i in range(1,21):
#     if i%2==0:
#         print(i)
# i = 10
# while i>=1:
#     print(i)
#     i-=1

# total = 0
# for i in range(1,11):
#     total+=i
# print(total)

# n = int(input("Enter Num: "))
# for i in range(1,11):
#     print(n*i)

# for i in range(1,51):
#     if i%3==0:
# #         print(i)
# n=int(input("Enter Num: "))
# fact=1
# while n>1:
#     fact*=n
#     n-=1
# print(fact)

# for i in range(1,101):
#     if i %5==0 and i%7==0:
#         print(i)
# for i in range(1,11):
#     print(i,"_>",i*i)
# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()

# l = [10, 20, 30, 40, 50]
# for i in l:
#     print(i)

# l = [5, 10, 15, 20, 25]
# for i in l:
#     if i>10:
#         print(i)

# l = [1, 2, 3, 4, 5]
# total = 0
# for i in l:
#     total+=i
# print(total)

# l = [1,2,3,4,5]
# print(l)

# b = [1, 2, 2, 3, 4, 4, 5]
# new_list = []
# for i in b:
#     new_list = list(set(b))
# print(new_list)
# b =[10, 15, 20, 25, 30, 35]
# set1 = []
# for i in b:
#     if i%2==0:
#         set1.append(i)
# print(set1)
# A = {1, 2, 3, 4, 5}
# B = {4, 5, 6, 7, 8}
# print(A|B)
# A = {1, 2, 3, 4}
# B = {3, 4, 5, 6}

# print(A is B, A.issubset(B), A.issuperset(B))
# v=[1, 2, 3, 2, 4, 5, 1, 6]
# dup=()
# new=[]
# for i in v:
#     new=list(set(v))
#     dup=list(set(v))
# print(new)
# print(dup)


# n =[10, 20, 30, 40, 50]
# print(len(n)==len(set)(n))
# n= [1, 2, 3, 4, 5, 6, 7, 8]
# even=[]
# odd=[]
# for i in n:
#     if i%2==0:
#         even.append(i)
#         print(even)
#     else:
#         print(odd,odd.append)
# v=[1, 2, 2, 3, 4, 4, 4, 5]
# new =[]
# for i in v:
#     new.list(set(v))
#     print(new)
# a={"Rahul", "Sita", "Arjun", "Sneha"}
# b={"Arjun", "Vijay", "Sneha", "Karan"}
# print(a.intersection(b))
# print(a|b)
# print(a.difference(b))
# b =[3, 5, 15, 18, 20, 30, 9]
# new=[]
# for i in b:
#     if (i%3==0 and i%5==0) and not(i%3==0 and i%5==0) :
#         new.append(i)
# print(new)
# v ="python is fun"
# a=v.replace(" ","")
# print(a[::-1])

# for i in range(6):
#     for k in range(i+1):
#         print("#",end="")
#     print()


# import time
# class YouTube:
#     def __init__(self):
       
#         self.videos = []
#         self.subscribers = 0
#     def upload_video(self, title, duration):
#         vid= len(self.videos) + 1
#         video_data = {
#             "id": vid,
#             "title": title,
#             "duration": duration,
#             "views": 0
#         }
#         self.videos.append(video_data)
#         print(f" Video Uploaded: '{title}' (ID: {vid})")
#     def search_video(self, query):
#         print(f"\n Searching for: '{query}'...")
#         results = [v for v in self.videos if query.lower() in v['title'].lower()]
#         if results:
#             for v in results:
#                 print(f" Found: {v['title']} | Views: {v['views']}")
#         else:
#             print(" No videos found.")
#     def play_video(self, video_id):
#         for v in self.videos:
#             if v['id'] == video_id:
#                 v['views'] += 1
#                 print(f"\n Playing: {v['title']}...")
#                 print(f" Views Updated: {v['views']}")
#                 return
#         print(" Error: Video ID not found.")
# my_channel = YouTube()
# my_channel.upload_video("Python Full Course", "2:00:00")
# my_channel.upload_video("MCA Roadmap 2026", "15:30")
# my_channel.upload_video("Machine Learning Basics", "45:00")
# my_channel.search_video("Python")
# my_channel.play_video(1) 
# my_channel.play_video(1) 

# my_channel = YouTube()
# my_channel.upload_video("Python Full Course", "2:00:00")
# my_channel.upload_video("MCA Roadmap 2026", "15:30")
# my_channel.upload_video("Machine Learning Basics", "45:00")
# my_channel.search_video("Python")
# my_channel.play_video(1) 
# my_channel.play_video(1) 
# def play_video(self, video_id):
#         for v in self.videos:
#             if v['id'] == video_id:
#                 v['views'] += 1
#                 print(f"\n Playing: {v['title']}...")
#                 print(f" Views Updated: {v['views']}")
#                 return
#         print(" Error: Video ID not found.")


# for i in range(1,21):
#     if i %2==0 and i>10 :
#         print(i,"Even")

# t =input("Enter: ")
# t=t.lower()
# if t==t[::-1]:
#     print("YSS")
# else:
#     print("NO")

# name = int(input("Abhishek 20 Black"))
# print(name)

# e=int(input("Enter Age"))
# if e>18:
#     print( "Aap Vote de sakte hain!")
# else:
#     print("Aap abhi chote hain, Vote nahi de sakte.")

# n=int(input("Enter num: "))
# for i in range(1,11):
#     print(n*i)

# prod=input("Milk, Bread, Eggs")
# items = []
# for i in prod:
#     items.append(i)
# print(items)

# import random
# secret = random.randint(1, 10)
# guess = int(input("1 se 10 ke beech ek number guess karein: "))
# if guess == secret:
#     print("Wah! Aapne sahi guess kiya! 🎉")
# else:
# #     print(f"Ohho! Galat jawab. Sahi number {secret} tha.")

# P=input("Enter PIN: ")
# if P=="python123":
#     print("Access Granted! Welcome.")
# else:
#     print("Access Denied! Password galat hai.")
    
# def num(a,b):
#     return a * b
# result =num(5, 4)
# print(result)

# num(2,5)

# num=int(input("Enter Num: "))
# if num%2==0:
#     print("Even")
# else:
#     print("Odd")

# secret = "python123"
# password = ""
# while password != "python123":
#     password=input("Enter Password")
# print("Unlock ho gaya!")

# import random
# secret = random.randint(1, 20)
# for i in range(5):
#     guess=int(input("Enter Your choice: "))
#     if guess == secret:
#         print("Jeet gaye!" )
#         break
#     else:
# #         print("Thoda chota number socho!")
# import random
# n=["Rock", "Paper", "Scissors"]
# random.choice(n)
# user=input("Entre Your Choice: ")
# if user == "camp":
#     print("")

# import random
# number = random.randint(1, 100)
# attempts = 0
# print("Maine 1 se 100 ke beech ek number socha hai. Guess karo!")
# while True:
#     guess = int(input("Aapka guess: "))
#     attempts += 1
#     if guess < number:
#         print("Thoda bada number try karo! (Too low)")
#     elif guess > number:
#         print("Thoda chota number try karo! (Too high)")
#     else:
#         print(f"Waah! Aapne {attempts} baar mein sahi guess kar liya!")
#         break

# for i in range(1,11):
#     print(i)

# li=["Rahul","Priya",""]
# for i in li:
#     if i in "Rahul":
#         print("Hello Rahul, welcome to the party!")
#         print("Hello Priya, welcome to the party!")     
#     else:
#         print("None")  

# nam=input("Enter Name: ")
# age=int(input("Enter Age:"))
# print(nam)
# print(age)

# nam=input("Enter Name: ")
# age=int(input("Enter Age:"))
# if age>18:
#     print("Aap vote de sakte hain! 🗳️")
# else:
#     print("Abhi aap chote hain, thoda intezar karein. ")

# from unittest import result
# n = int(input("Kaunsa table chahiye? "))
# for i in range(1,11):
#     result = n * i
#     print(f"{n} x {i} = {result}")

# import random
# secret_number = random.randint(1, 10)
# while True:
#     guess=int(input("Enter your guess: "))
#     if guess==secret_number:
#         print( "Wah! Aapne pehchan liya!")
#         break
#     else:
#         print( "Galat! Phir se koshish karo.")

# import random
# secret_number = random.randint(1, 10)
# while True:
#     guess=int(input("Enter your guess: "))
#     if guess==secret_number:
#         print( "Wah! Aapne pehchan liya!")
#         break
#     else:
#         print( "Galat! Phir se koshish karo.")

# def convert_to_inr(dollars):
#     rupees = dollars * 94
#     return rupees
# amount_in_dollars = float(input("Enter amount in dollars: "))
# amount_in_inr = convert_to_inr(amount_in_dollars)
# print(f"{amount_in_dollars} dollars is equal to {amount_in_inr} rupees.")

# try:
#     num1 = int(input("Pehla number: "))
#     num2 = int(input("Doosra number: "))
#     result = num1 / num2
#     print("Result:", result)
# except ZeroDivisionError:
#     print("Oye! Zero se divide nahi kar sakte.")
# except ValueError:
#     print("Arey! Sirf numbers likho, letters nahi.")

# try:
#     num1 = int(input("Pehla number: "))
#     num2 = int(input("Doosra number: "))
#     result = num1 / num2
#     print("Result:", result)
# except ZeroDivisionError:
#     print("Oye! Zero se divide nahi kar sakte.")
# except ValueError:
#     print("Arey! Sirf numbers likho, letters nahi.")

# numbers = [10, 20, 30, 40, 50]
# total=0
# for i in numbers:
#     total+=i
# print(total)

# for i in range(5):
#     for j in range(i+1):
#         print("%",end="")
#     print()

# b="Abhishek Malviy"
# r=""
# for i in b:
#     r=i+r
# print(r)
# my_list = [12, 45, 7, 89, 23, 56]
# max_value = my_list[0]
# for i in my_list:
#     if i > max_value:
#         max_value = i
# print(max_value)

# vowels = "aeiouAEIOU"
# for i in vowels:
#     if i in "aioueAEIOU":
#         print(i)

# nums = [1, 2, 2, 3, 4, 4, 4, 5]
# unique_nums = []
# for num in nums:
#     if num not in unique_nums:
#         unique_nums.append(num)
# print(unique_nums)

# for i in range(1,51):
#     if i %3==0:
#         print(i,"Fizz")
#     elif i%5==0:
#         print(i,"Buzz")
#     else:
#         print(i,"FizzBuzz")
        
# class Book:
#     def __init__(self, title, author):
#         self.title = title
#         def description(self):
#             b1 = Book("Harry Potter", "J.K. Rowling")
#             print(f"'{self.title}' by {self.author}")

# b1 = Book("Harry Potter", "J.K. Rowling")
# b1.display_info()

# b2 = Book("Atomic Habits", "James Clear")
# b2.display_info()

# class Student:
#     def __init__(self, naam):
#         self.name = naam
#         s1 = Student("Abhishek")
#         print(s1.name)

# arr = [10, 20, 30, 40, 50]
# for i in range(len(arr)):
#     if arr[i] == 40:
#         print("Found at index:", i)
#         break
    
# v= [1, 2, 3, 4]
# result = []
# for i in v:
#     result.append(i)
# print(v[::-1])

# v=[5, 1, 4, 2]
# for i in range(len(v)):
#     for j in range(i+1, len(v)):
#         if v[j] > v[j+1]:
#             v[j], v[j+1] = v[j+1], v[j]
# print(v)

# nums = [10, 20, 4, 45, 99]
# max1 = -1
# max2 = -1
# for  i in nums:
#     if i > max1:
#         max2 = max1
#         max1 = i
#     elif i > max2 and i != max1:
#         max2 = i
# print("First maximum:", max1)
# print("Second maximum:", max2)

# s1 = "listen"
# s2 = "silent"
# sort_s1 = sorted(s1)
# sort_s2 = sorted(s2)
# if sort_s1 == sort_s2:
#     print("The strings are anagrams.")
# else:
#     print("The strings are not anagrams.")

# arr = [1, 0, 2, 0, 3, 4, 0]
# new_list = []
# for i in arr:
#     if i != 0:
#         new_list.append(i)
# print(new_list)

# nums = [15, 42, 8, 91, 23]
# smallest = nums[0]
# for i in nums:
#     if i < smallest:
#         print(i)


# nums = [10, 20, 30, 40]
# total = 0
# for i in nums:
#     total += i
# print(total)

# nums = [10, 5, 20, 15, 30]
# total = 0
# for i in range(len(nums)):
#     if i % 2 == 0:
#         total += nums[i]
# print(total)

# nums = [10, 20, 30, 40, 50]
# target = 30
# found = False
# for i in range(len(nums)):
#     if nums[i] == target:
#         print(found = True)
#         break
# if found==False:
#     print("Nahi mila")
# nums = [1, 2, 3, 4]
# reversed_list = []
# for i in range(len(nums)-1, -1, -1):
#     reversed_list.append(i)
# print(reversed_list)

# nums = [1, 2, 2, 3, 4, 4, 5]
# unique_list = []
# for i in nums:
#     if i not in unique_list:
#         unique_list.append(i)
# print(unique_list)

# for i in range(3):
#     for j in range(3):
#         print("*", end=" ")
#     print()

# for i in range(4):
#     for j in range(i + 1):
#         print("*", end=" ")
#     print()
# n = 5
# fact = 1
# for i in (1,n):
#     fact = fact * i
# print(fact)

# a = 0
# b = 1

# for i in range(5):
#     c = a + b
#     a = b
#     b = c
# print(c)

# s = "level"
# print(s[::-1])

# max_val=[1,2,3,4,5]
# for i in max_val:
#     if i > max_val[0]:
#         max_val[0] = i
# print(max_val[0])

# p="python"
# print(p[::-1])

# arr = [10, 20, 30, 40, 50]
# left = 0
# right = len(arr) - 1
# while True:
#     left < right
#     arr[left] [right]
#     left(+1) 
#     right(-1)
#     print(arr)

# nums = [4, 2, 7, 1, 9]
# x = 7
# for i in nums:
#     if i == x:
#         print(i)
#     else:
#         print("Not Found")

# s = "radar"
# reverse_s = s[::-1]
# if s == reverse_s:
#     print("Palindrome")

# arr = [64, 34, 25, 12, 22]
# n = len(arr)
# for i in range(n):
#     for j in range(n-i-1):
#         if arr[j] > arr[j+1]:
#             arr[j], arr[j+1] = arr[j+1], arr[j]
# print(arr)

# nums = [1, 2, 2, 3, 3, 3, 4]
# counts = {}
# for i in nums:
#     if i in counts:
#         counts[i] +=1
#         print(counts)
#     else:
#         counts[i] = 1
#         print(counts[i])

# list1=[1,3,4,5,6,7]
# my_stack = []
# for i in list1:
#     my_stack.append(i)
#     my_stack.append(i)
#     my_stack.append(i)
#     my_stack.pop(i)
# print(my_stack)

# a="qwertyuiop"
# for i in range(len(a)):
#     print(i)


# for i in range(5):
#     for k in range(i-1):
#         print(" ",end="")
#     for j in range(i+1):
#         print("*",end="")
#     print()

# n=int(input("Enter Num: "))
# for i in range(1,11):
#     print(n*i)

# for i in range(5):
#     for j in range(i+1):
#         print("%",end="")
#     print()
    

# for m in range(5,0,-1):
#     for n in range(i+1):
#         print("%",end="")
#     print()

# a="Abhishek Malviy"
# print(a[::-1])
# a="Abhishek"
# b="Malviy"
# print(a is b)
# l="Abhishek"
# for i in range(len(l)):
#     print(i)
# for i in range(6):
#     for j in range(i+1):
#         print("7",end="")
#     print()
# for i in range(1,21):
#     print(i)

# # pronto...........
# import time
# class pronto:
#     def __init__(self):
#         self.movies = [
#             {"id": 1, "title": "Inception", "genre": "Sci-Fi", "rating": 8.8, "tags": ["dreams", "space", "mind-bending"]},
#             {"id": 2, "title": "The Dark Knight", "genre": "Action", "rating": 9.0, "tags": ["batman", "hero", "dc"]},
#             {"id": 3, "title": "Interstellar", "genre": "Sci-Fi", "rating": 8.6, "tags": ["space", "time", "future"]},
#             {"id": 4, "title": "The Hangover", "genre": "Comedy", "rating": 7.7, "tags": ["friends", "funny", "party"]},
#             {"id": 5, "title": "Extraction", "genre": "Action", "rating": 6.7, "tags": ["bullets", "hero", "thriller"]},
#             {"id": 6, "title": "Stranger Things", "genre": "Sci-Fi", "rating": 8.7, "tags": ["kids", "monsters", "80s"]}
#         ]
#         self.user_watchlist = []
#         self.watch_history = []

#     def show_all_movies(self):
#         print("\n--- Trending on PRONTO ---")
#         for m in self.movies:
#             print(f"[{m['id']}] {m['title']} | {m['genre']} |  {m['rating']}")
#         time.sleep(1)


#     def watch_movie(self, movie_id):

#         selected_movie = next((m for m in self.movies if m["id"] == movie_id), None)
#         if selected_movie:
#             print(f"\nPlaying: {selected_movie['title']}...")
#             time.sleep(2)
#             print("Enjoyed the movie! Adding to your history.")
#             self.watch_history.append(selected_movie)
#         else:
#             print("movie not found!")

#     def recommend_movies(self):

#         if not self.watch_history:
#             print("\nSuggesting Top Rated (No history found):")
#             top_rated = sorted(self.movies, key=lambda x: x['rating'], reverse=True)[:2]
#             for m in top_rated:
#                 print(f"Recommended: {m['title']} (Based on Rating)")
#             return


#         last_genre = self.watch_history[-1]["genre"]
#         print(f"\n--- Because you watched {self.watch_history[-1]['title']} ---")
        
#         for m in self.movies:
#             if m["genre"] == last_genre and m not in self.watch_history:
#                 print(f"Recommended: {m['title']} (Same Genre: {last_genre})")

# app = pronto()

# while True:
#     print("\n" + "="*30)
#     print("      PRONTO PYTHON      ")
#     print("="*30)
#     print("1. Browse Movies")
#     print("2. Watch a Movie")
#     print("3. My Recommendations")
#     print("4. Exit")
    
#     cmd = input("\nChoose an option: ")

#     if cmd == "1":
#         app.show_all_movies()
#     elif cmd == "2":
#         mid = int(input("Enter Movie ID to watch: "))
#         app.watch_movie(mid)
#     elif cmd == "3":
#         app.recommend_movies()
#     elif cmd == "4":
#         print("Goodbye! Happy Binging.")
#         break
#     else:
#         print("Invalid Choice!")
        
# import time
# class PRONTOPro:
#     def __init__(self):
#         self.movies = [
#             {"id": 1, "title": "Inception", "genre": "Sci-Fi", "rating": 8.8},
#             {"id": 2, "title": "The Dark Knight", "genre": "Action", "rating": 9.0},
#             {"id": 3, "title": "Interstellar", "genre": "Sci-Fi", "rating": 8.6},
#             {"id": 4, "title": "Friends", "genre": "Comedy", "rating": 8.9},
#         ]
#         self.users = {
#             "aman@email.com": {"password": "123", "name": "Aman", "plan": "Premium", "history": []},
#             "rahul@email.com": {"password": "456", "name": "Rahul", "plan": "Basic", "history": []}
#         }
#         self.current_user = None
#     def login(self):
#         print("\n--- pronto Login ---")
#         email = input("Email: ")
#         pwd = input("Password: ")
#         if email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#             return True
#         else:
#             print(" Invalid Email or Password!")
#             return False
#     def show_dashboard(self):
#         while self.current_user:
#             print("\n" + "="*30)
#             print(f"   PRONTO HOME - {self.users[self.current_user]['name']}   ")
#             print("="*30)
#             print("1. Browse Movies")
#             print("2. Watch History")
#             print("3. Profile Details")
#             print("4. Logout")
#             choice = input("\nChoose: ")
#             if choice == "1":
#                 self.browse_movies()
#             elif choice == "2":
#                 history = self.users[self.current_user]["history"]
#                 print(f"Your History: {history if history else 'No movies watched yet.'}")
#             elif choice == "3":
#                 u = self.users[self.current_user]
#                 print(f"\nName: {u['name']}\nPlan: {u['plan']}")
#             elif choice == "4":
#                 print("Logging out...")
#                 self.current_user = None
#     def browse_movies(self):
#         print("\nAvailable Movies:")
#         for m in self.movies:
#             print(f"[{m['id']}] {m['title']} ({m['genre']})")
#         mid = input("\nEnter Movie ID to watch (or 'b' to go back): ")
#         if mid.isdigit():
#             movie = next((m for m in self.movies if m["id"] == int(mid)), None)
#             if movie:
#                 print(f"Streaming {movie['title']} in {self.users[self.current_user]['plan']} Quality... 🎬")
#                 self.users[self.current_user]["history"].append(movie['title'])
#                 time.sleep(2)
# PRONTO_app = PRONTOPro()
# while True:
#     print("\n1. Login\n2. Exit")
#     start = input("Choice: ")
#     if start == "1":
#         if PRONTO_app.login():
#             PRONTO_app.show_dashboard()
#     elif start == "2":
#         break
# # while True:
# #     print("\n1. Login\n2. Exit")
# #     start = input("Choice: ")
# #     if start == "1":
# #         if PRONTO_app.login():
# #             PRONTO_app.show_dashboard()
# #     elif start == "2":
# #         break
# for i in range(5):
#     for j in range(i+1):
#         print("&",end="")
#     print()
# n=int(input("Enter Num: "))
# for i in range(1,11):
#     print(n*i)
# v=["Abhishek","malviy","100","Oriental","university","Indore"]
# new=[]
# for i in v:
#     new.append(i)
# print(new)
# for i in range(6):
#     for i in (i+1):
#         print("*",end="")
#     print()
# marks=int(input("Enter marks: "))
# if marks>=90:
#     print("Grade: A")
# elif marks>=75 and marks<89:
#     print("Grade: B")
# elif marks >=50 and marks<74:
#     print("Grade: C")
# else:
#     print("Fail")
# "admin"=input("Enter admin...")
# if "admin"=="admin":
#     print("....Wllcome...")
#     PIN=int(input("Enter PIN..."))
#     if PIN==123:
#         print("Login Successful")
#     else:
#         print("Wrong PIN")
# else:
#     print("Invalid Username")
# user=input("Enter Username: ")
# if user=="Abhishek":
#     print("Wellcome, Abhishek!")
#     PIN=int(input("Enter PIN:"))
#     if PIN==1234:
#         print("10000 ")
#         Balance= 100000
#         Amount=int(input("Enter Amount:"))
#         if user=="Abhishek" and PIN==1234 and Amount<Balance:
#             print("Withraw Successfull"/"Thank You")
#         else:
#             print("Insuffient Funds ")
#     else:
#         print("Wrong PIN")
# else:
#     print("invalid Username")
# Ex= int(input("Enter Experience.. "))
# if Ex>5:
#     print("80,000")
# elif Ex>3 and Ex<=5:
#     print("50,000")
# elif Ex>1 and Ex<=3:
#     print("30,000")
# else:
#     print("10,000")
# atm=input("Enter ATM Card: ")
# if atm == "yes":
#     print("Wllcome to ATM: ")
#     PIN=int(input("Enter PIN: "))
#     if PIN==000:
#         print("Login Successful:")
#         Amount=int(input("Enter Amount:"))
#         if Amount<5000:
#             print("Withraw Successfull"/"Thank You: ")
#         else:
#             print("Insufficient Funds")
#     else:
#         print("Wrong PIN: ")
# else:
#     print("Please insert your ATM Card: ")

# lift=int(input("Enter Floor Num: "))
# if lift==1:
#     print("You are on Ground Floor: ")
    
# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()
# for k in range(5,0,-1):
#     for l in range(k-1):
#         print("*",end="")
#     print()
# n=int(input("entre num: "))
# for i in range(1,11):
#     print(i*n)
# for i in range(1,50):
#     if i == 10 and i==20:
#         print(i,"End...")
#         continue
#     else:

# a = [1,2]
# b = []
# print(a is b)
# for i in range(1,11):
#     if i >30:
#         print("END...")
#         break

# n=int(input("Enter Num:..."))
# for i in range(1,11):
#     if i%3==0:
#         print(i)
# for i in range(1,51):
#     if i%3==0:
#         print(i)
# v=[1,2,3,4,5,6]
# for i in v:
#     if i%3==0:
# #         print(i)
# for i in range(11):
#     for j in range(i+1):
#         print("*",end="")
#     print()
# for k in range(11,0,-1):
#     for l in range(k-1):
#         print("*",end="")
#     print()

# import uuid
# from datetime import datetime
#          #input ka code
# class Flight:
#     def __init__(self, flight_id, source, destination, seats, price):
#         self.flight_id = flight_id
#         self.source = source
#         self.destination = destination
#         self.total_seats = seats
#         self.available_seats = seats
#         self.price = price
       
#        #Passenger ka 
# class Passenger:
#     def __init__(self, name, age):
#         self.name = name
#         self.age = age

#          #Booking ka
# class Booking:
#     def __init__(self, flight, passengers):
#         self.booking_id = str(uuid.uuid4())[:8]
#         self.flight = flight
#         self.passengers = passengers
#         self.time = datetime.now()

#       #FlightSystem ka
# class FlightSystem:
#     def __init__(self):
#         self.flights = []
#         self.bookings = {}

#          # flight append ka
#     def add_flight(self, flight):
#         self.flights.append(flight)

#         # flight search ka 
#     def search_flights(self, source, destination):
#         results = []
#         for f in self.flights:
#             if f.source == source and f.destination == destination:
#                 results.append(f)
#         return results

#           #flight show ka
#     def show_flights(self, flights):
#         for f in flights:
#             print(f"\nFlight ID: {f.flight_id}")
#             print(f"{f.source} -> {f.destination}")
#             print(f"Seats Available: {f.available_seats}")
#             print(f"Price: {f.price}")

#          # ticket booking ka 
#     def book_ticket(self, flight_id, passengers):
#         for f in self.flights:
#             if f.flight_id == flight_id:
#                 if f.available_seats >= len(passengers):
#                     f.available_seats -= len(passengers)
#                     booking = Booking(f, passengers)
#                     self.bookings[booking.booking_id] = booking
#                     print(f"\nBooking Successful! ID: {booking.booking_id}")
#                     return
#                 else:
#                     print("Not Enough Seats!")
#                     return
#         print("Flight not Found!")

#        # ticket cancel ka 
#     def cancel_ticket(self, booking_id):
#         if booking_id in self.bookings:
#             booking = self.bookings[booking_id]
#             booking.flight.available_seats += len(booking.passengers)
#             del self.bookings[booking_id]
#             print("Booking Cancelled!")
#         else:
#             print("Invalid Booking ID!")

#         #booking show ka
#     def show_booking(self, booking_id):
#         if booking_id in self.bookings:
#             b = self.bookings[booking_id]
#             print(f"\nBooking ID: {b.booking_id}")
#             print(f"Flight: {b.flight.flight_id}")
#             print(f"Passengers:")
#             for p in b.passengers:
#                 print(f" - {p.name}, Age {p.age}")
#         else:
#             print("Booking not Found!")

#           # flight system ka
# def seed_data(system):
#     system.add_flight(Flight("F101", "Delhi", "Mumbai", 50, 5000))
#     system.add_flight(Flight("F102", "Delhi", "Bangalore", 40, 6000))
#     system.add_flight(Flight("F103", "Mumbai", "Goa", 30, 3000))
#     system.add_flight(Flight("F104", "Chennai", "Delhi", 20, 5500))

# def main():
#     system = FlightSystem()
#     seed_data(system)
     
#      # flight system loops
#     while True:
#         print("\n--- Flight Booking System ---")
#         print("1. Search Flights")
#         print("2. Book Ticket")
#         print("3. Cancel Ticket")
#         print("4. View Booking")
#         print("5. Exit")

#         choice = input("Enter Choice: ")
#             # konsi flight vala
#         if choice == "1":
#             src = input("Enter Source: ")
#             dest = input("Enter Destination: ")
#             flights = system.search_flights(src, dest)
#             if flights:
#                 system.show_flights(flights)
#             else:
#                 print("No Flights Found!")

#            # choice 2 with Flight ID
#         elif choice == "2":
#             fid = input("Enter Flight ID: ")
#             n = int(input("Number of Passengers: "))
#             passengers = []
#             for i in range(n):
#                 name = input("Name: ")
#                 age = int(input("Age: "))
#                 passengers.append(Passenger(name, age))
#             system.book_ticket(fid, passengers)

#         elif choice == "3":
#             bid = input("Enter Booking ID: ")
#             system.cancel_ticket(bid)

#         elif choice == "4":
#             bid = input("Enter Booking ID: ")
#             system.show_booking(bid)

#         elif choice == "5":
#             print("Exiting...")
#             break

#         else:
#             print("Invalid choice!")
     
# if __name__ == "__main__":
#     main()
    
# import uuid
# from datetime import datetime
        
#         # seat konsi h 
# class Seat:
#     def __init__(self, seat_no, seat_type):
#         self.seat_no = seat_no
#         self.seat_type = seat_type  # window / aisle / middle
#         self.is_booked = False


# class Flight:
#     def __init__(self, flight_id, source, destination, base_price):
#         self.flight_id = flight_id
#         self.source = source
#         self.destination = destination
#         self.base_price = base_price
#         self.seats = self.create_seats()

#     def create_seats(self):
#         seats = []
#         types = ["window", "middle", "aisle"]
#         for i in range(1, 31):
#             seat_type = types[i % 3]
#             seats.append(Seat(f"S{i}", seat_type))
#         return seats

#     def available_seats(self):
#         return [s for s in self.seats if not s.is_booked]

# class Passenger:
#     def __init__(self, name, age):
#         self.name = name
#         self.age = age

# class Booking:
#     def __init__(self, user, flight, seats, total_price):
#         self.booking_id = str(uuid.uuid4())[:8]
#         self.user = user
#         self.flight = flight
#         self.seats = seats
#         self.total_price = total_price
#         self.time = datetime.now()

# class User:
#     def __init__(self, username):
#         self.username = username
#         self.bookings = []

# class Payment:
#     @staticmethod
#     def process(amount):
#         print(f"Processing payment of ₹{amount}...")
#         return True  # simulate success

# class FlightSystem:
#     def __init__(self):
#         self.flights = []
#         self.users = {}

#     def add_flight(self, flight):
#         self.flights.append(flight)

#     def register_user(self, username):
#         if username not in self.users:
#             self.users[username] = User(username)
#         return self.users[username]

#     def search_flights(self, src, dest):
#         return [f for f in self.flights if f.source == src and f.destination == dest]

#     def show_flights(self, flights):
#         for f in flights:
#             print(f"\n{f.flight_id}: {f.source} -> {f.destination} | Price: ₹{f.base_price}")

#     def show_available_seats(self, flight):
#         for s in flight.available_seats():
#             print(f"{s.seat_no} ({s.seat_type})", end="  ")
#         print()

#     def calculate_price(self, flight, seat_type, travel_class):
#         price = flight.base_price
#         if seat_type == "window":
#             price += 500
#         if travel_class == "business":
#             price *= 2
#         return price

#     def book_ticket(self, user, flight_id, seat_nos, travel_class):
#         flight = next((f for f in self.flights if f.flight_id == flight_id), None)
#         if not flight:
#             print("Flight not found!")
#             return

#         selected_seats = []
#         total_price = 0

#         for seat in flight.seats:
#             if seat.seat_no in seat_nos and not seat.is_booked:
#                 selected_seats.append(seat)
#                 total_price += self.calculate_price(flight, seat.seat_type, travel_class)

#         if len(selected_seats) != len(seat_nos):
#             print("Some seats not available!")
#             return

#         if Payment.process(total_price):
#             for seat in selected_seats:
#                 seat.is_booked = True

#             booking = Booking(user, flight, selected_seats, total_price)
#             user.bookings.append(booking)

#             print(f"\nBooking Done! ID: {booking.booking_id}")
#             print(f"Total Paid: ₹{total_price}")

#     def show_user_bookings(self, user):
#         for b in user.bookings:
#             print(f"\nBooking ID: {b.booking_id}")
#             print(f"Flight: {b.flight.flight_id}")
#             print(f"Seats: {[s.seat_no for s in b.seats]}")
#             print(f"Amount: ₹{b.total_price}")

# def seed(system):
#     system.add_flight(Flight("F201", "Delhi", "Goa", 4000))
#     system.add_flight(Flight("F202", "Mumbai", "Bangalore", 5000))

# def main():
#     system = FlightSystem()
#     seed(system)

#     username = input("Enter username: ")
#     user = system.register_user(username)

#     while True:
#         print("\n1. Search Flights")
#         print("2. Book Ticket")
#         print("3. My Bookings")
#         print("4. Exit")

#         choice = input("Choose: ")

#         if choice == "1":
#             src = input("From: ")
#             dest = input("To: ")
#             flights = system.search_flights(src, dest)
#             system.show_flights(flights)

#         elif choice == "2":
#             fid = input("Flight ID: ")
#             flight = next((f for f in system.flights if f.flight_id == fid), None)

#             if flight:
#                 system.show_available_seats(flight)
#                 seats = input("Enter seat numbers (comma): ").split(",")
#                 tclass = input("Class (economy/business): ")
#                 system.book_ticket(user, fid, seats, tclass)
#             else:
#                 print("Invalid flight!")

#         elif choice == "3":
#             system.show_user_bookings(user)

#         elif choice == "4":
#             break

# if __name__ == "__main__":
#     main()
# import uuid
# from datetime import datetime

# class Wallet:
#     def __init__(self):
#         self.balance = 10000 

#     def deduct(self, amount):
#         if self.balance >= amount:
#             self.balance -= amount
#             return True
#         return False

#     def add(self, amount):
#         self.balance += amount

# class Seat:
#     def __init__(self, seat_no):
#         self.seat_no = seat_no
#         self.is_booked = False

# class Flight:
#     def __init__(self, fid, src, dest, price):
#         self.flight_id = fid
#         self.source = src
#         self.destination = dest
#         self.price = price
#         self.seats = [Seat(f"S{i}") for i in range(1, 21)]

# class Booking:
#     def __init__(self, user, flight, seats, amount):
#         self.id = str(uuid.uuid4())[:8]
#         self.user = user
#         self.flight = flight
#         self.seats = seats
#         self.amount = amount
#         self.status = "CONFIRMED"
#         self.time = datetime.now()

# class User:
#     def __init__(self, name):
#         self.name = name
#         self.wallet = Wallet()
#         self.bookings = []

# class FlightSystem:
#     def __init__(self):
#         self.flights = []
#         self.users = {}

#     def add_flight(self, f):
#         self.flights.append(f)

#     def register(self, name):
#         if name not in self.users:
#             self.users[name] = User(name)
#         return self.users[name]

#     def search(self, src, dest):
#         return [f for f in self.flights if f.source == src and f.destination == dest]

#     def show_flights(self, flights):
#         for f in flights:
#             print(f"{f.flight_id}: {f.source}->{f.destination} ₹{f.price}")

#     def show_seats(self, flight):
#         for s in flight.seats:
#             status = "X" if s.is_booked else "O"
#             print(f"{s.seat_no}({status})", end=" ")
#         print()

#     def book(self, user, fid, seat_list):
#         flight = next((f for f in self.flights if f.flight_id == fid), None)
#         if not flight:
#             print("Flight not found")
#             return

#         selected = []
#         for s in flight.seats:
#             if s.seat_no in seat_list and not s.is_booked:
#                 selected.append(s)

#         if len(selected) != len(seat_list):
#             print("Seats not available")
#             return

#         total = len(selected) * flight.price

#         if not user.wallet.deduct(total):
#             print("Insufficient balance")
#             return

#         for s in selected:
#             s.is_booked = True

#         booking = Booking(user, flight, selected, total)
#         user.bookings.append(booking)

#         print(f"\nBooked! ID: {booking.id} | Paid: ₹{total}")

#     def cancel(self, user, bid):
#         for b in user.bookings:
#             if b.id == bid and b.status == "CONFIRMED":
#                 b.status = "CANCELLED"

#                 # refnd
#                 refund = int(b.amount * 0.8)
#                 user.wallet.add(refund)

#                 for s in b.seats:
#                     s.is_booked = False

#                 print(f"Cancelled! Refund: ₹{refund}")
#                 return

#         print("Invalid booking ID")

#     def history(self, user):
#         for b in user.bookings:
#             print(f"\nID: {b.id}")
#             print(f"Flight: {b.flight.flight_id}")
#             print(f"Seats: {[s.seat_no for s in b.seats]}")
#             print(f"Status: {b.status}")
#             print(f"Amount: ₹{b.amount}")

# def seed(sys):
#     sys.add_flight(Flight("F301", "Delhi", "Goa", 4000))
#     sys.add_flight(Flight("F302", "Mumbai", "Delhi", 5000))

# def main():
#     system = FlightSystem()
#     seed(system)

#     name = input("Enter name: ")
#     user = system.register(name)

#     while True:
#         print("\n1.Search 2.Book 3.Cancel 4.History 5.Wallet 6.Exit")
#         ch = input("Choice: ")

#         if ch == "1":
#             s = input("From: ")
#             d = input("To: ")
#             f = system.search(s, d)
#             system.show_flights(f)

#         elif ch == "2":
#             fid = input("Flight ID: ")
#             f = next((x for x in system.flights if x.flight_id == fid), None)
#             if f:
#                 system.show_seats(f)
#                 seats = input("Seats (comma): ").split(",")
#                 system.book(user, fid, seats)

#         elif ch == "3":
#             bid = input("Booking ID: ")
#             system.cancel(user, bid)

#         elif ch == "4":
#             system.history(user)

#         elif ch == "5":
#             print(f"Wallet Balance: ₹{user.wallet.balance}")

#         elif ch == "6":
#             break

# if __name__ == "__main__":
#     main()
# from flask import Flask, request, jsonify
# import uuid

# app = Flask(__name__)

#       # ticket wallet
# class User:
#     def __init__(self, name):
#         self.name = name
#         self.wallet = 10000
#         self.bookings = []

#       # price
# class Flight:
#     def __init__(self, fid, src, dest, price):
#         self.id = fid
#         self.src = src
#         self.dest = dest
#         self.price = price
#         self.seats = {f"S{i}": False for i in range(1, 21)}
     
#      # user Booking 
# class Booking:
#     def __init__(self, user, flight, seats, amount):
#         self.id = str(uuid.uuid4())[:8]
#         self.user = user.name
#         self.flight = flight.id
#         self.seats = seats
#         self.amount = amount
#         self.status = "CONFIRMED"

# users = {}
# flights = {}
# bookings = {}

# def seed():
#     flights["F401"] = Flight("F401", "Delhi", "Goa", 4000)
#     flights["F402"] = Flight("F402", "Mumbai", "Delhi", 5000)

# seed()
#          # ragister with name & post
# @app.route("/register", methods=["POST"])
# def register():
#     name = request.json["name"]
#     if name not in users:
#         users[name] = User(name)
#     return jsonify({"message": "User registered"})

#           #get vala
# @app.route("/search", methods=["GET"])
# def search():
#     src = request.args.get("src")
#     dest = request.args.get("dest")
    
#         # return ka 
#     result = []
#     for f in flights.values():
#         if f.src == src and f.dest == dest:
#             result.append({
#                 "id": f.id,
#                 "price": f.price
#             })
#     return jsonify(result)
   
#    # flight available??
# @app.route("/seats/<fid>", methods=["GET"])
# def seats(fid):
#     f = flights.get(fid)
#     if not f:
#         return jsonify({"error": "Flight not found"})
#     return jsonify(f.seats)

# @app.route("/book", methods=["POST"])
# def book():
#     data = request.json
#     user = users.get(data["user"])
#     flight = flights.get(data["flight"])
#     seat_list = data["seats"]

#     if not user or not flight:
#         return jsonify({"error": "Invalid user/flight"})

#     # check seats ka
#     for s in seat_list:
#         if flight.seats.get(s) == True:
#             return jsonify({"error": f"Seat {s} not available"})

#     total = len(seat_list) * flight.price

#     if user.wallet < total:
#         return jsonify({"error": "Insufficient balance"})

#     # deduct money ka 
#     user.wallet -= total

#     # mark seats ka
#     for s in seat_list:
#         flight.seats[s] = True

#     booking = Booking(user, flight, seat_list, total)
#     bookings[booking.id] = booking
#     user.bookings.append(booking)

#     return jsonify({
#         "booking_id": booking.id,
#         "amount": total
#     })
#          # cancle root part
# @app.route("/cancel", methods=["POST"])
# def cancel():
#     data = request.json
#     bid = data["booking_id"]
#     user = users.get(data["user"])

#     booking = bookings.get(bid)
#          # booking status check 
         
#     if not booking or booking.status != "CONFIRMED":
#         return jsonify({"error": "Invalid booking"})

#     booking.status = "CANCELLED"

#     # refund 80% ka
#     refund = int(booking.amount * 0.8)
#     user.wallet += refund

#     # free seats ka
#     flight = flights[booking.flight]
#     for s in booking.seats:
#         flight.seats[s] = False

#          # return cancelled ka message
#     return jsonify({
#         "message": "Cancelled",
#         "refund": refund
#     })
    
#            # flight routs chec
# @app.route("/wallet/<username>", methods=["GET"])
# def wallet(username):
#     user = users.get(username)
#     if not user:
#         return jsonify({"error": "User not found"})
#     return jsonify({"balance": user.wallet})

#     # user ki booking check with with route ki available h??
# @app.route("/bookings/<username>", methods=["GET"])
# def user_bookings(username):
#     user = users.get(username)
#     if not user:
#         return jsonify({"error": "User not found"})

#            # user ki booking final vali
#     result = []
#     for b in user.bookings:
#         result.append({
#             "id": b.id,
#             "flight": b.flight,
#             "seats": b.seats,
#             "status": b.status
#         })
#     return jsonify(result)

# if __name__ == "__main__":
#     app.run(debug=True)

# while True:
#     print("\n1. Login\n2. Exit")
#     c=input("choice..")
#     if c==1:
#         print("Login Successfull..")
#     elif c==2:
#         print("Exiting...")
#     else:
#         print("Invalid Choice..")
# # username_db = "admin"
# # password_db = "1234"
# # while True:
# #     print("\n1. Login\n2. Exit")
# #     choice = input("Enter choice: ")
# #     if choice == "1":
# #         username = input("Username: ")
# #         password = input("Password: ")
# #         if username == username_db and password == password_db:
# #             print("Login Successful!")
# #         else:
# #             print("Invalid credentials!")
# #     elif choice == "2":
# #         print("Exiting...")
# #         break
# #     else:
# #         print("Invalid Choice!")

# while True:
#     print("\n1. Login\n2. Exit")
#     choice = input("Enter choice: ")
#     if choice == "1":
#         print("Login Successfull...")
#     elif choice == "2":
#         print("Exiting...")
#         break
#     else:
#         print("Invalid Choice!")
        
# color = input("Enter a color: ")
# new = []
# for i in color:
#     if f"The sky is {i}" in i:
#         new.append(i)
# print(new)

# friends = []
# for i in range(3):
#     name = input("Enter friend name:")
#     friends.append(name)
#     print(f"Your friends are:", friends) 

# a=input("Enter Name: ")
# new=[]
# for i in a:
#     if i in "aioue":
#         new.append(i)
# print(new)

# li= [1,2,3,"Abhishek",5,7,"Malviy"]
# new= []
# for i in li:
#     if chr in i:
#         new.append(i)
# print(new)

# a="Abhishek"
# for i in range(len(a)):
#     print(i)

# username=input("Enter Username..")
# if username =="Abhishek":
#     print(username,"Wellcome..")
#     pa=int(input("Enter Password.."))
#     if username =="Abhishek" and pa == 1234:
#         print("Login Successfull..")
#         idd =input("Enter Your ID..")
#         if  idd == "1APY69NDJ":
#             print(100000)
#             amount = int(input("Enter Amont.."))
#             if amount < 100000:
#                 print("Transection Successfull..")
#             else:
#                 print("Need Authourity Permission..")
#         else:
#             print("Invalid ID..")
#     else:
#         print("Login Faild..")
# else:
#     print("Invalid Username..")
# for i in range(6):
#     for j in range(i):
#         print("*",end="")
#     print()
# for k in range(6,0,-1):
#     for h in range(k):
#         print("*",end="")
#     print()
# t=int(input("Enetr num.."))
# for i  in range(1,11):
# #     print(t*i)

# a=[1,2,3,4,5,6,7,8]
# new=[]
# for i in a:
#     if i >5:
#         new.append(i)
#         print(new)
#     else:
#         new.append(i)
#         print(new)
# for i in range(1,21):
#     if i == 8:
#         continue
# #     print(i)
# import random
# correctAnswer = random.randint(1,100)
# gameOver = False
# while gameOver == False:
#     playerGuess=int(input("Guess a num.. between 1 and 100:"))
#     if playerGuess==correctAnswer:
#         compareAnswer="Right"
#         gameOver=True
#     elif playerGuess>correctAnswer:
#         compareAnswer="High"
#     elif playerGuess < compareAnswer:
#         compareAnswer =  "Low"
#     if compareAnswer == "Right":
#         print("Correct! You Win!..")
#     elif compareAnswer == "High":
#         print("Too High! Guess Again!..")
#     elif compareAnswer == "Low":
#         print("Too Low! Guess Again")
# Starting_Salary= int(input("Enter Salary..."))
# Annual_Increment= int(input("Enter Annual Increment %... "))
# Number_of_Years= int(input("Enter Number of Years..."))

# num=int(input("Enter Positive Num..."))
# positiv=[]
# nagetive=[]
# if num %2==0:
#     print(num,"Psitive..")
# else:
#     print(num,"Nagitiv..")

# for i in range(1,11):
#     if i >6:
#         print(i)
        
# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()

# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()


# username=input("Enter Username...")
# if username=="Abhishek Malviy":
#     print("Wellcome",username)
#     pin=int(input("Enter PIN..."))
#     if  pin==000:
#         print("Login Successfull...")
#         internal_password=input("Enter Password...")
#         if internal_password=="ABC000":
#             print("10000")
#             amount=int(input("Enter Amount..."))
#             if amount<10000:
#                 print("Amount Debited Successfull...")
#             else:
#                 print("Insufficient Balance...")
#         else:
#             print("Invalid Password...")
#     else:
#         print("Login Faild...")
# else:
#     print("Enter Valid Username...")
# n=int(input("Enter num..."))
# for i in range(1,11):
#     print(n*i)
# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()
# for k in range(5,0,-1):
#     for l in range(k-1):
#         print("*",end="")
#     print()
# for i in range(6):
#     for j in range(i+1):
#         print("*",end="")
#     print()

# for i in range(5):
#     for k in range(i+1):
#         print("*",end="")
#     print()
    
# for l in range(6,0,-1):
#     for h in range(l):
#         print("*",end="")
#     print()
# num=int(input("Enter Num.."))
# # for i in range(1,11):
# #     print(num*i)
# v=[1,2,3,4,5,6]
# mum=[]
# for i in v:
#     if i%2==0:
#         mum.append(i)
# print(mum)
# def abhi(a,b):
#     print(a+b)
# abhi(1,2)
# for i in range(5):
#     for j in range(i+1):
#         print("*",end="") 
#     print()

# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()

# for k in range(5,0,-1):
#     for h in range(k-1):
#         print("*",end="")
#     print()

# n=int(input("Enter Num..."))
# for i in range(1,11):
#     print(n*i)

# for i in range(1,11):
#     if i ==5:
#         continue
#     print(i)

# name=input("Enter name: ")
# count=0
# for i in name:
#     if i in "aeiouAEIOU":
#         count+=1
# print(count)

# for i in range(1,51):
#     if i%3==0:
#         print(i,"Fizz")
#     elif i%5==0:
#         print(i,"Buzz")
#     elif i%3==0 and i%5==0:
#         print(i,"FizzBuzz")

# v=[1, 2, 2, 3, 4, 4, 4, 5]
# for i in v:
#     if v.count(i) > 1:
#         print(i)

# v=input("Enter String: ")
# new=[]
# for i in v:
#     if i not in new:
#         new.append(i)
# print(new)

# c=int(input("Enter Num..."))
# for i in range(1,11):
#     print(c*i)
# num=int(input("Enter Num..."))
# for i in num:
#     if i %2==0:
#         print(i,"Even..")
#     else:
#         print(i,"Odd..")

# v=[23, 45, 12, 67, 8, 90]
# smalest=v[0]
# for i in v:
#     if i < smalest:
#         smalest=i
# print(smalest)

# v="Python is very easy"
# count=0
# for i in range(len(v)):
#     count+=1
# print(count)

# v=[10, 20, 30, 40]
# total=0
# for i in v:
#     total+=i
# print(total)
# v=[10, -5, 23, -1, 0, 8]
# positive=[]
# for i in v:
#     if i > 0:
#         positive.append(i)
# print(positive)
# v="Python is fun"
# count=0
# for i in v:
#     if i in "aeiouAEIOU":
#         count+=1
# print(count)

# li=["rahul", "amit", "sneha", "priya"]
# new=[]
# for i in li:
#     new.append(i.upper())
# print(new)

# word=input("Enter Word: ")
# count=0
# for i in word:
#     if char == letter:
#         count+=1
# n=int(input("Enter Num..."))
# for i in range(1,11):
#     print(n*i)
# listt=[1,2,3,4,5,6,7,8,9,0]
# for i in listt:
# print("Hello World")
# a=1
# b=2
# print(a+b)
# name=input("Enter Name...")
# print(name)
# num=int(input("Enter Num..."))
# if num%2==0:
#     print("even")
# else:
#     print("odd")
# card=input("Enter Card...")
# if card== "inserted":
#     print(" ")
#     name=input("Enter Your Name...")
#     if name=="Abhishek":
#         print(" ")
#         PIN=int(input("Enter PIN..."))
#         if name == "Abhishek" and PIN ==000:
#             print(" ")
#             amount=int(input("Enter Amount..."))
#         if amount<=10000:
#             print("Withrawl Successfull...")
#         else:
#             print("Need Permission")
#     else:
#         print("Please Re-Enter Your Card")
# else:
#     print("Insert Your Card")


# # # # Safar...........
# import time
# class Safar:
#     def __init__(self):
#         self.movies = [ 
#             {"id": 1, "title": "Inception", "genre": "Sci-Fi", "rating": 8.8, "tags": ["dreams", "space", "mind-bending"]},
#             {"id": 2, "title": "The Dark Knight", "genre": "Action", "rating": 9.0, "tags": ["batman", "hero", "dc"]},
#             {"id": 3, "title": "Interstellar", "genre": "Sci-Fi", "rating": 8.6, "tags": ["space", "time", "future"]},
#             {"id": 4, "title": "The Hangover", "genre": "Comedy", "rating": 7.7, "tags": ["friends", "funny", "party"]},
#             {"id": 5, "title": "Extraction", "genre": "Action", "rating": 6.7, "tags": ["bullets", "hero", "thriller"]},
#             {"id": 6, "title": "Stranger Things", "genre": "Sci-Fi", "rating": 8.7, "tags": ["kids", "monsters", "80s"]}
#         ]
#         self.user_watchlist = []
#         self.watch_history = []
        
#     def show_all_movies(self):
#         print("\n--- Trending on Safar ---")
#         for m in self.movies:
#             print(f"[{m['id']}] {m['title']} | {m['genre']} |  {m['rating']}")
#         time.sleep(1)
#     def watch_movie(self, movie_id):

#         selected_movie = next((m for m in self.movies if m["id"] == movie_id), None)
#         if selected_movie:
#             print(f"\nPlaying: {selected_movie['title']}...")
#             time.sleep(2)
#             print("Enjoyed the movie! Adding to your history.")
#             self.watch_history.append(selected_movie)
#         else:
#             print("Movie not found!")
#     def watch_movie(self, movie_id):

#         selected_movie = next((m for m in self.movies if m["id"] == movie_id), None)
#         if selected_movie:
#             print(f"\nPlaying: {selected_movie['title']}...")
#             time.sleep(2)
#             print("Enjoyed the movie! Adding to your history.")
#             self.watch_history.append(selected_movie)
#         else:
#             print("Movie not found!")
#     def watch_movie(self, movie_id):

#         selected_movie = next((m for m in self.movies if m["id"] == movie_id), None)
#         if selected_movie:
#             print(f"\nPlaying: {selected_movie['title']}...")
#             time.sleep(2)
#             print("Enjoyed the movie! Adding to your history.")
#             self.watch_history.append(selected_movie)
#         else:
#             print("Movie not found!")
    
#     def show_all_movies(self):
#         print("\n--- Trending on Safar ---")
#         for m in self.movies:
#             print(f"[{m['id']}] {m['title']} | {m['genre']} |  {m['rating']}")
#         time.sleep(1)

#     def recommend_movies(self):

#         if not self.watch_history:
#             print("\nSuggesting Top Rated (No history found):")
#             top_rated = sorted(self.movies, key=lambda x: x['rating'], reverse=True)[:2]
#             for m in top_rated:
#                 print(f"Recommended: {m['title']} (Based on Rating)")
#             return
#     def show_all_movies(self):
#         print("\n--- Trending on Safar ---")
#         for m in self.movies:
#             print(f"[{m['id']}] {m['title']} | {m['genre']} |  {m['rating']}")
#         time.sleep(1)

          
#         if not self.watch_history:
#             print("\nSuggesting Top Rated (No history found):")
#             top_rated = sorted(self.movies, key=lambda x: x['rating'], reverse=True)[:2]
#             for m in top_rated:
#                 print(f"Recommended: {m['title']} (Based on Rating)")
#             return

#         last_genre = self.watch_history[-1]["genre"]
#         print(f"\n--- Because you watched {self.watch_history[-1]['title']} ---")
#         print(f"Suggesting more in {last_genre} genre: ")
        
#         for m in self.movies:
#             if m["genre"] == last_genre and m not in self.watch_history:
#                 print(f"Recommended: {m['title']} (Same Genre: {last_genre})")
#             else:
#                 print(f"If not Recmmonded: {m['tital']}(Same Genre: ) {last_genre}")
        
#         last-genre = self.watch_history[-1]["genre"]
#         print(f"\n- watched {self.watch_history[-1]['tital']}")
#         print("f\n- watched {self.watch_history[-1]['tital']}")
    
    
    
#         for i in self.movies:
#             if m["genre"] == last_genre and i not in self.watch_history:
#                 print(f"Recommended: {m['tital']} (Sanme genre: {last_genre})")
                
#             elif m["genre"] == last_genre and i not in self.watch_history:
#                 print(f"Recommended: {m['tital']} (Sanme genre: {last_genre})")
#                 print(f"Recommended: {m['tital']} (Sanme genre: {last_genre})")
#                 print(f"Suggesting more in {last_genre} genre: ")
                
#             else:
#                 print(f"If not Recommnded: {m['tital']} (sanme genre: {last_genre})")
#                 print(f"If not Recmmonded: {m['tital']}(Same Genre: ) {last_genre}")
            
    
  
# app = Safar()
# while True:
#     print("\n" + "="*30)
#     print("      Safar PYTHON      ")
#     print("="*30)
#     print("1. Browse Movies")
#     print("2. Watch a Movie")
#     print("3. My Recommendations")
#     print("4. Exit")
    
#     cmd = input("\nChoose an option: ")

#     if cmd == "1":
#         app.show_all_movies()
#     elif cmd == "2":
#         mid = int(input("Enter Movie ID to watch: "))
#         app.watch_movie(mid)
#     elif cmd == "3":
#         app.recommend_movies()
#     elif cmd == "4":
#         print("Goodbye! Happy Binging.")
#         break
#     else:
#         print("Invalid Choice!")
        
#     if cmd == "5":
#         app.show_all_movies()
#     elif cmd == "6":
#         mid = int(input("Enter Movie ID to watch: "))
#         app.watch_movie(mid)
#     elif cmd == "7":
#         app.recommend_movies()
#     elif cmd == "8":
#         print("Goodbye! Happy Binging. ")
#         break
#     else:
#         print("Invalid Choice!")


# import time
# class Safar:
#     def __init__(self):
#         self.movies = [
#             {"id": 1, "title": "Inception", "genre": "Sci-Fi", "rating": 8.8},
#             {"id": 2, "title": "The Dark Knight", "genre": "Action", "rating": 9.0},
#             {"id": 3, "title": "Interstellar", "genre": "Sci-Fi", "rating": 8.6},
#             {"id": 4, "title": "Friends", "genre": "Comedy", "rating": 8.9},
#             {"id": 5, "tital": "Avtar", "genre": "Animation", "rating": 9.1},
#             {"id": 6, "tital": "Lucy", "genre": "Action", "rating": 6.9},
#             {"id": 7, "tital": "Kantara", "genre": "Action", "rating": 7.5},
#             {"id": 8, "tital": "Saho", "genre": "Action", "rating": 4.3},
#             {"id": 9, "tital": "Ek hero","genre": "Romance", "rating": 3.2},
#             {"id": 10, "tital": "Saruluru", "genre": "Comady", "rating": 4.6},
#             {"id": 11, "tital": "Krish 3", "genre": "Action", "rating": 6.38}
            
            
            
#         ] 
#         self.users = {
#             "aman@email.com": {"password": "123", "name": "Aman", "plan": "Premium", "history": []},
#             "rahul@email.com": {"password": "456", "name": "Rahul", "plan": "Basic", "history": []},
#             "abhishekmalviy724@gmail.com": {"password": "000", "name": "Rohan", "Plan": "basic", "history": []},
#             "abhisheksawlakhiya@gmail.com": {"password":"111", "name": "Abhishek","plan": "primium", "histroy": []},
#             "rohan@gamil.com": {"password": {"password": "222", "name": "Rohan", "plan": "basic", "history": []}},
#             "amit@gamil.com": {"password": {"password": "333", "name": "Amit", "plan": "basic","hsitory": []}},
#             "sameerpathan@gmail.com": {"password": "444", "name": "Sameer", "plan": "primium", "history": []},
#             "amanjaiswal@gmail.com": {"passowrd": "555", "name": "Aman", "plan": "basic","history": []},
#             "vanshikakhatri@gmail.com": {"password": "666", "name": "Vanshika", "plan": "primium", "history": []}
   
   
#         }
#         self.current_user = None
#     def login(self):
#         print("\n--- Safar Login ---")
#         email = input("Email: ")
#         pwd = input("Password: ")
#         if email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#             return True
#         elif email in self.users and self.users[email]["password"] == pwd:
#             self.current_users = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']})")
#         elif email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#             return True
#         elif email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#             return True
#         elif email in self.users or {self.users[email]['again']} ({self.usres[email]['plan']}):
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#             for email in self.current_user(3):
#                 for email in (choice):
#                     for email in (4):
#                         print("4",end="")
#                         return False 
#                 print("Please wait...",end=" ")   
                     
#             print()   
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']})")
#             for email in (2):
#                 print("Please wait...",end=" ")
#                 for email in (len(choice)):
#                     for choice in (3):
#                         for email in (choice+1):
#                             print("name",end=" ")
#                     print()
#                 for i in (4):
#                     print(i+1)
#                     if choice == "2":
#                         print("Next Episode")
#                         print(len(choice))
#                     elif email in self.current_user and {self.usres[email]['again']} ({self.users[email]['plan']}):
#                         print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#                         for email in self.current_user(2):
#                             for email in (choice):
#                                 for email in (3):
#                                     for email in (choice+2):
#                                         print("Enter Email", end=" ")
#                                     print()
                                   
#         else:
#             print(" Invalid Email or Password!")
#             return False
#         #double code
#     def login(self):
#         print("\n--- Safar Login ---")
#         email = input("Email: ")
#         pwd = input("Password: ")
#         if email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWlcome back, {self.users[email]['name']}! ({self.users[email]['plna']}user)")
#             return True
#         elif email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}" f"({self.users[email]['plan']} Users)")
#         elif email in self.users and self.users[email]["pasword"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#         elif email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#             return True
#         else:
#             print(" Invalid Email or Password!")
#             return False
        
    
#     def login(self):
#         print("\n--- safar Login ---")
#         email = input("Email:")
#         pwd = input("Password:")
#         if email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']}) user)")
#             return True
#         else:
#             print(" Invalid Email or Pasword!")
#             print(" Invalid Email or Password!")
    
#     def login(self):
#         print("\n--- Safar Login ---")
#         email = input("Email: ")
#         pwd = input("Password: ")
#         if email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWlcome back, {self.users[email]['name']}! ({self.users[email]['plna']}user)")
#             return True
#         else:
#             print(" Invalid Email or Password!")
#             return False
#     def show_dashboard(self):
#         while self.current_user:
#             print("\n" + "="*30)
#             print(f"   ALTRONE HOME - {self.users[self.current_user]['name']}   ")
#             print("="*30)
#             print("1. Browse Movies")
#             print("2. Watch History")
#             print("3. Profile Details")
#             print("4. Logout")
#             choice = input("\nChoose: ")
#             choice = input("\nChoose: 2 ")
#             if choice == "1":
#                 self.browse_movies()
#             elif choice == "2":
#                 history = self.users[self.current_user]["history"]
#                 print(f"Your History: {history if history else 'No movies watched yet.'}")
#                 print(f"Your History: {history if history else 'No movies watched yet. '}")           
#             elif choice == "3":
#                 u = self.users[self.current_user]
#                 print(f"\nName: {u['name']}\nPlan: {u['plan']}")
#             elif choice == "4":
#                 history = self.users[self.current_user]["history"]
#                 print(f"Your History: {history if history else 'No movies watched yet. '}")
#             elif choice == "5":
#                 print("Logging out...")
#                 self.current_user = None
#             else:
#                 print(f"[{['id']}] {['title']} ({['genre']})")
#                 print("\nEnter Movie ID to watch (or 'b' to go back): ")
#                 if choice == "1":
#                     history = self.users[self.current_user]["history"]
#                     print(f"Your History: {history if history else 'Nn movies watched yet. '}")
#                 elif choice == "2":
#                     print(f"\nNmae: {u['name']}\nPlan: {u['Plan']}")
#                     print(f"Yoyr History: {history if history else 'No movies watched yet. '}")
#                 elif choice == "3":
#                     for choice in (3):
#                         for choice in (choice+1):
#                             print("Wait", end="")
#                         for choice in (choice*2):
#                             print("Loding your content",end=" ")
#                         print()
#                 elif choice == "4":
#                     print(f"Yoyr History: {history if history else 'No movies watched yet. '}")
#                     print(f"\nNmae: {u['name']}\nPlan: {u['Plan']}")
#                     if choice == "5":
#                         print("Please check your connection...")
#                         for choice in (6):
#                             print(end="")
#                     elif choice == "6":
#                         print("You can Subscribe for free")
#                         print(f"Yoyr History: {history if history else 'No movies watched yet. '}")
#                         if choice == "email@.com":
#                             print("Welcome")
#                             for i in range(3):
#                                 print("Please choice what you want watch")
#                                 if choice == "Next...":
#                                     print(f"Yoyr History: {history if history else 'No movies watched yet. '}")
#                                 elif choice == "Next":
#                                     print("Loding your content...")
#                             for choice in (len(5)):
#                                 if not "click":
#                                     print("Reback your content..")
#                                 elif choice == "2":
#                                     print("Thanks for watching..")
#                                 elif choice == "email" and choice == "2" and choice == "Next":
#                                     print("Exit")
#                                 elif choice == "3":
#                                     print(f"primium history : {history if history else 'Need primium. '}")
#                                     for i in range(5):
#                                         for j in range(i+1):
#                                             print("Get Primium",end=" ")
#                                         print()
#                             for k in range(6,0,-1):
#                                 print("Thank You.. ",end=" ")
#                                 for i in range(k-1):
#                                     print("1",end=" ")
#                                 if i =="1":
#                                     print("You got the primium")
#                                 elif i == "2":
#                                     print("Thank Now you can watch Your Next Episode..")
#                                 elif i == "3":
#                                     print("Next...")
#                                 self.current_user = None
#     def login(self):
#         print("\n--- Safar Login ---")
#         email = input("Email: ")
#         pwd = input("Password: ")
#         if email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#             return True
#         elif email in self.users and self.users[email]["password"] == pwd:
#             self.current_users = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']})")
#         elif email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#             return True
#         elif email in self.users and self.users[email]["password"] == pwd:
#             self.current_user = email
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#             return True
#         elif email in self.users or {self.users[email]['again']} ({self.usres[email]['plan']}):
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']} User)")
#             for email in self.current_user(3):
#                 for email in (choice):
#                     for email in (4):
#                         print("4",end="")
#             print()   
#             print(f"\nWelcome back, {self.users[email]['name']}! ({self.users[email]['plan']})")
                            
#         elif email in self.usres and {self.usres[email]['Primium'] ({self.users[email]['plan']})}:
#             print(f"\nWelcome with primium, {self.users[email]['name']}! ({self.users[email]['plan']})")
#             for i in range(5):
#                 for j in range(i*2):
#                     print("Next",end=" ")
#                 for i in range(j+1):
#                     print("Tag 1")
#                     print("\n Search new moives..")
#         elif choice == "4":
#             print("\n Comming soon.. ")
#             print(f"\nWelcome with primium, {self.users[email]["name"]}! ({self.users[email]['plan']})")
#         elif choice == "5":
#             print(f"[{choice['id']}] {choice['title']} ({choice['genre']})")
            
#         elif choice == "6":
#             print("from django.conf import settings")

#     def browse_movies(self):
#         print("\nAvailable Movies:")
#         for m in self.moviies:
#             print(f"[{m['id']}] {m['title']} ({m['genre']})")
#         mid = input("\nEnter Movie ID to watch (or 'b' to go back): ")
        
#         if mid.isdigit():
#             movie = next((m for m in self.movies if m["id"] == int(mid)), None)
#             if movie:
#                 print(f"Streaming {movie['title']} in {self.users[self.current_user]['plan']} Quality... ")
#                 self.users[self.current_user]["history"].append(movie['title'])
#                 time.sleep(2)
#         elif mid.isdigit():
#             movie = next ((m for m in self.movies if m["id"] == int(mid)), None)
#             if movie:
#                 print(f"Streaming {movie['tital']} in {self.users[self.current_user]['plan']} Quality ")
#                 self.users[self.current_user]["history"].append(movie)['tital']
#                 time.sleep(2)
#         elif mid.isdigit():
#             movie = next((m for m in self.movies if m["id"] == int(mid)), None)
#             if movie:
#                 print(f"Streaming {movie['title']} in {self.users[self.current_user]['plan']} Quality... ")
#                 self.users[self.current_user]["history"].append(movie['title'])
#                 time.sleep(2)

# safar_app = Safar()
# while True:
#     print("\n1. Login\n2. Exit")
#     start = input("Choice: ")
#     if start == "1":
#         if safar_app.login():
#             safar_app.show_dashboard()
#     elif start == "2":
#         print("Exiting...")
#         break
#     else:
#         print("Invalid choice! please try again.")
        
    
#     if cmd == "1":
#         app.show_all_movies()
#     elif cmd == "2":
#         mid = int(input("Enter Movie ID to watch: "))
#         app.watch_movie(mid)
#     elif cmd == "3":
#         app.recommend_movies()
#     elif cmd == "4":
#         print("Goodbye! Happy Binging.")
#         break
#     else:
#         print("Invalid Choice!")
        
#     if cmd == "5":
#         app.show_all_movies()
#     elif cmd == "6":
#         mid = int(input("Enter Movie ID to watch: "))
#         app.watch_movie(mid)
#     elif cmd == "7":
#         app.recommend_movies()
#     elif cmd == "8":
#         print("Goodbye! Happy Binging. ")
#         break
#     else:
#         print("Invalid Choice!")
    
#     #double loops
# while True:
#     print(("\n1. Login\2. Exit"))
#     start = input("Choice: ")
#     if start == "1":
#         if safar_app.login():
#             safar_app.show_dashboard()
#             if safar_app.login():
#                 safar_app.show_dashboard()
#             elif start == "2":
#                 break     
            
# while True:
#     print(("\n. Login\2. Exit"))
#     start = input("Choice: ")
#     if start == "3":
#         if safar_app.login():
# #             safar_app.show_dashboard()
#             if safar_app.login():
#                 safar_app.show_dashboard()
#             elif start == "3":
#                 break
#             elif safar_app.show_dashboard():
#                 print("Invalid choice! please try again.")
#                 safar_app.login()
#                 for i in range(4):
#                     print("This is your content...")
#                     for choice in ("\n1. Login\2. Exit"):
#                         for choice in (3):
#                             print("Invalid choice! please try again.",end="")
#                             for choice in ():
#                                 print("3",end="")
#                             print()

                
            
# while True:
#     print("\n1. Login\2. Exit")
#     start = input("Choice: ")
#     if start == "1":
#         if safar_app.login().as_integer_ratio:
#             safar_app.show_dashboard()
#             if safar_app.login():
#                 safar_app.show_dashboard()
#             elif start == "2":
#                 print("Exiting...")           
#             elif start == "3":
#                 break
            
# # # v=[1,2,3,4,5,6,7,8,9]
# # # new=[]
# # # for i in v:
# # #     if i%3==0:
# # #         new.append(i)
# # #     print(i)

# # # for i in range(5):
# # #     for j in range(i+1):
# # #         print("*",end="")
# # #     print()

# # # num=int(input("Enter num..."))
# # # for i in range(1,11):
# # #     print(num*i)

# # # for i in range(6):
# # #     for j in range(i):
# # #         print("*",end="")
# # #     print()
    
# # # for k in range(6,0,-1):
# # #     for l in range(k):
# # #         print("*",end="")
# # #     print()

# # # v=[1,2,3,4,5,6,78,9]
# # # for i in v:
# # #     if i%9==0:
# # #         print(i)

# # # card=input("Inserted Your Card ")
# # # if card == "yes":
# # #     print("Wllcome")
# # #     languge=input("English"/"Hindi")
# # #     if card == "yes" and languge == "English" and languge == "Hindi":
# # #         print("Check Balance", "Cash Withrawl", "Diposit Amount")

# for i in range(1,11):
#     for j in range(i):
#         print("*",end="")
#     for k in range(10,0,-1):
#         print("*",end="")
#     for l in range(10,0,-1):
#         print("*",end="")
#     print()

# for i in range(5):
#     for j in range(i+1):
#         print("*",end=" ")
#     print()
    
# for k in range(5,0,-1):
#     for h in range(k-1):
#         print("*",end=" ")
#     print()
# li1=[1,2,3,4,5,6,7,8,9,]
# for i in range(len(li1)):
#     print(i)
# li1=[1,2,3,4,5,6,7,8,9,]
# for i in range(len(li1)):
#     print()

# card = input("Please Insert Your card. ")
# if card == "yes":
#     print( )
#     lang=input("Languge prefer..")
#     if  lang == "ok":
#         print( )
#         pin=int(input("Enter PIN"))
#         if pin == 000:
#             print( )
#             amount= int(input("Enter Amount."))
#             if amount <5000:
#                 print("Withrawl Successful.")
#             else:
#                 print("Need permission.")
#         else:
#             print("Wrong PIN.")
#     else:
#         print("Prefer your languge.")
# else:
#     print("Please Insert Your Card. ")

# for i in range(6):
#         for k in range(i+1):
#             print("*",end=" ")
#         print()
        
# for h in range(6,0,-1):
#     for g in range(h-1):
#         print("*",end=" ")
#     print()

# def abhi(a,b):
#     print(a+b)
    
# abhi(1,2)

# for i in range(5):
#     for j in range(i+1):
#         print("*",end=" ")
#     print()
    
# for k in range(5,0,-1):
#     for h in range(k-1):
#         print("*",end=" ")
#     print()

# for i in range(1,11):
#     print(i)
    
# for i in range(1,21):
#     if i == 7:
#         print(i)
#         continue
# for i in range(1,11):
#     print(i) 

# for i in range(1,11):
#     print(i)
#     for j in range(i+1):
#         print(j,end="")
#     print()

# AbhishekmalviyAbhishek= "cvnm," #pascal
# # a=45.4
# # print((type(a)))
# v=5/5
# b=5//5
# print(type(v))
# print(type(b))
# v=5j
# print(type(v))

# s="54"
# print(type(s))

# b= False
# print(type(b))
# 
# s= 67
# print(chr(s))

# l=[1,2,3,3,44]
# print(l)

# l=(1,2,3,3)
# print(l)

# s="Abhishek"
# print(s[3])

# a="python"
# print(a[3])
# print(a[-2])
# c="Computer"
# print(c[0])
# print(c[-2])
# v="Programming"
# c="Elephant"
# k="Keyboard"
# n="Computer"
# a="Abhishek"
# print(a[1:5:3])
# print(n[3:5])
# print(c[4:8:3])

# print(v[0:11:10])

# print(k[0:4:3])

# Word = "Programming"
# print(Word[1:3])
# print(Word[-1:-3])

# Word = "Elephant"
# print(Word[-1:-4:-1])
# Word = "Developer"
# print(Word[-1:-4:-1])
# Word = "Education"
# print(Word[-1:-4:-1])
# Word = "Computer"
# print(Word[-1:-4:-1])

# Word = "Programming"
# print(Word[1:10:2])
# Word = "Elephant"
# print(Word[2:7:2])
# Word = "Keyboard"
# print(Word[0:6:2]+Word[5])
# Word = "Programming"
# Word2 = "Elephant"
# Word = "Computer"

# print(Word[0:5:2])
# print(Word2[-1:-5:-1])
# print(Word[0:9:2])

# Word = "Education"
# print(Word[0:9:2])
# d = "Programming"
# print(d[0:11:2])
# rd = "Keyboard"
# print(rd[-1:-5:-1])

# Word = "Developer"
# print(Word[0:9:2])
# ord = "Programming"
# print(ord[-1:-6:-1])
# d = "Education"
# print(d[-1:-5:-1])
# rd = "Computer"
# print(rd[-1:-7:-2])
# c= "Abhishek"
# print(c[-1:-4:-1] + c[-4])

# v= "Programming"
# print(v[-1:-8:-2] + v[3])
# a= "Education"
# print(a[0:4:3]+a[5:8:2])
# b= "Computer"
# print(b[0:7:3])
# c= "Developer"
# print(c[-1:-7:-1])
# d= "Abhishek"
# print(d[0:4:3]+d[5:8:2])

# a= "Programming"
# print(a[-1:-4:-1]+a[-10:-12:-1])

# b= "Education"
# print(b[0:6:5]+b[6:9:2])

# c= "Computer"
# print(c[0:3:2]+c[5:8:2])

# d= "Developer"
# print(d[0:9:2])

# e= "Abhishek"
# print(e[0:2]+ e[-2:-4:-1]+e[-1])

# g= "Programming"
# print(g[0:4:3]+g[-2:-4:-1]+g[-1])

# Word = "DataStructure"
# print(Word[::2])
# d = "ArtificialIntelligence"
# print(d[-1:-13:-1])
# e= "Programming"
# print(e[0:4:3]+e[5:7]+e[-2])
# f= "ComputerScience"
# print(f[0:7:3]+f[8:15:2])
# g= "Developer"
# print(g[0:2]+g[5:8:2])
# h= "Abhishek"
# print(h[-1:-4:-1]+h[-5:-7:-1]+h[0])
# n= "Artificial"
# print(n[-1:-4:-1]+ n[2:5])

# a=23
# a=str(a)
# print(type(a))

# v="34"
# v=int(v)
# print(type(v))

# g="ghjhgf"
# print(bool(g))

# a=2
# print(2/2)

# c="45"
# c=int(c)
# print(type(c+10))

# b="python"
# c=""
# print(bool(b))
# print(bool(c))

# a=29
# n=29%5
# print(n)
# print(a//5)

# print(4 ** 3)

# q="0"
# w=(1)
# e=(-1)
# print(bool(e))
# print(bool(w))
# print(bool(q))

# r="250"
# r=int(r)
# print(r-50)

# t="0"
# print(bool(t))
# print(bool(""))

# # print(15/4)
# # print(15//4)

# # y="12.5"
# # print(float(y)*2)

# # print(2 ** 5 % 3)

# # a="75"
# # print(int(a)+25)
# # b="8.5"
# # print(float(b)*2)
# # print(bool("False"))
# # print(bool(0.0),bool(0.1))
# # print(3 ** 4)
# # c='100'
# # n=100
# # print(int(c)+n)
# # print(bool([]),bool([1,2,]))
# # print(50 / 8, 50 // 8, 50 % 8)
# # m="12"
# # print(str(m))

# # n="Abhishek"
# # age=12
# # print("my name is ",n," and my age is ",age)
# # print(f"my name is {n} and my age is {age}")

# # age = int(input("enter our age: "))
# # print(age)

# name = input("Enter your name: ")
# print(f"Hello {name}!")
# age  = int(input("Enter your age : "))
# print(f"My age is {age} years: ")
# city=input("Enter your city: ")
# print(f"i live in {city} )")
# a=input("Enter your full name :")
# print(f"hello {a}")
# no=int(input("Enter a number: "))
# print(f"is equale {no+10}  ")
# numm=int(input("Enter Your 1st no."))
# num=int(input("Enter Your 2nd no."))
# print(f"your no. is {numm+num}")
# name=input("Enter your name: ")
# age=int(input("Enter your age: "))
# print(f"My name is {name} and My age is {age}")

# age =int(input("Enter your age: "))
# print(f"Next year you will be {age  } years old.")
# print(1+2,2-2,2*2,2/2,2//2,2%2,2**3)
# a=4
# a=a+3
# a=a+3
# a=a+10
# print(a)

# a=1
# b=1
# print(a is b, a>b,a<b, a>=b, a<=b, a!=b)

# print("AB">"CD")

# print(123>100 and 23==23 and 45<90 and 12<20)

# print(20<92 or 23==63 or 45<90 or 12<20)

# print(not 1==1 )

# print(25+7,25-7,25*7)
# print(50/6,50//6,50%6)
# print(3**5)
# a = 10
# print(a+5 , a*2, a-8)
# print((8 + 4) * 2)
# print(100//9,100%9)
# print(2 ** 3 ** 2)
# print(17/5,17//5,17%5)
# w = 5
# b = 3
# print()
# a=15
# if a>0:
#     print(a)

# year=int(input("Enter YEAr"))
# if year %100==0 and year%400==0:
#     print("leep ")
# elif year %100!=0 and year %4==0:
#     print("leep1")
# else:
#     print("not")

# num=int(input("Enter your num: "))
# if num>0:
#     print("positive")
# else:
#     print("not positive")
# age = int(input("Enter Your age "))
# if age >18:
#     print("Eligible to Vote")
# else:
#     print("not")
# num=int(input("enter num"))
# if num %2==0:
#     print("even")
# else:
#     print("odd")
# marks=int(input("Enter your marks"))
# if marks>=90:
#     print(("A"))
# elif marks >=75:
#     print("B")
# elif marks >=50:
#     print("C")
# else:
#     print("Fail")
# p=input("Enter Password")
# if p=="python123":
#     print("Login Successful")
# else:
#     print("Login Faild")

# # num=int(input("NEtre num"))
# # if num%3==0:
# #     print("Fizz")
# # elif num%5==0:
# #     print("Buzz")
# # elif num%3==0 and num%5==0:
# #     print("FizzBuzz")
# # else:
# #     print("No match")

# # y=int(input("Enter year"))
# # if y%100==0 and y%400==0:
# #     print("its leep year")
# # elif y%100!=0 and y%4==0:
# #     print("leep")
# # else:
# #     print("not a leep year")

# # name=input("Enter Name")
# # if name=="admin":
# #     print("Wlcome Admin")
# # else:
# #     print("Access denied")
# num=int(input("Enter num"))
# if num==0:
#     print("Zero")
# elif num >0:
#     print("Psitive")
# else:
#     print("negative")

# for i in range(1,11):
#     print(i,"Hello")
# a=range(1,11)
# for i in a:
#     print(i)
# for i in range(10,0,-1):
#     print(id)

# n=int(input("NUm"))
# for i in range(1,11):
#     print(n*i)

# a="Abhishek Mlaviy"
# print(len(a))
# for i in range(len(a)):
#     print(a[i])
# a="Abhishek mlaviy"
# for i in a:
#     print(i)
# for i in range(1,21):
#     if i == 15:
#         print("break hai")
#         break
#     print(i)
# else:
#     print("break")


# # for i in range(0,5):
# #     print(i)
# # for i in range(1,11):
# #     print(i)
# # for i in range(2,21):
# #     if i %2==0:
# #         print(i,"Even")
# #     else:
# #         print(i,"Odd")
# # for i in range(10,0,-1):
# #     print(i)
# # t=int(input("ENter nUm"))
# # for i in range(1,11):
# #     print(t*i)
# for i in range(6,11):
#     if i %2==0:
#         print(i,"Even")
#     else:
#         print(i,"Odd")
# n=int(input("NEtre num"))
# for i in range(n):
#     print("Hello ")
# n=int(input("NEtre num"))
# for i in range(n):
#     print(i)
# n=int(input("NEtre num"))
# for i in range(n,0,-1):
#     print(i)
# n=int(input("Table"))
# for i in range(1,11):
#     print(n*i)
# a=10
# a=a+5
# print(a)
# n=int(input("NEtre num"))
# sum = 0
# for i in range(1,n+1):
#     sum = sum + i
# print(f"you sum is {sum}")

# n=int(input("NEtre num"))
# fact = 1
# for i in range(1,n+1):
#     fact = fact * i
# print(fact)
    
# n=int(input("NEtre num"))
# sum = 0
# odd = 0
# for i in range(1,n+1):
#     if i %2==0:
#         sum=sum+i
        
#     else:
#         odd=odd+i
# print(odd,sum)

# n=int(input("NEtre num"))
# for i in range(1,n+1):
#     if n %i==0:
#         print(i)
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n):
#     if n%i==0:
#         sum=sum+i
# print(sum)
# if sum==n:
#     print("p")
# else:
#     print("not p")
# n=int(input("NEtre num"))
# count=0
# for i in range(1,n+1):
#     if n%i==0:
#         count=count+1
# print(count)
# if count==2:
#     print("prime")
# else:
#     print("not ")



# n=int(input("NEtre num"))
# for i in range(1,n+1):
#     print(i)
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     sum=sum+i
# print(sum)
# n=int(input("NEtre num"))
# even=0
# for i in range(1,n+1):
#     if i%2==0:
#         print(i,"even")
#     else:
#         print(i,"odd")
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     if i%2==0:
#         sum=sum+i
# print(f"sum of all even nums..{sum}")
# n=int(input("NEtre num"))
# for i in range(1,11):
#     print(n*i)
# n=int(input("NEtre num"))
# for i in range(n,0,-1):
#     print(i)
# n=int(input("NEtre num"))
# fact=1
# for i in range(1,n+1):
#     fact != fact + i
# print(fact)
# n=int(input("NEtre num"))
# count=0
# for i in range(1,n+1):
#     if i%2==0:
#         count=count+i
# print(count)

# n=int(input("NEtre num"))
# for i in range(1,n+1):
#     print(i)
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     sum=sum+i
# print(sum)
# n=int(input("NEtre num"))
# even=0
# for i in range(1,n+1):
#     if i%2==0:
#         print(i,"even")
#     else:
#         print(i,"odd")
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     if i%2==0:
#         sum=sum+i
# print(f"sum of all even nums..{sum}")
# n=int(input("NEtre num"))
# for i in range(1,11):
#     print(n*i)
# n=int(input("NEtre num"))
# for i in range(n,0,-1):
#     print(i)
# n=int(input("NEtre num"))
# fact=1
# for i in range(1,n+1):
#     fact != fact + i
# print(fact)
# n=int(input("NEtre num"))
# count=0
# for i in range(1,n+1):
#     if i%2==0:
#         count=count+i
# print(count)

# n=int(input("NEtre num"))
# for i in range(1,n+1):
#     print(i)
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     sum=sum+i
# print(sum)
# n=int(input("NEtre num"))
# even=0
# for i in range(1,n+1):
#     if i%2==0:
#         print(i,"even")
#     else:
#         print(i,"odd")
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     if i%2==0:
#         sum=sum+i
# print(f"sum of all even nums..{sum}")
# n=int(input("NEtre num"))
# for i in range(1,11):
#     print(n*i)
# n=int(input("NEtre num"))
# for i in range(n,0,-1):
#     print(i)
# n=int(input("NEtre num"))
# fact=1
# for i in range(1,n+1):
#     fact != fact + i
# print(fact)
# n=int(input("NEtre num"))
# count=0
# for i in range(1,n+1):
#     if i%2==0:
#         count=count+i
# print(count)

# n=int(input("NEtre num"))
# for i in range(1,n+1):
#     print(i)
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     sum=sum+i
# print(sum)
# n=int(input("NEtre num"))
# even=0
# for i in range(1,n+1):
#     if i%2==0:
#         print(i,"even")
#     else:
#         print(i,"odd")
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     if i%2==0:
#         sum=sum+i
# print(f"sum of all even nums..{sum}")
# n=int(input("NEtre num"))
# for i in range(1,11):
#     print(n*i)
# n=int(input("NEtre num"))
# for i in range(n,0,-1):
#     print(i)
# n=int(input("NEtre num"))
# fact=1
# for i in range(1,n+1):
#     fact != fact + i
# print(fact)
# n=int(input("NEtre num"))
# count=0
# for i in range(1,n+1):
#     if i%2==0:
#         count=count+i
# print(count)


# n=int(input("NEtre num"))
# for i in range(1,n+1):
#     print(i)
# n=int(input("NEtre num"))
# for i in range(1,n+1):
#     print(f"n-{i}")
# n=int(input("NEtre num"))
# for i in range(n):
#     if i%2==0:
# #         print(i)
# n=int(input("NEtre num"))
# for i in range(n):
#     if i%2!=0:
#         print(i)
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     sum=sum+i
# print(sum)
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     if i%2==0:
#         sum=sum+i
# print(sum)
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     if i%2!=0:
#         sum =sum+i
# print(sum)
# n=int(input("NEtre num"))
# fact = 1
# for i in range(1,n+1):
#     fact=fact+i
# print(fact)


# n=int(input("NEtre num"))
# for i in range(n,0,-1):
#     print(i)
# n=int(input("NEtre num"))
# fact=1
# for i in range(1,n+1):
#     fact=fact+i
# print(fact)
# n=int(input("NEtre num"))
# for i in range(n+1):
#     for j in range(i+1):
#         print("*",end="")
#     print()
# n=int(input("NEtre num"))
# fact=1
# for i in range(1,n+1):
#     fact=fact*i
# print(fact)


# n=int(input("NEtre num"))
# even=0
# count=0
# for i in range(1,n+1):
#     if i%2==0:
#         count=count+1
# print(count,"even",)
# n=int(input("NEtre num"))
# fact=1
# for i in range(1,n+1):
#     fact = fact * i
# print(fact)
# n=int(input("NEtre num"))
# for i in range(n,0,-1):
#     for j in range(i):
#         print("*", end="")
#     print()
# n=int(input("NEtre num"))
# for i in range(1,n+1):
#     for j in range(i):
#         print("*", end="")
#     print()
# n=int(input("NEtre num"))
# sum=0
# for i in range(1,n+1):
#     if i%2==0:
#         sum=sum+i
# print(sum)



# a="Abhishek"
# b=""
# for i in range(len(a)-1,-1,-1):
#     b=b+a[i]
# print(b)
# a="SAS"
# b=""
# for i in range(len(a)-1,-1,-1):
#     b=b+a[i]
# if b==a:
#     print("p")
# else:
#     print("noy=t")
# d="djvhoh8w470r98/.,[P  1[]]"
# chr=0
# dig = 0
# spche=0
# for i in d:
#     if i.isdigit():
#         dig = dig +1
#     elif i.isdigit():
#         chr=chr+1
#     else:
#         spche=spche+1
# print(dig,chr,spche)



# a = "Abhishek malviy"
# count=0
# for i in a:
#     if i in "a,e,i,o,u":
#         count=count+1
# print(count)
# a = "Programming"
# for i in range(len(a)):
#     print(a[i])
# a = "I Love Python Programming"
# count=0
# for i in a:
#     if i in " ":
#         count=count+1
# a = "programming"
# count=0
# for i in a:
#     if i in "m":
#         count=count+1
# print(count)


# # a=1
# # while a<=20:
# #     print(a)
# #     a=a+1
# # a=int(input("num"))
# # rev=0
# # while a>0:
# #     rev=rev*10+a%10
# #     a=a//10
# # print(rev)
# # a=int(input("num"))
# # copy=a
# # rev=0
# # while a>0:
# #     rev=rev*10+a%10
# #     a=a//10
# # if copy== rev:
# #     print("yes P")
# # else:
# #     print("not")
# import random 
# num = random.randint(1,10)
# tries=0
# while True:
#     guess=int(input("enter num"))
#     if num == guess:
#         tries+=1
#         print("correct")
#         break
#     elif num <guess:
#         print("little lower")
#     elif num > guess:
#         print("littel highre")
#     else:
#         tries+=1
#         print("Wrong")
    
# a=1
# while a<6:
#     print(a)
#     a+=1
# a=1
# while a<11:
#     if a%2==0:
#         print(a)
#     a+=1


# a=1
# while a<=3:
#     print(a)
# #     a+=1
# a=1
# while a <= 5:
#     print(a)
#     a+=1
# i = 6
# while i>=1:
#     print(i)
#     i-=1
# i=100
# while i>=1:
#     print(i)
#     i-=1
# n=int(input("NEtre num "))
# i=1
# while i<=10:
#     print(n*i)
#     i+=1
# a=2
# while a<=5:
#     print(a)
#     a+=1
# a=5
# while a>=1:
#     print(a)
#     a-=1

# a=10
# while a<=50:
#     print(a)
#     a+=10


# a=1
# while a<=9:
#     print(a)
#     a+=1
# a=2
# while a<=10:
#     if a%2==0:
#         print(a)
#     a+=1
# a=100
# while a>=50:
#     print(a)
#     a-=10
# n=int(input("Entre num"))
# a=1
# while a<=n:
#     print(a)
#     a+=1
# n=int(input("Entre num"))
# a=1
# count=0
# while a<=n:
#     count+=1
#     print(count)
#     a+=1
# n=int(input("Entre num"))
# a=1
# while a<=n:
#     if a%2==0:
#         print(a)
#     a+=1


# a=0
# while a<=25:
#     print(a)
#     a+=5
# a=2
# while a<=12:
#     if a%2==0:
#         print(a)
#     a+=1
# a=1
# while a<=19:
#     print(a)
#     a+=3
# a=20
# while a>=10:
#     print(a)
#     a-=2


# # n=int(input("Entre num"))
# # a=1
# # sum=0
# # while a<=n:
# # #     sum+=a
# # #     print(sum)
# # #     a+=1
# # n=int(input("Entre num"))
# # a=1
# # sum=0
# # while a<=n:
# #     if a%2==0:
# #         sum+=1
# #     print(sum)
# #     a+=1
# n=int(input("Entre num"))
# a=1
# while a<=n:
#     print(n*a)
#     a+=1

# n=int(input("Entre num"))
# a=1
# sum=0
# while a<=n:
# #     sum+=a
# #     print(sum)
# #     a+=1
# n=int(input("Entre num"))
# a=1
# sum=0
# while a<=n:
#     if a%2==0:
#         sum+=1
#     print(sum)
#     a+=1


# n=int(input("Entre num"))
# a=1
# fact=1
# while a<=n:
#     fact=fact*a
#     print(fact)
#     a+=1

# n=int(input("Entre num"))
# a=1
# sum=0
# while a<=n:
#     sum+=a
#     print(sum)
#     a+=1
# n=int(input("Entre num"))
# a=2
# sum=0
# while a<=n:
#     if a%2==0:
#         sum+=a
#     print(sum)
#     a+=2
# n=int(input("Entre num"))
# a=1
# count=0
# while a<=n:
#     count+=1
#     print(count)
#     a+=1


# # a = "Programming"
# # print(a[0])
# a = "Abhishek"
# print(a[-1:-4:-1])
# a = "Education"
# print(a[0:9:2])
# a = ""
# b = "Python"
# print(bool(a),bool(b))
# print(10//3, 10%3)
# print(2**4)
# print(5>3 and 10<20)
# n=int(input("num"))
# if n > 0:
#     print("p")
# elif n<0:
#     print("n")
# else:
#     print("Zero")
# n=int(input("num"))
# if n%2==0:
#     print("p")
# else:
#     print("n")
# n=int(input("num"))
# sum=0
# for i in range(1,n+1):
#     sum+=i
# # print(sum)
# n=int(input("num"))
# fact=1
# for i in range(1,n+1):
#     fact*=i
# print(fact)
# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()
# a=10
# while a>=5:
#     print(a)
#     a-=1
# n=int(input("num"))
# a=1
# sum=0
# while a<=n:
#     sum = sum +a
#     print(sum)
#     a+=1
# n=int(input("num"))
# a=1
# fact=1
# while a<=n:
#     fact=fact *a
#     print(fact)
#     a+=1


# def sum(a,b):
#     print(f" sum is {a+b}")
# sum(1,3)
# sum(3,5)
# def hello(name,age):
#     print(f"my name is {name} and age is {age}")
# hello(age=20,name="Abhishek")
# def p(a,b=3):
#     print(f"sum is {a+b}")
# p(1,7)
# # def hello():
# #     return "how are you "
# # print(hello)

# def python():
#     print(f"Hello World ")
# python()

# def python():
#     print("Hello")
# python()
# python()
# python()
# def abhi(a,b):
#     print(f"Sum is {a+b}")
# abhi(10,20)
# def abhi(a,b):
#     print(f"Sum is {a*b}")
# abhi(5,5)
# def abhi():
#     print("*****")
# # abhi()
# for i in range(1,11):
#     print(i)
# a=1
# while a<=10:
#     print(a)
#     a+=1
# for i in range(10,0,-1):
#     print(i)
# for i in range(0,5):
#     print(i)
# print("Done!")
# n=int(input("Enter num"))
# sum =0
# for i in range(1,n+1):
#     sum+=i
# print(sum)
# n=int(input("Enter num"))
# sum=0
# a=1
# while a<=n:
#     sum+=a
#     print(sum)
#     a+=1
# n=int(input("Enter num"))
# for i in range(1,11):
#     print(n*i)
# n=int(input("Enter num"))
# a=1
# while a<=10:
#     print(n*a)
#     a+=1
# n=int(input("Enter num"))

# for i in range(1,n+1):
  
#     print(f"Current Number is : {i} and the cube is 1 {i**3}")
# numbers = [12, 75, 150, 180, 145, 525, 50]
# for i in numbers:
#     if i>500:
#         break
#     if i>150:
#         continue
#     if i%5==0:
# #         print(i)
# list1 = [10, 20, 10, 30, 10, 40, 50]
# target=10
# count=0
# for i in list1:
#     if i == target:
#         count+=1
# print(count)
# my_list = [10, 20, 30, 40, 50, 60, 70, 80, 90, 100]
# for i in my_list:
#     if i%20==0:
#         print(i)
# list1 = [10, 20, 30, 40, 50]
# list1.reverse()
# print(list1)
# p="Python"
# new=""
# for i in p:
#     new = i + new
# print(f"org is {p}")
# print(f"new is {new}")
# a="Loops are Fun!"
# count=0
# for i in a:
#     if i in "a,i,o,u,e":
#         count+=1
# print(count)
# num = int(input(76542))
# print(num[::-1])
# n=int(input("Enter num"))
# for i in range(1,n+1):
#     print(i)
# for i in range(1,6):
# #     print(i)
# for i in range(5,0,-1):
# #     print(i)
# for i in range(0,11):
# #     if i%2==0:
# # #         print(i)
# # for i in range(1,10):
# #     if i%2!=0:
# #         print(i)
# m=int(input("Entre num "))
# for i in range(1,m+1):
#     print(i)
# m=int(input("Entre num "))
# for i in range(1,m+1):
#     print(f"your num  is {i} and no. is {i+1}")
# n=int(input("Entre num "))
# sum=0
# for i in range(1,n+1):
#     sum+=i
# print(sum)
# m=int(input("Entre num "))
# sum=0
# for i in range(1,m+1):
#     if i%2==0:
#         sum+=i
# # print(sum)
# # n=int(input("Entre num "))
# # count=0
# # for i in range(1,n+1):
# #     if i%2==0:
# #         count+=1
# # print(count)
# n=int(input("Entre num "))
# count=0
# for i in range(1,n+1):
#     if i%2!=0:
#         count+=1
# print(count)
# n=int(input("Entre num "))
# fact=1
# for i in range(1,n+1):
#     fact*=i
# print(fact)
# for i in range(5):
#     for j in range(i+1):
#         print("*",end="")
#     print()
# for i in range(5,0,-1):
#     for j in range(i):
# #         print("*",end="")
# #     print()
# v=int(input("1234"))
# sum=0
# for i in v:
#     sum+=i
# print(sum)



# def hello():
#     return "hellooo"
# print(hello())

# def abhi():
#     print("Hello World")
# abhi()

# def abhi():
#     print("Python")
# abhi()

# abhi()
# # abhi()
# def abhi():
#     print("Abhishek")
# abhi()
# def show_star():
#     print("****")
# show_star()
# def greet(name):
#     print(f"Hello {name}")
# greet("Abhishek")
# def add(a, b):
#     print(f"sum is {a+b}")
# add(10,20)
# def add(a, b):
#     print(f"multiply is {a*b}")
# add(5,4)
# def square(n):
# #     print(f"squar is {n**2}")
# # square(6)
# def table(n):
#     for i in range(1,11):
#         print (n*i)
# table(5)
# def count_to_n(n):
#     for i in range(1,6):
#         print(i)
# count_to_n(5)
# def even_numbers(n):
#     for i in range(2,n+2):
#         if i%2==0:
#             print(i)
# even_numbers(10)
# def stars(n):
#     for i in range(1,n+1):
#         print("*",end="")
# stars(4)



# def age(x):
#     print(f"You are {x} years old")
# age(30)

# def full_name(first, last):
#     print(first,last)
# full_name("Abhishek","Malviy")

# def even_odd(n):
#     if n%2==0:
#         print("Even")
#     else:
#         print("odd")
# even_odd(8)
# even_odd(7)

# def biggest(a,b):
#         print(max(a,b))
# biggest(10,20)

# def power(a,b):
#     print(a**b)
# power(2,5)

# def table(n):
#     for i in range(1,11):
#         print(f"5 x {i} = {n*i}")
# table(5)

# def factorial(n):
#     fact=1
#     for i in range(1,n+1):
#         fact*=i
#     print(fact)
# factorial(5)

# def count_vowels(text):
#     count=0
#     for i in text:
#         if i in "a,i,o,u,e":
#             count+=1
#     print(count)
# count_vowels("Programming")

# def reverse_string(text):
#     print(text[::-1])
# reverse_string("python")

# def hello():
#     return "hellooo"
# print(hello())

# def square(n):
#     print(n**2)
# square(5)
# def cube(n):
#     print(n**3)
# cube(4)
# def square(n):
#     print(n*n)
# square(7)
# def is_even(n):
#     return n%2==0
# print(is_even(7))
# print(is_even(8))



# def abhi(a,b):
#     return a+b
# r=abhi(10,20)
# print(r)
# def square(n):
#     return n**2
# a=square(6)
# print(a)
# def cube(n):
#     return n**3
# s=cube(3)
# print(s)
# def is_even(n):
#     return n%2==0
# print(is_even(2))
# print(is_even(3))
# def biggest(a, b):
#     return max (a,b)
# print(biggest(10,25))
# def name(name):
#     return name
# print(name("Abhishek"))
# def multiply(a, b):
#     return a*b
# a=multiply(5,4)
# print(a+10)
# def age():
#     return age
# a=age(18)
# print(age()+2)


# a=[1,2,3,4,5]
# for i in range(len(a)):
#     print(a[i])
# a=[1,2,3,4,5]
# a.append(6)
# print(a)
# r=[1,2,3,4,5]
# r.insert(2,2)
# print(r)
# t=[1,2,3,4,5]
# t.remove(2)
# print(t)
# t=[1,2,-3,4,5,-3,-6]
# print("psitive")
# for i in t:
#     if i>0:
#         print(i)
# print("negetive")
# for i in t:
#     if i<0:
#         print(i)
# t=[1,2,3,4,5]
# sum=0
# for i in t:
#     sum+=i
# print(sum/len(t))
# t=[1,2,3,4,5,67]
# largest=t[0]
# index=0
# for i in range(len(t)):
#     if t[i] >largest:
#         largest=t[i]
#         index = i
# print(f"is {largest} and is {index}")
# t=[1,2,3,4,5,67]
# larg=t[0]
# lrag2=t[0]
# for i in t:
#     if i>larg:
#         lrag2 = larg
#         larg = i
#     elif i>lrag2:
#         lrag2 = i
# print(lrag2,larg)
# t=[1,2,3,4,5]
# for i in range(len(t)-1):
#     if t[i] < t[i+1]:
        
#         continue
#     else:
#         print("not")
#         break
# else:
#     print("sorted")



# a = [10, 20, 30, 40, 50]
# for i in a:
#     print(i)
# a = [1, 2, 3, 4, 5]
# sum=0
# for i in a:
#     sum+=i
# print(sum)
# a = [10, 20, 30, 40, 50]
# sum=0
# for i in a:
#     sum+=i
# print(sum/len(a))
# a = [1, 2, 3, 4, 5]
# new=[]
# for i in a:
# #     print(i**2)
# #     new.append(i)
# # print(new)


# # a = 15
# # b = 4
# # print(a+b,a-b,a*b,a/b,a//b,a%b)
# n=int(input("Enter num"))
# # if n > 0:
# #     print("P")
# # elif n<0:
# #     print("N")
# # else:
# #     print("Zero")
# n=int(input("Enter num"))
# fact=1
# for i in range(1,n+1):
#     fact*=i
# print(fact)
# n=int(input("Enter num"))
# sum=0
# for i in range(1,n+1):
#     sum+=i
# print(sum)
# n=int(input("Enter num"))
# a=1
# while a<=n:
#     print(a)
#     a+=1
# a = "Programming"
# c= "m"
# count=0
# for i in a:
#     if i == c:
#         count+=1
# print(count)
# a = "Abhishek"
# print(a[::-1])
# def square(n):
#     return n**2
# a=(square(5))
# print(a)
# def table(n):
#     for i in range(1,11):
#         print(n*i)
# table(5)
# a = [10, 20, 30, 40, 50]
# sum=0
# for i in a:
#     sum+=i
# print(sum)
# a = [5, 8, 2, 9, 1]
# largest=[]
# for i in a:
#     if i == max(a) :
#         largest.append(i)
# print(largest)
# a = [10, 20, 30, 20, 40, 20]
# target=20
# count=0
# for i in a:
#     if i ==target:
#         count+=1
# # print(count)


# # a = [10, 20, 30, 20, 40, 20]
# # larg=a[0]
# # for i in range(len(a)):
# #     if a[i] > larg:
# #         larg = a[i]
# #         index = i
# # print(larg,index)
# a = [10, 20, 30, 20, 40, 20]
# larg=a[0]
# larg2 =a[0]
# for i in a:
#     if i > larg:
#         larg2 = larg
#         larg= i
#     elif i>larg2:
#         larg2  = i
# print(larg2,larg)
# a = [10, 20, 30]
# for i in  range(len(a)-1):
#     if a[i] < a[i+1]:
#         continue
#     else:
#         print("not")
#         break
# else:
#     print("yss")


# a = [12, 5, 8, 20, 3]
# for i in a:
#     if i == min(a):
# #         print(i)
# a = [10, 20, 30, 40, 50]
# print(a[::-1])
# a = [2, 4, 6, 8]
# for i in a:
#     print(i*i)
# a = [1, 2, 3, 4, 5]
# new=[]
# for i in a:
#     i*2
#     new.append(i)
# print(new)
# a = [11, 22, 33, 44, 55]
# for i in a:
#     if i %2!=0:
#         print(f"all odd {i}")
# a = [1, 2, 3, 2, 4, 2, 5]
# target=2
# count=0
# for i in  a:
#     if i == target:
#         count+=1
# print(count)
# a = [10, 20, 30, 40, 50]
# for i in a:
#     if i == 30:
#         print("found")
#     else:
#         print("not found")
# a = [5, 2, 9, 1, 7]
# for i in a:
#     if i == max(a):
#         print("lagest",i)
#     else:
#         print("smalest",i)
# a = [1, 2, 3, 4, 5]
# for i in a:
#     print(i*2)

# a = [6,1, 2, 3, 4, 5]
# d= sorted(a)
# print(d)
# a = [6,1, 2, 3, 4, 5]
# a.revers
# print(a)
# a = [6,1, 2, 3, 4, 5]
# a.pop(5)
# print(a)


# a = [6,1, 2, 3, 4, 5]
# print(a)
# a = [6,1, 2, 3, 4, 5]
# sum=0
# for i in a:
#     sum+=i
# print(sum/len(a))
# print(sum)
# a e()= [6,1, 2, 3, 4, 5]
# largest= a[0]
# for i in a:
#     if a[0] > largest:
#         largest = i
# #         # index=i
# # print(largest)
# # a = [6,1, 2, 3, 4, 5]
# # smalest= a[0]
# # for i in a:
# #     i > smalest
# #     smalest = i
# # print(smalest)
# # a = [6,1, 2, 3, 4, 5]
# # count=0
# # for i in a:
# #     count+=1
# # print(count)
# # a = [6,1, 2, 3, 4, 5]
# # new=[]
# # for i in a:
# #     if i%2==0:
# #         new.append(i)
# # print(new)
# # a = [6,1, 2, 3, 4, 5]
# # new=[]
# # for i in a:
# #     if i%2!=0:
# #         new.append(i)
# # print(new)
# a = [6,1, 2, 3, 4, 5]
# sum=0
# for i in a:
#     if i%2==0:
#         sum+=i
# print(sum)
# a = [6,1, 2, 3, 4, 5]
# sum=0
# for i in a:
#     if i%2!=0:
#         sum+=i
# print(sum)
# a = [6,1, 2, 3, 4, 5]
# count=0
# for i in a:
#     if i%2==0:
#         count+=1
# print(count)
# a = [6,1, 2, 3, 4, 5,7]
# count=0
# for i in a:
#     if i%2!=0:
#         count+=1
# print(count)
# a = [6,1, 2, 3, 4, 5,7]
# a.reverse()
# print(a)
# a = [6,1, 2, 3, 4, 5,7]
# a.copy()
# print(a)
# a = [6,1, 2, 3, 4, 5,7]
# new=[]
# for i in a:
#     new.append(i*2)
# print(new)
# a = [6,1, 2, 3, 4, 5,7]
# new=[]
# for i in a:
#     new.append(i**2)
# print(new)
# a = [6,1, 2, 3, 4, 5,7]
# new=[]
# for i in a:
#     i * 2
#     new.append(i*3)
# print(new)
# a = [6,1, 2, 3, 4, 5,7]
# target = 3
# for i in a:
#     if i == 3:
#         print("yss its present")
# a = [6,1, 2, 3, 4, 5,7,-1]
# count=0
# for i in a:
#     if i>0:
#         count+=1
# print(count)
# a = [6,1, 2, 3, 4, 5,7]
# larg=a[0]
# larg2=a[0]
# for i in a:
#     if a[0] > larg:
#         larg = i
#         larg>larg2
# print(larg2)
# a = [6,1, 2, 3, 4, 5,7]
# largest = a[0]
# second_largest=a[0]
# for i in a:
#     if i > largest:
#         second_largest = largest
#         largest = i
#     elif i > second_largest:
#         second_largest = i
# print(second_largest,largest)

# a = [6,1, 2, 3, 4, 5,7]
# smalest=[0]
# second_smalest=[0]
# for i in a:
#     if i < smalest:
#         second_smalest = smalest
#         smalest = i
#     elif i < second_smalest:
#         second_smalest = i
# print(second_smalest,smalest)

# a = [6,1, 2, 3, 4, 5,7]
# a.sort()
# print(a)
# a = [6,1, 2, 3, 4, 5,7]
# # print(a[0])
# a = [6,1, 2, 3, 4, 5,7]
# a.append(9)
# # print(a)
# a = [6,1, 2, 3, 4, 5,7]
# a.remove(6)
# print(a)
# a = [6,1, 2, 3, 4, 5,7]
# a.reverse()
# print(a)
# numbers = [10, 20, 30, 40, 50]
# print(numbers[2])
# numbers = [10, 20, 30, 40, 50]
# print(len(numbers))
# numbers = []
# if len(numbers)==0:
# #     print("E")
# # else:
# #     print("Not E")

# n = [10, 20, 30, 40, 50]
# largest= n[0]
# for i in n:
#     if i > largest :
#         largest = i
# print(largest)

# n= [10, 20, 30, 40, 50]
# smalest = n[0]
# second_smalest=n[0]
# for j in n:
#     if j < smalest:
#         smalest = j
# print(smalest)

# s = [10, 20, 30, 40, 50]
# largest=s[0]
# second=s[0]
# for i in s:
#     if i>largest:
#         second=largest
#         largest =i
# print(second)

# a = [10, 50, 20, 80, 40]
# largest=a[0]
# second=a[0]
# for i in a:
#     if i>largest:
#        second = largest
#        largest = i
# print(second)
# a = [12, 45, 8, 30, 22]
# largest=a[0]
# second=a[0]
# for i in a:
#     if i > largest:
#         second=largest
#         largest=i
# print(f"1st largest is {largest} and 2nd largest is {second}")
# a = [10, 50, 20, 80, 40]
# largest = a[0]
# for i in a:
#     if i >largest:
#         largest=i
# print(largest)
# a = [10, 50, 20, 80, 40]
# smalest=a[0]
# for i in a:
#     if i<smalest:
#         smalest=i
# print(smalest)
# a = [7, 25, 12, 40, 18]
# Largest =a[0]
# Second_Largest =a[0]
# for i in a:
#     if i >Largest:
#         Second_Largest=Largest
#         Largest=i
#         Second_Largest=i
#         print(Second_Largest)
# a = [7, 25, 12, 40, 18]
# largest=a[0]
# second=a[0]
# for i in a:
#     if i >largest:
#         second=largest
#         largest=i
# print(second,largest)



# a = [10, 30, 20]
# largest=a[0]
# second=a[0]
# for i in a:
#     if i > largest:
#         second=largest
#         largest=i
# print(second,largest)


# a = [15, 40, 25]
# largest=a[0]
# second=a[0]
# for i in a:
#     if i > largest:
#         largest=second
#         second=i
# # print(largest,second)
# a = [8, 50, 30, 20]
# largest=a[0]
# second=a[0]
# for i in a:
#     if i >largest:
#         largest=second
#         second=i
# print(largest,second)

# a = [100, 10, 80, 20]
# largest=0
# second=0
# for i in a:
#     if i>=largest:
#         largest=i
#     elif i <= largest and i > second:
#         second=i
# print(second,largest)

# # for i in range(1,6):
# #     for j in range(i+1):

# # n=int(input("Enter num"))
# # new=[]
# # for i in range(n+1):
# #     ele = input("enter element for list")
# #     new.append(ele)
# # print(new)

# a = [1,2,3,"5678","p]=w028e",3.3]
# st=[]
# iintt=[]
# flo=[]
# for i in a:
#     if type(i) == int:
#         iintt.append(i)
#     elif type(i) == str:
#         st.append(i)
#     elif type(i) == float:
#         flo.append(i)
        
# print(st)
# print(iintt)
# print(flo)

# for i in range(5):
#     for j in range(i+1):
#         print(" * ",end="")
#     print()

# for i in range(5):
#     for j in range(8):
#         if (i == 1 and j == 4) or (i==2 and j==3) or (i==2 and j==5) or (1==3 and j==2) or (i==3 and j==6) or (i==4 and j==1) or (i==4 and j==2) or (i==4 and j==3) or (i==4 and j==4) or (i==4 and j==5) or (i==4 and j==6) or (i==4 and j==7):
#             print("*",end= " ")
#         elif (i==1 and j==1) or (i==1 and j==2) or (i==1 and j==3) or (i==2 and j==1) or (i==2 and i==2) or (i==3 and i==3) or (i==3 and i==3) or (i==3 and i==4) or (i==3 and i==5):
#             print(" ",end="")
#     print()       
    
    
