[#RBbuilding

## OCTOBER 27TH - OCTOBER 31ST
With our chassis stabilized and drive behavior improved, this week we shifted focus to aligning our robot design and code with the Push Back game objectives. Now that we are moving into autonomous work and focusing less on our build, here is a summary of what Stepan and I have done so far this season:

**Mechanical / Hardware Work:**

- After the stability fixes last week, we started using the ball intake/tracker, so we can reliably pick up and identify blocks. In the early season, we tested different orientations for the intake (horizontal vs angled) and found that an **angled intake at about 30°** allowed us to scoop blocks more consistently without bouncing them off the field tiles.

- We mounted a preliminary hopper/feeder above the intake that aligns blocks to feed into our scoring mechanism. During testing we had frequent jams when two blocks tried to feed simultaneously, so we added a guide and supporting stand offs to ensure blocks filter in one by one.

- On the scoring end, since the goals are “long goals” and “center goals” on the field (per game manual) we adopted a rolling output with a polycarb hood for aim. Testing in September confirmed that this material was our best choice.

- We also adjusted the robot’s center of gravity by moving the pneumatics tank slightly forward so the robot doesn’t tilt backward under intake load.

**Programming / Autonomous Work:**

- Stepan began building an autonomous routine that starts in our alliance’s loader zone, scoops 2 blocks, drives forward to a long goal, and executes the flipper to score. He used odometry (tracking wheel encoders + IMU) to drive precisely to the goal location.


**Reflection / Next Steps:**

- What went well: Our intake/hopper setup is performing much better. Blocks are being captured with ~90% reliability and our scoring flipper is consistent in practice.

- In driver practice I also placed emphasis on **parking** the robot in our park zone at the end of the match—important in Push Back for bonus parking points.

- What still needs work: The autonomous scoring routine is incomplete. I am concerned about accuracy as well, as we still lose blocks when feeding and sometimes fail to flip correctly. Also the driver stage transitions (intake → drive to goal → scoring → reposition) are still slow and need tightening.

- Next week’s goals:
    
    1.  Expand autonomous routine to score **3-4 blocks** instead of 2
        
    2. Begin integrating the **control-zone scoring strategy** (since goals have control zones worth extra points) into the program and drive practice. We’ll test different goal alignment positions to maximize control. 
        
    3. Continue driver practice under full-match timing (1:45 driver period) and simulate match conditions (intake from loader, score, reposition, park).