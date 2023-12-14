def selection_sort(arr):
	for i in range(len(arr)):
		mindex=i
		for j in range(i+1 , len(arr)):
			if(arr[j]<arr[mindex]) :
				mindex=j
		
		temp=arr[i]
		arr[i]=arr[mindex]
		arr[mindex]=temp
	
	return arr
	
A=[]
n=int(input("Enter no of students in array : "))
print("Enter students percentage")
for i in range(n):
	x=float(input())
	A.append(x)

bucket=[]
Nb=10
bucket=[[]for i in range(Nb) ]
print("\n")


for i in A:
	Bnum=int(i/Nb)
	bucket[Bnum].append(i)


sorteddata=[]
for i in range(Nb):
	bucket[i]=selection_sort(bucket[i])
	sorteddata= sorteddata+bucket[i]
 
 
print("Sorted array is :-  \n")
print(sorteddata)
print("\n")

print("Top five percentage:-")
for i in range(5):
	print(sorteddata[len(sorteddata)-i-1])