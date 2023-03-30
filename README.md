#include <iostream>
int main(){
  int N;
  std::cout<<"N=...? ";
  std::cin>>N;
  long sum_left=0, sum_right=0;
  bool correct=true;;
  for (int n=1; n<=N; ++n){
    int power=n, i;
    sum_right+=n;
    for (i=0; i<5; ++i)
      power*=n;
    sum_left+=power;
    for (i=5; i<7; ++i)
      power*=n;
    sum_left+=power;
    if (sum_left==2*sum_right*sum_right*sum_right*sum_right){
      std::cout<<"Correct for n="<<N<<", "<<sum_left<<"="<<sum_left<<std::endl;
    }
    else{
      correct=false;
      std::cout<<"Incorrect for n="<<N<<", "<<sum_left<<"!="<<2*sum_right*sum_right*sum_right*sum_right<<std::endl;
    }
  }
  std::cout<<(correct?"Statement correct":"Statement incorrect")<<std::endl;
  return 0;
}

//kirilov kirill DKIP-281 - внес изменения
