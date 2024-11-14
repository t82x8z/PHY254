java c
PHY254 
Problem set #3 
Fall 2024 
1 Are these forces conservative? [20%] 
1.1. Consider the two-dimensional force 
1.1.1. Evaluate the work done

along the three paths joining the origin O to the point P = (1, 1) as shown in figure 1(a) and defined as follows:
(a) This path goes along the x axis to Q = (1, 0) and then straight up to P. Hint: divide the integral into two pieces,  
(b) On the path y = x2. Hint: you can replace the term dy in eqn. (1) by dy = 2x dx and convert the whole integral into an integral over x.
(c) This path is given parametrically as x = t3, y = t2. Hint: rewrite x, y, dx and dy in eqn. (1) in terms of t and dt, and convert the integral into an integral over t.
1.1.2. Based on these calculations, is the force conservative? If yes, what is the potential en-ergy?
1.2. Do the same problem, but for the force  

Figure 1: Paths for Q1.
2 Lennard-Jones potential [60%] 
For record-keeping, we ask you to submit your code along with your report, with a 5% penalty if your code is absent. However, the marker will not look at it, unless they feel the need to. (For example, they suspect plagiarism.) All your answers and figures should be in your report.
The Lennard-Jones potential models the radial potential energy of vibrating diatomic molecules. The “LJ” or “6-12” potential function is

where ² > 0 is a constant with units of energy and rm is a length. The potential has a minimum at r = rm , where r > 0 represents the radial separation between two atoms. The minimum has a depth of −² . V (r ) goes to zero as r → ∞ and diverges as r → 0. This PhET simulation uses the Lennard-Jones potential.
2.1. Calculate the radial force F(r ) associated with this potential energy. Where is it attractive and where is it repulsive? Where is the stable equilibrium point and why is it stable?
2.2. Let us measure energy in units of ² and distances in units of rm. That is, let’s introduce V0 = V /² and r0 = r /rm, and let’s drop the primes to obtain

Write a Python script. to plot the potential in the range 0.8 ≤ r ≤ 3.0, and its associated force (in these units). For V (r ), you should get a plot that looks roughly like the one on the Wikipedia page.
2.3. Modify the script. lennard-jones_TEMPLATE.py to calculate the motion under the force you found above. Set up the script. to calculate the velocity v(t) and position r (t), using an Euler-Cromer time stepping scheme. Similarly to what we did above, assume the mass of the atom is m = 1 in some atomic units.
Now run the script. with initial conditions r0 = 1.02, v0 = 0. Make a plot showing the posi-tion and velocity for about 10 periods of this motion. You should observe that the motion is oscillatory. Does it look approximately sinusoidal? Estimate the period by looking at graph-ical output or by computationally findin代 写PHY254 Problem set #3 Fall 2024Python
代做程序编程语言g twice the average time between crossings of r = 1. What period do you get?
Note: by measuring energy in units of ² , mass in atomic mass units and radii in units of rm, we have effectively chosen “atomic time units” where each unit of time is given by  Your answer will naturally emerge in these units.
2.4. In these atomic units, let x = r −1. Now the minimum is located at x = 0. Expand V (x) about V (0) up to second order in x. Use this calculation to find the period T of small oscillations and compare your analytic answer to the numerical result found in the previous part.
2.5. Now decrease the initial displacement r0 toward smaller r , for example try r0 = 0.95, 0.90 and 0.85. Describe what happens as r0 decreases; include selected plots. Go back to your plot of the potential in part 2.2., and indicate the locations of all the various initial conditions you tried. Can you explain this behaviour and relate it to molecular physics?
We will now create a composite of trajectories in (x, v) phase space, known as a phase space portrait. The idea is to plot the trajectories for a range of values of x0 and v0. You can hand in multiple plots, but try to include several trajectories on each plot. The trick to do this with Matplotlib is to nest the numerical integration loop inside a larger loop. Here is one approach to doing this (you may have to interpret and adapt it):
ntrajectories = 20 # number of trajectories to plot
delta = 0.01 # increment between initial positions
trajectory_number = 0 # initialize trajectory counter
# an outer loop to calculate ntrajectories trajectories
while trajectory_number < ntrajectories:
radi = np.empty(nt) # position: initialize to empty
vels = np.empty(nt) # velocity: initialize to empty
radi[0] = 0.85 + trajectory_number*delta # initial position
vels[0] = 0. # initial velocity
ii = 0 # initialize loop
# main loop
while ii < nt-1:
# Here you update velocity and position like in previous question
# Plot this trajectory in phase space
plt.plot(radi, vels)
trajectory_number += 1
# . . .
plt.show()
2.6. Identify the separatrix, which is the curve that separates bounded from unbounded motions.
2.7. For points starting from the zero force point r0 = 1, find the escape velocity for which the trajectories switch from being bounded to being unbounded.
3 Beads on angled rails [20%]
(Morin 4.33) Two horizontal frictionless rails make an angle θ with each other, as shown in Figure 2. Each rail has a bead of mass m on it, and the beads are connected by a spring with spring constant k and relaxed length zero. Assume that one of the rails is positioned a tiny distance above the other, so that the beads can pass freely through the crossing. Find the normal modes.

Figure 2: Morin’s Fig. 4.27.



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
