# PyBer_Analysis
Performing analysis on ride-sharing City data to uncover trends.
## Overview of Project
This weeks challenge helps us build upon our skills learned in the PyBer with Matplotlib module. For deliverables, the client wanted a summary DataFrame of the ride-sharing data by city type. Pandas and Matplotlib was used to create a multi-line graph that shows the total weekly fares for each city type. This report summarizes how the data differs by city type and how those differences can be used by decisionmakers at PyBer.

## Results
Using the Pandas groupby() function with the count() and sum() methods on PyBer DataFrame columns, the the total number of rides, total number of drivers, and the total fares were found for each city type. Then, the average fare per ride and per driver was calculated for each city type. Finally, these parameters were added to a new DataFrame and formatted into columns.


### Election Results Summary
![election_results](https://user-images.githubusercontent.com/107658895/176082445-ede641f1-8329-431c-8e59-a02f2ff13f01.png)
##### Figure 1 above displays the election results that were printed on the terminal and text file


# Code:

    #Add our dependencies.
    import csv
    import os

    #Add a variable to load a file from a path.
    file_to_load = os.path.join( "Resources", "election_results.csv")
    
    #Add a variable to save the file to a path.
    file_to_save = os.path.join("analysis", "election_analysis.txt")

    #Initialize a total vote counter.
    total_votes = 0

    #Candidate Options and candidate votes.
    candidate_options = []
    candidate_votes = {}

    #1: Create a county list and county votes dictionary.
    county_list = []
    county_votes = {}

    #Track the winning candidate, vote count and percentage
    winning_candidate = ""
    winning_count = 0
    winning_percentage = 0

    #2: Track the largest county and county voter turnout.
    largest_county_turnout = ""
    largest_county_turnout_count = 0
    largest_county_percentage = 0

    #Read the csv and convert it into a list of dictionaries
    with open(file_to_load) as election_data:
    # Read the file object with the reader function.
    reader = csv.reader(election_data)

    #Read the header
    header = next(reader)

    #For each row in the CSV file.
    for row in reader:

        #Add to the total vote count (either work)
        #total_votes = total_votes + 1
        total_votes += 1

        #Get the candidate name from each row.
        candidate_name = row[2]

        #3: Extract the county name from each row.
        county_name = row[1]

        #If the candidate does not match any existing candidate add it to the candidate list
        if candidate_name not in candidate_options:

            # Add the candidate name to the candidate list.
            candidate_options.append(candidate_name)

            # And begin tracking that candidate's voter count.
            candidate_votes[candidate_name] = 0

        #Add a vote to that candidate's count
        candidate_votes[candidate_name] += 1

        #4a: Write an if statement that checks that the
        # county does not match any existing county in the county list.
        if county_name not in county_list:

            #4b: Add the existing county to the list of counties.
            county_list.append(county_name)

            #4c: Begin tracking the county's vote count.
            county_votes[county_name] = 0

        #5: Add a vote to that county's vote count.

        county_votes[county_name] += 1

#Save the results to our text file.
with open(file_to_save, "w") as txt_file:

    #Print the final vote count (to terminal)
    election_results = (
        f"\nElection Results\n"
        f"-------------------------\n"
        f"Total Votes: {total_votes:,}\n"
        f"-------------------------\n\n"
        f"County Votes:\n"
    )
    
    #Print election results to the terminal.
    print(election_results, end="")
   
    #Saves the final vote counts to the .txt
    txt_file.write(election_results)

    #6a: Write a for loop to get the county from the county dictionary.
    for county in county_list:
        
        #6b: Retrieve the county vote count.
        county_vote = county_votes.get(county)
        
        #6c: Calculate the percentage of votes for the county.
        county_vote_percentage = float(county_vote) / float(total_votes) * 100

         #6d: Print the county results to the terminal.
        county_results = f"{county}: {county_vote_percentage:.1f}% ({county_vote:,})\n"
        
        #Print county votes results to the terminal.
        print(county_results)

         # 6e: Save the county votes to a .txt file.
        txt_file.write(county_results)
         
         #6f: Write an if statement to determine the winning county and get its vote count.
        if (county_vote > largest_county_turnout_count) and (
            county_vote_percentage > largest_county_percentage
        ):
            #True
            largest_county_turnout_count = county_vote
            largest_county_percentage = county_vote_percentage
            largest_county_turnout = county

    #7: Print the county with the largest turnout to the terminal.
    winning_county_print = (
        f"-------------------------\n"
        f"Largest County Turnout: {largest_county_turnout}\n"
        f"-------------------------\n"
    )

    #Print winning county print with the largest county turnout to the terminal.
    print(winning_county_print)

    #8: Save the county with the largest county turnout to a .txt file.
    txt_file.write(winning_county_print)

    #Save the final candidate vote count to the .txt file.
    for candidate_name in candidate_votes:

        #Retrieve vote count and percentage
        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        candidate_results = f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n"

        #Print candidate results in terminal
        print(candidate_results)

        #Save the candidate results to our .txt file.
        txt_file.write(candidate_results)

        #Determine winning vote count, winning percentage, and candidate.
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage

    #Print the winning candidate (to terminal)
    winning_candidate_summary = (
        f"-------------------------\n"
        f"Winner: {winning_candidate}\n"
        f"Winning Vote Count: {winning_count:,}\n"
        f"Winning Percentage: {winning_percentage:.1f}%\n"
        f"-------------------------\n"
    )
    
    #Print winning candidate summary in terminal
    print(winning_candidate_summary)

    #Save the winning candidate's name to the .txt file
    txt_file.write(winning_candidate_summary)


## Summary
Based on the functionality of this script, it's propose can be used for other elections big or small. It would be an interesting parameter to see the geographical location of each person who voted and create a heat map. This will give valuable information of where to do more outreaching to get a more wholistic representation of the local population. The limitations of this dataset are that they only limit a few parameters. It would also be interesting to see the age groups and genders that participated in the election so that the parties can go about better strategizing for target audiences they struggled. 
