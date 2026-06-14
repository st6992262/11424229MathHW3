<!DOCTYPE html>
<html lang="en">

</head>

<body>

<h1>Problem 4: Heat Treatment of Steel Plate</h1>
<h2>Heat Conduction Equation Solved by Laplace Transform</h2>

<hr>

<h2>1. Problem Statement</h2>

<p>
A thick steel plate is initially at a uniform temperature
\(T_0=20^\circ C\).
At \(t=0\), the surface is suddenly immersed into a salt bath
maintained at \(T_s=800^\circ C\).
Assuming the plate behaves as a semi-infinite solid,
determine the temperature distribution \(T(x,t)\) and calculate
the temperature at depth \(x=0.05\,m\) after \(100\,s\).
</p>

<h2>2. Mathematical Modeling</h2>

<h3>Heat Conduction Equation</h3>

<p>
$$
\frac{\partial T}{\partial t}
=
a\frac{\partial^2 T}{\partial x^2}
$$
</p>

<ul>
<li>\(T(x,t)\): Temperature inside the plate</li>
<li>\(a\): Thermal diffusivity</li>
<li>\(x\): Distance from the surface</li>
<li>\(t\): Time</li>
</ul>

<h3>Initial Condition</h3>

<p>
$$
T(x,0)=T_0
$$
</p>

<h3>Boundary Conditions</h3>

<p>
$$
T(0,t)=T_s
$$
</p>

<p>
$$
T(\infty,t)=T_0
$$
</p>

<h2>3. Derivation Using Laplace Transform</h2>

<h3>Step 1: Define Dimensionless Temperature</h3>

<p>
$$
\theta(x,t)
=
\frac{T(x,t)-T_s}
     {T_0-T_s}
$$
</p>

<p>
The governing equation becomes
</p>

<p>
$$
\frac{\partial \theta}{\partial t}
=
a\frac{\partial^2 \theta}{\partial x^2}
$$
</p>

<h3>Step 2: Apply Laplace Transform</h3>

<p>
Let
</p>

<p>
$$
\Theta(x,s)
=
\mathcal{L}
\{
\theta(x,t)
\}
$$
</p>

<p>
Then
</p>

<p>
$$
s\Theta-1
=
a\frac{d^2\Theta}{dx^2}
$$
</p>

<p>
or
</p>

<p>
$$
a\frac{d^2\Theta}{dx^2}
-
s\Theta
=
-1
$$
</p>

<h3>Step 3: Solve the ODE</h3>

<p>
The general solution is
</p>

<p>
$$
\Theta(x,s)
=
\frac{1}{s}
+
Ce^{-x\sqrt{s/a}}
$$
</p>

<p>
Using the boundary conditions,
</p>

<p>
$$
C=-\frac{1}{s}
$$
</p>

<p>
Thus
</p>

<p>
$$
\Theta(x,s)
=
\frac{1}{s}
\left(
1-e^{-x\sqrt{s/a}}
\right)
$$
</p>

<h3>Step 4: Inverse Laplace Transform</h3>

<p>
Using the standard Laplace transform pair,
</p>

<p>
$$
\mathcal{L}^{-1}
\left\{
\frac{1}{s}
e^{-b\sqrt{s}}
\right\}
=
\mathrm{erfc}
\left(
\frac{b}{2\sqrt{t}}
\right)
$$
</p>

<p>
we obtain
</p>

<p>
$$
\theta(x,t)
=
\mathrm{erf}
\left(
\frac{x}
     {2\sqrt{at}}
\right)
$$
</p>

<h2>4. Final Solution</h2>

<div class="box">

<p>
$$
T(x,t)
=
T_s
+
(T_0-T_s)
\mathrm{erf}
\left(
\frac{x}
     {2\sqrt{at}}
\right)
$$
</p>

</div>

<p>
Substituting
\(T_s=800^\circ C\),
\(T_0=20^\circ C\),
and
\(a=1.5\times10^{-5}\,m^2/s\),
</p>

<p>
$$
T(x,t)
=
800
-
780
\mathrm{erf}
\left(
\frac{x}
     {2\sqrt{1.5\times10^{-5}t}}
\right)
$$
</p>

<h2>5. Numerical Calculation</h2>

<p>
For
</p>

<p>
$$
x=0.05\,m,
\qquad
t=100\,s
$$
</p>

<p>
$$
\frac{x}{2\sqrt{at}}
=
\frac{0.05}
     {2\sqrt{(1.5\times10^{-5})(100)}}
=
0.6455
$$
</p>

<p>
$$
\mathrm{erf}(0.6455)
\approx
0.6387
$$
</p>

<p>
$$
T(0.05,100)
=
800
-
780(0.6387)
$$
</p>

<p>
$$
T(0.05,100)
\approx
301.8^\circ C
$$
</p>

<h2>6. Engineering Significance</h2>

<h3>Heat Penetration</h3>

<ul>
<li>Temperature decreases with increasing depth.</li>
<li>Heat gradually penetrates into the steel plate.</li>
<li>The surface heats up much faster than the interior.</li>
</ul>

<h3>Error Function Solution</h3>

<p>
$$
T(x,t)
=
T_s
+
(T_0-T_s)
\mathrm{erf}
\left(
\frac{x}
     {2\sqrt{at}}
\right)
$$
</p>

<p>
This solution is widely used in transient heat conduction problems involving semi-infinite solids.
</p>

<h3>Applications</h3>

<ul>
<li>Steel quenching processes</li>
<li>Heat treatment engineering</li>
<li>Metal manufacturing</li>
<li>Thermal diffusion analysis</li>
</ul>

</body>
</html>
