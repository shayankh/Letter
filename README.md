/*Problem 8.11:

Provide a class for authoring a simple letter. In the constructor, supply the names of
the sender and the recipient:
public Letter(String from, String to)
Supply a method
public void addLine(String line)
to add a line of text to the body of the letter.
Supply a method
public String getText()
that returns the entire text of the letter. The text has the form:
Dear recipient name :
blank line
first line of the body
second line of the body
last line of the body
blank line
Sincerely,
blank line
sender name.
Also supply a main method that prints this letter.
Dear John:
I am sorry we must part.
I wish you all the best.
Sincerely,
Mary
Construct an object of the Letter class and call addLine twice.		*/

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
