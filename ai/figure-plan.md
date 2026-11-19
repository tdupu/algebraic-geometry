# Figure plan for `curves-and-surfaces.tex`

Status: **done (2026-11-19).** Taylor approved all 58 drafts (the count of
55 below was an arithmetic slip; the tables list 58 IDs). They are inserted
into `curves-and-surfaces.tex` from `figures/<slug>.tex`, with the shared
style block in the preamble. Defaults were used for the open questions below:
B2 draws the real acnode plus a schematic of the two branches over $\CC$; F1
uses $(2y-x^2)(x^2+2y^2-2y-1)=2/5$; I1 is a fresh TikZ `fig:flat-limit`; H6
redraws `schubert.png`; pgfplots is not used. Changes made while drafting:
G4 uses the irreducible tacnode $y^2=x^4(1-x)$, because $y^2=x^4$ is
reducible; A10 swaps $D(x)$ and $D(y)$ to the correct axes.

Workflow (Taylor's, 2026-11-19):

1. Agree on this plan.
2. Draft every approved figure in TikZ and collect them in one preview PDF,
   with each figure captioned on its own page.
3. Taylor comments on the PDF; revise until approved.
4. Insert the approved figures into the manuscript.

Line numbers refer to `curves-and-surfaces.tex` at commit `dc53800`.

---

## Conventions used in every figure

One shared style block, so the same concept looks the same everywhere:

| Concept | Look |
|---|---|
| Curve or surface under study | black, thick |
| Exceptional divisor $E$ (and $E_i$) | red, thick |
| Hyperplanes, cutting lines, sections $H$, $L$ | blue, dashed |
| Open sets and charts | light green or light orange fill, with a label naming the open |
| Tangent and normal vectors | purple arrows |
| Marked points | filled dots, each labelled; multiplicity written as "mult $m$", never a bare number |
| Maps between panels | black arrows labelled with the map's name |

Each colour also has a dash pattern or a label, so the figures still work in
black and white.

- **Real pictures where honest.** Real loci of concrete equations, such as the
  nodal cubic, the cusp, $y^2=x^3+ax+b$ and the blow-up chart $y=mx$, are
  plotted exactly from their equations with TikZ `plot` (or pgfplots, which is
  built on TikZ). The caption says "real points of …".
- **Schematic pictures.** Pictures that cannot be real, such as $\PP^5$,
  abstract surfaces and $\Spec$ of a local ring, say "schematic" in the
  caption. When a dimension is reduced, the caption says so.
- Captions follow the create-figure rules. They open with what the figure
  shows, then reference the target and define every symbol and colour, and
  claim nothing beyond what the text proves.

---

## The figures

Legend:

- **Req** means the manuscript asks for this picture. **New** means it is a
  proposed addition.
- Priority: **H** high, **M** medium, **L** low/optional.
- A figure that serves several locations is drawn once and cited from each.

### A. Schemes, charts, local pictures

| ID | Lines | Req/New | Pri | What to draw | The one fact shown |
|---|---|---|---|---|---|
| A1 | 197, 215 | New | H | $\PP^1$ drawn as a circle with $0$ at the bottom and $\infty$ at the top. $U=\{X_1\ne0\}$ is shaded green (everything but $\infty$) and $V=\{X_0\ne0\}$ is shaded orange (everything but $0$). The overlap is labelled $U\cap V=\Spec\QQ[x,x^{-1}]$, glued by $y=1/x$. | $\PP^1$ is two affine lines glued along $\mathbb{G}_m$. |
| A2 | 238, 266, 2985 | New | H | Real points of $E: y^2=x^3+ax+b$. Panel (a) is the chart $U'$ in two cases: $(a,b)=(-1,0)$, which has two real components, and $(a,b)=(0,1)$, which has one. Panel (b) is the chart $V'$ with coordinates $(u,v)$ near $O=[0{:}1{:}0]$, where $v=u^3+auv^2+bv^3$ passes through the origin with a flex: the line $Z=0$ meets $E$ only at $O$, with multiplicity 3. | $E$ is covered by $U'\cup V'$; the one missing point $O$ is a flex, and $3O$ is a hyperplane section (2985). |
| A3 | 393 | New | M | The panel (a) curve again. The region $y\ne0$, where $\eta=dx/2y$ is used, is drawn in one colour. Small neighbourhoods of the three points with $y=0$, where $\eta=dy/f'(x)$ is used instead, are drawn in another. $O$ is labelled "chart $V'$". | $\eta$ is regular everywhere, because these opens cover $E$. |
| A4 | 443 (Req), 503 | Req | H | The unit circle $g=x^2+y^2-1=0$. (a) The open $\partial g/\partial y\ne0$, which is the circle minus $(\pm1,0)$, projects to the $x$-axis; it is a 2:1 local homeomorphism, and the two vertical-tangent points are marked as the failures. (b) The same for $\partial g/\partial x\ne0$ projecting to the $y$-axis. | On each open, the coordinate projection is étale, so $dx$ (respectively $dy$) trivializes $\Omega$ there. |
| A5 | 588 (Req) | Req | M | A surface $X$ fibred over a curve $Y$, with $S$ a point. At $x\in X$, the vertical arrow along the fibre is $f^*T_{X/Y}$, and the image arrow in $T_{f(x)}Y$ is $T_{Y/S}$. A dashed "horizontal lift" is labelled "not canonical". | $0\to f^*T_{X/Y}\to T_{X/S}\to T_{Y/S}\to0$. The vertical directions form a sub-bundle, and the horizontal directions are only a quotient. |
| A6 | 600 (Req), 640 (Req) | Req | H | One figure, referenced from both places. The real paraboloid $z=x^2+y^2$ contains the parabola $\{y=0, z=x^2\}$, which contains the point $0$. They are labelled $Y_0\subsetneq Y_1\subsetneq Y_2$ and, in the margin, by their primes $P_2\subset P_1\subset P_0$ in $k[x,y,z]/(z-x^2-y^2)$. | A maximal chain of length 2, so the dimension is 2; a point is cut out by 2 equations, so its height is 2. |
| A7 | 655 (Req) | Req | M | The example $f=y^2$ in $k[x,y]$, with $P=(y)$. The $x$-axis $V(P)$ is drawn as a thin line, and $V(f)$ as the same line with a shaded "doubled" band, labelled $\Spec k[x,y]/(y^2)$. | $V(P)\subset V(f)$ is a nilpotent thickening and has the same dimension. |
| A8 | 1802 (Req), 1792 | Req | M | Three panels on a curve $Z$ with a point $z$. (a) A Zariski open neighbourhood: $Z$ minus finitely many points, with the holes drawn. (b) $\Spec\mathcal{O}_{Z,z}$: the point $z$ plus the generic point $\eta$, drawn as a fuzzy cloud, which is "smaller than every open". (c) $\Spec\kappa(z)$: the point alone. | $\Spec\kappa(z)\to\Spec\mathcal{O}_{Z,z}\to Z$ are progressively smaller "neighbourhoods", and the middle one is not Zariski open. |
| A9 | 1813, 1863–1865 (Req) | Req | H | Three panels: (a) the statement: a curve $X$ with a hole at $x$ maps to $Y\subset\PP^n$, and the limit point $y$ fills the hole; (b) Taylor's picture one: a local neighbourhood of $x$ mapping onto $y$; (c) Taylor's picture two: $\Spec A\ni x$ and $\Spec B\ni y$, with $X\setminus x\to\Spec B$, written affine-locally as $B\to A_t$. | The data "at $x$" and the data "away from $x$" glue to a morphism $X\to Y$. |
| A10 | 2673 (Req) | Req | M | $xy=0$, with its three fpqc pieces drawn separately and mapping in: the punctured $x$-axis $D(x)$, the punctured $y$-axis $D(y)$, and a formal neighbourhood $\Spec\CC[[x,y]]/(xy)$ of the origin (a small cross inside a dotted disc). | The three pieces together cover the scheme. |
| A11 | 1532 | New | L | Schematic curve covered by $U_i,U_j$, with local equations $f_i,f_j$ and $f_i/f_j\in\mathcal{O}(U_i\cap U_j)^\times$ on the overlap. | Cartier data are local equations with unit ratios. |

### B. Singular plane curves

| ID | Lines | Req/New | Pri | What to draw | Fact |
|---|---|---|---|---|---|
| B1 | 732 (Req), 545 | Req | H | Real points of $y^2=x^2(x+1)$, the loop and the tail, with the tangent lines $y=\pm x$ at the node dashed. Annotations: $\dim T_p=1$ at a smooth point and $\dim T_{(0,0)}=2$ at the node (for 545). | The node has two tangent directions, and its cotangent space has dimension $n-\mathrm{rk}\,J=2$. |
| B2 | 692 (Req) | Req | H | **Needs a decision; see question 1.** $y^2=x^2(x-1)$ has real points consisting of an *isolated point* at the origin plus a branch for $x\ge1$. That real picture hides the singularity. Plan: draw the real picture, and add a second panel or caption explaining that over $\CC$ two branches meet there, with tangents $y=\pm ix$. | The origin is not regular. |
| B3 | 729 | New | H | Normalization: the $t$-line maps onto the nodal cubic by $t\mapsto(t^2-1,\,t(t^2-1))$. Colour $t<0$ and $t>0$ differently so that the two branches are visible. $t=\pm1$ both go to the node; $t=y/x$ is labelled. | $t=y/x$ is integral but not in $A$; the normalization separates the branches. |

### C. Divisors, linear series, maps to projective space

| ID | Lines | Req/New | Pri | What to draw | Fact |
|---|---|---|---|---|---|
| C1 | 907 | New | H | $\PP^1$ drawn as a circle. The example $f=x(x-1)^2$ has zeros at $0$ (mult 1) and $1$ (mult 2), and a pole at $\infty$ (mult 3). | $\mathrm{div}(f)=Z(f)-\deg(f)\cdot\infty$, of degree 0. |
| C2 | 894, 2296, 3961 | New | M | (a) A curve $X\to\PP^1$: $f^{-1}(0)$ (zeros) and $f^{-1}(\infty)$ (poles) as point sets, with the same count. (b) A surface with a pencil of curves $f^{-1}(t)$ sweeping from $D_1$ to $D_2$. | Rationally equivalent divisors are fibres of one map to $\PP^1$. |
| C3 | 2388 (Req) | Req | H | Three panels with real points: a conic (ellipse), a cubic (the A2 curve) and a smooth quartic, each cut by a blue line in $d=2,3,4$ real points. | A line meets a degree-$d$ plane curve in $d$ points; this is the input to $g=(d-1)(d-2)/2$. |
| C4 | 988, 1035 | New | H | Three panels: a line in $\PP^2$ meeting $H$ in 1 point; a conic $[X_0^2{:}X_0X_1{:}X_1^2]$ meeting $H$ in 2 points; and the real twisted cubic $(t,t^2,t^3)$ in a 3D box, meeting a plane in 3 points. | Degree-$d$ divisors on $\PP^1$ correspond to embeddings whose hyperplane sections have $d$ points. |
| C5 | 1005, 2719, 4226, 4303 | New | H | Two conics (drawn as circles) in $\PP^2$ meeting in 4 points. A schematic side panel shows $v_2(\PP^2)\subset\PP^5$ with two hyperplanes, labelled "schematic: codimension 3 is not drawable". The same picture is reused for $C\cdot C'=4$ for a conic and a moved conic. | $\deg v_2(\PP^2)=4$, and the self-intersection of a conic is 4. |
| C6 | 1161 (Req), 2744 | Req | H | $\PP^2$ (an affine chart) with the point $P_0$, the pencil of lines through $P_0$, and a target line $\PP^1$. A point $Q$ maps to $\overline{P_0Q}\cap\PP^1$. $P_0$ is marked "undefined: base locus". | Projection from a point; a pencil with a base point. |
| C7 | 1638 | New | M | $\PP^2$ with a degree-$d$ curve $V_+(G)$, the hyperplane $H$, and a general line $L$ meeting $V_+(G)$ in $d$ points. | $V_+(G)\sim dH$, so $\mathrm{Cl}(\PP^n)=\ZZ$. |
| C8 | 1728 | New | L | The coordinate triangle with the three charts $\{X_i\ne0\}$. $\eta=dx\wedge dy$ is regular on one chart and has a pole of order 3 along $H=\{X_2=0\}$. | $K_{\PP^2}=-3H$. |
| C9 | 2701 | New | H | Three panels with real points: (a) $t\mapsto(t,t^2)$, a closed immersion; (b) $t\mapsto(t^2-1,t^3-t)$, which identifies $t=\pm1$ and fails to separate points (a node); (c) $t\mapsto(t^2,t^3)$, which kills $\partial_t$ at $0$ and fails to separate tangent vectors (a cusp). | Both conditions in Theorem `thm:points-and-tangents` are needed. |
| C10 | 2896 | New | M | A curve in $\PP^3$ with three blue planes: one through $x$; one through $x$ and $y$; one tangent at $x$ (mult 2). | What $h^0(D-x)$, $h^0(D-x-y)$ and $h^0(D-2x)$ count. |
| C11 | 3038 | New | H | Real circle with a rational point $P$. Lines through $P$ of slope $m$ meet the circle in one more point, which gives $m\leftrightarrow$ point. The tangent line at $P$ corresponds to $P$ itself. | A conic with a rational point is $\cong\PP^1$. |
| C12 | 3031 | New | L | A curve with a hyperplane $H$ meeting it only at $x$, to high order; $X\setminus x$ sits inside the affine space $\PP^{g+1}\setminus H$. Shown with a schematic plane model. | A projective curve minus a point is affine. |

### D. Tangent and normal vectors

| ID | Lines | Req/New | Pri | What to draw | Fact |
|---|---|---|---|---|---|
| D1 | 2596 (Req) | Req | H | $\Spec F[\varepsilon]/(\varepsilon^2)$ drawn as a dot with a short "decapitated" arrow stub, mapping to a curve $X$; its image is a point $x$ with a purple tangent arrow. | A tangent vector is a map from the dual numbers. |
| D2 | 2577 | New | M | (a) A smooth real surface $f=0$ in $\AA^3$ with its tangent plane $\nabla f\cdot v=0$. (b) The nodal cubic from B1, whose Zariski tangent space at the node is the whole plane. | Zariski tangent space = the kernel of the Jacobian, which jumps at singular points. |
| D3 | 3314 (Req), 3340 | Req | H | (a) A curve $Y$ in a surface $X$: purple tangent arrows along $Y$, $T_X\vert_Y$ as planes, and normal arrows as the quotient, labelled $0\to T_Y\to T_X\vert_Y\to N_{Y/X}\to0$. (b) $Y=D_1\cap D_2$ in 3-space, with two normal arrows, each normal to one surface. | Normal bundle = quotient; for a complete intersection $N_Y=\mathcal{O}(D_1)\oplus\mathcal{O}(D_2)$. |

### E. Covers and ramification

| ID | Lines | Req/New | Pri | What to draw | Fact |
|---|---|---|---|---|---|
| E1 | 3054, 3218, 3284 | New | H | A degree-3 cover $X\to Y$ drawn as stacked sheets. A generic fibre has 3 points. One fibre is $2P_1+P_2$, with $P_1$ marked "ramification, $e=2$" and $Q$ marked "branch point". An inset shows the local model $z\mapsto z^e$. | $f^*Q=\sum e(P/Q)P$; ramification is where sheets come together. |
| E2 | 3073 | New | L | A triangulation of $Y$ pulled back to $X$: cells multiply by $d$, except at the branch vertices. | The topological proof of Riemann–Hurwitz. |
| E3 | 2439 | New | M | The real parabola $x=y^2$ projected to the $x$-axis. Over $x>0$: 2 points; over $0$: a double point (length 2); over $x<0$: no real points, though there are 2 over $\CC$, which the caption says. | A finite flat map has constant fibre length. |
| E4 | 2456 | New | M | The real hyperbola $xy=1$ projected to the $x$-axis; the fibre over $0$ is empty, because the point escapes to infinity. | Quasi-finite does not imply finite. |
| E5 | 3569, 3615 | New | H | Real points of $y^2=Q(x)$ with $\deg Q=8$ (genus 3): four ovals over the intervals where $Q>0$, the 8 roots marked on the $x$-axis, and the 2:1 projection. | The hyperelliptic (Weierstrass) model; $2g+2$ branch points. |
| E6 | 3696 | New | M | The factorization $C\xrightarrow{2:1}\PP^1\xrightarrow{v_{g-1}}\PP^{g-1}$ for $g=3$, with the image a conic in $\PP^2$. Conjugate points $x,\iota(x)$ go to the same image point. | The canonical map of a hyperelliptic curve is not an embedding. |
| E7 | 2349 | New | L | A lattice parallelogram in $\CC$ glued into a torus $E(\CC)=\CC/\Lambda$, with $O$ and $P$ marked. | Degree-0 divisors on $E$ and the group law. |
| E8 | 3832 | New | L | A sphere, a torus and a genus-2 surface, labelled $\kappa=-\infty,0,1$. | Kodaira dimension of curves. |

### F. Surfaces and intersection theory

| ID | Lines | Req/New | Pri | What to draw | Fact |
|---|---|---|---|---|---|
| F1 | 3576 (Req) | Req | H | A smooth real plane quartic with a "sombrero" profile (**see question 2**), and a line meeting it in 4 points. | $\omega_C=\mathcal{O}(1)\vert_C$: canonical divisors are line sections, of degree $4=2g-2$. |
| F2 | 3990 (Req: empty example) | Req | H | The parabola $y=x^2$ with lines $y=c$ for $c>0$ (2 points) and the tangent line $y=0$ (1 point, multiplicity $\mathrm{len}\,k[x]/(x^2)=2$). | Intersection multiplicity as a length, and its invariance under moving. This session also writes the example's prose (agreed with the manuscript-review session): $y=0$ and $y=x^2$ meet only at $(0,0)$, with multiplicity $\mathrm{len}\,k[x,y]_{(x,y)}/(y,y-x^2)=\mathrm{len}\,k[x]/(x^2)=2$, matching Bézout $1\cdot2=2$. |
| F3 | 3879, 3490/3738, 4846, 5061 | New | H | Real hyperboloid $Z_0Z_3=Z_1Z_2$ (an affine chart) with a few lines from each of the two rulings; a plane section gives a $(1,1)$ curve. | $\PP^1\times\PP^1\cong$ a quadric; $\rho=2$; the classes of the two rulings. |
| F4 | 4126, 4242 | New | H | (a) Curves $C$ and $D$ tangent at a point. (b) $D$ moved to $D'$, now meeting $C$ transversally in 2 marked points. | The moving lemma: the intersection number is computed transversally. |
| F5 | 4087 | New | L | A conic with a family of lines; the tangent lines (the singular hyperplane sections) are marked. | Bertini: a general hyperplane section is smooth. |

### G. Blow-ups

All real pictures here use the chart $\{(x,m): y=mx\}$ of $\mathrm{Bl}_0\AA^2$ (from the text's $xT_1=yT_0$ with $m=T_1/T_0$). The exceptional divisor $E$ is the $m$-axis, in red. This gives honest, exact pictures.

| ID | Lines | Req/New | Pri | What to draw | Fact |
|---|---|---|---|---|---|
| G1 | 4359 (Req) | Req | H | $\AA^2(\RR)$ with lines through $0$, each coloured by its slope, which is its value in $\PP^1$. At $0$ every colour meets, marked "undefined". | The slope map $\AA^2\dashrightarrow\PP^1$ is undefined only at $0$. |
| G2 | 4432, 4434 (Req) | Req | H | (a) "Misleading": a plane with a line sticking up out of it. (b) "Better": the real surface $\{y=mx\}\subset\RR^3$, a twisted ruled surface, with the red line $E$ ($x=y=0$) running through it, smoothly part of the surface. | $\mathrm{Bl}_0\AA^2$ is irreducible, and $E$ is not a separate component. |
| G3 | 4495, 4496 (Req), 4671 | Req | H | (a) $\mathrm{Bl}_0 C$ for the nodal cubic: two points over the node. (b) The strict transform in the chart: $m^2=x+1$, a smooth curve meeting $E$ at $m=\pm1$, the two tangent slopes, drawn over B1 with the projection. | $\widetilde{C}\cong\mathrm{Bl}_0C$; $h^*C=\widetilde{C}+2E$, and the branches are separated. |
| G4 | 4549 | New | H | Resolution towers in chart pictures. Cusp $y^2=x^3$: $m^2=x$, smooth and tangent to $E$, done in one step. Tacnode $y^2=x^4$: $m^2=x^2$, a node on $E$, then a second blow-up gives two disjoint branches. The value of $p_a$ is labelled at each stage. | Blowing up lowers $p_a$ until the curve is regular. |
| G5 | 4689, 4693 (Req) | Req | H | Schematic $\mathrm{Bl}_pS$. (a) $C,D$ meet away from $p$, so the pullbacks meet the same way. (b) $D$ through $p$: $h^*D=\widetilde{D}+E$, and $\widetilde{D}$ meets $E$ once (at $D$'s tangent direction). | $h^*C\cdot h^*D=C\cdot D$, $E\cdot h^*D=0$, $E^2=-1$. |
| G6 | 4781 | New | M | $S$ containing a red $(-1)$-curve $E$, mapped by $\varphi_{\mathcal{L}}$ to $S_0$, with $E$ collapsed to a smooth point $p$. Drawn as the mirror image of G5. | Castelnuovo contraction. |
| G7 | 4904 | New | H | Left: C6 (lines through $p$). Right: $\mathrm{Bl}_p\PP^2\to\PP^1$, where the lines become disjoint fibres and $E$ becomes a section meeting each fibre once. | Resolving a rational map by blowing up its base locus. |

### H. Cubic surface, Grassmannians, Schubert cycles

| ID | Lines | Req/New | Pri | What to draw | Fact |
|---|---|---|---|---|---|
| H1 | 5027 (Req), 4969, 4735 | Req | H | $\PP^2$ with 6 general points. Highlighted: one point $p_i$ (type A, becomes $E_i$, red), one line $L_{ij}$ (type B, blue), and one conic $Q_i$ through the other 5 points (type C, green). All 15 lines are shown faintly in an inset. The count $6+15+6=27$ is labelled. | The three types of lines on the cubic surface. |
| H2 | 5061 | New | H | Three panels: $\PP^2$ with $p_1,p_2,L_{12}$; $\mathrm{Bl}_{p_1,p_2}\PP^2$ with the chain $E_1-\widetilde{L}_{12}-E_2$; contracting $\widetilde{L}_{12}$ gives $\PP^1\times\PP^1$ (drawn as a square grid), where $E_1,E_2$ become one line from each ruling. | $\mathrm{Bl}_2\PP^2\cong\mathrm{Bl}_1(\PP^1\times\PP^1)$. |
| H3 | 5183 | New | H | A schematic pencil of planes $H_\lambda\supset L_0$. Small panels show $H_\lambda\cap S=L_0\cup Q_\lambda$ for a smooth conic, and the degenerate case where $Q_\lambda$ is a pair of lines, which happens 5 times. | Each line meets $5\times2=10$ others. |
| H4 | 5251 | New | M | A plane $H$ with the triangle $L\cup L'\cup L''=H\cap S$, and another line $M$ piercing $H$ at a point on one side. | Every line meets one of the triangle's lines (counting step). |
| H5 | 5136 | New | M | Left: lines in $\PP^3$ (an affine box). Right: a schematic quadric in $\PP^5$, where each line is one point. | $\GG(1,3)$ is the Plücker quadric. |
| H6 | 5557 | New | H | **Redraw `schubert.png` in TikZ** (see question 4): $\Sigma_1,\Sigma_2,\Sigma_{1,1},\Sigma_{2,1},\Sigma_{2,2}$ relative to a red flag $F_0\subset F_1\subset F_2$, and the containment poset. | The Schubert cycles of $\GG(1,3)$, filling the empty subsection. |
| H7 | 5144 | New | L | The incidence correspondence $\Gamma\subset\PP^{19}\times\GG(1,3)$ with both projections; the fibre over $[S]$ is 27 points and the fibre over $[L]$ is $\PP^{15}$. | The dimension count behind the 27 lines. |

### I. Flatness

| ID | Lines | Req/New | Pri | What to draw | Fact |
|---|---|---|---|---|---|
| I1 | 5693 (Req; file missing), 5634, 5736 | Req | H | **Replaces the missing `flat-limit.eps`, keeping the label `fig:flat-limit`.** (a) A flat family: $xy=t$, with hyperbolas degenerating to the axes as $t\to0$. (b) Not flat: $\Spec k[x,y]/(xy)$ over the $x$-line, where the whole $y$-axis sits over $x=0$, so the fibre contains a component. (c) Not flat: $k[x,y]/(y^2,xy)$, the $x$-axis with an embedded fat point at the origin. | A fibre is a flat limit iff it contains no component of $X$. |
| I2 | 5745 | New | L | $\mathrm{Bl}_0\AA^2\to\AA^2$: point fibres away from $0$, and a red $\PP^1$ over $0$. Could be one more panel of I1. | Blow-up at a point is not flat. |

### Kept as is
- **5278** `grr.jpeg` is a photograph of Grothendieck's notebook. It is not a
  drawing to redo.

### Recommended: no figure
- 229: the real picture of $D_+(X_0^2+X_1^2)$ is misleading.
- 1197: the Čech triple-overlap picture is generic.
- 1391: Grothendieck vanishing; nothing to draw.
- 1602: $\mathrm{Cl}(\AA^n)=0$; nothing to draw.
- 1903: the normalization of $\PP^1$ in $F$; too abstract.
- 3196: a fat point; A7 covers it.
- 3434: a curve on a surface; too generic.
- 3456: a real K3 quartic is not drawable honestly in TikZ.
- 4012: reuse G2 instead.
- 4486: an arithmetic blow-up; low value.
- 4855: algebraic equivalence; C2 covers it.
- 5513: the section of $\mathrm{Sym}^3E$; too abstract.
- 5751: supports; low value.

---

## Count
- 26 requested locations, merged into 21 figures:
  - group A: A4–A10;
  - group B: B1, B2;
  - groups C–F: C3, C6, D1, D3, F1, F2;
  - groups G–I: G1, G2, G3, G5, H1, I1.
- 34 new figures.
  - H: A1, A2, B3, C1, C4, C5, C9, C11, E1, E5, F3, F4, G4, G7, H2, H3, H6.
  - M: A3, C2, C7, C10, D2, E3, E4, E6, G6, H4, H5.
  - L: A11, C8, C12, E2, E7, E8, F5, H7, I2.
- **55 figures in total.**
  - If only the requested figures plus the high-priority new ones are drawn,
    the total is 38.

## Implementation plan
1. **Style block.** Write one style block for the preamble (`tikz`, the `calc`,
   `3d` and `arrows.meta` libraries, and possibly `pgfplots`). It holds the
   colour styles above and macros for points, $E$, hyperplanes and charts.
2. **Drafting.** Draft each figure as its own file `figures/fig-<id>-<slug>.tex`,
   with label `fig:<slug>`. Drafting runs in parallel by group, one subagent
   per group with write access only to its own files. Real loci are plotted
   from their exact equations.
3. **Preview PDF.** Build the preview PDF (`ai/figure-preview.pdf`) from the
   manuscript's preamble plus the style block. Each figure gets its own page,
   with its draft caption, the proposed cross-reference sentence ("See
   Figure~\ref{…}."), and the line it attaches to.
4. **Inspection and review.** Check for overlapping labels, clipping and
   overfull boxes, then hand the PDF to Taylor for comments.
5. **Insertion.** Only after approval: insert `[H]` floats before each target,
   `\input` the figure files, replace the `\taylor{draw…}` notes they resolve,
   recompile and check the result.

## Questions for Taylor
1. **Line 692.** The text says $y^2=x^2(x-1)$. Its real picture is an isolated
   point plus a branch, which differs from the nodal cubic $y^2=x^2(x+1)$ used
   at line 729. Is the sign intended (an acnode example), or a typo for $x+1$?
2. **Line 3576, "sombrero".** Which picture do you have in mind? One option is
   a smooth quartic whose real locus has a W-shaped arc, cut by a horizontal
   line in 4 points.
3. **`flat-limit.eps`.** The file is missing from the repo. Do you have the
   original? Otherwise I1 is a fresh TikZ drawing based on the caption.
4. **`schubert.png`.** Should it be redrawn in TikZ (H6, the default given "all
   TikZ"), or included as the image?
5. **pgfplots.** Is it OK to use for the exact real plots? It is built on
   TikZ. The alternative is plain TikZ `plot`.
6. **Scope.** All 55 figures, or the requested ones plus the high-priority new
   ones (38)?
7. **Records.** Is `ai/` the right place for the preview and records, and
   `figures/` for the figure sources?
