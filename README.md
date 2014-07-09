Problem 8.11:

Provide a class for authoring a simple letter. In the constructor, supply the names of the sender and the recipient:

	public Letter(String from, String to)

Supply a method

	public void addLine(String line)

to add a line of text to the body of the letter.

Supply a method
	
	public String getText()

that returns the entire text of the letter. The text has the form:<br>

Dear recipient name:<br>
blank line<br>
first line of the body<br>
second line of the body<br>
last line of the body<br>
blank line<br>
Sincerely,<br>
blank line<br>
sender name.<br>

Also supply a main method that prints this letter.<br>

Dear John:<br>
I am sorry we must part.<br>
I wish you all the best.<br>
Sincerely,<br>
Mary.<br>

Construct an object of the Letter class and call addLine twice.

	import java.util.*;
		
	public class Letter
	{
		public static String From()
		{
			Scanner kb = new Scanner(System.in);
			System.out.println("Enter sender's name: ");
			String from = "\n\nSincerely, \n\n" + kb.nextLine() + ".";
			return from;
		}
	
		public static String getText()
		{
			Scanner kb = new Scanner(System.in);
			System.out.println("Enter three lines of text: ");
			String line = "";
			for(int i = 0; i<3; i++)
			{
				line = line.concat("\n" + kb.nextLine());
				
			}
			return line;
		}
		
		public static String To()
		{
			Scanner kb = new Scanner(System.in);
			System.out.println("Enter recipient's name: ");
			String to = "\n\nDear " + kb.nextLine() + ",\n";
			return to;
		}	
		
		public static void main(String[] args)
		{
			String Header = To();
			String Body = getText();
			String Footer = From();
			
			System.out.print(Header + Body + Footer);
		}
	}
