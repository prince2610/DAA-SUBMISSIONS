#include <bits/stdc++.h>
#include <vector>
using namespace std;
 
// Function to find the cheapest cost
// from source to destination using K stops
int findCheapestPrice(int cities,
                      vector<vector<int> >& flights,
                      int src, int dst, int stops)
{
    // Distance from source to all other nodes
    vector<int> dist(cities, INT_MAX);
    dist[src] = 0;
 
    // Do relaxation for V-1 vertices
    // here we need for K stops so we
    // will do relaxation for k+1 stops
    for (int i = 0; i <= stops; i++) {
 
        vector<int> intermediate(dist);
 
        for (auto flight : flights) {
 
            if (dist[flight[0]] != INT_MAX) {
                intermediate[flight[1]]
                    = min(intermediate[flight[1]],
                          dist[flight[0]]
                              + flight[2]);
            }
        }
 
        // Update the distance vector
        dist = intermediate;
    }
 
    // Return the final cost
    return dist[dst] == INT_MAX ? -1 : dist[dst];
}
 
// Driver Code
int main()
{
    // Input flight : {Source, Destination, Cost}
    vector<vector<int> > flights
        = { { 4, 1, 1 }, { 1, 2, 3 }, { 0, 3, 2 }, { 0, 4, 10 }, { 3, 1, 1 }, { 1, 4, 3 } };
 
    // vec, n, stops, src, dst
    int stops = 2;
    int totalCities = 5;
 
    // Given source and destination
    int sourceCity = 0;
    int destCity = 4;
 
    // Function Call
    long ans = findCheapestPrice(
        totalCities, flights, sourceCity,
        destCity, stops);
    cout << ans;
    return 0;
}
