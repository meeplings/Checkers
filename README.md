Checkers
========
package checkers;
import java.util.Scanner;
public class checkersMain {
	public static void main (String args[]){
		//objects
		Scanner scan = new Scanner(System.in);
		checkersTiles tile = new checkersTiles();
		checkersBoard board = new checkersBoard();
		
		// variables
		String move = "";
		int bc = 0;
		int rc = 0;
		int p1T = 0;
		int p2T = 0;
		int x1 =0;
		int x2 = 0;
		int y1 = 0;
		int y2 = 0;
		String pieceType = "";
		boolean turn = false;
		// false -> player 1's turn
		// true -> player 2's turn
		boolean game = false;
		boolean winner = false;
		// false -> p1 wins
		// true -> p2 wins
		
		
		System.out.println( "Welcome to the game of checkers!");
		
		// Game loop
		while(game == false){
			board.setBoard(checkersBoard.board);
			System.out.println("The current board is as follows(0 = empty square, 1 = black square, 2 = red square, 3 = red black king, 4 = red king):");
		       for(int i = 0; i < checkersBoard.board.length; i++){
		    	   for(int j = 0; j < checkersBoard.board[i].length; j++){    
		    		   System.out.print(checkersBoard.dispBoard(i,j, checkersBoard.board) + "  ");
		    		   if(j != 1 || j != 3)
		    			   bc++;
		    		   if( j != 2 || j != 4)
		    			   rc++;
		    		   if(bc == 64){
		    			   game = true;
		    			   winner = true;
		    		   }
		    		   if(rc == 64){
		    			   game = true;
		    			   winner = false; 
		    		   }
		    	   }
		    	   System.out.println();
			}
		       while(turn == false){
		    	   System.out.println("It is player one's turn");
		    	   System.out.println("Are you going to move a king(enter k) or a normal piece(enter n)?");
		    	   pieceType = scan.next();
		    	   
		    	   if(pieceType.equals("n"));{
		    		   
		    		   System.out.println("Which of the following moves would you like to make? \nmake a move(enter m) or take a tile(enter t)?");
			    	   move = scan.next();
			    	   if(move.equalsIgnoreCase("m")){
			    		   
			    		   System.out.println("Enter the x co-ordinate of the piece you want to move:");
			    		   x1 = scan.nextInt();
			    		   System.out.println("Enter the y co-ordinate of the piece you want to move:");
			    		   y1 = scan.nextInt();
			    		   System.out.println("Enter the x co-ordinate of the tile you want to move into:");
			    		   x2 = scan.nextInt();
			    		   System.out.println("Enter the y co-ordinate of the tile you want to move into:");
			    		   y2 = scan.nextInt();
			    		   tile.moveTile(x1,y1,x2,y2,turn);
			    	   }
			    	   else if(move.equalsIgnoreCase("t")){
			    		   
			    		   System.out.println("Enter the x co-ordinate of the piece you want to move:");
			    		   x1 = scan.nextInt();
			    		   System.out.println("Enter the y co-ordinate of the piece you want to move:");
			    		   y1 = scan.nextInt();
			    		   System.out.println("Enter the x co-ordinate of the tile you want to take:");
			    		   x2 = scan.nextInt();
			    		   System.out.println("Enter the y co-ordinate of the tile you want to take:");
			    		   y2 = scan.nextInt();
			    		   tile.takeTile(x1,y1,x2,y2,turn);
			    	   }   
		    	   }  
		    	    if(pieceType.equals("k")){
		    		   System.out.println("Which of the following moves would you like to make? \nmake a move(enter m) or take a tile(enter t)?");
			    	   move = scan.next();
			    	   if(move.equalsIgnoreCase("m")){
			    		   
			    		   System.out.println("Enter the x co-ordinate of the piece you want to move:");
			    		   x1 = scan.nextInt();
			    		   System.out.println("Enter the y co-ordinate of the piece you want to move:");
			    		   y1 = scan.nextInt();
			    		   System.out.println("Enter the x co-ordinate of the tile you want to move into:");
			    		   x2 = scan.nextInt();
			    		   System.out.println("Enter the y co-ordinate of the tile you want to move into:");
			    		   y2 = scan.nextInt();
			    		   tile.moveTileKing(x1,y1,x2,y2,turn);
			    	   }
			    	   else if(move.equalsIgnoreCase("t")){
			    		   
			    		   System.out.println("Enter the x co-ordinate of the piece you want to move:");
			    		   x1 = scan.nextInt();
			    		   System.out.println("Enter the y co-ordinate of the piece you want to move:");
			    		   y1 = scan.nextInt();
			    		   System.out.println("Enter the x co-ordinate of the tile you want to take:");
			    		   x2 = scan.nextInt();
			    		   System.out.println("Enter the y co-ordinate of the tile you want to take:");
			    		   y2 = scan.nextInt();
			    		   tile.takeTileKing(x1,y1,x2,y2,turn);
			    	   }     
		    	   }
		       }
		       
			game = true;
			}
		// Game over
		if(game == true){
			System.out.println("Game over!");
			
				System.out.println("P1 wins!");
			}
		
				System.out.println("P2 wins!");
			}
		
	
}
