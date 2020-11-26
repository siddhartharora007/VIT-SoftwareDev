# VIT-SoftwareDev

Problem Statement:  
https://docs.google.com/document/d/16CNXNQ-VLLSoVe7CvJFBzueawgrCjWorB7zMLNvOF94/edit?usp=sharing
#include <bits/stdc++.h> 
using namespace std; 

\\two players black and white
bool whiteWins(int rowW, int colW, int rowB, int colB) 
{ 
    int white = 0, black = 0; 

    while (1) { 

        // If white can move 
        if (rowW != 5) { 

            // If white pawn can kill black pawn 
            // White wins 
            if (rowB == rowW + 1 
                && (colB == colW - 1 || colB == colW + 1)) 
                return true; 

            // Make the move forward 
            else
                rowW++; 
        } 

        // White has no moves 
        // White loses 
        else
            return false; 

        // If black can move 
        if (rowB != 1) { 

            // If black pawn can kill white pawn 
            // White loses 
            if (rowB == rowW + 1 
                && (colB == colW - 1 || colB == colW + 1)) 
                return false; 

            // Make the move forward 
            else
                rowB--; 
        } 

        // Black has no moves 
        // White wins 
        else
            return true; 
    } 

    // If white has got more moves 
    if (white > black) 
        return true; 

    return false; 
} 

// Driver code 
int main() 
{ 
    int rowW = 2, colW = 2, rowB = 3, colB = 3; 
    if (whiteWins(rowW, colW, rowB, colB)) 
        cout << "White"; 
    else
        cout << "Black"; 
    return 0; 
} 
