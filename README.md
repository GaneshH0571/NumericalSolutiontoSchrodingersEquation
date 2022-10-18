# Numerical Solution to radial Schrodingers Equation

Since analytical solutions to the radial Schr¨odinger equation are known for only a
few central potentials, such as the Coulomb potential or the harmonic oscillator
potential, it is necessary to resort to numerical methods to obtain solutions in
practical cases.
We use finite difference techniques to find numerical solutions to the radial
equation on a finite grid covering the region r = 0 to a practical infinity, a∞, a
point determined by requiring that P(r) be negligible for r > a∞.
Near the origin, there are two solutions to the radial Schr¨odinger equation,
the desired solution which behaves as r
`+1
, and an irregular solution, referred
to as the complementary solution, which diverges as r
−` as r → 0. Numerical
errors near r = 0 introduce small admixtures of the complementary solution into
the solution being sought. Integrating outward from the origin keeps such errors
under control, since the complementary solution decreases in magnitude as r increases. In a similar way, in the asymptotic region, we integrate inward from a∞
toward r = 0 to insure that errors from small admixtures of the complementary
solution, which behaves as e
λr for large r, decrease as the integration proceeds
from point to point. In summary, one expects the point-by-point numerical
integration outward from r = 0 and inward from r = ∞ to yield solutions that
are stable against small numerical errors.
The general procedure used to solve Eq.(2.13) is to integrate outward from
the origin, using an appropriate point-by-point scheme, starting with solutions
that are regular at the origin. The integration is continued to the outer classical
turning point, the point beyond which classical motion in the potential V (r) +
`(` + 1)/2r
2
is impossible. In the region beyond the classical turning point, the
equation is integrated inward, again using a point-by-point integration scheme,
starting from r = a∞ with an approximate solution obtained from an asymptotic
32 CHAPTER 2. CENTRAL-FIELD SCHRODINGER ¨ EQUATION
series. Typically, we choose a∞ so that the dimensionless quantity λr ≈ 40
for the first few steps of the inward integration. With this choice, P(r) is
roughly 10−12 of its maximum value near a∞. The solutions from the inward
and outward integrations are matched at the classical turning point. The energy
is then adjusted until the derivative of P(r) is continuous at the matching point.
The resulting function P(r) is an eigenfunction and the corresponding energy
E is its eigenvalue. To find a particular eigenfunction, we make use of the fact
that different eigenfunctions have different numbers of nodes for r > 0. For a
given value of `, the lowest energy eigenfunction has no node, the next higher
energy eigenfunction has one node, and so on. We first make a preliminary
adjustment of the energy to obtain the desired number of nodes and then make
a final fine adjustment to match the slope of the wave function at the classical
turning point.
