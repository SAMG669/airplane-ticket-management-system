# airplane-ticket-management-system
import numpy as np
from pprint import pprint
def dp_dynamic_pricing(N, T, P, D):

    M = len(P)
    V = np.zeros((T+1, N+1))
    policy = [[None]*(N+1) for _ in range(T)]


    for t in range(T-1, -1, -1):
        for s in range(N+1):
            best = -1
            best_choice = (0,0)
            for j,p in enumerate(P):
                max_possible_sell = min(s, int(D[t][j]))

                for x in range(max_possible_sell+1):
                    revenue = p * x + V[t+1][s-x]
                    if revenue > best:
                        best = revenue
                        best_choice = (j, x)
            V[t][s] = best
            policy[t][s] = best_choice
    return V, policy

if __name__ == '__main__':
    N = 50
    T = 6
    P = [50, 100, 150, 200]

    D = np.array([
        [30, 10, 4, 1],
        [25, 12, 6, 2],
        [20, 10, 8, 3],
        [15, 8, 6, 4],
        [10, 6, 4, 3],
        [5, 4, 3, 2],
    ])
