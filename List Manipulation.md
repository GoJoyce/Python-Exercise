"""
Mutating Lists.
"""

#print("Updating Items")
#print("==============")

	lst = list(range(5))
	print(lst)

	lst[1] = -7
	lst[3] = 17
	print(lst)

	#Output: Updating Items
	==============
	[0, 1, 2, 3, 4]
	[0, -7, 2, 17, 4]



#print("Adding Items")
#print("============")

	lst.append(42)
	print(lst)

	lst.insert(2, 75)
	print(lst)

	lst2 = [-56, 27, 8]
	lst.extend(lst2)
	print(lst)
	lst.append(lst2)
	print(lst)


	#Output:Adding Items
	============
	[0, -7, 2, 17, 4, 42]
	[0, -7, 75, 2, 17, 4, 42]
	[0, -7, 75, 2, 17, 4, 42, -56, 27, 8]
	[0, -7, 75, 2, 17, 4, 42, -56, 27, 8, [-56, 27, 8]]

print("Removing Items")
print("==============")

	lst.pop()  #remove the last thing on the list
	print(lst)
	lst.pop(3)
	print(lst)

	#Output: Removing Items
	==============
	[0, -7, 75, 2, 17, 4, 42, -56, 27, 8]
	[0, -7, 75, 17, 4, 42, -56, 27, 8]
