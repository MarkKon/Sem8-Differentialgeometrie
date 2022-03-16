## Wiederholung:

$\gamma : I\to \mathbb R^n$. $\|\dot\gamma\| = 1 \Rightarrow \kappa(t) := \|\ddot\gamma(t)\|.

### 1. Definition und Berechnung

- **Satz** Sei $\gamma: I\to \mathbb R^2$ eine reguläre Kurve. Sei $\alpha(t)$ der Winkel von $0x$ zu $\dot\gamma(t)$. Dann $$\kappa(t) = \frac{|\dot\alpha(t)|}{\|\dot\gamma(t)\|}$$. ![](Figure 2_1)

  Proof: Assume $\|\dot\gamma(t)\| = 1.$ Then $\dot\gamma(t) = (\cos\alpha(t), \sin\alpha(t))$. Then $\ddot\gamma = \dot\alpha(t)(-\sin\alpha(t),\cos\alpha(t))$- Now $\kappa(t) = \|\ddot\gamma\| = |\dot\alpha(t)| = \frac{|\dot\alpha(t)|}{\|\dot\gamma(t)\|}$.

  Now let $\delta = \gamma\circ \varphi$ any reparametrization. The quotient $\kappa(t) = \frac{|\dot\alpha(t)|}{\|\dot\gamma(t)\|}$ is invariant under reparametrization (with $\beta = \alpha\circ \varphi$): 
  $$
  \frac{
    |\frac{\mathrm d}{\mathrm ds}\beta|
  }
  {
    |\frac{\mathrm d}{\mathrm ds}\delta|
  }
  =
  \frac{
    |\dot \alpha\frac{\mathrm dt}{\mathrm ds}\beta|
  }
  {
    |\frac{\dot\gamma\mathrm dt}{\mathrm ds}\delta|
  }
  = \frac{|\dot\alpha|}{\|\dot\gamma\|}.
  $$
- Example: Curvature of the tractrix ![](Figure 1_9)
  $y = f(x)$ Thus $f'(x) = -\frac{\sqrt{1-x^2}}x$. Thus $f(x) = \int_1^x-\frac{\sqrt{1-x^2}}x\mathrm d x = \log(\frac{1+\sqrt{1-x^2}}x) - \sqrt{1-x^2}$ (with substitution $x = \sin u$). $\gamma(x) = (x, f(x))$

  $\sin\beta = x, \beta' = \frac1{\sqrt{1-x^2}}, \frac{\mathrm d \gamma}{\mathrm dx} = (1, -\frac{\sqrt{1-x^2}}x)$ and $\frac{\mathrm d\gamma}{\mathrm d x} = \frac1x$.

  $$\kappa = \frac{|\frac{\mathrm d\alpha}{\mathrm d x}|}{\|\frac{\mathrm d\gamma}{\mathrm d x}\|} = \frac{|\frac{\mathrm d\beta}{\mathrm d x}|}{\|\frac{\mathrm d\gamma}{\mathrm d x}\|} = \frac x{\sqrt{1-x^2}} = \tan\beta$$

  ![](2_2)

  Other good parameterizations: $x = \sin t, x = \tanh s$.

### 2. Signed curvature

$\kappa\geq 0$. 

- ** Lemma**: $\gamma: I\to \mathbb R^n$. If $\|\dot\gamma\| = \const$, then $\dot\gamma\perp\ddot \gamma$. 

  Proof. $\|\dot\gamma\| = const \Rightarrow \|\dot\gamma\|^2 = const$ Thus $\frac{\mathrm d}{\mathrm dt}(\|\dot\gamma\|^2) = \frac{\mathrm d}{\mathrm dt}\langle \dot\gamma,\dot\gamma\rangle = 2\langle\dot\gamma, \ddot \gamma\rangle $ And thus   $\dot\gamma\perp\ddot \gamma$. 

- **Definition**. Let $\gamma: I\to \mathbb R^2$ be unit-speed. Let $\nu_s(t)$ be a unit vector such that $(\dot\gamma(t),\nu_s(t))$ is a right-handed ONB. Then $\ddot \gamma = \kappa_s \cdot \nu_s$, and $\kappa_s$ is called the _signed curvature_. $\kappa_s = \pm \kappa$ since $\|\ddot\gamma\| =\kappa$. ![](2_3)
- **Definition**. A _closed regular curve_ is a regular curve $\gamma: \mathbb R\to \mathbb R^n$ such that $\forall t: \gamma(t+L) = \gamma(t)$, $L\in \mathbb R_{\geq 0}$. 
- **Theorem** For any closed regular curve $\gamma: \mathbb R\to \mathbb R^2$, one has $\int_0^L\kappa_s(t)\mathrm dt = 2k\pi$ for some $k\in\mathbb Z$. 
- **Lemma**. $\gamma: I\to \mathbb R^2$ unit-speed, then $\kappa_s = \dot\alpha$. 
  
  Proof: $\gamma = (\cos\alpha(t), \sin\alpha(t))$, thus $\nu_s = (-\sin\alpha(t), \cos\alpha(t))$ and $\ddot\gamma = \dot\alpha(t)(-\sin\alpha(t), \cos\alpha(t)) = \dot\alpha(t)\nu_s$. Thus $\alpha(t) = \kappa_s$.

  Proof of **Theorem**. 
  $\alpha(0)$ is the angle from $0x$ to $\dot\gamma(0)$ well defined $\mathrm{mod}2\pi$. Once a value $\alpha(0)$ is chosen, it can be extended uniquely to $\alpha: \mathbb R\to \mathbb R$ such that $\dot\gamma(t) = (\cos\alpha(t), \sin\alpha(t))$ for all $t$. 

  $$
  \int_0^l \kappa_s(t)\mathrm dt = \int_0^L\dot\alpha(t)\mathrm dt = \alpha(L)-\alpha(0) = 2k\pi$. 
  $$

  $k$ is called the _turning number_.
- **Theorem** Let $f: I\to \mathbb R$ be any smooth function. Then there is a unique (up to rigid motion) unit-speed curve $\gamma: I\to \mathbb R^2$ such that $\kappa_s(t) = f(t)$.

  Proof. $\gamma(t) = \gamma(t_0)+ \int_{t_0}^t\dot\gamma(t)\mathrm d t$. $\dot\gamma(t) = (\cos\alpha(t),\sin\alpha(t))$. $\dot\alpha(t) = f(t)$ then $\alpha(t) = \alpha(t_0) + \int_{t_0}^tf(t)\mathrm d t$.

- Example ![](2_4)

### 3. Space Curves: Curvature and torsion

- Let $\gamma :I\to \mathbb R^3$ be a unit-speed curve. Denote $T(t):= \dot\gamma(t)$. Assumption: $\kappa(t)= \|\ddot\gamma(t)\| \neq 0 \forall t\in I$.  

  $\|\dot\gamma(t)\| = 1 \Rightarrow \ddot\gamma\perp\dot\gamma$. Denote $N(t) := \frac{\ddot\gamma(t)}{\|\ddot\gamma(t)\|}$ the _principal normal_ to $\gamma$. Then $T(t), N(t)$ two orthogonal unit vectors.
- **Definition** The _binormal_ is $B(t) = T(t)\times N(t)$. That is, $(T(t), N(t), B(t))$ is a positively oriented orthonormal basis, the _Frenet-Serret frame_ (a frame is an basis with an origin vector).
- $T(t):= \dot\gamma(t), N(t) = \frac{\ddot\gamma(t)}{\|\ddot\gamma(t)\|}, B(t) = T(t)\times N(t)$. 
- **Theorem**. $\dot B(t)$ is collinear with $N(t)$ for all $t$.
- **Definition**. If $\dot B(t) = -\tau(t)\cdot N(t)$, then $\tau(t)$ is called the _torsion_ of $\gamma$. 

  Proof. $\dot B(t) = a(t)T(t) + b(t)N(t) + c(T)B(t)$. where $a(t) = \langle \dot B(t), T(t)\rangle$ etc. We need to show that $a(t) = 0 = c(t)$. 
  - $\|B(t)\| = 1 \Rightarrow 0 = \frac{\mathrm d}{\mathrm dt}(\|B(t)\|^2) = 2\langle B(t), \dot B(t)\rangle$ and therefore $c(t) = 0$. 
  - Differentiate $B$ = $T\times N$: $\dot B = \dot T\times N + T\times \dot N = \kappa N\times N + T\times \dot N = T\times \dot N$. Then as $\langle \times \dot N, T\rangle = 0$, $\langle \dot B , T\rangle = 0$ and thus $a(t) = 0$. 

- Meaning of the torsion: $\mathrm{span}\{T, N\}$ the _osculating plane_ is the best planar approximate of the curve (as it contains the first two deriveratives in the Taylor-expansion). Rotation speed of $\mathrm{span}\{T, N\}$ is the rotation speed of $T\times N = B$. This is $\|\dot B\| = |\tau|.$ 
- **Theorem** (Frenet-Serret-formulas): For any space curve $\gamma: I\to \mathbb R^3$ of unit speed and non-vanishing curvature one has: 
  - $\dot T = \kappa N$,
  - $\dot N = -\kappa T + \tau B$,
  - $\dot B = -\tau N$.

  In matrix form: 
  $$
  \left(\begin{array}{c}
  \dot T\\
  \dot N\\
  \dot B
  \end{array}\right)
  = 
  \left(\begin{array}{ccc}
  0 & \kappa & 0\\
  -\kappa & 0 & \tau \\
  0&-\tau & 0
  \end{array}\right)\cdot\left(
  \begin{array}{c}
  T\\
  N\\
  B
  \end{array}\right)
  $$
  
  Proof. 1) and 3) hold by definition. For 2):
    - $\langle \dot N , T\rangle = -\kappa$

      $\langle N, T = 0 \forall t \Rightarrow \langle \dot N, T\rangle +  \langle N, \dot T\rangle = \langle \dot N, T\rangle +  \langle N, \kappa\rangle = 0$
    - $\langle \dot N, N\rangle = 0$ (as $N$ is a unit vector)
    - $\langle\dot N , B\rangle$ similar to first item.

- **Lemma** The torsion of an arbitrary regular curve $\gamma$ in $\mathbb R^3$ is given by 
  $$
  \tau = 
  \frac{
    \det(\dot\gamma, \ddot\gamma, \dddot\gamma)
  }
  {
    \|\dot\gamma\times \ddot\gamma\|^2
  }
  .$$ 
  In particular, if $\|\dot \gamma \| = 1, then 
  $$
  \tau = 
  \frac{
    \det(\dot\gamma, \ddot\gamma, \dddot\gamma)
  }
  {
    \kappa^2
  }
  $$
  (Homework using Frenet-Serret)

### Nicht prüfungsrelevant:

- **Remark:** The deriverative of any moving frame is a skew symmetric matrix.
