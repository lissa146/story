# story
#include<iostream>
#include<Windows.h>
using namespace std;
/// <summary>
/// global variables
/// </summary>
string inventory[10] = { " ", " ", " ", " ", " ", " ", " ", " ", " ", " " };
int health = 100;
//funtions
int gold = 100;
void Shop();
char input;

void Battlesystem();
void ItemDropper();
void Cat();
bool Haswon = false;
int main() {
	//local variables
	srand(time(NULL));//rand the seed so it changes what it give you for item dropper
	int room = 1;
	char direction;
	int milkshake = 0;
	bool chest1 = false;//have we have open teh frist chest
	bool Realend = false;
						//bool chests[5] = { 0,0,0,0,0 };//if u have alot of chest
	Beep(800, 200);
	cout << "you drive to the mouiantans but soon you see a deer you crash in to the woods" << endl;
	cout << "you wake up in a forest you can't see the beign of it nor the end of the forest you get out of your car," << endl;
	while (input != 'q' && Haswon == false && health >0) { //////game loop
		cout << "your inventory:" << endl;
		for (int i = 0; i < 10; i++) cout << inventory[i] << " ";
		cout << endl;
		 
		switch (room) {
		case 1:
			
			system("color 0A");
			cout << "you can go (e)ast but your head feels horrible " << endl;
			cout << "you go to your nearly deystoryed trunk and open a (b)ox" << endl;
			cout << "theres a rock? " << endl;
			if (Realend == true && inventory[0] == "left dounut chunk" && inventory[1] == "donut chunk" && inventory[2] == "half a dounut"){
				cout << "why did you come back?" << endl;
				cout << "oh well your stuck now" << endl;
				cout << "you see the forest cave in on you" << endl;
				cout << "you cant see you knock out" << endl;
				input = 'q'; //end game loop
				break;
			}
			if (inventory[0] != "left dounut chunk")
				if (inventory[0] == "left dounut chunk")
					cout << "you go east" << endl;
			cin >> direction;
			if (direction == 'e')
				room = 2;
			if (direction == 'r') {
				inventory[0] = "left dounut chunk";
			}
			if (direction == 'b') {
				if (chest1 == false) {
					cout << "the box has!" << endl;
					ItemDropper();
					chest1 = true;
				}
				else {
					cout << "the chest is empty" << endl;
				}
			}
			break;
		case 2:
			cout << "the forest is vast you can go (w)est to the forest or (e)ast where there is an abandoned house also there a (s)hop next to you" << endl;
			cout << "theres a treasure chest in the corner (o)pen?" << endl;
			cin >> direction;
			if (direction == 'e')
				room = 3;
			if (direction == 'o') {
				ItemDropper();
			}
			if (direction == 'w')
				room = 1;
			if (direction == 's') {
				Shop();
			}
			break;
		case 3:
			cout << "The house is big from the outside the forest is (w)est" << endl;
			cout << "or (s)outh were you see a corn field and see an eye in the corn field" << endl;
			cout << "the a barrel open it?" << endl;

			cin >> direction;
			if (direction == 'w')
			room = 2;
			if (direction == 's')
			room = 4;
			if (direction == 'o') {
			if (inventory[1] != "dounut chunk") {
			cout << "there's a donut chunk" << endl;
			inventory[1] = "dounut chunk";
			cout << "there might be another chunk in room 5" << endl;
			}
			else { cout << "there's nothing here!" << endl; }
			}
			break;




		case 4:
			cout << " you're in the corn field you can go deeper (s)outh but you feel like someone is staring at you or you can go back to the woods (n)orth " << endl;
			cin >> direction;
			if (direction == 'n')
				room = 3;
			if (direction == 's')
				room = 5;
			break;
		case 5:
			cout << " you walk though the corn field feeling a slight sense of uneasyness but you aee the end of the felid go (w)est or (n)orth back to the middle of the corn felid" << endl;
			cout << "theres a shuck of corn leaning downwards look at it?" << endl;
			cin >> direction;
			if (direction == 'w')
				room = 6;
			if (direction == 'n')
				room = 4;
			if (direction == 'l') {
				if (inventory[2] != "half a dounut") {
					cout << "there's half a donut" << endl;
					inventory[2] = "half a dounut";
					cout << "you might need this" << endl;
				}
				else { cout << "there's nothing here!" << endl; }
			}
			break;
		case 6:
			cout << " w or e " << endl;
			cin >> direction;
			if (direction == 'w')
				room = 7;
			if (direction == 'e')
				room = 5;
			break;

		case 7:
			cout << "you see the forest again expect now you see a door (o)pen it? or go (e)ast back to the corn feild " << endl;
			cin >> direction;
			if (direction == 'e')
				room = 6;
			if (direction == 'o')
				if (inventory[0] == "left dounut chunk" && inventory[1] == "dounut chunk" && inventory[2] == "half a dounut") {
					cout << "with the the power of a left dounut chunk,a dounut chunk and half a dounut can you open the mysterious door" << endl;
					room = 8;
					inventory[0] = " ";
				}
			break;
		case 8:
			cout << " the door opens you dont feel good you smell something of roiting flesh go (e)ast? or go (n)orth back to the door " << endl;
			cin >> direction;
			if (direction == 'e')
				room = 9;
			if (direction == 'n')
				room = 7;
			break;
		case 9:
			cout << "you see a monster you can (f)ight,(r)un    " << endl;
			cout << "       .----.__" << endl;
			cout << "      /---.__  \ " << endl;
			cout << "     /       `\ |" << endl;
			cout << "    | o     o  \|" << endl;
			cout << "  ./| .vvvvv.  |\ " << endl;
			cout << " / /| |     |  | \ " << endl;
			cout << "//' | `^vvvv'  |/\\" << endl;
			cout << "~   \          |  \\" << endl;
			cout << "    |          |   ~" << endl;
			cout << "     7        /" << endl;
			cout << " _ /    .    |" << endl;
			cout << "  -|_/\/ `--.|_" << endl;
			cin >> direction;
			if (direction == 'e')
				room = 10;
			if (direction == 'r')
				room = 8;
			if (direction == 'f') {
				Battlesystem();
				if (health > 0) {
					cout << " you've defeated the boss!" << endl;
					Realend = true;
				}
				else {
					cout << "you died " << endl;
					break;
				}
			}
			break;
		case 10:
			cout << "you finally see light though some bushes You escape " << endl;
			cin >> direction;
			Haswon == true;
			break;

		}


	}//end of loop
	if (Haswon == true) {
	cout << " you see the road " << endl;
	cout << " your so exsuted you fall down " << endl;
	}

}//end of main


///funtions

void Cat() {
	int num = rand() % 100;
	if (num < 20) ///
		cout << "milkshake licks his paw" << endl;
	if (num < 80) {
		cout << " /\_/\ " << endl;
		cout << "( o.o )" << endl;
		cout << " > ^ < " << endl;
		cout << "milkshake purrs" << endl;
	}
	if (num < 60) {
		cout << " _._     _,-'""`-._" << endl;
		cout << "(,-.`._,'(       |\`-/|" << endl;
		cout << "    `-.-' \ )-`( , o o)" << endl;
		cout << "          `-    \`_`\"'- " << endl;
		cout << "milkshake has a fish" << endl;
	}
	if (num < 40){
		cout << "   |\      _,,,---,,_" << endl;
	cout << "ZZZzz /,`.-'`'    -.  ;-;;,_" << endl;
	cout << "     |,4-  ) )-,_. ,\ (  `'-'" << endl;
	cout << "     '---''(_/--'  `-'\_) " << endl;
	cout << "milkshake is sleeping " << endl;
	}
	else
		cout << "you got nothing" << endl;


}//end of pet function

void Battlesystem() {
	system("color 1B");
	cout << " Battle commemcing" << endl;
	int MonsterHealth = 50;
	char input;
	while (health > 0 && MonsterHealth > 0) {
		
		
		if (inventory[1] != "shield") {///if you dont have the shield
			cout << " the Monster hits you for 95 Hp" << endl;
			health -= 95;
		}
		else {

			cout << " the monster hits you for 50 hp" << endl;
			health -= 50; 
			Beep(800, 200);
		}
		//player acctakcs
		if (inventory[1] == "sword") {
			cout << " you hit the monster with your sword for 30 hp" << endl;
			MonsterHealth -= 30;
		}
		else {
			cout << "you punch the monster" << endl;
			MonsterHealth -= 3;
		}


		cout << " your health : " << health << ". Monster Health :" << MonsterHealth << endl;
		system("pause");
		if (health > 0 && MonsterHealth)
			cout << " you can (f)ight, (r)un, or use a (p)otion" << endl;
		cin >> input;
		if (input == 'r') {
			int num = rand() % 100;
			if (num < 80) {
				cout << " you escape the battle" << endl;
				break;
			}
			else  cout << " chance to run failed" << endl;
		}
		if (input == 'p') {
			if (inventory[2] == "\'potion\'") {
				cout << (" gulg gulg ") << endl;
				health += 35;
				inventory[2] = " ";

			}

		}// end of user input




	}// end of battle loop[
	system("pause");
}//end of funtion








void ItemDropper() {
	int num = rand() % 100; //0-99
	if (num < 20) {
		cout << "sword" << endl;
		inventory[4] = "sword";
	}
	else if (num < 50) {
		cout << "you got a chicken named jorge" << endl;
		inventory[5] = "chicken named jorge";
	}
	else if (num < 75) {
		cout << "you got a sword" << endl;
		inventory[6] = "sword";
	}
	else {
		cout << "you get  nothing!" << endl;
	}


}

void Shop() {
	string input = "asdfasdfsadf";
	while (input != "q") {
		cout << "welcome to the shop" << endl;
		cout << "you have $" << gold << endl;
		cout << "items for sale" << endl;
		cout << " 1) cupcake $5" << endl;
		cout << " 2) chicken  50$" << endl;
		cout << " 3) leaf 100$ " << endl;
		cout << "4) key  10$" << endl;
		cout << " if you don't want anything (q)uit" << endl;
		cout << " what would u like to purchase" << endl;
		cin >> input;


		if (input == "1") {
			if (gold >= 5) {
				cout << " you bought the cupcake " << endl;
				inventory[1] = "cupcake";
				gold -= 5;
			}
			else
				cout << " u cant even buy a cupcake" << endl;
		}
		if (input == "2") {
			if (gold >= 50) {
				cout << " you bought the chicken named jorge " << endl;
				inventory[2] = "chicken named jorge";
				gold -= 50;
			}

			else
				cout << " u cant even buy a chicken" << endl;
		}
		if (input == "3") {
			if (gold >= 100) {
				cout << " you bought the leaf " << endl;
				inventory[3] = "leaf";
				gold -= 100;
			}

			else
				cout << " u cant even buy a leaf" << endl;
		}
		if (input == "4") {
			if (gold >= 10) {
				cout << " you bought the key " << endl;
				inventory[4] = "key";
				gold -= 10;
			}

			else
				cout << " u cant even buy a key" << endl;


		}

	}
}
