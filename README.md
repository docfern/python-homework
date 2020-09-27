# python-homework
Week 2

# import libraries
import os
import csv

# open path and read csv
PyBankcsv = os.path.join("Resources", "budget_data.csv")
with open(PyBankcsv, "r") as csvfile:
    csvreader = csv.reader(csvfile, delimiter=",")
    csv_header = next(csvfile)

# Initialize
    profitloss = []
    line_num = []
    profitloss_change = []

# Append information
    for rows in csvreader:
        profitloss.append(int(rows[1]))
        line_num.append(rows[0])

# Calculate the change in profit    
for x in range(1, len(profitloss)):
        profitloss_change.append((int(profitloss[x]) - int(profitloss[x-1])))

# Calculate profitloss average with a rounding off feature and calculate the total months 
        profitloss_average = round((sum(profitloss_change) / len(profitloss_change)), 2)
        total_months = len(line_num)

# Determine the max and min changes in profitloss
        greatest_increase = max(profitloss_change)
        greatest_decrease = min(profitloss_change)

# Show results
print("Financial Analysis")
print(f"------------------------------------------------------- \n")
print(f"Total Months: {total_months} \n")
print(f"Total: $ {sum(profitloss)} \n")
print(f"Average Change: $ {profitloss_average} \n")
print(f"Greatest Increase in Profits: {months[revenue_change.index(max(revenue_change))+1]} (${greatest_increase}) \n")
print(f"Greatest Decrease in Profits: {months[revenue_change.index(min(revenue_change))+1]} (${greatest_decrease}) \n")


# Financial Analysis
.....
### total months: 86
### Total: $38382578
### Average change: $-2315.1176470588234
### Greatest Increase in Profits: Feb-2012 $1926159
### Greatest Decrease in Profits: Sep-2013 $-2196167
