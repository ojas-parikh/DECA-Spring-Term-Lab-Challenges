# DECA-Spring-Term-Lab-Challenges

Lab2:Challenge


My initial design took inspiration from the example showed to us from the lecture, I was struggling to start the challenge so I decided to take this basic design for a 3x3 multiplier and extend it to 16x16 multiplier. This initial design can be found in [Multiplier Issie Design] (#mult.dgm). This design however is not compliant with the 64 adder limit. 


After many hours of work, I have a multiplier block that multiplies 16 bit numbers together, taking 16 clock cycles to do so and using only 20 adders. This design can be found in (#mult_v3_2.dgm) in my repository. Following on from this succesful design I think I have two avenues to explore for improvement, first I can either add more adders to see if I can cut the cycles down but I need to consider how much additional cost each adder involves compared to its benefit in speed. Another avenue is using software rather than state machines to implement a multi-cycle multiplication.


After a few more hours of work, I have succesfully implemented the multiplier block with the rest of the EEP1, such that code written stores two values one in RA and RB, then the multiplier does RA*RB and the result is stored in two registers (one for most significant 16 bits and one for the least significant 16 bits) that can be chosen seperately. My final design uses 28 adders - 12 half adders and 16 full adders. 

Unfortunately, time constraints have limited my ability to further improve my design for speed. With additional time I think instead of just 1 16bit full adder I could have two 16 bit full adders and set up the correct timing mechanism to add more than two partial products at a time.

My EEP1 design with my multiplier can be found in the files of this repository, as can the code needed to implement a multiplication.

Further explanation of the design/ design process can be found in my Logbook.
