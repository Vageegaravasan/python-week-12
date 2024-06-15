1.
a=int(input())
s=0
for i in range(a):
    if(a==2**i):
        s=s+1
if(1<=s):
    print("True")
else:
    print("False")

2.
def cat_books():
    genres = {}

    while True:
        try:
            ln = input().strip()
            if ln == "":
                raise EOFError
            b, g = ln.split(', ')
            
            if g not in genres:
                genres[g] = []
            genres[g].append(b)
        
        except EOFError:
            for g in genres:
                bs = ', '.join(genres[g])
                print(f"{g}: {bs}")
            break

if __name__ == "__main__":
    cat_books()

3.
X = int(input())
shoe_sizes = list(map(int, input().split()))
inventory = {}

for size in shoe_sizes:
    if size in inventory:
        inventory[size] += 1
    else:
        inventory[size] = 1

N = int(input())
total_revenue = 0

for _ in range(N):
    size, price = map(int, input().split())
    if size in inventory and inventory[size] > 0:
        total_revenue += price
        inventory[size] -= 1

print(total_revenue)


4.
def calculate_average_marks(N, column_names, student_data):
    marks_index = column_names.index("MARKS")
    total_marks = 0
    valid_students_count = 0
   
    for student in student_data:
        if len(student) > marks_index and student[marks_index].isdigit():
            total_marks += int(student[marks_index])
            valid_students_count += 1
           
    if valid_students_count == 0:
        return 0  # No valid students with marks found
   
    average_marks = total_marks / valid_students_count
    return average_marks

if __name__ == "__main__":
    N = int(input())
    column_names = input().split()
    student_data = []
    for _ in range(N):
        student_info = input().split()
        student_data.append(student_info)
   
    average_marks = calculate_average_marks(N, column_names, student_data)
    print("{:.2f}".format(average_marks))

5.
a=int(input())
b=[int(x) for x in input().split()]
c=int(input()) 
s=0
for i in range(0,a):
    for j in range(0,a):
        if abs(b[i]-b[j])==c and i<j:
     
            s+=1
print(s)
