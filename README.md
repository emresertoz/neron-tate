# neron-tate

This code computes the Néron-Tate pairing of divisors on curves over the rationals in Magma. It implements the algorithm from *Explicit 
arithmetic intersection theory and computation of Néron-Tate heights*
by Raymond van Bommel, David Holmes, Steffen Müller [https://arxiv.org/abs/1809.06791](https://arxiv.org/abs/1809.06791) in Magma, 
with major improvements in the archimedean local height computation due to Emre Sertöz and Robin de Jong.

**Main functions**
- HeightPairing(D1::DivCrvElt, D2::DivCrvElt)
- Height(D::DivCrvElt)
- Regulator(S::[DivCrvElt])
- ArchimedeanNeronPairing(C::CrvPln,D::DivCrvElt,E::DivCrvElt): can be applied even if no regular model can be computed
- NonArchimedeanIntersectionNumbers(D::DivCrvElt, E::DivCrvElt): computes non-archimedean intersections in the local heights, useful
  for local p-adic heights.

**Scope**
The code works only over the rationals. For the non-archimedean part, we use Magma's RegularModel, which only works for curves 
embedded in a weighted projective plane.

**Authors**: Raymond van Bommel, David Holmes, Steffen Müller, Emre Sertöz
