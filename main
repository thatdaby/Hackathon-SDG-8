import time
import random
tutorial = open("intro.txt","r")

#ANSI COLOURS
end = "\033[0;0m"
red = "\033[1;31m"
green = "\033[1;32m"
blue = "\033[0;34m"
bold = "\033[1m"
yellow = "\033[1;33m"

#art
print(f'''

                              █████▓▓██    ████▓▓█
                            ██▓▓▒▒▒▒▒▓█ ██▓▓▒▒▓▒▒█
                          █▓▒▒▒▒▒▒▓▓▓██▓▓▒▒▒▒▒▓▒▓█
                          █▓▒▓▒▓██    █▒▒▒▒▓██ █  
                         ███████    ██████        
                         ██▓▓▓▓█    ██▓▓▓█        
                         ██▓▓▓▓█    ██▓▓▓█        
                         ██▓▓▓▓█    ██▓▓▓██       
                         █▓▓▓▓▓█    █▓▓▓▓▓█       
                         ██▓▓▓▓█   ███▓▓▓▓█       
 █████████████████████   ██▓▓▓▓█   ███▓▓▓▓█       
█▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓█  ██▓▓▓▓█   ███▓▓▓▓█       
█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▓█ ██▓▓▓▓█   ███▓▓▓▓█       
█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▓█ █▓▓▓▓▓█   █▓▓▓▓▓▓█       
█▒████▓▒▒▒████▒▒▒████▒▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█    
█▒█▒▒▓▓▒▒▒▓▒▒█▒▒▒▓▒▒█▒▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█    
█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█    
█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█    
█▒█▓▓▓▓▒▒▒█▓▓█▒▒▒█▓▓█▒▓▒▒█▓▓█▒▒▒█▓▓█▒▒▓▓▓▓█▒▒█    
█▒█▓▓█▓▒▒▒█▓▓█▒▒▒█▓▓█▒▓▒▒█▓▓█▒▒▒█▓▓█▒▒▓█▓▓█▒▒█    
█▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓█▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓█    
{yellow}
╔═╗┌─┐┌─┐┌┬┐┌─┐┬─┐┬ ┬  ╔╦╗┌─┐┌┐┌┌─┐┌─┐┌─┐┬─┐
╠╣ ├─┤│   │ │ │├┬┘└┬┘  ║║║├─┤│││├─┤│ ┬├┤ ├┬┘
╚  ┴ ┴└─┘ ┴ └─┘┴└─ ┴   ╩ ╩┴ ┴┘└┘┴ ┴└─┘└─┘┴└─
{end}
''')
#Worker Names
def namePicker():
    global workerName
    #FIRST NAME
    listOfNames = open("firstName.txt").read().splitlines()
    workerFN = random.choice(listOfNames)
    #LAST NAME
    listOfNames = open("lastName.txt").read().splitlines()
    workerLN = random.choice(listOfNames)
    
    workerName = f"{workerFN} {workerLN}"

#Tutorial
for line in tutorial:
    print(line)
    time.sleep(2)

#stats
day = 1
totalday = 5
money = round(random.randint(1500,2500),2)
safety = random.randint(50,75)
prodLvl = random.randint(50,75)
morale = round((random.randint(60,70)),2)
passiveMoney = 1
income = 1
suspicion = []
Colour = "none"
eventCount=1

oldMorale = 1
oldProdLvl = 1

#Function to make sure values dont bypass
def checkStats():
    global morale
    global safety
    global prodLvl
    global money
    
    if morale<0:
        morale=0
    elif morale>100:
        morale=100

    elif money<0:
        money=0

    if prodLvl<0:
        prodLvl=0

    if safety<0:
        safety=0
    elif safety>100:
        safety=100

    
def overview():
    baseIncome = 200
    global fctryStat
    global passiveMoney
    global morale
    global prodLvl
    global oldMorale
    global oldProdLvl
    global income
    if morale != oldMorale or oldProdLvl != prodLvl:
        moraleMult = morale/100
        prodMult = prodLvl/100
        passiveMoney = round(baseIncome*(1+(moraleMult+prodMult)/2),0)
    fctryStat = round(((safety + prodLvl + morale)/3),2)
    numStatus(fctryStat)
    print(f"Factory Status: {statColour}{fctryStat}%{end}")
    print(f'''
    {bold}DAY: {day}/{totalday}{end}
    
    Passive Money Per Day: {green}{bold}${passiveMoney}{end}
    
    ------------------------------
    [Morale: {bold}{morale}%{end}/100%]
    ------------------------------
    [Money: {bold}${money}{end}]
    ------------------------------
    [Factory safety: {bold}{safety}%{end}/100%]
    ------------------------------
    [Production Level: {bold}{prodLvl}%{end}/100%]
    ------------------------------
    ''')
    oldMorale = morale
    oldProdLvl = prodLvl
    income = passiveMoney
    return income

#Stat Colour
def numStatus(stat):
    global statColour
    if stat >= 70:
        statColour = green
    elif stat >= 50:
        statColour = yellow
    else:
        statColour = red

#START OF MAIN
overview()
if day==6:
    if fctryStat >= 85:
        print('★ YOU WIN')
        print("Stat overview")
        overview()

#Chooses the random event for you.
def randomEvent():
    global evenCount
    global money
    global safety
    global prodLvl
    global morale
    userAsk = ""
    strangerAsk = ""
    randomEventChoice=random.randint(1,10)
    match randomEventChoice:
            case 1:
                while userAsk != 'y' or 'n':
                    userAsk=input(f"""
        The floors are starting to have cracks. It's dangerous but costs a lot to repair.
                    
            Press {bold}[Y]{end} to repair it: 
            ({bold}{red}Lose profit by $500-$1000{end} BUT {bold}{green}increase safety by 30%.{end})
                    
            Press {bold}[N]{end} to Leave it be: 
            ({bold}{red}Decrease Safety by 30%-40%{end})
                    
            [Input]: """)
                    try:
                        if userAsk.lower()=="y":
                            print("\nYou decided to fix it up.")
                            money-=random.randint(500,1000)
                            safety+=random.randint(20,30)
                            break
            
                        elif userAsk.lower()=="n":
                            print("\nYou left it be.")
                            safety-=random.randint(30,40)
                            break
                        
                        else:
                            print('INVALID INPUT!')
                    except:
                        print('INVALID INPUT!')
                        
                time.sleep(1)
                
            case 2:
                while userAsk != 'y' or 'n':
                    userAsk=input(f"""
    
    Your factory machines are making odd noises... They are also working slower than usual.
                
        Press {bold}[Y]{end} to fix the machine 
        ({bold}{red}Lose $250-$500{end} BUT {bold}{green}production level stays the same.{end})
                
        Press {bold}[N]{end} to leave it 
        (Production Level {bold}{red}Decrease by 20%-30%{end})
            
        [Input]: """)
                    try:
                        if userAsk.lower()=="y":
                            print("You fixed the machine.")
                            money-=random.randint(250,500)
                            break
            
                        elif userAsk.lower()=="n":
                            print("You left the machine alone")
                            prodLvl-=random.randint(20,30)
                            break
                        
                        else:
                            print('INVALID INPUT!')
                    except:
                        print('INVALID INPUT!')
                time.sleep(1)
        
            case 3:
                namePicker()
                while userAsk.lower() != 'y' or 'n':
                    userAsk=input(f"""
    {bold}{workerName}{end} requested raise.
            
        Press {bold}[Y]{end} to give them a raise 
        ({bold}{red}Lose $200-$400{end}, BUT {bold}{green}Increase morale by 20%-25%{end})
                
        Press {bold}[N]{end} to refuse 
        ({bold}{red}Lower morale by 10%-15%{end})
                
        [Input]: """)
                    try:
                        if userAsk.lower()=="y":
                            print("You gave them a raise.")
                            money-=random.randint(200,400)
                            morale+=random.randint(20,25)
                            break
            
                        elif userAsk.lower()=="n":
                            morale-=random.randint(10,15)
                            break
                        
                        else:
                            print('INVALID INPUT!')
                    except:
                        print('INVALID INPUT!')

                time.sleep(1)
            case 4:
                while userAsk != 'y' or 'n':
                    userAsk=input(f"""
    A controversial, yet powerful company is willing to work with you. Your employees however, don't exactly feel comfortable working with them.
                
        Press {bold}[Y]{end} to accept the offer 
        ({green}{bold}Increase profit by $500-$700{end} and {green}{bold}increase production level by 10%-20%{end}, {red}{bold}decrease morale by 20%-25%{end})
                
        Press {bold}[N]{end} to refuse 
        ({green}{bold}Increase morale by 20%-25%{end})
        
        [Input]: """)
                    try:
                        if userAsk.lower()=="y":
                            print("You took the offer.")
                            money+=random.randint(500,700)
                            prodLvl+=random.randint(10,20)
                            morale-=random.randint(20,25)
                            break
            
                        elif userAsk.lower()=="n":
                            print("You declined.")
                            morale+=random.randint(20,25)
                            break
                        
                        else:
                            print('INVALID INPUT!')
                    except:
                        print('INVALID INPUT!')
                
                time.sleep(1)   
                
            case 5:
                while userAsk != 'y' or 'n':
                    userAsk=input(f"""
    You decide to make your all employees do some safety training since theres new recruits. However, most of the workers show annoyance from having to do it again.
        
        Press {bold}[Y]{end} to ignore the complaints and keep training 
        ({red}{bold}Lose 10%-20% morale{end}, but {green}{bold}increase safety by 25%-30%{end}).
        
        Press {bold}[N]{end} to cancel safety training 
        ({green}{bold}gain 20%-30% morale{end}, but {red}{bold}lose 30%-40% safety{end})
        
        [Input]: """)
                    try:
                        if userAsk.lower()=="y":
                            print("You took the training")
                            morale-=random.randint(10,20)
                            safety+=random.randint(30,40)
                            break
            
                        elif userAsk.lower()=="n":
                            print("You skipped training.")
                            morale+=random.randint(20,30)
                            safety-=random.randint(30,40)
                            break
                        
                        else:
                            print('INVALID INPUT!')
                    except:
                        print('INVALID INPUT!')
    
                time.sleep(1)
                
            case 6:
                while userAsk != 'y' or 'n':
                    userAsk=input(f"""
    A random OSHA inspection is happening in your area. You obviously have the worst factory standards ever, but the inspector looks broke.
    
        Press {bold}[Y]{end} to bribe the OSHA agent to leave you alone 
        ({red}{bold}Spend $1,500-$2,000 to make them leave{end})
        
        Press {bold}[N]{end} to let the OSHA inspector inspect your factory 
        ({green}{bold}Morale increase by 1%{end})
        
        [Input]: """)
                    try:
                        if userAsk.lower()=="y":
                            print("You bribed the agent.")
                            money-=random.randint(1500,2000)
                            break
            
                        elif userAsk.lower()=="n":
                            print("You let the inspection happen.")
                            morale+=1
                            if safety < 50:
                                print('The OSHA inspector has fined you $1,000 for poor saftey!')
                                money -= 1000
                            break
                        
                        else:
                            print('INVALID INPUT!')
                    except:
                        print('INVALID INPUT!')
                        
                time.sleep(1)    
            
            case 7:
                while userAsk != 'y' or 'n':
                    userAsk=input(f"""
    You decide to partake in dropshipping to make some extra money. Although the workers have no idea how to manage a factory without you.           
                
        Press {bold}[Y]{end} to ignore your workers and keep dropshipping 
        ({green}{bold}increase money by $1-$3,000{end}, {red}{bold}BUT lower production by 20%-40%{end} AND {red}{bold}lower morale by 10%-20%{end})            
        
        Press {bold}[N]{end} to come back to work. 
        ({green}{bold} Increase morale by 2%{end})
        
        [Input]: """)
                    try:
                        if userAsk.lower()=="y":
                            money+=random.randint(1,3000)
                            prodLvl-=random.randint(20,40)
                            morale-=random.randint(10,20)
                            break
                        
                        elif userAsk.lower()=="n":
                            morale+=2
                            break
                        
                        else:
                            print('INVALID INPUT!')
                    except:
                        print('INVALID INPUT!')

                time.sleep(1)    
                
            case 8:
                while userAsk != 'y' or 'n':
                    userAsk=input(f"""
    You want to cheap out on the materials to increase profits, but the machinery might not handle it.
    
        Press {bold}[Y]{end} to use cheaper materials 
        ({green}{bold}Increase profits by $500-$1,500{end} BUT lower production by {red}{bold} 20%-30%.{end})
            
        Press {bold}[N]{end} to not use cheaper materials
        (Nothing happens.)
        
        [Input]: """)
                    try:
                        if userAsk.lower()=="y":
                            print("You decide to user cheaper materials")
                            money+=random.randint(500,1500)
                            prodLvl-=random.randint(20,30)
                            break
                        
                        elif userAsk.lower()=="n":
                            print("Nothing happens.")
                            break
                        
                        else:
                            print('INVALID INPUT!')
                    except:
                        print('INVALID INPUT!')
                        
                time.sleep(1)
                
            case 9:
                while userAsk != 'y' or 'n':
                    userAsk=input(f"""
    You think working overtime can increase profits, but your workers are already tired.
    
        Press {bold}[Y]{end} to go overtime.
        ({green}{bold} increases money by $200-$500{end}, {red}{bold}but will decrese morale by 10%-15%{end})
        
        Press {bold}[N]{end} to not work overtime.
        (Nothing happens.)
        
        [Input]: """)
                    try:
                        if userAsk.lower()=="y":
                            print("You decide to make your workers work overtime.")
                            money+=random.randint(200,500)
                            morale-=random.randint(10,15)
                            break
                        
                        elif userAsk.lower()=="n":
                            print("Nothing happens.")
                            break
                        
                        else:
                            print('INVALID INPUT!')
                    except:
                        print('INVALID INPUT!')

                time.sleep(1)
                
            case 10:
                namePicker()
                while userAsk.lower() != 'y' or 'n':
                    userAsk = input(f"""
    A Stranger comes to your Factory an requests to do business with you...
        
        Press {bold}[Y]{end} to accept {yellow}{bold}the proposition.{end}
        (???)
        
        Press {bold}[N]{end} to decline.
        (Nothing happens.)
        
        [Input]: """)
                    try:
                        if userAsk.lower() == 'y':
                            while strangerAsk.lower() != 'y' or 'n':
                                strangerAsk = input(f'''
    The stranger offers you to sacrifice ONE employee for {green}{bold}$5,000.{end}
    
        ONLY Press {bold}[Y]{end} to accept.{end}
        ({red}{bold}-30% MORALE...{end})
    
        [Input]: ''')
                                try:
                                    if strangerAsk.lower() == 'y':
                                        money += 5000
                                        morale -= 30
                                        print(f"{workerName} is gone.")
                                        break
                                        
                                    elif strangerAsk.lower() == 'n':
                                        morale = 0
                                        money = 0
                                        prodLvl = 0
                                        fctryStat = 0
                                        safety = 0
                                        print("You feel all your hard work being taken away.")
                                        time.sleep(1)
                                        break
                                    else:
                                        print("The Stranger Warns you to answer accordingly.")
                                except:
                                    print('Wrong Answer.')
                            break
                            
                        elif userAsk.lower() == 'n':
                            print('The stranger Leaves, Nothing Happens.')
                            time.sleep(1)
                            break
                        else:
                            print("The Stranger Warns you to answer accordingly.")
                            time.sleep(1)
                    except:
                        print('invalid input')
        
#Main Code.
#The loop of each day.
while day!=6:
    if fctryStat < 35 or prodLvl <= 10 or morale <= 10 or money<=500 or safety<=20:
        print("YOU LOST!!! ONE OF THE STATS WENT TOO LOW")
        break
    
    while eventCount<4:
        print(f"\nEvent {bold}{eventCount}{end} of 4")
        randomEvent()
        print("\n")
        checkStats()
        overview()
        eventCount+=1
        
    if eventCount==4:
        print(f"\nDay {bold}{day}{end} Complete!")
        print("Your stats for today are:")
        print("\n")
        overview()
        money += income
        dayContinue=input(f"Press {bold}[Y]{end} to cotinue to the next day. ")
        if dayContinue.lower()=="y":
            day+=1
            eventCount=1
            print("Starting a new day!")
            time.sleep(1)
#If the player manages to reach 6 days
if day==6:
    print("\n")
    overview()
    #endings based on player stats.
    if money>=3000 and morale>=75 and prodLvl>=75 and fctryStat>=75:
        print("You're the greatest manager ever! You made your factory into an amazing place to work at! Go you!")
    else:
        print("You uh...tried. At least nobody died. (I hope...!)")
