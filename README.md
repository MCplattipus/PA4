//PA4
//project 4 simple shell
#include <string>
#include <vector>
#include <iostream>

using namespace std;

struct three_str
{
	string toke_type;
	string token;
	string usage;
};

//void scan(vector<three_str> scantokens, string input);



int main(int argc, char const *argv[])
{
	string input;
	cout << "Enter a sentence: ";

	
	
	vector<three_str> tokens;

	while(input != "bye")
	{
		getline(cin, input);
		
			string::size_type position = input.find(' ');
			three_str sub_string;
			cout << position << endl;
			while(position != string::npos)
			{
				

				sub_string.token = input.substr(0,position);
				// if (sub_string.token == ("defprompt" || "cd" || "listprocs" || "run" || "assignto" || "<bg>"))
				// {
				// 	sub_string.toke_type = "keyword";
				// }
				// else if (sub_string.token[0] == '$' || sub_string.token == ("PATH" || "ShowTokens") ) 
				// {
				// 	substring.toke_type = "variable";
				// }
				// else if (sub_string.token == ("#" || "="))
				// {
				// 	sub_string.toke_type = "metaChar";
				// }
				// else if (sub_string.token[0] ==  "\"")
				// {
				// 	sub_string.toke_type = "string"
				// }
				// sub_string.usage = ' ';

				cout << sub_string.token << endl;

				input.erase(0,position+1);
				

				tokens.push_back(sub_string);
				position = input.find(' ');
				
			}

			sub_string.token = input;
			tokens.push_back(sub_string);

		


//scan(tokens, input);
		cout << "after scan" << endl;
		for (int i = 0; i != tokens.size(); ++i)
		{
			string temp_token = tokens[i].token;
			cout << i << " = " << temp_token << endl;
		}


	}



	return 0;
}

/*scan(vector<three_str> &scantokens, string input)
{
			string::size_type position = input.find(' ');
			three_str sub_string;
			cout << position << endl;
			while(position != string::npos)
			{
				

				sub_string.token = input.substr(0,position);
				sub_string.toke_type = ' ';
				sub_string.usage = ' ';

				cout << sub_string.token << endl;

				input.erase(0,position+1);
				

				scantokens.push_back(sub_string);
				position = input.find(' ');
				
			}

			sub_string.token = input;
			scantokens.push_back(sub_string);

			return;
};*/
