import java.io.*;
import java.text.SimpleDateFormat;
import java.util.Date;

/* 
Serializable Solution
*/

public class Solution implements Serializable{
    public static void main(String[] args) throws IOException, ClassNotFoundException {

        FileOutputStream fos = new FileOutputStream("D:\\JR\\JavaRushTasks\\2.JavaCore\\src\\com\\javarush\\task\\task20\\task2014\\test.dat");
        FileInputStream fis = new FileInputStream("D:\\JR\\JavaRushTasks\\2.JavaCore\\src\\com\\javarush\\task\\task20\\task2014\\test.dat");

        ObjectOutputStream oos = new ObjectOutputStream(fos);
        ObjectInputStream ois = new ObjectInputStream(fis);


        Solution savedObject = new Solution(21);
        oos.writeObject(savedObject);

        Solution loadedObject = new Solution(23);
        loadedObject = (Solution) ois.readObject();

        System.out.println(savedObject);
        System.out.println(loadedObject);
        System.out.println(savedObject.string.equals(loadedObject.string));
    }

    private final transient String pattern = "dd MMMM yyyy, EEEE";
    private transient Date currentDate;
    private transient int temperature;
    String string;

    public Solution(int temperature) {
        this.currentDate = new Date();
        this.temperature = temperature;

        string = "Today is %s, and the current temperature is %s C";
        SimpleDateFormat format = new SimpleDateFormat(pattern);
        this.string = String.format(string, format.format(currentDate), temperature);
    }

    @Override
    public String toString() {
        return this.string;
    }
}
