package sangatamizh;
import java.util.HashMap;
import java.util.Map;
public class HotelRoom {
    private int roomNumber;
    private boolean isBooked;
    private static Map<Integer, HotelRoom> hotelRooms = new HashMap<>();
    public HotelRoom(int roomNumber) {
        this.roomNumber = roomNumber;
        this.isBooked = false;
        hotelRooms.put(roomNumber, this);
    }
    public boolean isAvailable() {
        return !isBooked;
    }
    public boolean bookRoom() {
        if (!isBooked) {
            isBooked = true;
            System.out.println("Room " + roomNumber + " has been successfully booked.");
            return true;
        } else {
            System.out.println("Room " + roomNumber + " is already booked.");
            return false;
        }
    }
    public boolean cancelBooking() {
        if (isBooked) {
            isBooked = false;
            System.out.println("Booking for room " + roomNumber + " has been canceled.");
            return true;
        } else {
            System.out.println("Room " + roomNumber + " is not currently booked.");
            return false;
        }
    }
    public static HotelRoom getRoom(int roomNumber) {
        return hotelRooms.get(roomNumber);
    }
    public static void main(String[] args) {
        HotelRoom room101 = new HotelRoom(101);
        HotelRoom room102 = new HotelRoom(102);

        room101.bookRoom();
        room101.bookRoom();
        room101.cancelBooking();
        room101.bookRoom();
        System.out.println("Room 102 available? " + room102.isAvailable());
    }
}
