# Things todo at some point

## Critical

* Fix line 325 where StrongApproximation is imported from magma library using hardcoded path. This importing must be done dynamically. 
* non_archimedean_part.mag: This also imports with hardcoded paths, it must be dynamically done.
* In AbelJacobiImageOfCanonicalDivisor, we move away the canonical divisor away from infinity. We should also move away from the singularities of the planar model, if any. 
  - Archimedean part of NT will work even if the planar model is singular, so we should continue to allow for that.
  - It is unclear to us why we need to move away from infinity in general. Maybe this condition can be relaxed if infinity is smooth.

## Important

* Merge the Arch and NonArch code

## Luxury 

* Test to see if support of E or D intersects Weierstrass locus, swap if needed, throw error if both intersect.
* Even if both E and D intersect the Weierstrass locus, we could evaluate the pairing using derivatives of theta functions ("L'Hopital"). 
  - Then there would be no constraints other than E,D disjoint.
* Maybe we can get rid of the BetterMoveAway function by creating a canonical divisor that already is not supported at infinity or singularities.
  - This should get rid of the comparatively slow move away function
  - Also, BetterMoveAway can in principle fail if there is no good place. Now that we are using it in a subroutine not meant to be accessed by the user, this is a problem.
* Currently the standard theta char is found using 10 digits of precision. This might break if genus is high. In principle, one could use the bounds for normalized theta function to compute the minimal precision required.
* It would almost certainly be faster to compute the pairing as in vBHM *if* it is known a priori that D is not a special divisor. Perhaps that option should be made available?
  - The problem is that I'm currently breaking the evaluation of the pairing <D,E> into the evaluation of *many* pairings of the form <p-q,r-s>. This takes time because each evaluation of theta functions is expensive.
* Line 308 of archimedean_part checks if certain theta evaluations are zero to precision (which suggests D might be supported on Weierstrass points). But if we check that D is not supported on Weierstrass points than we should increase precision and recompute everything, since the log of those terms will dominate and magnify the error.

## Easy but minor

* Create and use a category called AugmentedPlaneCurve to make things cleaner? Or just use RiemannSurfaces? 
  - In any case, you better introduce checks to make sure the input is an augmented plane curve in most functions in archimedean_part

