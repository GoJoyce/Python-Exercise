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
	
	
	
Practice 1: 

	"""
	Simple task list.
	"""

	def new(tasklist, task):
	    """Add new task"""
	    tasklist.append(task)

	def remove_by_num(tasklist, tasknum):
	    """Remove by number"""
	    if tasknum > 0 and tasknum <= len(tasklist):
		tasklist.pop(tasknum - 1)

	def remove_by_name(tasklist, taskname):
	    """Remove by name"""
	    if taskname in tasklist:
		tasklist.remove(taskname)

	def printlist(tasklist):
	    """Print task list"""
	    print("========================")
	    num = 1
	    for task in tasklist:
		print(num, task)
		num += 1
	    print("========================")

	def run():
	    """Manipulate task list"""
	    tasks = []
	    new(tasks, 'Teach Class')
	    printlist(tasks)

	    new(tasks, 'Buy some ties')
	    new(tasks, 'Learn Python')
	    printlist(tasks)

	    new(tasks, 'Build new task list')
	    printlist(tasks)

	    remove_by_num(tasks, 1)
	    printlist(tasks)
	    remove_by_num(tasks, 2)
	    printlist(tasks)

	    remove_by_name(tasks, 'Buy some ties')
	    printlist(tasks)


Practice 2: Flatten a nested list

	def flatten(nested_list):
	    flattened_list = []
	    for sub_list in nested_list:
		flattened_list.extend(sub_list)
	    return flattened_list

	
	print(flatten([]))
	print(flatten([[]]))
	print(flatten([[1, 2, 3]]))
	print(flatten([["cat", "dog"], ["pig", "cow"]]))
	print(flatten([[9, 8, 7], [6, 5], [4, 3, 2], [1]]))


	# Output
	#[]
	#[]
	#[1, 2, 3]
	#['cat', 'dog', 'pig', 'cow']
	#[9, 8, 7, 6, 5, 4, 3, 2, 1]


Practice 3: Remove deplicates from a list while preserving the order of items

	myList = [1, 2, 3, 1, 2, 5, 6, 7, 8]
	cleanlist = []
	#cleanlist.append(x) for x in myList if x not in cleanlist


	def remove_duplicates(items):
	    no_duplicates = []
	    for item in items:
		if item not in no_duplicates:
		    no_duplicates.append(item)
	    return no_duplicates



	print(remove_duplicates([]))
	print(remove_duplicates([1, 2, 3, 4]))
	print(remove_duplicates([1, 2, 2, 3, 3, 3, 4, 5, 6, 6]))
	print(remove_duplicates(["cat", "dog", "cat", "pig", "cow", "cat", "pig", "pug"]))


	# Output
	#[]
	#[1, 2, 3, 4]
	#[1, 2, 3, 4, 5, 6]
	#['cat', 'dog', 'pig', 'cow', 'pug']
