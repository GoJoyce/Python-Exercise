"""
Tuple examples.
"""

# Lists and tuples are both sequences
	print("Sequences")
	print("=========")
	lst = [1, 5, 7, 3]
	tup = (1, 5, 7, 3)

	print(lst, tup)
	print(lst[2])
	print(tup[2])
	print(tup[:2])
	print(tup[2:3])
	
	Output:
	Sequences
	=========
	[1, 5, 7, 3] (1, 5, 7, 3)
	7
	7
	(1, 5)
	(7,)


# Tuples are immutable
	lst[0] = 9
	print(lst)
	# tup[0] = 9
	# print(tup)

	Output: 
	[9, 5, 7, 3]
	Error

print("")
print("Tuple Methods")
print("=============")

	print(tup.index(7))
	print(tup.count(4))

	Output:
	Tuple Methods
	=============
	2
	0

print("")
print("Iteration")
print("=========")

	for item in tup:
			print(item)


	Output:
	Iteration
	=========
	1
	5
	7
	3

print("")
print("Conversion")
print("==========")

	lst2 = [8, 6, 4, 8, 2]
	print(lst2)
	tup2 = tuple(lst2)
	print(tup2)
	# tup2[3] = 7   #result in an error
	lst3 = list(tup2)
	print(lst3)
	lst3[2] = 7
	print(lst2, tup2, lst3)


	Output:
	Conversion
	==========
	[8, 6, 4, 8, 2]
	(8, 6, 4, 8, 2)
	[8, 6, 4, 8, 2]
	[8, 6, 4, 8, 2] (8, 6, 4, 8, 2) [8, 6, 7, 8, 2]
