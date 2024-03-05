```java

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

class My implements Comparator<Object>
{
    public int compare(Object i1,Object i2)
    {
        ArrayList<Integer> arr1=new ArrayList<>();
        ArrayList<Integer> arr2 = new ArrayList<>();
        try {
            // Attempt to cast the Object to ArrayList
             arr1 = (ArrayList<Integer>) i1;
            arr2 = (ArrayList<Integer>) i2;
        } catch (ClassCastException e) {
            // Handle the ClassCastException
            System.out.println("Cannot cast Object to ArrayList: " + e.getMessage());
        }
        if(arr1.get(0)!=arr2.get(0)){
            if(arr1.get(0)>arr2.get(0)) return 1;
            else if(arr1.get(0) < arr2.get(0)) return -1;
        }else{
            if(arr1.get(1)>arr2.get(1)) return 1;
            else if(arr1.get(1) < arr2.get(1)) return -1;
        }
        return 0;
    }
}

public class Main 
{
    public static void main(String[] args) 
    {
        ArrayList<ArrayList<Integer>> arr = new ArrayList<>();
        arr.add(new ArrayList<>(List.of(1, 2)));
        arr.add(new ArrayList<>(List.of(3, 3)));
        arr.add(new ArrayList<>(List.of(2, 2)));
        arr.add(new ArrayList<>(List.of(1 , 1)));
        Collections.sort(arr, new My());
        
       for(var x:arr) 
            System.out.println(x);

    } 
}

// enum Day {
//     // Enum constants
//     MONDAY("Monday"),
//     TUESDAY("Tuesday"),
//     WEDNESDAY("Wednesday"),
//     THURSDAY("Thursday"),
//     FRIDAY("Friday"),
//     SATURDAY("Saturday"),
//     SUNDAY("Sunday");

//     // Enum fields
//     private final String dayName;

//     // Enum constructor
//     private Day(String dayName) {
//         this.dayName = dayName;
//         // System.out.println(this.dayName);
//     }

//     // Enum method
//     public String getDayName() {
//         return dayName;
//     }
// }

// public class Main {
//     public static void main(String[] args) {
//         Day day = Day.MONDAY;
        
//         // Accessing enum fields and methods
//         System.out.println(day + " is " + day.getDayName());
//     }
// }

// import java.io.FileInputStream;
// import java.io.FileOutputStream;
// import java.io.IOException;

// public class Main {
                                                     
//     public static void main(String[] args) throws IOException {
//         try(FileInputStream fis = new FileInputStream("./Challanges/input.txt")){
//             byte[] data = new byte[fis.available()];
//             fis.read(data);
//             try (FileOutputStream fos = new FileOutputStream("./Challanges/output.txt")) {
//                 for(byte by: data){
//                     if((char)by!=' ') fos.write(by+(97-65));
//                     else fos.write(by);
//                 }
//             }
//         }
//     }
// }

```