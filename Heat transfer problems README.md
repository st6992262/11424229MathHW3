<!DOCTYPE html>
<html lang="en">

</head>

<body>

<h1>Problem 4: Heat Transfer Engineering Case – Steel Quenching</h1>
<h2>Transient Heat Conduction in a Semi-Infinite Solid</h2>

<hr>

<h2>1. Problem Statement</h2>
<p>
A thick steel plate is initially at a uniform temperature
\(T_0 = 20^\circ C\).
At \(t=0\), the surface is suddenly immersed in a salt bath at
\(T_s = 800^\circ C\).
Assuming the plate can be approximated as a semi-infinite solid,
find the temperature distribution inside the steel plate and determine
the temperature at depth \(x=0.05\,m\) after \(t=100\,s\).
</p>

<h2>2. Mathematical Modeling (Heat Conduction Equation)</h2>

<p>
The one-dimensional transient heat conduction equation is:
</p>

<p>
$$
\frac{\partial T}{\partial t}
=
a \frac{\partial^2 T}{\partial x^2}
$$
</p>

<p>
where
</p>

<ul>
<li>\(T(x,t)\): temperature in the steel plate</li>
<li>\(a\): thermal diffusivity</li>
<li>\(x\): depth below the surface</li>
<li>\(t\): time</li>
</ul>

<p>
Given:
</p>

<ul>
<li>\(T_0 = 20^\circ C\)</li>
<li>\(T_s = 800^\circ C\)</li>
<li>\(a = 1.5 \times 10^{-5}\, m^2/s\)</li>
</ul>

<h2>3. Derivation (Analytical Solution)</h2>

<h3>Step 1: Initial and Boundary Conditions</h3>

<p>
Initial condition:
</p>

<p>
$$
T(x,0)=T_0
$$
</p>

<p>
Boundary conditions:
</p>

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

<h3>Step 2: Use the Semi-Infinite Solid Solution</h3>

<p>
For a semi-infinite solid with a suddenly changed surface temperature, the solution is:
</p>

<p>
$$
T(x,t)
=
800
+
(20-800)
\mathrm{erf}
\left(
\frac{x}{2\sqrt{at}}
\right)
$$
</p>

<p>
Therefore,
</p>

<p>
$$
T(x,t)
=
T_s
+
(T_0-T_s)
\mathrm{erf}
\left(
\frac{x}{2\sqrt{at}}
\right)
$$
</p>

<h3>Step 3: Substitute the Given Values</h3>

<p>
At \(x=0.05\,m\) and \(t=100\,s\),
</p>

<p>
$$
\eta
=
\frac{x}{2\sqrt{at}}
=
\frac{0.05}{2\sqrt{(1.5\times10^{-5})(100)}}
$$
</p>

<p>
$$
=
\frac{0.05}{2\sqrt{0.0015}}
=
\frac{0.05}{0.07746}
\approx 0.645
$$
</p>

<p>
From the error function table,
</p>

<p>
$$
\mathrm{erf}(0.645)\approx 0.639
$$
</p>

<p>
Substitute into the temperature formula:
</p>

<p>
$$
T(0.05,100)
=
800 + (20-800)(0.639)
$$
</p>

<p>
$$
=
800 - 780(0.639)
$$
</p>

<p>
$$
\approx 301.6^\circ C
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
\frac{x}{2\sqrt{at}}
\right)
$$
</p>
</div>

<div class="box" style="margin-top: 15px;">
<p>
$$
T(0.05,100)\approx 302^\circ C
$$
</p>
</div>

<h2>5. Engineering Significance</h2>

<h3>Heat Penetration Behavior</h3>

<ul>
<li>The surface temperature rises immediately to the salt bath temperature.</li>
<li>Heat gradually diffuses into the interior of the steel plate.</li>
<li>Deeper points remain cooler because thermal diffusion takes time.</li>
</ul>

<h3>Applications</h3>

<ul>
<li>Steel quenching and heat treatment</li>
<li>Thermal design of solids</li>
<li>Transient heat transfer analysis</li>
</ul>

</body>
</html>
