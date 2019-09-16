# Scientific-Data-Analysis
f=open('results.txt','r')
exprNum = f.readline()
exprNum = exprNum.split(' ')
exprNumList = []
for i in range(len(exprNum)-1):
    exprNumList.append(int(exprNum[i]))  
  	 
exprDate = f.readline()
exprDate = exprDate.split(' ')
exprDateList = []
for i in range(len(exprDate)-1):
    exprDateList.append(float(exprDate[i]))

exprTime = f.readline()
exprTime = exprTime.split(' ')
exprTimeList = []
for i in range(len(exprTime)-1):
    exprTimeList.append(float(exprTime[i]))

exprData = f.readline()
exprData = exprData.split(' ')
exprDataList = []
for i in range(len(exprData)-1):
    exprDataList.append(float(exprData[i]))

cristina_data = ["Experiment Number", exprNumList," ","Date of the Experiment", exprDateList," ", "Time of the Experiment", exprTimeList," ", "Data of the Experiment", exprDataList]
##print('cristina_data')
print("")
for x in cristina_data:
##    print(x)


    choice='0'
while True:
    print(' ')
    print("This program will help you perform a detailed analysis of the experimental results")
    print(' ')
    
    print("Main Choice: Choose 1 of 5 choices")
    print(' ')
    print("Choose 1 to display data ")
    print("Choose 2 to work with full data ")
    print("Choose 3 to work with a portion of data ")
    print("Choose 4 to work with advanced data processing ")
    print("Choose 0 to exit")


    print(' ')
    choice = input("Please make a choice: ")
    print(' ')




    if choice == "1":

        ##Q1 reading and displaying the data
        
        f=open('results.txt.','r')
        row=[]
        for line in f:
            row.append([float(x) for x in line.split()])

        width = len(row)
        height = len(row[0])
        print ("================================================================================")
        print ("|  Experiment Number  |    Date (dd.mm)    |      Time      |      Result      |")
        print ("================================================================================")

        for i in range (height):
            print('{:>13}'.format(row[0][i]), " ",'{:>19.2f}'.format(row[1][i]), " ", '{:>16.2f}'.format(row[2][i]), " ", '{:>16.4f}'.format(row[3][i]), " ",)


        ##f=floating point (decimal points)
        ## :>13 numbers to fit in the columns
        ## .2f number of decimal points




        ##Q2a-Q2d menu to perform various options
                                   
    elif choice == "2":
        print("Main Choice: Choose 1 of 8 choices")
        print(' ')
        print("Choose 1 to find the maximum ")
        print("Choose 2 to find the minimum ")
        print("Choose 3 to find the average ")
        print("Choose 4 to find the standard deviation ")
        print("Choose 5 to calculate how many experiments resulted in values greater than your input ") 
        print("Choose 6 for ascending order ")
        print("Choose 7 for descending order ")
        print("Choose 8 to exit")

        print(' ')
        choice = input("Please make a choice: ")
        print(' ')
    
        
        if choice == "1":
            print(' ')
            print ("The maximum value of the experimental result is: ", max(exprDataList))
            print(' ')
        
        elif choice == "2":
            print(' ')
            print ("The minimum value of the experimental result is: ", min(exprDataList))
            print(' ')
        
        elif choice == "3":
            from statistics import mean
            print(' ')
            print ("The average value of the experimental results is: ", mean(exprDataList))
            print(' ')
        
        elif choice == "4":
            from statistics import stdev
            print(' ')
            print ("The standard deviation value of the experimental result is: ", stdev(exprDataList))
            print(' ')
        
        elif choice == "5":
            a = int(input("Enter a value: "))
            
            counter = 0
            for i in exprDataList:
               if i>a:
                   counter+=1

            print(' ')       
            print("The number greater ")
            print(counter)
            print(' ')
        
            g=[]
            for i in exprDataList:
                if i>a:
                    g.append(i)
                    
            print("These results are",g)
            
                
        elif choice == "6":
            def bubblesort(exprDataList):
                for i in range(0,len(exprDataList)-1):
                    for j in range(i+1,len(exprDataList)):
                        if exprDataList[i]>exprDataList[j]:
                            exprDataList[i], exprDataList[j] = exprDataList[j], exprDataList[i]
                return exprDataList
            print(' ')
            print("In ascending order: ",(bubblesort(exprDataList)))
            print(' ')

        
        elif choice == "7":
            def bubblesort(exprDataList):
                for i in range(0,len(exprDataList)-1):
                    for j in range(i+1,len(exprDataList)):
                        if exprDataList[i]<exprDataList[j]:
                            exprDataList[i], exprDataList[j] = exprDataList[j], exprDataList[i]
                return exprDataList
            print(' ')
            print("In descending order: ",(bubblesort(exprDataList)))
            print(' ')

        
        elif choice == "8":
            print("You chose to exit ") 
            break
        else:
            print ("Not valid choice try again")
 
    ##Menu to perform question 3
            
    elif choice == "3":
        print("Please choose an option")
        print(' ')
        print("Choose 1 - Time range")
        print("Choose 2 - Specific date")
        print("Choose 3 - Experiment number range")
        print("")

    ##Menu to perform question 4
        
    elif choice == "4":
        print("Main Choice: Choose 1 of 2 choices")
        print(' ')
        print("Choose 1 to type in an experimental value to find the experimental number, date, and time ")
        print("Choose 2 to modify any of the values of the experiment ")

    ##To exit the program
    elif choice == "0":
        print("You chose to exit ") 
        break

    ##If user puts an invalid option
    else:
        print ("Not valid choice try again")
