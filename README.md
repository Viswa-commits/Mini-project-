# Mini-project-
// Java pprogram to automatically generate CAPTCHA and
// verify user
import java.util.*;
import java.io.*;
 
class GFG
{
    
    static boolean checkCaptcha(String captcha, String user_captcha)
    {
        return captcha.equals(user_captcha);
    }
     
    
    static String generateCaptcha(int n)
    {
        Random rand = new Random(62); 
         
        
        String chrs = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
      
        String captcha = "";
        while (n-->0){
            int index = (int)(Math.random()*62);
            captcha+=chrs.charAt(index);
        }
           
        return captcha;
    }
     
    // Driver code
    public static void main(String[] args)throws IOException
    {
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
         
        // Generate a random CAPTCHA
        String captcha = generateCaptcha(9);
        System.out.println(captcha);
      
        // Ask user to enter a CAPTCHA
        System.out.println("Enter above CAPTCHA: ");
        String usr_captcha = reader.readLine();
      
        // Notify user about matching status
        if (checkCaptcha(captcha, usr_captcha))
            System.out.println("CAPTCHA Matched");
        else
            System.out.println("CAPTCHA Not Matched");
    }
}
 
// This code is contributed by shruti456rawal
