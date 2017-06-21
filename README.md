# hw2

#include <iostream>

using namespace std;

const int Telemarketer_Terrifier_Index = 15485863;

int main()
{
     long LastNumber = 1111111;
     int busy = 0;
     int noAns = 0;
     int answered = 0;
     int salemade = 0;
     short NumOfCalls = 0;
    do{
        NumOfCalls ++;
        long PhoneNumber = (( LastNumber * 7919 + 104729) % Telemarketer_Terrifier_Index) % 8999999 + 1000000;
        cout << "Calling " <<PhoneNumber <<"..." <<endl;
        LastNumber = PhoneNumber;
        int ComputedNumber = PhoneNumber%3;

        if(ComputedNumber == 0)
        {
            busy ++;
        }
        else if (ComputedNumber == 1)
        {
            noAns ++;
        }
        else if (ComputedNumber == 2 && PhoneNumber%100>75)
        {
            answered++;
            salemade++;
            cout <<"Sale made at phone number " << PhoneNumber <<endl;
        }
        else
        {
            answered++;
        }





    }while(NumOfCalls < 300 || salemade < 30);
    return 0;

}
