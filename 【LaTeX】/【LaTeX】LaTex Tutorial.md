# LaTeX Tutorial

[TOC]

## Greek Alphabet

```LaTeX
\\ \theta \ \lambda \ \epsilon                    \        → a blank space
\\ \theta \; \lambda \; \epsilon                  \;       → a 5/18em blank space
\\ \theta \enspace \lambda \enspace \epsilon      \enspace → a 1/2em blank space
\\ \pi \quad \sigma \quad \omega						      \quad    → a 1em blank space
\\ \phi \qquad \varphi \qquad \Phi \qquad \varPhi \qquad   → a 2em blank space
```

$$
\\ \theta \ \lambda \ \epsilon
\\ \theta \; \lambda \; \epsilon
\\ \theta \enspace \lambda \enspace \epsilon
\\ \pi \quad \sigma \quad \omega
\\ \phi \qquad \varphi \qquad \Phi \qquad \varPhi
$$

| Greek letter |       LaTeX Form        | Greek letter |    LaTeX Form     |
| :----------: | :---------------------: | :----------: | :---------------: |
|    *α A*     |        \alpha A         |      N       |       \nu N       |
|    *β B*     |         \beta B         |    *ξ Ξ*     |      \xi \Xi      |
|    *γ Γ*     |      \gamma \Gamma      |    *o O*     |        o O        |
|    *δ Δ*     |      \delta \Delta      |    *π Π*     |  \pi \varpi \Pi   |
|   *ϵ ε E*    | \epsilon \varepsilon E  |   *ρ ϱ P*    |  \rho \varrho P   |
|    *ζ Z*     |         \zeta Z         |    *σ Σ*     |   \sigma \Sigma   |
|    *η H*     |         \eta H          |    *τ T*     |      \tau T       |
|   *θ ϑ Θ*    | \theta \vartheta \Theta |    *υ Υ*     | \upsilon \Upsilon |
|    *ω Ω*     |      \omega \Omega      |   *ϕ φ Φ*    | \phi \varphi \Phi |
|    *κ K*     |        \kappa K         |    *χ X*     |      \chi X       |
|    *λ Λ*     |     \lambda \Lambda     |    *ψ Ψ*     |     \psi \Psi     |
|    *μ M*     |          \mu M          |     *ι*      |       \iota       |

**PS: Upper Greek Letter can become *italics*** **by using "var"**
$$
\Sigma \rightarrow \varSigma
$$

## Superscript & Subscript 

```LaTeX
\\H_2O
\\cm^3
\\x^{y+z}  
\\P_{ij}
\\x_i
\\x_{\rm i}
```

$$
\\H_2O
\\cm^3
\\x^{y+z}
\\P_{ij}
\\x_i
\\x_{\rm i}
$$

## Fraction & Square Root

```LaTeX
\\ \frac{1}{2}
\\ \frac{x}{y+z}
\\ \frac{\frac{1}{x}}{e+1}  #compare with line4, not recommended
\\ \frac{\dfrac{1}{x}}{e+1} #recommended 

\\ \sqrt[3]{x+1}
\\ \sqrt{\sqrt{x+1}}
\\ \sqrt{x+\sqrt{x+\sqrt{x+1}}}
```

$$
\\ \frac{1}{2}
\\ \frac{x}{y+z}
\\ \frac{\frac{1}{x}}{e+1}
\\ \frac{\dfrac{1}{x}}{e+1}

\\ \sqrt[3]{x+1}
\\ \sqrt{\sqrt{x+1}}
\\ \sqrt{x+\sqrt{x+\sqrt{x+1}}}
$$

## Common Operator

```LaTeX
\\+-
\\ \times \cdot \div
\\ \pm \ \mp
\\ > < \ge \le \gg \ll 
\\  = \ne \approx \equiv
\\ \cap \cup \in \notin \subseteq \subsetneqq \varnothing
\\ \forall \ \exists \ \nexists
\\ \because \ \therefore
\\ \R \ \Q \ \N \ \Z \ \Z_+
\\ \cdot \ \cdots \ \vdots \ \ddots
\\ \infty \ \partial \ \degree
```

$$
\\+-
\\ \times \cdot \div
\\ \pm \ \mp
\\ > < \ge \le \gg \ll 
\\  = \ne \approx \equiv
\\ \cap \cup \in \notin \subseteq \subsetneqq \varnothing
\\ \forall \ \exists \ \nexists
\\ \because \ \therefore
\\ \R \ \Q \ \N \ \Z \ \Z_+
\\ \cdot \ \cdots \ \vdots \ \ddots
\\ \infty \ \partial \ \degree
$$

## Advanced Operator

```LaTeX
\\ \sum \ \prod
\\ \sum_{i=0}^{n} x_{i} \ \prod_{i=0}^n x_i
\\ \frac {\sum\limits_{i=0}^{n} x_i}{\prod\limits_{i=0}^n x_i}
\\ \int \ \int_a^b \ \iint \ \iiint \ \oint \ \oiint
\\ \int_{-\infty}^{0} f(x)\,\text d x
```

$$
\\ \sum \ \prod
\\ \sum_{i=0}^{n} x_{i} \ \prod_{i=0}^n x_i
\\ \frac {\sum\limits_{i=0}^{n} x_i}{\prod\limits_{i=0}^n x_i}
\\ \int \ \int_a^b \ \iint \ \iiint \ \oint \ \oiint
\\ \int_{-\infty}^{0} f(x)\,\text d x
$$



## Common Function

```LaTeX
\\ \sin x \ \cos x \sec x \tan x
\\ \log_2 x \ \ln x \lg x
\\ \lim_{x \to 0} \frac{x}{\sin x}
```

$$
\\ \sin x \ \cos x \sec x \tan x
\\ \log_2 x \ \ln x \lg x
\\ \lim_{x \to 0} \frac{x}{\sin x}
$$

## Vector

```latex
\\ \vec x \ \vec y \ \vec z
\\ \overrightarrow {ABC}

\\ \bar x
\\ \overline {ABC}
\\ \widehat{ABC} \ \widetilde{ABC} 

\\ \mathbf R

\\ \dot{a} \ \ddot{a} \ \dddot{a} \ \mathring{a}
\\ \hat{a} \ \check{a} \ \tilde{a} \ \acute{a} 
```

$$
\\ \vec x \ \vec y \ \vec z
\\ \overrightarrow {ABC}

\\ \bar x
\\ \overline {ABC}
\\ \widehat{ABC} \ \widetilde{ABC} 

\\ \mathbf R

\\ \dot{a} \ \ddot{a} \ \dddot{a} \ \mathring{a}
\\ \hat{a} \ \check{a} \ \tilde{a} \ \acute{a}
$$

## Arrow

```LaTeX
\\ \gets      \ \to
\\ \leftarrow \ \rightarrow \ \leftrightarrow 
\\ \Leftarrow \ \Rightarrow \ \Leftrightarrow
\\ \longleftarrow \ \longrightarrow \ \longleftrightarrow
\\ \Longleftarrow \ \Longrightarrow \ \Longleftrightarrow
\\ \mapsto \ \longmapsto
\\ \hookleftarrow \ \hookrightarrow
\\ \leftharpoonup \ \rightharpoonup
\\ \leftharpoondown \ \rightharpoondown
\\ \rightleftharpoons
\\ \uparrow \ \downarrow \ \updownarrow
\\ \Uparrow \ \Downarrow \ \Updownarrow
\\ \nearrow \ \searrow \ \swarrow \ \nwarrow
\\ \leadsto
```

$$
\\ \gets      \ \to
\\ \leftarrow \ \rightarrow \ \leftrightarrow 
\\ \Leftarrow \ \Rightarrow \ \Leftrightarrow
\\ \longleftarrow \ \longrightarrow \ \longleftrightarrow
\\ \Longleftarrow \ \Longrightarrow \ \Longleftrightarrow
\\ \mapsto \ \longmapsto
\\ \hookleftarrow \ \hookrightarrow
\\ \leftharpoonup \ \rightharpoonup
\\ \leftharpoondown \ \rightharpoondown
\\ \rightleftharpoons
\\ \uparrow \ \downarrow \ \updownarrow
\\ \Uparrow \ \Downarrow \ \Updownarrow
\\ \nearrow \ \searrow \ \swarrow \ \nwarrow
\\ \leadsto
$$

## Brackets & Parentheses

```LaTeX
\\( \ )
\\ \{ \ \}
\\ [ \ ]
\\ \lceil \ \rceil \lfloor \ \rfloor
\\ (0,\frac{1}{a}]
\\ \left(0,\frac{1}{a}\right]          
\\ \frac{\partial f}{\partial z}|_{x=0}
\\ \left.\frac{\partial f}{\partial z}\right|_{x=0}
```

$$
\\( \ )
\\ \{ \ \}
\\ [ \ ]
\\ \lceil \ \rceil \lfloor \ \rfloor
\\ (0,\frac{1}{a}]
\\ \left(0,\frac{1}{a}\right]
\\ \frac{\partial f}{\partial z}|_{x=0}
\\ \left.\frac{\partial f}{\partial z}\right|_{x=0}
$$

**PS: use "\left. \right" to add adpative attributes**

## Piecewise Function

```LaTeX
f(x)=
\begin{cases}
	\sin x,&\dfrac{\pi}{2}\le x \le 2π \\
	0,&\text {else}
\end{cases}
```

$$
f(x)=
\begin{cases}
	\sin x,&\dfrac{\pi}{2}\le x \le 2π \\
	0,&\text {else}
\end{cases}
$$

## Linear Equations 

```LaTeX
\begin{cases}
3x+2y-z=7\\
2y+7z=8\\
3z=8
\end{cases}
```

$$
\begin{cases}
3x+2y-z=7\\
2y+7z=8\\
3z=8
\end{cases}
$$

## Matrix

```LaTeX
\begin{matrix}
	a & b & \cdots & c \\
	\vdots & \vdots & \ddots & \vdots\\
	d & e & \cdots & d
\end{matrix}

\begin{pmatrix}
	a & b & \cdots & c \\
	\vdots & \vdots & \ddots & \vdots\\
	d & e & \cdots & d
\end{pmatrix}

\begin{bmatrix}
	a & b & \cdots & c \\
	\vdots & \vdots & \ddots & \vdots\\
	d & e & \cdots & d
\end{bmatrix}

\begin{vmatrix}
	a & b & \cdots & c \\
	\vdots & \vdots & \ddots & \vdots\\
	d & e & \cdots & d
\end{vmatrix}
```

$$
\begin{matrix}
	a & b & \cdots & c \\
	\vdots & \vdots & \ddots & \vdots\\
	d & e & \cdots & d
\end{matrix}

\begin{pmatrix}
	a & b & \cdots & c \\
	\vdots & \vdots & \ddots & \vdots\\
	d & e & \cdots & d
\end{pmatrix}

\begin{bmatrix}
	a & b & \cdots & c \\
	\vdots & \vdots & \ddots & \vdots\\
	d & e & \cdots & d
\end{bmatrix}

\begin{vmatrix}
	a & b & \cdots & c \\
	\vdots & \vdots & \ddots & \vdots\\
	d & e & \cdots & 
\end{vmatrix}
$$

## Hands-on Projects

$$
F(x,y) = \int_{-\infty}^x\int_{-\infty}^y f(u,v)\mathrm dv\mathrm du
$$

$$
P(X=k)={\mathrm e}^{-\lambda} \frac{\lambda^k}{k!},\quad k=0,1,2,\cdots
$$

$$
f(x)=\frac{1}{\sqrt{2\pi}\sigma}\mathrm{e}^{\frac{(x-\mu)^2}{2\sigma^2}}
$$

$$
\rho_{XY}=\frac{Cov(X,Y)}{\sqrt{D(x)}\sqrt{D(Y)}}
$$

$$
\oint_S \vec E \cdot d\vec S = \frac{1}{\varepsilon_0}\sum_{i=1}^n q_i
$$

$$
\begin{align}
	E_x &= \frac{\lambda}{4\pi\varepsilon_0r}(\cos \theta_1 - \cos \theta_2)\\
	E_y &= \frac{\lambda}{4\pi\varepsilon_0r}(\sin \theta_2 - \sin \theta_1)
\end{align}
$$

## References

[The Great, Big List of LaTeX Symbols](https://www3.nd.edu/~nmark/UsefulFacts/LaTeX_symbols.pdf)

