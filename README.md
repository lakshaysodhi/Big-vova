# Big-vova

#include <bits/stdc++.h>

using namespace std;

int main()
{
    int t;
    cin>>t;
    while(t--){
    
        int n;
        cin>>n;
        vector<int> A(n);
        for(int i=0;i<n;i++){
            cin>>A[i];
        }
        int max=A[0];
        int index=0;
        for(int i=1;i<n;i++){
            if(A[i]>max){
                max=A[i];
                index=i;
            }
        }
        int temp=A[0];
        A[0]=A[index];
        A[index]=temp;
        int gcd=A[0];
        for(int i=1;i<n;i++){
            max=__gcd(gcd,A[i]);
            index=i;
            for(int j=i+1;j<n;j++){
                if(__gcd(gcd,A[j])>max){
                    max=__gcd(gcd,A[j]);
                    index=j;
                }
            }
            gcd=max;
            temp=A[i];
            A[i]=A[index];
            A[index]=temp;
        }
        for(int i=0;i<n;i++){
            cout<<A[i]<<" ";
        }
        cout<<endl;
    }
    return 0;
}
