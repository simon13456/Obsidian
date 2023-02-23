# 6.3
## The Z transform
The z-transform of a discrete sequence h(n), expressed as H(z), is defined as :
$$H(z) =  \sum\limits_{n=-\infty}^{\infty} h(n)z^{-n}$$
We can determine the frequency response of an IIR digital filter by expressing z in polar form as :
$$ z = re^{j\omega} $$
![[Pasted image 20230223171400.png]]

Causal filter’s H(z) transfer function has a single pole at location p on the z-plane, its transfer function can be represented by
$$ H(z) = \frac{1}{1-pz^{-1}}$$
and the filter’s time-domain impulse response sequence is
$$ h(n) = p^n * u(n)$$
where $u(n)$ represents a unit step (all ones) sequence beginning at time $n = 0$.
A value of |p| < 1 means that the pole must lie inside the z-plane’s unit circle.
# 6.4
>[!notes]
>The effect of a single unit of time delay is to multiply the z-transform of the undelayed sequence by $z^{-1}$ 


>[!danger] Important en criss
> z à la moins qqch c'est un delai, $z^{-1}$ c'est 1 avant et $z^{-2}$ c'est 2 avant. Sa marche aussi pour le turfu avec  $z^{1}$ et  $z^{2}$ qui sont 1 et 2 dans le futur.
# 6.11
## Bilinear transform
>[!notes]
> This design technique approximates a prototype analog filter defined by the continuous Laplace transfer function $H_c(s)$ with a discrete filter whose transfer function is $H(z)$.

If the transfer function of a prototype analog filter is Hc(s), then we can obtain the discrete IIR filter z-domain transfer function H(z) by substituting the following for s in Hc(s):
$$s= \frac{2}{t_s}\frac{1 - z ^{-1}}{1 + z ^{-1}}$$
$$t_s = \frac{1}{f_s}$$
s-plane to z-plane mapping characteristic:
$$z = \frac{(1 + \sigma t_s /2) + j\sigma _a t_s /2}{(1 - \sigma t_s /2) - j\sigma _a t_s /2}$$
>[!notes]
 >Any pole located on the left side of the s-plane (σ < 0) will map to a z-plane location inside the unit circle.

 Useful expression for the z-domain frequency $\omega_d$, in terms of the s-domain frequency $\omega_a$ as :
$$\omega _d = 2\tan^{-1} \frac{\omega_a t_s}{2},-\pi \leq \omega_d \leq \pi$$
 No IIR filter response aliasing can occur with the bilinear transform design method.