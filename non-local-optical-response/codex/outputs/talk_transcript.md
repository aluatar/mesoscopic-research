# From local optics to mesoscopic electrodynamics

Journal-club transcript for Fedor Shukin  
Target duration: approximately 35–40 minutes  
Date: July 27th 2026

## Slide 1 — From local optics to mesoscopic electrodynamics

Good afternoon. Today I want to talk about what happens to optical electrodynamics when a metallic structure becomes so small that the electronic structure of its boundary is no longer hidden.

The path will begin with ordinary local Maxwell theory, because that remains the right baseline. I will then move through microscopic orbital calculations, effective surface response, and quantum hydrodynamics. The endpoint is a recent volume-integral formulation of self-consistent hydrodynamics—the article listed as reference [1] in the supplied review—but the talk is really about the chain of ideas that makes that endpoint useful.

The phrase I would like you to keep in mind is this: at mesoscopic scales, the boundary is not only where we impose boundary conditions. The boundary itself becomes a frequency-dependent optical response.

## Slide 2 — At a nanometre, the boundary is no longer a line

Here is the whole problem in one literature figure. Gonçalves and co-workers place three descriptions side by side. On the right, classical Maxwell theory uses a local bulk permittivity and a perfectly sharp density step. On the left, a microscopic description retains atomic structure, quantum confinement, and Landau damping. In the middle, the Feibelman surface response keeps the leading electronic length scale while leaving the surrounding electrodynamics macroscopic.

In a local Maxwell calculation, the metal begins at a perfectly sharp plane. The induced charge is mathematically confined to that plane, even though the bulk permittivity may be dispersive and lossy.

At a scale of one or a few nanometres, that idealization becomes visible. The equilibrium electron density can extend past the ionic surface. The induced charge has a finite centroid. The current can have a longitudinal component, and in a sufficiently narrow junction electrons can cross the gap.

So the question is not simply whether the system is “quantum.” Of course the electrons are quantum at every size. The useful question is: which part of the microscopic response has become experimentally resolvable, and how can we retain that part without calculating every electron in the entire device?

That is the role of a mesoscopic model.

## Slide 3 — The route from Maxwell to a mesoscopic model

This slide is the map for the talk.

We start with local optics and a bulk dielectric function. It is compact and scalable, but it forgets spatial structure. The opposite limit is a microscopic calculation based on orbitals, densities, and a two-point susceptibility. That contains much more information but becomes expensive very quickly.

Between those limits are two kinds of compression. Feibelman parameters compress the microscopic interface into a small number of surface-response functions. Hydrodynamic models instead retain density and current as continuum fields, including longitudinal electronic motion.

The final step is a computational one: can a self-consistent hydrodynamic model, including a diffuse equilibrium surface, be solved cheaply enough to be useful in repeated optical calculations?

The point is not to crown one model as the winner. It is to understand what each response object remembers and what it throws away.

## Slide 4 — Classical local optics: the successful baseline

Let me first be fair to classical local response. The polarization or current at a point is proportional to the electric field at that same point. The coefficient can depend on frequency, so the model still contains bulk dispersion and absorption. It can also be combined with an accurate geometry, retardation, radiation, substrates, and sophisticated numerical solvers.

For structures that vary slowly on electronic length scales, this is not merely convenient; it is the controlled macroscopic limit.

The approximation is hidden at the interface. The material profile jumps abruptly, and all induced surface charge is assigned to one mathematical plane. No amount of mesh refinement changes that assumption. A finer mesh gives a more accurate solution of the local constitutive law; it does not create spatial dispersion, spill-out, or tunnelling.

This distinction between numerical convergence and physical convergence will return several times.

## Slide 5 — Breakdown is controlled by the smallest field scale

Overall particle size is not the only relevant scale. What matters is the smallest length over which the optical field changes.

The natural comparisons are quantities such as \(q\ell\), \(\ell/R\), \(\ell/g\), and \(\ell/t\). Here \(\ell\) might mean a screening length, a spill-out width, a Fermi wavelength, a mean free path, a tunnelling decay length, or an exciton radius.

This is why a one-hundred-nanometre antenna with a one-nanometre gap may exhibit stronger nonlocal effects than a much smaller isolated particle. The gap produces Fourier components with wavevector of order one over the gap size.

The literature result on the right makes the size dependence concrete. Toscano and co-workers plot the surface-plasmon energy against inverse nanowire radius. Their self-consistent hydrodynamic calculation gives different trends for sodium and silver, because spill-out and interband screening compete differently in the two materials. The lower panel also shows a Bennett surface mode that has no counterpart in a one-resonance local picture. The point is not that every system follows these curves, but that \(1/R\) exposes physics that the bulk dielectric function cannot encode.

It is also why a resonance shift by itself is not a unique signature. The same shift could come from a surface centroid, a geometric error, a spacer thickness, a facet, chemistry, or interband screening. Strong evidence normally requires more than one observable—ideally one reactive quantity and one dissipative or transport quantity.

## Slide 6 — Nanoparticles and 2D materials expose different nonlocalities

There are at least two distinct routes to the breakdown of a local description.

For a finite metal nanoparticle, the surface-to-volume ratio grows as the radius decreases. Discrete electron–hole transitions coexist with a collective plasmon. Facets, curvature, \(d\)-band screening, and spill-out all affect the spectrum. The difficulty is not simply that the dielectric function becomes size dependent; several microscopic mechanisms become entangled.

For an atomically thin material, nonlocality is present in the in-plane response from the beginning. A graphene sheet is more naturally described by \(\sigma_{2D}(q,\omega)\) than by a purely frequency-dependent sheet conductivity. Large-\(q\) plasmons approach the Landau-damping continuum. In a semiconductor monolayer, exciton dispersion and finite coherence length similarly make \(\chi_{2D}(q,\omega)\) the relevant object.

These systems are different, but both tell us that frequency alone is no longer enough.

## Slide 7 — The microscopic route: orbitals, screening, and correlations

The most direct answer is to calculate the electronic structure microscopically.

Hartree–Fock gives orbitals with exact exchange but misses dynamical correlation. Density-functional theory provides a ground-state density and practical orbitals. Time-dependent DFT or the random-phase approximation gives a dynamical susceptibility. GW and the Bethe–Salpeter equation improve quasiparticle energies and excitons, while nonequilibrium Green functions are natural for open boundaries and transport.

The common feature is that the response depends on two positions. A perturbation at \(\mathbf r'\) produces density at \(\mathbf r\). That two-point susceptibility can contain atomic structure, transitions, surface states, spill-out, screening, and—with the appropriate formalism—charge transfer.

These methods therefore provide the reference against which effective models should be judged. But DFT or Hartree–Fock should not be described as exact many-body solutions; they are levels in a hierarchy of microscopic approximations.

## Slide 8 — Microscopic quantum models do not scale

The problem is scale.

A realistic nanophotonic device may require thousands or millions of atoms, many frequencies, multiple geometries, roughness realizations, substrates, and open electromagnetic space. A microscopic calculation may answer one carefully chosen structure, but it rarely supports the parameter sweep needed to design a device or fit an experiment.

There is also a transfer problem. A calculated absorption spectrum is tied to one geometry. What we would really like to export is a compact material response that can be reused in a boundary-element, finite-element, or integral-equation solver.

That compression step is where mesoscopic modelling begins. We calculate the expensive electronic structure only where it is indispensable, then encode its observable effect in a smaller response object.

The next two slides show both the power and the limitation of the microscopic route.

## Slide 9 — Atoms reorganize the optical spectrum

This is Figure 2 from the 2024 work of Chaudhary and Weissker. The calculations use real-time TDDFT with a consistent \(U\) correction to describe silver clusters over a remarkably broad size range.

At the smallest sizes the spectra consist of discrete electron–hole transitions. As the number of atoms grows, a broader localized surface-plasmon resonance emerges. The icosahedral and fcc-based particles do not evolve identically, which shows that “particle size” is not a complete microscopic descriptor.

This is a valuable benchmark because the same electronic model is used across the sequence. It demonstrates how atomic transitions evolve into something that resembles a classical collective plasmon.

But it also exposes the computational boundary. Even a calculation involving roughly ten thousand active electrons reaches only a few nanometres. That is large for TDDFT, yet tiny compared with a realistic optical antenna or a full device sweep.

## Slide 10 — A collective plasmon emerges—but not as a universal curve

Figure 3 from the same paper plots the localized plasmon energy against inverse radius, from Ag\(_4\) to Ag\(_{923}\).

There is a systematic size trend, but it is not one universal line. The smallest clusters retain discrete structure. The larger clusters approach a collective resonance, while different structural families remain separated at comparable size.

This matters for phenomenological size corrections. If I fit one radius-dependent dielectric function to these data, that fit would absorb quantum confinement, atomic geometry, and \(d\)-electron screening into one number. It might interpolate one dataset while giving the wrong physical interpretation.

So the microscopic result should be used as a calibration benchmark. The next question is whether a smaller set of surface or nonlocal response functions can reproduce the part of the spectrum that matters at larger scales.

## Slide 11 — Before tunnelling, the screening charge has already moved

This regime diagram from Zhu and co-workers is a useful bridge between atomistic and mesoscopic descriptions.

At large gaps, local Maxwell theory describes the bonding dimer plasmon with a geometric dielectric gap. As the gap enters the few-nanometre range, the centroid of the screening charge shifts away from the nominal interface. The optical gap is then different from the geometric gap even though the bodies remain electronically separated.

At still smaller gaps, wavefunctions overlap and current crosses the junction. Charge-transfer plasmons can appear before mechanical contact.

These are two different failures. A shifted charge centroid can be represented by a surface response or, less specifically, by hydrodynamics. A conductive gap cannot. Once electrons traverse the gap, the topology of the electromagnetic boundary problem has changed, and a transport-calibrated model is required.

## Slide 12 — Compressing a quantum interface into two response functions

Feibelman’s idea is to replace the full microscopic surface layer by its leading moments.

The perpendicular parameter \(d_\perp\) is the centroid of the induced charge measured from a stated reference plane. The parallel parameter \(d_\parallel\) similarly describes the tangential-current response.

These parameters are complex and frequency dependent. Their real parts primarily affect phase and resonance energy. Their imaginary parts carry surface-enabled loss. They are not universal lengths: they depend on material, crystallographic surface, environment, frequency, and potentially wavevector.

The two experimental panels on the right are a useful reality check. Yang and co-workers retrieve both the real and imaginary parts of \(d_\perp\) from families of film-coupled resonators. Thus the compact surface quantity is constrained by measured spectral shifts and losses, rather than being introduced only as a diagrammatic centroid.

The advantage is enormous. Instead of resolving angstrom-scale charge density in every device geometry, we can insert two surface functions into modified Maxwell boundary conditions.

The price is that the compression is normally first order and interface local. Strong curvature, multiple facets, charge transfer, or pronounced \(q\) dependence may require more information.

## Slide 13 — The surface response is complex, dispersive, and measurable

Yang and co-workers demonstrated that this is not only a theoretical construction.

Their film-coupled resonators provide families of resonance shifts and linewidths. From these data they retrieve a complex, frequency-dependent perpendicular surface response for an Au–AlO\(_x\) interface.

Two points are important. First, the nonclassical shifts are large in the reported architecture—more than thirty percent. Second, they fit both resonance position and linewidth. That is much more constraining than fitting one spectral peak, because the real and imaginary parts of the response must remain mutually consistent.

The retrieval is still not automatically transferable. It depends on the chosen reference plane, the interface structure and facet, and the range of wavevectors sampled by the resonators.

Nevertheless, this experiment supports the central mesoscopic idea: a complex surface response can be an observable material property rather than an arbitrary numerical correction.

## Slide 14 — Spill-out starts in the ground state

The next distinction is subtle but important.

A nonzero surface centroid does not necessarily imply dynamical nonlocality. If the equilibrium electron density changes smoothly across the ionic boundary, the induced charge already occupies a finite-width region. That produces spill-out or spill-in and a finite \(d\) parameter even if the response is local at every point in that inhomogeneous profile.

The two profiles from Toscano and co-workers show the distinction directly. In the self-consistent model, panel b, the equilibrium electron density has a diffuse tail and the induced charge spreads across the ionic radius. In the hard-wall model, panel c, the equilibrium density is a step and the induced charge is forced against that artificial boundary.

Finite electron-gas compressibility is a different effect. It is dynamical and produces longitudinal density motion.

The two contributions can reinforce or cancel. For some surfaces, spill-out shifts the effective charge outward and tends to redshift a plasmon. Hard-wall hydrodynamic pressure tends to push charge inward and often produces a blueshift.

This is why one should not equate every nonclassical shift with one generic “nonlocal correction.” The sign and magnitude depend on which microscopic mechanism the model retains.

## Slide 15 — Compute the interface once; reuse it in Maxwell solvers

This slide shows the multiscale pipeline suggested by the surface-response approach.

We first perform a microscopic calculation for a representative planar interface. From the induced charge and current, we take the appropriate moments and obtain \(d_\perp(\omega)\) and \(d_\parallel(\omega)\). Those functions enter modified boundary conditions in a Maxwell solver, which can then treat many device geometries.

This is mesoscopic in a very literal sense. The atomic-scale information is neither discarded nor reproduced everywhere. It is compressed into a reusable boundary response.

The possible failure modes are also clear. The planar parameter may not transfer to strong curvature, a different facet, a chemically modified interface, or a broad range of wavevectors. If the optical field probes volume density motion rather than only a thin interface, a surface correction may also be too severe a compression.

That motivates the hydrodynamic route.

## Slide 16 — Tunnelling changes the topology of the boundary

Before moving to hydrodynamics, let me close the nanogap story.

Savage and co-workers measured optical spectra together with conductance in a controllable gold junction. Tan and co-workers then showed that molecular conductance controls the capacitive-to-conductive plasmon crossover.

At large gaps, the junction behaves capacitively and the bonding mode redshifts as the gap closes. At the onset of tunnelling, the optical crossover follows junction conductance rather than only nominal separation. Once the junction supports appreciable current, a charge-transfer mode becomes possible.

This pairing of optics with transport is powerful because it removes much of the ambiguity in gap calibration.

It also defines a firm model boundary. Surface parameters and hard-wall hydrodynamics can correct separated polarizable bodies. A conductive junction needs a quantum-corrected model, NEGF, or another response calibrated to transport.

## Slide 17 — A surface correction is not yet a bulk nonlocal model

Surface response and hydrodynamics are complementary rather than competing ideas.

The Feibelman route assumes that the microscopic structure is confined to a thin interface layer. It compresses that layer into a small number of moments. This is efficient and naturally carries complex surface loss.

The hydrodynamic route retains density and current as fields throughout the metal. It therefore captures longitudinal waves, finite compressibility, and a wavevector-dependent bulk response.

The hydrodynamic model is needed when the field varies appreciably inside the electron gas, not only across a thin surface sheet. But it requires an electronic closure and an additional boundary treatment. In other words, it retains more volume dynamics while making stronger assumptions about the continuum electron fluid.

Both models can be derived as different reductions of the same underlying microscopic susceptibility.

## Slide 18 — Quantum hydrodynamics keeps density and current

The simplest linearized hydrodynamic Drude model combines charge continuity with an equation of motion for the current.

The familiar Drude term accelerates the current in the electric field. The pressure term, proportional to the gradient of the induced charge, couples neighboring points. This produces a longitudinal electronic wave and a nonlocal dielectric response depending on wavevector.

In the simplest closure, the parameter \(\beta\) is related to the Fermi velocity. GNOR adds a diffusion-like term to represent additional damping.

The figure on the right is the original sphere comparison from the 2014 GNOR paper by Mortensen and co-workers. In panel a, hydrodynamic pressure shifts the dipole resonance relative to the local result, with the shift growing approximately as \(\beta/R\). In panel b, adding diffusion produces both a shift and a size-dependent broadening. The sequence from six- to two-nanometre radius makes the central modelling advantage visible: one continuum closure changes a measurable spectrum systematically with size.

The appeal is computational. Density and current remain continuum fields, so they can be coupled to Maxwell solvers for structures much larger than an atomistic calculation.

The model is still effective. The pressure closure, damping, and boundary condition must be calibrated, and the basic version contains no detailed chemistry or interband structure.

## Slide 19 — Complex gap-mode propagation tests both phase and loss

Boroviks and co-workers provide an instructive experimental test of this type of model.

Using scattering-type near-field microscopy, they measure the complex propagation constant of gap surface plasmons in crystalline gold–alumina–gold waveguides.

The real part of the wavevector reports confinement and phase. The imaginary part reports propagation loss. In few-nanometre gaps, the measured loss exceeds the local-response prediction. A GNOR description can fit the complex trend with an effective diffusion scale.

This is stronger than comparing only resonance energy because one model must account for both phase and attenuation.

But the fit should not be overinterpreted. The extracted diffusion coefficient is an effective closure. The experiment supports missing nonlocal and surface-enabled loss, but it does not uniquely prove that one microscopic diffusion process is responsible.

## Slide 20 — Hard-wall hydrodynamics moves the problem to the boundary

The standard hydrodynamic model normally imposes zero normal current at the ionic surface. The electron fluid can compress, but it cannot spill across that chosen boundary.

This boundary condition gives a stable, inexpensive model and often predicts a blueshift because the induced charge is pushed inward. It also supports longitudinal modes.

What it omits is equally important: equilibrium spill-out, facet chemistry, detailed interband screening, tunnelling, and a microscopic derivation of phenomenological damping.

So adding a nonlocal differential equation does not automatically give a realistic surface. In fact, the model can move uncertainty from the bulk constitutive law into the boundary condition.

The natural next step is to determine the equilibrium density self-consistently, so the electron gas defines its own diffuse optical boundary.

## Slide 21 — Let the equilibrium density define the metal surface

Self-consistent hydrodynamics, often called quantum hydrodynamic theory or SC–HDM in this context, adds that missing equilibrium step.

First, an orbital-free energy functional is minimized to obtain the equilibrium density \(n_0(\mathbf r)\). Second, density and current are linearized around that diffuse profile. Third, the induced fields are coupled back to Maxwell electrodynamics.

This creates a useful hierarchy. Hard-wall HDM has nonlocal dynamics but a sharp equilibrium density. SC–HDM has nonlocal dynamics and a diffuse equilibrium density. TDDFT retains orbitals and microscopic transitions as well.

Figure 1(a) from Toscano and co-workers shows what this hierarchy does to an actual spectrum. For a two-nanometre sodium nanowire, the local response, hard-wall hydrodynamics, and self-consistent hydrodynamics place the main resonance at visibly different energies. The charge-density insets show why: allowing the equilibrium density to spill out changes where the screening charge lives. The self-consistent calculation also produces a higher-energy Bennett mode, so the difference is not only a rigid shift of one peak.

The self-consistent model is more physical at the surface, but it is not parameter free. Results depend on the kinetic-energy functional, the treatment of the density tail, interband calibration, and the numerical resolution of very different length scales.

That numerical burden is precisely what the final group of slides addresses.

## Slide 22 — A spherical volume-integral route removes the exterior mesh

We now arrive at the recent work of Mystilidis and co-workers, the article numbered [1] in the review.

The computational problem is that a diffuse density requires a fine material mesh, while the electromagnetic exterior is infinite. A conventional differential-equation calculation can therefore spend most of its effort on empty space.

The proposed volume-integral formulation uses the homogeneous dyadic Green tensor to account for radiation without meshing the exterior. For a sphere, the polarization is expanded in vector spherical harmonics, and the diffuse radial density is represented with cubic Lagrange functions. Transverse-electric, transverse-magnetic, and longitudinal sectors become small radial systems.

The impressive speedup is therefore real but symmetry enabled. The method is especially elegant for a sphere; extension to arbitrary geometries is a separate challenge.

## Slide 23 — The integral solver recovers established LRA and HDM limits

Before trusting the self-consistent result, the authors test the integral formulation in limits where an independent solver is available.

Figure 2 compares local-response and hard-wall hydrodynamic spectra with OpenSANS S-matrix calculations for radii from one to five nanometres. The reported relative error is about 0.08 percent in the benchmark quantities, and the dipolar resonance follows the expected quasistatic radius trend.

This is a strong numerical validation of the spherical expansion, radial discretization, and coupling of the relevant field sectors.

It is important to state exactly what has been validated. Agreement with OpenSANS checks the implementation in LRA and HDM. It does not validate the self-consistent orbital-free functional as a material description of real sodium or a noble metal.

That distinction separates solver verification from physical validation.

## Slide 24 — Self-consistency redshifts the dipole and reveals a surface mode

Figure 3 contains the central physical result.

For a sodium-like sphere of radius two nanometres, the local dipole lies near 3.49 electronvolts. Hard-wall hydrodynamics shifts it upward to about 3.64 electronvolts. The self-consistent diffuse model shifts it downward to about 3.30 electronvolts.

The sign change is physically meaningful. Hard-wall pressure pushes the response inward, whereas the diffuse equilibrium density allows an outward centroid. The self-consistent spectrum also contains a Bennett-type surface feature near 4.1 electronvolts, and the induced-charge maps distinguish that mode from the ordinary dipole.

The reported average runtimes are 85.69, 87.95, and 94.36 seconds for LRA, HDM, and SC–HDM. In this spherical implementation, self-consistency costs only about ten percent more than the local calculation.

## Slide 25 — The same calculation can export an effective surface response

The authors then take one further mesoscopic step. From the radial induced charge they form a spherical \(d_\perp\)-like centroid.

The resulting response is smooth around the dipole resonance and develops Lorentzian structure at the Bennett mode. This suggests a useful multiscale strategy: use self-consistent hydrodynamics to calculate a surface response, then export that response to a cheaper boundary-corrected solver.

There are several cautions. A centroid extracted from a finite sphere is not automatically the same as a planar, causal, facet-independent \(d(q,\omega)\). The chosen radius and reference surface matter. The response must be checked for broadband causality and passivity, and the paper reports that a first zero near 4.62 electronvolts is numerically sensitive.

So the bridge is promising, but the transfer step still needs careful validation.

## Slide 26 — What the spherical bridge still cannot do

Let me summarize the contribution without asking it to do more than it actually does.

The method reproduces established LRA and HDM benchmarks. It solves self-consistent hydrodynamics with only about ten percent overhead in the tested spherical geometry. It shows how a diffuse equilibrium changes resonance positions and creates a Bennett-type feature. It can also extract a compact surface-response quantity.

What remains open is extension to arbitrary shapes, edges, substrates, and touching junctions; treatment of noble metals with interband screening and facets; systematic calibration of the orbital-free functional and density tail; and transfer of a stable \(d(q,\omega)\) to general BEM or FEM geometries.

Direct experimental validation of the sodium-like spectra is also absent.

My conclusion is that this is a strong solver result and a valuable computational bridge, but not yet a universal material model.

## Slide 27 — A hierarchy of response objects—not a single winner

This table collects the hierarchy.

Local optics uses \(\varepsilon(\omega)\) or a local sheet conductivity. It is the scalable baseline. Microscopic approaches use a two-point susceptibility or open-system Green functions and retain the most electronic structure at the highest cost.

Feibelman parameters retain complex surface centroids. HDM and GNOR retain volume compressibility and longitudinal waves. Self-consistent hydrodynamics adds a diffuse equilibrium density. Quantum-corrected and transport models become necessary when a gap conducts.

For hybrid systems, especially metal–2D structures, these response objects should remain separate. The metal may need \(d\) parameters or QHT, while graphene or a semiconductor monolayer needs \(\sigma_{2D}(q,\omega)\) or \(\chi_{2D}(q,\omega)\).

Hiding both subsystems in one fitted effective permittivity makes it impossible to identify which subsystem carries momentum dependence or loss.

## Slide 28 — From local optics to mesoscopic electrodynamics

Let me finish with five points.

First, local Maxwell theory remains the controlled baseline while electronic lengths are small compared with the field-variation scale.

Second, microscopic calculations reveal the missing physics—atoms, transitions, facets, spill-out, and tunnelling—but do not scale to device sweeps.

Third, Feibelman parameters provide a powerful compression of a thin quantum interface into measurable complex surface response.

Fourth, hydrodynamics retains nonlocal density and current dynamics, while self-consistency is needed when the equilibrium surface is diffuse.

Finally, the spherical volume-integral formulation shows that this self-consistent bridge can be computationally practical, although transfer to realistic materials and arbitrary geometries remains open.

So the model-selection question is not merely, “Is this system quantum?” It is: which response object contains the physics that the experiment is actually resolving?
