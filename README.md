def read_and_modify_file():
    # Ask user for the input filename
    input_filename = input("Enter the name of the file to read: ")

    try:
        # Try opening the file
        with open(input_filename, 'r') as file:
            content = file.read()
            print("\n File read successfully.")

        # Modify the content - here we convert text to uppercase
        modified_content = content.upper()

        # Write to a new file
        output_filename = "modified_" + input_filename
        with open(output_filename, 'w') as new_file:
            new_file.write(modified_content)
            print(f" Modified content written to: {output_filename}")

    except FileNotFoundError:
        print(" Error: The file does not exist.")
    except IOError:
        print(" Error: Could not read the file.")

# Run the program
read_and_modify_file()
