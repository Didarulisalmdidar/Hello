# Hello
#include<bits/stdc++.h>
#define ll long long
using namespace std;
int main()
{
    ll t;
    cin>>t;
    while(t--)
    {
        ll n;
        cin>>n;
        ll ar[n+2];
        for(ll i=1;i<=n;i++)
        {
            cin>>ar[i];
        }
        ll pre[n+2];
        pre[0]=0;
        for(ll i=1;i<=n;i++)
            pre[i]=pre[i-1]^ar[i];
            ll kk=0;
        for(ll i=1;i<n;i++)
        {
            ll a=pre[i];
            ll b=pre[n]^pre[i];
            if(a==b)
            {
                kk=1;
                break;
            }
        }
        for(ll i=1;i<n-1;i++)
        {
            for(ll j=i+1;j<n;j++)
            {
                ll a=pre[i];
                ll b=pre[i]^pre[j];
                ll c=pre[n]^pre[j];
                if(a==b and b==c)
                {
                    kk=1;
                    break;
                }
            }
        }
        if(kk==1)
            cout<<"YES"<<endl;
        else
            cout<<"NO"<<endl;
    }
}
