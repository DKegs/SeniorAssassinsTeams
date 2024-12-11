import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import java.util.Random; 

public class TeamAssignment{
	public TeamAssignment() {
		
	}
	
	
	//Randomizes Team Hunting *****************
	public static ArrayList<Integer> Randomize(int NumOfTeams){
		Random rand = new Random(); 
		ArrayList<Integer> Hunt = new ArrayList<Integer>();
		ArrayList<Boolean> Hunted = new ArrayList<Boolean>();
		for(int i = 0; i < NumOfTeams; i++) {
			Hunted.add(false);
		}
		//sets all teams as not being hunted
		for(int i = 0; i < Hunted.size(); i++) {
			Hunted.set(i, false);
		}
		//setting and keeping track of the original team
		int initial = rand.nextInt(NumOfTeams);
		int current = initial;
		int hunting = rand.nextInt(NumOfTeams);
		while(initial == hunting) {
			hunting = rand.nextInt(NumOfTeams);
		}
		Hunt.add(initial + 1);
		Hunt.add(hunting + 1);
		Hunted.set(hunting, true);
		Hunted.set(initial, true);
		Hunted.set(0, false);
		current = hunting;
		//loop that sets all teams to hunt other teams without any overlaps
		while(Hunted.contains(false)) {
			   hunting = rand.nextInt(NumOfTeams);
			   while(current == hunting || Hunted.get(hunting) == true) {
					hunting = rand.nextInt(NumOfTeams);
			   }
			   Hunt.add(hunting + 1);
			   Hunted.set(hunting, true);
			   current = hunting;
		}
		return Hunt;
	}
	
	public static ArrayList<Integer> SortedRandomize(ArrayList<Integer> Hunting){
		Collections.sort(Hunting);
		return Hunting;
	}
	
	
	
	//Converts Numbers to Team Names and Makes it Organized ****************************
	public static void ConvertToText(ArrayList<Integer> Hunting, ArrayList<String> TeamNames) {
		for(int i = 0; i < Hunting.size() - 1; i++) {
			System.out.println(TeamNames.get(Hunting.get(i)) + "is hunting " + TeamNames.get(Hunting.get(i + 1)));
		}
		System.out.println(TeamNames.get(Hunting.get(Hunting.size() - 1)) + "is hunting " + TeamNames.get(Hunting.get(0)));
	}
	
