Sprague-Grundy Theorem for Impartial Games

Learning Resources

1. https://www.youtube.com/watch?v=HdRgnzRk56Q&feature=youtu.be <br/>
   Watch at 1.75x speed

2. http://web.mit.edu/sp.268/www/nim.pdf <br/>
   This article has some interesting games too

3. https://codeforces.com/blog/entry/63054 <br/>
   I didn't read this, because it escalates pretty quickly (has problems related to FFT too)

Problems

All the ones we did in the lecture were covered in the youtube link posted above

Some other ones - 

1. ADAPAWN - https://www.codechef.com/COOK102B/problems/ADAPWNS <br/>

   In this  question, the main observation was that only the alternate piles matter. That part was correct. <br/>
   What I said about the summing up the alternate piles and that reduces to a 1 pile game of removing only 1 or 2 coins is wrong. That reduction is incorrect. <br/>
   A counter example can be something like (x 1 y 2) ( x,y is any number). The sum is 3, and thus it's a losing state in the 1 pile game of removing 1 or 2 coins, but it is actually a winning state.

   The first move is (x 1 y 1), for which if the opponent plays anything else apart from the 1, it can be mirrored. The game will either go to (x 0 y 1) or (x 1 y 0), to which we can just move the one. Now, until the board becomes 0, we can keep mirroring our opponent's moves since the board's confuguration is (x 0 y 0).  

  
   The actual answer is that you consider these n/2 alternating piles starting from the end as different piles of the (1,2) games, compute the grundy number for each and then take the xor.
   If the xor is 0, then it's a losing state, else it's a winning state.

   Let's call the piles that matter as significant and the others as insignificant. The idea is that this reduces to a n/2 pile game of nim(after you compute the grundy number for this new game)

   It's also bogus nim as, if the opponent does not move from these piles, he moves form the insignificant ones and you can always mirror his move.

   The reason that our significant piles (the alternating ones) start from the last and alternate is because if we take the other n/2 piles, then we will
   lose our ability to mirror the opponents move. The only move we can't mirror is if the opponent plays from the last pile.Hence we need the last pile, and thus we choose our alternating piles which includes this last one. 

  You can prove that this approach is correct as it's a direct reduction to nim, which is correct. 


   

2. ADAPAWN editorial - https://discuss.codechef.com/questions/144217/adapwns-editorial <br/>
   This editorial has some extra problems

3. Hackerrank - https://www.hackerrank.com/domains/algorithms?filters%5Bsubdomains%5D%5B%5D=game-theory
