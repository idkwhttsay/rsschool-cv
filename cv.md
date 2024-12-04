# Tatarinov Daniil

![Photo](https://media.licdn.com/dms/image/D4D03AQFtRieXvYUAQw/profile-displayphoto-shrink_400_400/0/1708682474156?e=1724889600&v=beta&t=JHxPiU1HfBSf8pl6rZoYCxY1OabK_XogG3VADnUn8SU)

## Junior Full-Stack Developer

***

## Contact information:

**Phone:** +77776198227

**E-mail:** danil.tatarinov.00@gmail.com

**Telegram:** @DanTatar

**RSSchool Discord Name:** Daniil Tatarinov (@idkwhttsay)

**Address:** Satpayev St. 133/2 • Almaty, Kazakhstan

[LinkedIn](https://www.linkedin.com/in/daniil-tatarinov-a463712a0/)

[Instagram](https://www.instagram.com/tatarinov.danil/)

[GitHub](https://github.com/idkwhttsay)

***

## Education

### National Physics Mathematics School (NPhMS); Almaty, Kazakhstan
* **Date of Graduation:** June 2024
* **GPA:** 4.93/5
* **SAT:** EBRW-660 Math-800 Overall: 1460/1600
* **Advanced Placement:** Calculus BC - 5, Calculus AB - 5, Computer Science A - 5
* **IELTS Overall:** 7.5/9.0

### Georgia Institute of Technology;  Atlanta, GA, USA
* **Date of Graduation:** 2028
* **Ranking:** #36 in the World - Times Higher Education, #8 in Computer Science in US - US News

***

## About Me
I'm a responsible leader with passions for software development and creative coding problem-solving who believes that connecting communities diversifies mindsets and creates progress.

***

## Awards
* Republican Olympiad in Informatics - X3 Bronze(2022, 2023, 2024)
* Eurasian Olympiad in Informatics - Bronze(2022) Gold(2023)
* Kazakhstan Bilim Olympiad in Informatics - Silver(2022)
* International Zhautykov Olympiad in Computer Science - Bronze(2024)
* Best Class of 2024 NPhMS School Graduate Award
* "Mektep Maktanyshy" (Hope of the School) Award (2023, 2024)

***

## Experience, Extracurricular Activities

### METAFORRA, QADAM App - Almaty, Kazakhstan
**Junior Back-End Developer (Nest.JS)**

* Programmed w/ team of 11 the monetary awards system in pedometer w/ National Bank of Kazakhstan’s support, and developed a “Digital Tenge”
* Connected external APIs, SMS-provider and learnt database ops
* Operated with PostgreSQL, PostMan, Redis, Docker
* Mastered Nest.JS framework and Typescript programming language
* Received a letter of appreciation from the National Bank of Kazakhstan

### Commentarius - subject & HW management app
**Founder, Full-Stack programmer**

* Designed app structure in Figma, learnt React Native from scratch in a month
* Wrote ~1500 lines of code
* Implemented Firebase database for Google SingIn and storing data
* Posted it in open source on [GitHub](https://github.com/idkwhttsay/Commentarius.git)

### Almaty Code Cup - International competitive programming tournament
**Founder, Head-Organizer**

* Fundraised $10000 for the Prize Fund and organization expenses
* Sponsored by Yandex, PhysTech School Almaty, Kazakhstan Competitive Programming Federation, MyExtra, KBTU
* Boosted project synergy by attracting top problem-setters and International Olympiad winners from 3 countries
* Attracted 880 participants from 55 cities and negotiated with Kazakhstan Competitive Programming Federation & other organizations for securing free advertisement
* Produced test generators, checkers, validators, statements, and main solutions in C++ for several tasks for Qualifying and Final Rounds
* [Website](https://acc.bc-pf.org/)

### “Easy to Learn” Book - guide to Olympiad mathematics world
**Co-author**

* Proved math & number theory algorithms in Computer Science, adapted math theorems to C++ in the most trivial way, optimized them, mathematically proved every step
* Mission of my chapter: show application of some of the math theorems in competitive programming, [link](https://shorturl.at/hlNRV)
* Wrote a 13-page chapter w/practice Qs, solutions on number theory and collaborated with Olympiad math community

***

## Code Example

Codeforces Round 190 (Div. 1) - [Task E. Ciel and Gondolas.](https://codeforces.com/problemset/problem/321/E?locale=en)

``` C++
#include <bits/stdc++.h>
#define pb push_back
#define sz(v) (int)v.size()
#define in insert
#define ld double
#define all(v) v.begin(),v.end()
#define ent "\n"
#define S second
#define F first
//#define int long long
#define pii pair <int, int>

/*#pragma GCC optimize("O3")
#pragma GCC optimize("O2,unroll-loops")
#pragma GCC target("avx,avx2")*/

using namespace std;

//const int INF = 1e18;
const int N = 3e5+123;
const int MAX = 5e4;
const int mod = 1e9+7;
const double PI = 3.1415926536;
const int B = 260;

const double eps = 1e-20;

//mt19937 rnd(chrono::steady_clock::now().time_since_epoch().count());

void speed(){
    ios_base::sync_with_stdio(0);
    cin.tie(0);
    cout.tie(0);
}

int dx[4] = {-1, 0, 0, 1};
int dy[4] = {0, -1, 1, 0};

int n,k;
int dp[4010][810];
int a[4010][4010];

int get(int l, int r){
    return (a[r][r]-a[r][l-1]-a[l-1][r]+a[l-1][l-1])/2;
}

void calc(int L, int R, int opt_L, int opt_R, int K){
    if(L > R) return;
    int mid = (L+R)/2;
    int res = mod;
    int opt_pos;

    for(int i = opt_L; i <= opt_R; ++i){
        if(dp[i-1][K-1] + get(i, mid) < res){
            res = dp[i-1][K-1] + get(i, mid);
            opt_pos = i;
        }
    }

    dp[mid][K] = res;
    calc(L, mid-1, opt_L, opt_pos, K);
    calc(mid+1, R, opt_pos, opt_R, K);
}

void solve() {
    cin >> n >> k;
    for(int i = 1; i <= n; ++i){
        for(int j = 1; j <= n; ++j){
            cin >> a[i][j];
            a[i][j] += a[i-1][j]+a[i][j-1]-a[i-1][j-1];
        }
    }

    for(int i = 1; i <= n; ++i){
        dp[i][1] = get(1, i);
    }

    for(int i = 2; i <= k; ++i){
        calc(1,n,1,n,i);
    }

    cout << dp[n][k];
}

signed main() {
    speed();
    int tt = 1;
    //cin >> tt;
    while(tt --){
        solve();
        cout << ent;
    }
}
```

***

## Skills

* Designing apps in Figma
* Operating with servers and SQL databases
* HTML and CSS development skills
* Object oriented programming in Java
* Back-End development on Nest.JS
* C++ advanced competitive programming skills