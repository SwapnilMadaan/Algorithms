"Q.1: Given order of n matrices, find the minimum multiplication operations required
for multiplying n matrices."

#include<iostream>
using namespace std;

#define INFINITY 1000
#define MAX_NODES 1024
//int n,dist[MAX_NODES][MAX_NODES];
typedef	enum { permanent,tentative } label_type;

struct state
	{
		int predecessor;
		int length;
		label_type label;
	};
void shortest_path(int s,int t,int n, int ** dist)
{
	state* st=new state[n];

	int i,k,min;
	 state* p;
	for( i=0; i<n ; i++)
	{
	    p = &st[i];
		p->predecessor = -1;
		p->length=INFINITY;
		p->label = tentative;
	}

	st[t].length=0;
	st[t].label=permanent;
	k=t;

	do
	{
		for(i=0;i<n;i++)
			if(dist[k][i]!=0 && st[i].label==tentative)
			{
				if((st[k].length + dist[k][i])<st[i].length)
				{
					st[i].predecessor=k;
					st[i].length=st[k].length+dist[k][i];
				}
			}


			k=0;min=INFINITY;
			for(i=0;i<n;i++)
				if(st[i].label==tentative && st[i].length<min)
				{
					min=st[i].length;
					k=i;
				}
				st[k].label=permanent;
	}
	while(k!=s);
	int * path = new int [n];

    //Printing the path
    cout<<"\nPATH::/n";
	i=0;k=s;
	do
	{
	    cout<<k <<" --> ";
		path[i++]=k;
		k=st[k].predecessor;
	}
	while(k>=0);
	cout<<endl;



}

int main()
{
	int n,s,t;
	cout<<"Enter the number of vertices"<<"\n";
	cin>>n;
	cout<<"Enter the source vertex"<<"\n";
	cin>>s;
	cout<<"Enter the destination"<<"\n";
	cin>>t;


	int ** dist = new int * [n];

	for(int  I = 0 ; I<n ; I++)
	{
		dist[I] = new int [n];
	}
	for(int i=0;i<n;i++)
	{
		cout<<"Enter the weights for row"<<i<<"\n";
		for(int j=0;j<n;j++)
		{
			cin>>dist[i][j];
		}
	}
	shortest_path(s,t,n,dist);

	return 0;
}
