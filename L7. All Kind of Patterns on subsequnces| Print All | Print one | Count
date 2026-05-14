L7. All Kind of Patterns in Recursion | Print All | Print one | Count
Problem Statement

Given an array and a value K,
print all subsequences whose sum is exactly K.

Example:

Array = [1,2,1]
K = 2

Output:

[1,1]
[2]
Main Recursion Idea

At every index we have 2 choices:

Take the element
Not take the element
==================================================================================================================================

#include <bits/stdc++.h>
using namespace std;

void fun(int ind, int arr[], int n, int tar,
         vector<int>& ds, int sum) {

    // Base Case
    if(ind == n) {

        if(sum == tar) {

            for(auto it : ds) {
                cout << it << " ";
            }

            cout << endl;
        }

        return; // VERY IMPORTANT
    }

    // Pick
    ds.push_back(arr[ind]);
    sum += arr[ind];

    fun(ind + 1, arr, n, tar, ds, sum);

    // Backtrack
    ds.pop_back();
    sum -= arr[ind];

    // Not Pick
    fun(ind + 1, arr, n, tar, ds, sum);
}

int main() {

    int arr[] = {1,2,1};

    int n = sizeof(arr)/sizeof(arr[0]);

    vector<int> ds;

    fun(0, arr, n, 2, ds, 0);

    return 0;
}

=============================================================================================================================================

print one 

Main Difference
Problem	Return Type	Stops Recursion?
Print All	void	No
Print One	bool	Yes
Count	int	No
==============================================================================================================================================

#include <bits/stdc++.h>
using namespace std;

bool fun(int ind, int arr[], int n, int tar,
          vector<int>& ds, int sum) {

    // Base Case
    if(ind == n) {

        if(sum == tar) {

            for(auto it : ds) {
                cout << it << " ";
            }

            cout << endl;

            return true;
        }

        return false;
    }

    // Pick
    ds.push_back(arr[ind]);
    sum += arr[ind];

    if(fun(ind + 1, arr, n, tar, ds, sum) == true) {
        return true;
    }

    // Backtrack
    ds.pop_back();
    sum -= arr[ind];

    // Not Pick
    if(fun(ind + 1, arr, n, tar, ds, sum) == true) {
        return true;
    }

    return false;
}

int main() {

    int arr[] = {1,2,1,3};

    int n = sizeof(arr)/sizeof(arr[0]);

    vector<int> ds;

    fun(0, arr, n, 5, ds, 0);

    return 0;
}

========================================================================================================================================
count 
========================================================================================================================================
#include <bits/stdc++.h>
using namespace std;

int fun(int ind, int arr[], int n, int tar, int sum) {

    // Base Case
    if(ind == n) {

        if(sum == tar) {

            return 1;
        }

        return 0;
    }
    sum += arr[ind];

    int l = fun(ind + 1, arr, n, tar, sum);

    // Backtrack
    sum -= arr[ind];

    // Not Pick
    int r = fun(ind + 1, arr, n, tar, sum);

    return l + r;
}

int main() {

    int arr[] = {1,2,1,3};

    int n = sizeof(arr)/sizeof(arr[0]);

    cout << fun(0, arr, n, 5, 0);

    return 0;
}
========================================================================================================================================
