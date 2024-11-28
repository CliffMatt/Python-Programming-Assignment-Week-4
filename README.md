# Python-Programming-Assignment-Week-4
Week 4 Assignment
def modify_file():
    """
    Reads a file, modifies its contents, and writes the modified data to a new file.
    Includes error handling for file-related issues.
    """
    try:
        # Prompt the user for the input filename
        input_filename = input("Enter the name of the file to read: ")

        # Attempt to open and read the file
        with open(input_filename, 'r') as infile:
            data = infile.readlines()  # Read all lines from the file
            print(f"File '{input_filename}' successfully read!")

        # Modify the content (example: appending " - Modified" to each line)
        modified_data = [line.strip() + " - Modified\n" for line in data]

        # Prompt for the output filename
        output_filename = input("Enter the name of the new file to write to: ")

        # Write the modified data to the new file
        with open(output_filename, 'w') as outfile:
            outfile.writelines(modified_data)
            print(f"Modified content successfully written to '{output_filename}'!")

    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' does not exist. Please check the filename and try again.")
    except IOError as e:
        print(f"An I/O error occurred: {e}")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Call the function to run the program
modify_file()
