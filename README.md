# passcheck
class Solution {
public:
    bool strongPasswordCheckerII(string password) {
        int u,l,d,special;
       
        int i;
        bool flag=false;
       int n=password.length();
       if(n<8){
           return false;
       } 
       u=l=d=special=0;
       for(int i =0;i<n;i++){
           if(isupper(password[i])){
               u++;
           }
           else if(islower(password[i])){
               l++;
           }
           else if(isdigit(password[i])){
               d++;
           }
           else{
               special++;
           }
           if(i>0){
               if(password[i-1]==password[i]){
                   flag=true;
                   break;
               }
           }
       }
       if(l>0 &&d>0 && u>0 && special>0 && flag==false){
           return true;
       }
       return false;
    }
};
