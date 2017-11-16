# Lab3
install.packages("lpSolve")
install.packages("lpSolveAPI")
library(lpSolve)
library(lpSolveAPI)

# Read in dataset
Data <- read.csv("18-fantasy-football-class-example.csv")
str(Data)

# Create objective Function
F.ObjFun <- Data$Projected.Points

# Create Constraints for all variables
F.Constraints <- matrix(c(Data$QuarterBack, Data$RunningBack, Data$WideReceiver, 
                          Data$TightEnd, Data$Defense, Data$Flex, Data$Cost), ncol = 7, byrow = FALSE)

# Transform Constraints 
F.Constraints <- t(F.Constraints)

# Create Direction of Constraints
F.Direction <- c("=","=","=","=","=","=","<=")

# Create Right Hand Side of Constraint
F.RightHS <- c(1,2,3,1,1,1,200)

# Use LP Function to solve for first optimal solution 
LP_Solution <- lp("max", F.ObjFun, F.Constraints, F.Direction, F.RightHS, all.bin = TRUE)
LP_Solution$objval
LP_Solution$solution

write.csv(LP_Solution$solution, "LPSolution.csv")

# Optimal Solution Number Two - Make all players/defenses that were in first Optimal Solution infeasible (cost = 1000) except for Flex
# Update original data file with Optimal Solution for team 1

F.Constraints <- matrix(c(Data$QuarterBack, Data$RunningBack, Data$WideReceiver, 
                          Data$TightEnd, Data$Defense, Data$Flex, Data$Cost1), ncol = 7, byrow = FALSE)

F.Constraints <- t(F.Constraints)

LP_Solution_Team2 <- lp("max", F.ObjFun, F.Constraints, F.Direction, F.RightHS, all.bin = TRUE)
LP_Solution_Team2$objval
LP_Solution_Team2$solution

write.csv(LP_Solution_Team2$solution, "LPSolution2.csv")
# Optimal Solution Number Three
# Update original data file with Optimal Solution for Teams 1 and 2

F.Constraints <- matrix(c(Data$QuarterBack, Data$RunningBack, Data$WideReceiver, 
                          Data$TightEnd, Data$Defense, Data$Flex, Data$Cost2), ncol = 7, byrow = FALSE)

F.Constraints <- t(F.Constraints)

LP_Solution_Team3 <- lp("max", F.ObjFun, F.Constraints, F.Direction, F.RightHS, all.bin = TRUE)
LP_Solution_Team3$objval
LP_Solution_Team3$solution

write.csv(LP_Solution_Team3$solution, "LPSolution3.csv")

# Optimal Solution Number Four
# Update original data file with Optimal Solution for Teams 1,2 and 3

F.Constraints <- matrix(c(Data$QuarterBack, Data$RunningBack, Data$WideReceiver, 
                          Data$TightEnd, Data$Defense, Data$Flex, Data$Cost3), ncol = 7, byrow = FALSE)

F.Constraints <- t(F.Constraints)

LP_Solution_Team4 <- lp("max", F.ObjFun, F.Constraints, F.Direction, F.RightHS, all.bin = TRUE)
LP_Solution_Team4$objval
LP_Solution_Team4$solution

write.csv(LP_Solution_Team4$solution, "LPSolution4.csv")
# Optimal Solution Number Five
# Update original data file with Optimal Solution for Teams 1-4

F.Constraints <- matrix(c(Data$QuarterBack, Data$RunningBack, Data$WideReceiver, 
                          Data$TightEnd, Data$Defense, Data$Flex, Data$Cost4), ncol = 7, byrow = FALSE)

F.Constraints <- t(F.Constraints)

LP_Solution_Team5 <- lp("max", F.ObjFun, F.Constraints, F.Direction, F.RightHS, all.bin = TRUE)
LP_Solution_Team5$objval
LP_Solution_Team5$solution

write.csv(LP_Solution_Team5$solution, "LPSolution5.csv")

# Optimal Solution Number Six
# Update original data file with Optimal Solution for Teams 1-5

F.Constraints <- matrix(c(Data$QuarterBack, Data$RunningBack, Data$WideReceiver, 
                          Data$TightEnd, Data$Defense, Data$Flex, Data$Cost5), ncol = 7, byrow = FALSE)

F.Constraints <- t(F.Constraints)

LP_Solution_Team6 <- lp("max", F.ObjFun, F.Constraints, F.Direction, F.RightHS, all.bin = TRUE)
LP_Solution_Team6$objval
LP_Solution_Team6$solution

write.csv(LP_Solution_Team6$solution, "LPSolution6.csv")

# Optimal Solution Number Seven
# Update original data file with Optimal Solution for Teams 1-6

F.Constraints <- matrix(c(Data$QuarterBack, Data$RunningBack, Data$WideReceiver, 
                          Data$TightEnd, Data$Defense, Data$Flex, Data$Cost6), ncol = 7, byrow = FALSE)

F.Constraints <- t(F.Constraints)

LP_Solution_Team7 <- lp("max", F.ObjFun, F.Constraints, F.Direction, F.RightHS, all.bin = TRUE)
LP_Solution_Team7$objval
LP_Solution_Team7$solution

write.csv(LP_Solution_Team7$solution, "LPSolution7.csv")

# Optimal Solution Number Eight
# Update original data file with Optimal Solution for Teams 1-7

F.Constraints <- matrix(c(Data$QuarterBack, Data$RunningBack, Data$WideReceiver, 
                          Data$TightEnd, Data$Defense, Data$Flex, Data$Cost7), ncol = 7, byrow = FALSE)

F.Constraints <- t(F.Constraints)

LP_Solution_Team8 <- lp("max", F.ObjFun, F.Constraints, F.Direction, F.RightHS, all.bin = TRUE)
LP_Solution_Team8$objval
LP_Solution_Team8$solution

write.csv(LP_Solution_Team8$solution, "LPSolution8.csv")

# Optimal Solution Number Nine
# Update original data file with Optimal Solution for Teams 1-8

F.Constraints <- matrix(c(Data$QuarterBack, Data$RunningBack, Data$WideReceiver, 
                          Data$TightEnd, Data$Defense, Data$Flex, Data$Cost8), ncol = 7, byrow = FALSE)

F.Constraints <- t(F.Constraints)

LP_Solution_Team9 <- lp("max", F.ObjFun, F.Constraints, F.Direction, F.RightHS, all.bin = TRUE)
LP_Solution_Team9$objval
LP_Solution_Team9$solution

write.csv(LP_Solution_Team9$solution, "LPSolution9.csv")

# Optimal Solution Number Ten
# Update original data file with Optimal Solution for Teams 1-9

F.Constraints <- matrix(c(Data$QuarterBack, Data$RunningBack, Data$WideReceiver, 
                          Data$TightEnd, Data$Defense, Data$Flex, Data$Cost9), ncol = 7, byrow = FALSE)

F.Constraints <- t(F.Constraints)

LP_Solution_Team10 <- lp("max", F.ObjFun, F.Constraints, F.Direction, F.RightHS, all.bin = TRUE)
LP_Solution_Team10$objval
LP_Solution_Team10$solution

write.csv(LP_Solution_Team10$solution, "LPSolution10.csv")
