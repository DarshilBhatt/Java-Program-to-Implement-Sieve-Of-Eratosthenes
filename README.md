import java.util.Scanner;
 
/** Class SieveOfEratosthenes **/

public class SieveOfEratosthenes

{
    
    /** Function to calculate all primes less than n **/
    
    private int[] calcPrimes(int N)
    
    {
        
        int[] arr = new int[N + 1];
        
        for (int i = 2; i <= Math.sqrt(N); i++)
        
        {
            
            if (arr[i] == 0)
            
            {
                
                for (int j = i * i; j <= N; j += i)
                
                {
                    
                    arr[j] = 1;
                
                }
            
            }
        
        }
        
        return arr;
    
    }
    
    /** Function to get all primes **/
    
    public void getPrimes(int N)
    
    {
        
        int[] primes = calcPrimes(N);
        
        display(primes);
    
    }
    
    /** Function to display all primes **/
    
    public void display(int[] primes)
    
    {
        
        System.out.print("\nPrimes = ");
        
        for (int i = 2; i < primes.length; i++)
            
            if (primes[i] == 0)
                
                System.out.print(i +" ");
        
        System.out.println();
    
    }
    
    /** Main function **/
    
    public static void main (String[] args) 
    
    {
        
        Scanner scan = new Scanner(System.in);
        
        System.out.println("Sieve Of Eratosthenes Prime Algorithm Test\n");
        
        /** Make an object of SieveOfEratosthenes class **/
        
        SieveOfEratosthenes soe = new SieveOfEratosthenes();
        
        /** Accept n **/
        
        System.out.println("Enter number to find all primes less than the number\n");
        
        int n = scan.nextInt();
        
        soe.getPrimes(n);        
    
    }
    
}
