#include <bits/stdc++.h>
using namespace std;
typedef long long ll;

ll look_at_learned_questions(const vector<vector<ll> > &table, vector<ll> &ans, const vector<ll> &T, const ll &M, const ll &N){
    ll i = M, w = N, k = 0;
    while(i >= 0 && w >= 0 && table[w][i] != 0){
        if(table[w][i] == table[w][i-1]){
            ans[i] = 0;
            i--;
        }
        else{
            ans[i] = 1;
            w = w - T[i];
            k++;
            i--;
        }
    }
    return k;
}

void fill_table(vector<vector<ll> > &table, const vector <ll> &T,
                const vector <ll> &K, vector<ll> &ans,  const ll &M, const ll &N){
    for(ll i = 1; i <= M; i++){
        for(ll w = 1; w <= N; w++){
            table[w][i] = table[w][i-1];
            if(T[i] <= w){
                table[w][i] = max(table[w][i], (table[w - T[i]][i-1] + K[i]));
            }
        }
    }
    cout << table[N][M] << endl;
    cout << "The number of questions learned: " <<  look_at_learned_questions(table, ans, T, M, N) << endl;
}

void print_ans(const vector<ll> &ans){
    cout << "Numbers of learned questions: ";
    for(ll j = 1; j < ans.size(); j++){
        if(ans[j] == 1){
            cout << j << " ";
        }
    }
}

int main(){
    ll M, N;
    cin >> M >> N;
    vector <ll> T(M+1);
    vector <ll> K(M+1);
    vector<ll> ans(M+1);
    vector<vector<ll> > table(N+1, ans);

    for(ll i = 1; i <= M; i++) {
        cin >> T[i] >> K[i];
    }

    fill_table(table, T, K, ans, M, N);
    print_ans(ans);
    
    return 0;
}
