 week_four_-Assignment-
def modify_line(line):
    Example modification: make all text lowercase and strip whitespace
    return line.lower().strip()

def process_file():
     Ask the user for the source filename
    source_file = input("Enter the name of the file to read from: ")

    try:
        Try to open and read the source file
        with open(source_file, 'r') as file:
            lines = file.readlines()

        Modify each line
        modified_lines = [modify_line(line) + "\n" for line in lines]

        Ask the user for the output filename
        target_file = input("Enter the name of the file to write to: ")

         Write modified lines to the target file
        with open(target_file, 'w') as file:
            file.writelines(modified_lines)

        print(f"✅ File '{target_file}' created with modified content.")

    except FileNotFoundError:
        print(f"❌ Error: The file '{source_file}' does not exist.")
    except PermissionError:
        print("❌ Error: You don't have permission to access this file.")
    except Exception as e:
        print(f"❌ An unexpected error occurred: {e}")

 Run the program
process_file()
