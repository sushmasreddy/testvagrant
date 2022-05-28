class TEAM: def init(self,name,points,last5): self.name = name self.points = points self.last5 = last5

def get_last5(self):
    return self.last5

def get_points(self):
    return self.points

def add_team(self,team,points,last5):
    team = TEAM(team,points,last5)
    ipl.append(team)
    
    
def show_data(self):
    print ("{:<8} {:<10} {:<10}".format( self.name, self.points, self.last5))
print() def cons_loss(loss,result): res = [] for i in range(ipl.len()): s = ipl[i].get_last5() count = 0 conloss = 0 for j in range(len(s)): if(s[j]==result): count += 1 conloss = max(conloss,count) else: count = 0 if(conloss==loss): res.append(ipl[i]) return res

def queries(): try: n = int(input("""Press 1 for points table. Press 2 to search consecutive win/loss teams Press any other digit to exit."""))

    if n==1:
        print ("{:<12} {:<10} {:<10}".format("    Team","Pts","Last 5"))
        for i in range(ipl.__len__()):
           print("{:<4}".format(i+1),end="") 
           ipl[i].show_data()
        queries()
    elif n==2:
        num = int(input("Enter the consective win/loss you are looking for?"))
        result = input("Type W for win or L for lose.")
        res = cons_loss(num, result)
        
        sum_points = 0
        for i in range(res.__len__()):
                res[i].show_data()
                sum_points += res[i].get_points()
        
        if res.__len__()!=0:
            print("Avg. Points ->  " + str(sum_points/res.__len__()) )
        
        queries()
except ValueError as e:
    print("\n\nInvlaid Input, Try again")
    queries()
    
print()
ipl = []

def main():

i = TEAM("",0,"")
i.add_team("GT",20,"WWLLW")
i.add_team("LSG", 18, "WLLWW")
i.add_team("RR",16,"WLWLL")
i.add_team("DC",14,"WWLWL")
i.add_team("RCB",14,"LWWLL")
i.add_team("KKR",12,"LWWLW")
i.add_team("PBKS",12,"LWLWL")
i.add_team("SRH",12,"WLLLL")
i.add_team("CSK",8,"LLWLW")
i.add_team("MI",6,"LWLWW")

res = cons_loss(2,"L")
print("List of teams who lost 2 matches consecutivily.")
sum_points = 0
for i in range(res.__len__()):
        res[i].show_data()
        sum_points += res[i].get_points()

print("Avg. Points ->  " + str(sum_points/res.__len__()) )

queries()
main()
