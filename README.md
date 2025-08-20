public class Main {
    public static void main(String[] args) {
        HotelRoom room1 = new HotelRoom(101);        
        System.out.println(room1.checkAvailability());          
        System.out.println(room1.bookRoom());  
        System.out.println(room1.checkAvailability());        
        System.out.println(room1.bookRoom());   
    }
}
class HotelRoom {
    private final int roomNumber;
    private boolean isBooked;
    public HotelRoom(int roomNumber) {
        this.roomNumber = roomNumber;
        this.isBooked = false;
    }
    public boolean checkAvailability() {
        return !isBooked;
    }
    public String bookRoom() {
        if (!isBooked) {
            isBooked = true;
            return "Room " + roomNumber + " booked successfully!";
        } else {
            return "Room " + roomNumber + " is already booked.";
        }
    }
}
