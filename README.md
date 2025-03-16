Lab2:Challenge


My initial design took inspiration from the example showed to us from the lecture, I was struggling to start the challenge so I decided to take this basic design for a 3x3 multiplier and extend it to 16x16 multiplier. This initial design can be found in [Multiplier Issie Design] (#mult.dgm). This design however is not compliant with the 64 adder limit. 

<img width="1242" alt="image" src="https://github.com/user-attachments/assets/3b1dc3a2-f23c-4229-b971-6a3e33eda99d" />



After many hours of work, I have a multiplier block that multiplies 16 bit numbers together, taking 16 clock cycles to do so and using only 20 adders. This design can be found in (#mult_v3_2.dgm) in my repository. Following on from this succesful design I think I have two avenues to explore for improvement, first I can either add more adders to see if I can cut the cycles down but I need to consider how much additional cost each adder involves compared to its benefit in speed. Another avenue is using software rather than state machines to implement a multi-cycle multiplication.


After a few more hours of work, I have succesfully implemented the multiplier block with the rest of the EEP1, such that code written stores two values one in RA and RB, then the multiplier does RA*RB and the result is stored in two registers (one for most significant 16 bits and one for the least significant 16 bits) that can be chosen seperately. My final design uses 28 adders - 12 half adders and 16 full adders. 

Unfortunately, time constraints have limited my ability to further improve my design for speed. With additional time I think instead of just 1 16bit full adder I could have two 16 bit full adders and set up the correct timing mechanism to add more than two partial products at a time.

My EEP1 design with my multiplier can be found in the files of this repository, as can the code needed to implement a multiplication.

Further explanation of the design/ design process can be found in my Logbook.

If all "copy" files are downloaded and opened with ISSIE you should see an EEP1 with my multiplier implemented.

<img width="980" alt="Screenshot 2025-03-14 at 11 09 11" src="https://github.com/user-attachments/assets/b5fbec71-abb6-4631-84c4-8178426b851a" />
<img width="647" alt="Screenshot 2025-03-14 at 11 09 31" src="https://github.com/user-attachments/assets/bc0c9fe5-8863-4f10-b4bd-e331ff966ad8" />
<img width="758" alt="Screenshot 2025-03-14 at 11 09 43" src="https://github.com/user-attachments/assets/50f2a63e-092d-49c6-9ffd-eeefba0b5931" />


This is the code I used to implement my multiplier, specifically to compute and store 12x5:

<img width="165" alt="image" src="https://github.com/user-attachments/assets/80457eee-4cf6-4e8e-b6bd-aabd1091e16f" />

While the actual multiplication takes 16 clock cycles, the entire process of storing 12 and storing 5 in the registers then mulitplying them and storing the 32 bit result in two registers takes a total of 22 clock cycles.

This is an improvement over the purely software implementation.

My multiplier works for these tests I have done 12x5, 12x12, 5x100 , 0x10 x 16. They all take a total of 22 clock cycles.

However this design didn't always work due to timing issues. My final design can be found int the multv4 sheet, it uses 29 adders however I think this could be reduce to 25/24 adders with a bit more design work on the counters but I couldn't find the time to do this before the deadline.

