"""
List Objects and References.
"""

print("Look Alikes")

	lst1 = [7, 3, 2]
	lst2 = [7, 3, 2]
	print(lst1, lst2)



	lst1[1] = -8
	print(lst1, lst2)
	
	Output:
	[7, 3, 2] [7, 3, 2]
	[7, -8, 2] [7, 3, 2]


print("Aliases")


	lst3 = [1, 5, 9]
	lst4 = lst3
	print(lst3, lst4)

	lst3[1] = 17
	print(lst3, lst4)
	
	Output:
	[1, 5, 9] [1, 5, 9]
	[1, 17, 9] [1, 17, 9]


print("Copies")

	lst5 = [8, 9, 4]
	# This makes a shallow copy
	lst6 = list(lst5)
	print(lst5, lst6)

	lst5[1] = -2
	print(lst5, lst6)

	Output:
	[8, 9, 4] [8, 9, 4]
	[8, -2, 4] [8, 9, 4]


print("Function Arguments")

	def mutate_list(alist):
			"""
			Add an element to the input.
			"""
			alist.append(42)

	lst7 = [1, 2, 3]
	print(lst7)
	mutate_list(lst7)
	print(lst7)

	Output:
	[1, 2, 3]
	[1, 2, 3, 42]



"""
Some simple examples of reference issues for lists
"""

#Part 1 - references to two distinct objects
	iipp1_instructors = ["Joe", "Scott", "John", "Stephen"]
	iipp2_instructors = ["Joe", "Scott", "John", "Stephen"]
	print(iipp1_instructors)
	print(iipp2_instructors)
	
	output:
	['Joe', 'Scott', 'John', 'Stephen']
	['Joe', 'Scott', 'John', 'Stephen']

#Mutate one of the two objects
	iipp2_instructors.pop()
	print(iipp1_instructors)
	print(iipp2_instructors)
	print()

	output:
	['Joe', 'Scott', 'John', 'Stephen']
	['Joe', 'Scott', 'John']

#Part 2 - two references to the same object

	iipp1_instructors = ["Joe", "Scott", "John", "Stephen"]
	iipp2_instructors = iipp1_instructors
	print(iipp1_instructors)
	print(iipp2_instructors)
	
	output:
	['Joe', 'Scott', 'John', 'Stephen']
	['Joe', 'Scott', 'John', 'Stephen']

#Mutate the object
	iipp2_instructors.pop()
	print(iipp1_instructors)
	print(iipp2_instructors)
	print()
	
	output:
	['Joe', 'Scott', 'John']
	['Joe', 'Scott', 'John']


#Part 3 - two references to an object and a copy of the object

	iipp1_instructors = ["Joe", "Scott", "John", "Stephen"]
	iipp2_instructors = list(iipp1_instructors)
	print(iipp1_instructors)
	print(iipp2_instructors)
	
	output:
	['Joe', 'Scott', 'John', 'Stephen']
	['Joe', 'Scott', 'John', 'Stephen']


#Mutate the one of the objects
	iipp2_instructors.pop()
	print(iipp1_instructors)
	print(iipp2_instructors)

	output:
	['Joe', 'Scott', 'John', 'Stephen']
	['Joe', 'Scott', 'John']
