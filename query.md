Hello! I’m getting pretty confused on how to read binary, ~, the right shifting and negative numbers. from Q8 my understanding on how to read it was for example:

![image](https://github.com/user-attachments/assets/b4d80a2d-56f2-49d7-a960-1e3f2c0b28bb)

we read it as 2^0 + 2^1 + 2^5 + 2^7 + 2^8 + 2^11.

Then Q13 introduces us to all the bit methods and thats where i get all confused. 

the hackerank vid provided says the highest power is used to denote sign. in the case of the 8-bit example in the video, what if its 11111111? 

(1) why isnt 11111111 255?

(2) How does 11101110 give -18? assuming i understand the first bit denotes sign, its 1101110. Why isnt it 2^7 + 2^6 + 2^3 + 2^2 +2^1?

![image](https://github.com/user-attachments/assets/96f59572-2df4-420f-ba90-8b28665d72ec)

Confusion with Unary:

The hackerrank video says you transform 18 to -18 by flipping the 1s and 0s. I assume thats what the ~/ unary does for us.

![image](https://github.com/user-attachments/assets/081e3cab-7e63-40b9-96e8-dccd6ae7b59c)

Then why does flipping the bits of 0 make it -1?

Thank you!
