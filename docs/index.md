##Welcome
```c++
#include <iostream>
#include <fstream>
using namespace std;
const int n = 5;
string items[n];
bool rep;

void check(){
    for (int z = 0; z < n; ++z) {
        for (int i = 0; i < n; ++i) {
            for (int j = 0; j < n; ++j) {
                if(i!=j){
                    if(items[i] == items[j]){
                        rep = true;
                        items[i]=items[i+1];
                    }
                }
            }
        }
    }
    }

int main() {

    cout<< "If you are over with your list then just keep on pressing enter :)"<<endl;
    cout<<"Enter items: ";
    int f = 0;
    do {
        for (int i = 0; i < n; ++i) {
            cin >> items[i];
        }
        f++;
    } while (f<1);
    check();

    for (int i = 0; i < n; ++i) {
        cout<<items[i]<<endl;
    }

    ofstream myfile ("items.txt");
    if (myfile.is_open())
    {
        myfile << "My list: \n";
        myfile << "\n";
        for (auto & item : items) {
            myfile << item << endl;
        }
        if (rep){
            myfile << "There were some items that were repeated so i deleted it...";
        }
        myfile.close();

    }
    else cout << "Unable to open file";
    return 0;
}


```