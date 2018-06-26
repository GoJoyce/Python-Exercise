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
