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
