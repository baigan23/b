def longword():
	str=input("enter string:")
	s=str.split()
	max=0
	for ele in  s:
		if len(ele)>max:
			max=len(ele)
			word=ele
	print("Longest word is",word)
	print("Length is:",len(word))

def palindrome():
	str=input("enter string:")
	s=str[::-1]
	print(s)
	if(str==s):
		print("String is palindrome")
	else:
		print("String is not palindrome")

def freq_char():
	str=input("enter string:")
	ch=input("enter character to check:")
	count=0
	for i in range(len(str)):
		if(str[i]==ch):
			count+=1
	print("character",ch,"occurs",count,"times in string")

def display_index_of_first_appearance_of_the_substring() :
   M = input("Enter the main string : ")
   S = input("Enter the sub string to check : ")
   print("Main String : %s"%M)
   print("Substring String : %s"%S)
   L1 = len(M)
   L2 = len(S)
   if(L1 >= L2) :
      for i in range((L1 - L2 + 1)) :
         flag = 1
         for j in range(L2):
            if(M[i+j] != S[j]) :
               flag = 0
               break
         if(flag == 1) :
            print("Substring %s found at index %d\n\n"%(S,i))
            break;
      if(flag == 0) :
         print("Substring not found in the main string\n\n")
   else :
      print("Substring is greater than main string\n\n")	
def occwords():
        print("To count the occurance of each word in a given string:")
        str=input("Enter the sring:")
        l=str.split()
        arr=[1 for i in range(len(l))]
        for i in range(len(l)):
                for j in range(i+1,len(l)):
                        if l[i]==l[j] and arr[j]!=-1:
                                arr[i]=arr[i]+1
                                arr[j]=-1
        for i in range(len(arr)):
                if arr[i]!=-1:
                        print(l[i],arr[i])


def main():
    while True:
        print("\n1.longest word")
        print("\n2.palindrome")
        print("\n3.charc freq")
        print("\n4.index of first substring")
        print("\n5.occur of each word")
        print("\n6.exit")
        ch=int(input("Enter choice:"))
        if ch==6:
            quit()
        elif ch==1:
            longword()
        elif ch==2:
            palindrome()
        elif ch==3:
            freq_char()
        elif ch==4:
            display_index_of_first_appearance_of_the_substring() 
        elif ch==5:
            occwords()
main()