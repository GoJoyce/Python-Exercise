"""
#Question 1 - Create a list formed by 8 copies of True and 8 copies of False
"""

	truefalse_list = 8 * [True] + 8 * [False]
	print(truefalse_list)

	#Output
	#[True, True, True, True, True, True, True, True, False, False, False, False, False, False, False, False]


"""
#Question 2 - Create a list of words form a string consisting of words separated by spaces
"""

	quote = "Bring me a shrubbery"
	word_list = quote.split(" ")
	print(word_list)

	#Output
	#['Bring', 'me', 'a', 'shrubbery']


"""
#Question 3- Count the number of times that a word appears in string of text
"""

	def word_count(text, word):
	    """
	    Given a string text consist of words separate by spaces and a string word
	    (with no spaces), return the number of times that word appears in the text
	    """
	    word_list = text.split(" ")
	    return word_list.count(word)



	print(word_count("this pigdog is a fine pigdog", "pigdog"))
	print(word_count("this pigdog is not a dog", "dog"))
	print(word_count("this pigdog is not a pig", "pigdog"))

	# Output
	#2
	#1
	#1



"""
#Question 4 - Analyze an example of a list reference situation
"""


	list1 = [2, 3, 5, 7, 11, 13]

	list2 = list1

	print(list1)
	print(list2)

	list2[0] = 0

	print(list1)
	print(list2)


	#Answer - list1 and list2 are references to the same list
	#Updating an item in one list mutates the other list


	#Output
	#[2, 3, 5, 7, 11, 13]
	#[2, 3, 5, 7, 11, 13]
	#[0, 3, 5, 7, 11, 13]
	#[0, 3, 5, 7, 11, 13]
	
	
"""
#Question 5 - Analyze another example of a list reference situation
"""

	list1 = [2, 3, 5, 7, 11, 13]

	list2 = list(list1)

	print(list1)
	print(list2)

	list2[0] = 0

	print(list1)
	print(list2)


	# Answer - list1 and list2 are two references to distinct lists
	# Updating an item in one list does not affect the second list


	# Output
	#[2, 3, 5, 7, 11, 13]
	#[2, 3, 5, 7, 11, 13]
	#[2, 3, 5, 7, 11, 13]
	#[0, 3, 5, 7, 11, 13]



"""
#Question 6 - Compute the largest number in a list
"""

	def list_max(numbers):
	    maximum = numbers[0]
	    for number in numbers[1 :]:
		if number > maximum:
		    maximum = number
	    return maximum

	print(list_max([4]))
	print(list_max([-3, 4]))
	print(list_max([5, 3, 1, 7, -3, -4]))
	print(list_max([1, 2, 3, 4, 5]))


	# Output
	#4
	#4
	#7
	#5



"""
#Question 7 - Take a list of integers and concatenate their digits
"""

	def concatenate_ints(int_list):
	    digits = ""
	    for number in int_list:
		digits += str(number)
	    return int(digits)

	print(concatenate_ints([4]))
	print(concatenate_ints([4, 0, 4]))
	print(concatenate_ints([123, 456, 789]))
	print(concatenate_ints([32, 796, 1000]))


	# Output
	#4
	#404
	#123456789
	#327961000
