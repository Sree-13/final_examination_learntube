#Given a string S. In this task you have to print all unique permutations of the given string in lexicographically sorted order.

Description
Given a string S, Write a program to print all unique permutations of the given string in lexicographically sorted order.

String ABCD



def unique_permutations(s):
    def backtrack(start):
        if start == len(s):
            unique_permutations.append(''.join(s))
            return
        
        for i in range(start, len(s)):
            if i != start and s[i] == s[start]:
                continue
            s[start], s[i] = s[i], s[start]
            backtrack(start + 1)
            s[start], s[i] = s[i], s[start]

    unique_permutations = []
    s = list(s)
    s.sort()
    backtrack(0)
    return unique_permutations

# Input string
input_string = "ABCD"

# Get unique permutations
permutations = unique_permutations(input_string)

# Print the result
for perm in permutations:
    print(perm)
