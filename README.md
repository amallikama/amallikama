@@ -0,0 +1,26 @@
#!/bin/bash
# Function to prompt user for a guess
guessing_game() {
    local correct_number=$(ls -1 | wc -l)  # Count the number of files in the current directory
    local guess=0  # Initialize the user's guess to 0
    # Loop until the user guesses correctly
    while [[ $guess -ne $correct_number ]]; do
        # Prompt the user for a guess
        echo "How many files are in the current directory?"
        read guess
        # Check if the guess is correct
        if [[ $guess -lt $correct_number ]]; then
            echo "Too low! Try again."
        elif [[ $guess -gt $correct_number ]]; then
            echo "Too high! Try again."
        else
            echo "Congratulations! You guessed correctly."
        fi
    done
}
# Run the guessing game
guessing_game
