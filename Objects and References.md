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


print("")
print("Aliases")


	lst3 = [1, 5, 9]
	lst4 = lst3
	print(lst3, lst4)

	lst3[1] = 17
	print(lst3, lst4)
	
	Output:
	[1, 5, 9] [1, 5, 9]
	[1, 17, 9] [1, 17, 9]

print("")
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


print("")
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
