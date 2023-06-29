# Things todo at some point

## Critical

* Fix line 325 where StrongApproximation is important from magma library using hardcoded path. This importing must be done dynamically. 
* In AbelJacobiImageOfCanonicalDivisor, we move away the canonical divisor away from infinity. We should also move away from the singularities of the planar model, if any. 
  - Archimedean part of NT will work even if the planar model is singular, so we should continue to allow for that.
  - It is unclear to us why we need to move away from infinity in general. Maybe this condition can be relaxed if infinity is smooth.

## Important

* Merge the Arch and NonArch code
* Test to see if support of E or D intersects Weierstrass locus, swap if needed, throw error if both intersect.

## Luxury 

* Even if both E and D intersect the Weierstrass locus, we could evaluate the pairing using derivatives of theta functions ("L'Hopital"). 
  - Then there would be no constraints other than E,D disjoint.
* Maybe we can get rid of the BetterMoveAway function by creating a canonical divisor that already is not supported at infinity or singularities.
  - This should get rid of the comparatively slow move away function
  - Also, BetterMoveAway can in principle fail if there is no good place. Now that we are using it in a subroutine not meant to be accessed by the user, this is a problem.



