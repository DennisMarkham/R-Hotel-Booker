firstfloor <- 100:139
secondfloor <- 200:239
thirdfloor <- 300:339

allRooms <- c(firstfloor, secondfloor, thirdfloor)



occupancy <- rep(c(0), each = length(allRooms))



Hotel_Data_Frame <- data.frame(
Room_Number = allRooms,
Room_Occ = occupancy

)

numberToIndex <- function(roomNumber){

#the empty rooms variable represents how many more rooms could be on the floor without breaking
#the rules of math.  While room floor has 100 - 139, there are 60 empty rooms.  If it were 100 - 199
#it would be 0.  If it were 100 - 198, there would be 1. Etc.

emptyRooms <- 60

subtNumber <- 99 + (emptyRooms * (floor(roomNumber/100) - 1)) 




if(roomNumber < 200)
{
return (roomNumber - subtNumber)
}

else if(roomNumber < 300)
{
return (roomNumber - subtNumber)
}

else if (roomNumber < 400)
{
return (roomNumber - subtNumber)
}

#notice how the minus amount keeps increasing by 60.  You could probably write a formula for this
#okay, here's what I could do. Get the roomNumber, divide it by 100 and round it down so 129 becomes
#1 etc.  Then I subtract 1 from it.  Then multiple the resulant number be 60, and subtract it from
#the room number.  That's a mouthful, but...


}

fillRoom <- function(roomNumber, occupants)
{
roomIndex = numberToIndex(roomNumber)

Hotel_Data_Frame$Room_Occ[roomIndex] <- occupants
Hotel_Data_Frame <<- Hotel_Data_Frame

}

fillRoom(122, 1)

fillRoom(233, 4)

checkOccupancy <-function(roomNumber)
{

roomIndex = numberToIndex(roomNumber)
Hotel_Data_Frame$Room_Occ[roomIndex]


}

checkOccupancy(133)

Hotel_Data_Frame
