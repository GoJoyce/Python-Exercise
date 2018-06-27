In Python, files are opened using the open function:
  
	# The name of the file to open
	filename = "starwars.txt"

	# The mode in which to open it (read, text)
	mode = "rt"
	r = read
	t = text
	b = binary

	# Actually open the file
	openfile = open(filename, mode)
	
	
Open file objects have many different read methods, but the most basic is intuitively called read:
	
	openfile = open("gonewiththewind.txt", "rt")

	filedata = openfile.read()
	print(filedata)


open file objects have many different write methods, but the most basic is intuitively called write:

	openfile = open("mymoviescript.txt", "wt")

	openfile.write('I wish I had an idea for a movie...\n')
	
	
Finally, never forget to close the file! To do so, open file objects have a close method:

	openfile = open("emptyfile.txt")

	openfile.close()
	


# Reading Files using Ilteration

#Using readlines()
#readlines creates a list of strings that you can iterate over

	datafile1 = open("the_idiot.txt", "rt")

	for line in datafile1.readlines():
	    print(line)

	datafile1.close()

	print("")
	print("================================")
	print("")

#Direct iteration
#This is faster for large files, as no list is created

	datafile2 = open("the_idiot.txt", "rt")

	for line in datafile2:
	    print(line)

	datafile2.close()
	
	
	
# Writing Files.


	print("Opening Files")
	print("=============")

	openfile = open("output.txt", "wt")  # wt - erases the file first

	# Modes for writing:
	#  w - write (erases the file first)
	#  a - write (appends to the end of the file)
	#  t - text (default)
	#  b - binary
	#  + - open for read and write

	print(type(openfile))
	print(openfile)


	openfile.close()

	print("")
	print("Writing")
	print("=======")

	def checkfile(filename):
	    """
	    Read and print the contents of the file named filename.
	    """
	    datafile = open(filename, "rt")
	    data = datafile.read()
	    datafile.close()
	    print(data)


	# Write
	outputfile = open("output.txt", "wt")
	outputfile.writelines(["first line\n", "second line\n"])
	outputfile.write("third line\nfourth line\n")
	outputfile.close()

	print("Initial file contents:")
	checkfile("output.txt")

	Output: 
	Initial file contentes:
	first line
	second line
	third line
	fourth line


	# Overwrite
	outputfile2 = open("output.txt", "wt")
	outputfile2.write("overwriting contents\n")
	outputfile2.close()

	print("Overwritten file contents:")
	checkfile("output.txt")

	Output:
	Overwritten file contents:
	Overwritng contents



	# Append
	outputfile2 = open("output.txt", "at")   # at - appends to the end of the file
	outputfile2.write("appending to contents\n")
	outputfile2.close()

	print("Appended file contents:")
	checkfile("output.txt")
	
	Output:
	Appended file contents:
	Overwritng contents
	appending to contents



"""
Examples of paths used in Python
Expects current_file.txt in same directory as this code
Expects parent_file.txt in parent directory of this code
Expects child_file.txt in sub-directory child
"""

	def echo_file(file_name):
	    """
	    Open a file, read its contents, and echo to console
	    """
	    my_file = open(file_name, 'r')
	    my_file_text = my_file.read()
	    print(my_file_text)
	    my_file.close()                       


#Examples using absolute paths on Windows - Use raw strings to handle backslash
	
	def run_absolute_path_examples():
	
	    current_abs_path = r"C:\Users\jwarren\Dropbox\Python Scripting\course 2\week4\paths\current_file.txt"
	    child_abs_path = r"C:\Users\jwarren\Dropbox\Python Scripting\course 2\week4\paths\child\child_file.txt"
	    parent_abs_path = r"C:\Users\jwarren\Dropbox\Python Scripting\course 2\week4\parent_file.txt"
	    echo_file(current_abs_path)
	    echo_file(child_abs_path)
	    echo_file(parent_abs_path)
	    print()

	run_absolute_path_examples()



#Examples using relative paths - current_file.txt in same directory as this code
	
	def run_relative_path_examples():
  	 	echo_file("current_file.txt")
	    echo_file("child/child_file.txt")           # Note that slash works on Windows
	    echo_file("../parent_file.txt")
	    print()


	run_relative_path_examples()


import os

	def run_os_path_examples():
	    """
	    Examples of computing/manipulating paths reliably using the os module
	    """

	    # Get absolute path using os.path - note path uses backslashes on Windows
	    current_abs_path = os.path.abspath("current_file.txt")
	    print(current_abs_path)

	    # Get absolute path to child_file.text using os.path
	    child_abs_path = os.path.abspath("child/child_file.txt")
	    print(child_abs_path)

	    # Get cwd (current working directory)
	    working_dir = os.getcwd()
	    print(working_dir)

	    # Construct paths using os.path.join
	    child_rel_path = os.path.join(working_dir, "child", "child_file.txt")
	    print(child_rel_path)

	    parent_rel_path = os.path.join(working_dir, os.pardir, "parent_file.txt")
	    print(parent_rel_path)

	run_os_path_examples()
