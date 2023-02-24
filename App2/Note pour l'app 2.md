# Chapitre 1
## 1.1
>*discrete-time signal* : a signal whose independent time variable is quantized so that we know only the value of the signal at discrete instants in time.

>[!Note]
If a continuous sinewave represents a physical voltage, we could sample it once every $t_s$ seconds and represent the sinewave as a sequence of discrete values.
## 1.3
![[Pasted image 20230206154231.png]]
## 1.4
>*LTI* : linear time-invariant
## 1.5
A linear system’s output is the sum of the outputs of its parts. Where:
$x(n)_1+x(n)_2 → y(n)_1+y(n)_2$
## 1.6
A time-invariant system is one where a time delay (or shift) in the input sequence causes an equivalent time delay in the system’s output sequence. Keeping in mind that n is just an indexing variable we use to keep track of.
## 1.7
LTI systems have a useful commutative property by which their sequential order can be rearranged with no change in their final output
![[Pasted image 20230206155952.png]]
# Chapitre 2
## 2.1
![[Pasted image 20230206213142.png]]

\- An x(n) sequence of digital sample values,
representing a sinewave of fo Hz, also exactly represents sinewaves at other
frequencies, namely, fo + kfs.
So you can write:

>$x(n)=\sin(2\pi f_0 nt_0) =\sin(2\pi (f_0 +kF_s) nt_0)$ \- Eq. (2-5)

>[!FAQ]- Formally
>When sampling at a rate of fs samples/second, if k is any positive or negative
integer, we cannot distinguish between the sampled values of a sinewave of ''
fo Hz and a sinewave of (fo+kfs) Hz.

![[Pasted image 20230206214954.png]]
\-Figure 2–2(b) shows another example of frequency ambiguity that we’ll
call aliasing, where a 4 kHz sinewave could be mistaken for a –2 kHz
sinewave. In Figure 2–2(b), $f_o = 4$ kHz, $f_s = 6$ kHz, and $k =-1$ in Eq. (2–5), so
that $fo+kfs = [4+(-1 * 6)] = -2 kHz$
$\frac{f_s}{2}$ is an important quantity in sampling theory and is referred to by different
names in the literature, such as critical Nyquist, half Nyquist, and folding
frequency.
## 2.2
![[Pasted image 20230206222442.png]]
\-Given that the continuous x(t) signal, whose spectrum is shown in Figure 2–4(a), is sampled at a rate of fs samples/second, we can see the spectral replication effects of sampling in Figure 2–4(b) showing the original spectrum in addition to an infinite number of replications.To illustrate why the term folding frequency is used, let’s lower our sampling frequency to $f_s = 1.5$B Hz. The spectral result of this undersampling is illustrated in Figure 2–4(c)
# Chapitre 3
The DFT is a mathematical procedure used to determine the harmonic,
or frequency, content of a discrete signal sequence.The DFT is useful in analyzing any discrete sequence regardless of what that sequence actually represents.

\-The DFT’s origin, of course, is the continuous Fourier transform X( f ) defined as :

>$X(f)=\int_{-\infty}^{\infty} x(t)e^{-j\pi ft}dt$

DFT equation(exponential form): → $X(m) = \sum\limits_{n=0}^{N-1}x(n)e^{{-j\pi 2nm}/{N}}$

From Euler’s relationship,  $e-jø = cos(ø)-jsin(ø)$, Eq. (3–2) is equivalent to : 

 $X(m) = \sum\limits_{n=0}^{N-1} x(n)[\cos(2 \pi nm /N - j \sin(2 \pi nm / N)]$ 
- X(m) = the mth DFT output component, i.e., X(0), X(1), X(2), X(3), etc.,
- m = the index of the DFT output in the frequency domain,
- m = 0, 1, 2, 3, . . ., N–1,
- x(n) = the sequence of input samples, x(0), x(1), x(2), x(3), etc.,
- n = the time-domain index of the input samples, n = 0, 1, 2, 3, . . ., N–1,
- j= , and
- N = the number of samples of the input sequence

If we plot the X(m) output magnitudes as a function of frequency, we produce
the magnitude spectrum of the x(n) input sequence
## 3.2
DFT is called conjugate symmetric. When the input sequence x(n) is real, as it will be for all of our examples, the complex DFT outputs for $m = 1$ to $m= (N/2) - 1$ are redundant with frequency output values for $m > (N/2)$. The mth DFT output will have the same magnitude as the $(N–m)th$ DFT output.
## 3.7
IDTF : $x(n) =\frac{1}{N} \sum\limits_{m=0}^{N-1}X(m)e^{{j\pi nm}/{N}}$ and $x(n) = \frac{1}{N}\sum\limits_{n=0}^{N-1} X(m)[\cos(2 \pi nm /N + j \sin(2 \pi nm / N)]$
## 3.8
A characteristic known as leakage causes our DFT results to be only an approximation of the true spectra of the original input signals prior to digital sampling
# Chapitre
## 4.3
FFT
$x(n) = \sum\limits_{n=0}^{(N/2)-1} x(2n)e^{{-j2\pi(2n)m}/{N}}+e^{{-j2\pi m}/{N}}\sum\limits_{n=0}^{(N/2)-1} x(2n+1)e^{{-j2\pi(2n)m}/{N}}$

TFD : Sticks
TFSD : Line, cause time is discret, not frequency
%% Vue en classe %%

$X(\omega) = \frac {\sin (\omega K/2)}{\sin (\omega / 2)}$

The twiddle factor W is:

$W_N = e^{-j2\pi /N}$
>[!Notes]+
>Et quand on voit un indice et un facteur, on se dit juste que on replace l'indice par N et que on fait la puissance(qui dans notre cas devient juste une multiplication du facteur de  $e^{-j2\pi /N}$ par le facteur)
# Chapitre 5
Pour les filtres passe-bas: 
 $h(n)=\frac{\sin(\pi nk/N)}{\sin(\pi n/N)}$ Quand $N\not= 0$
 $h(n)=\frac{K}{N}$ Quand $N=0$

![[Pasted image 20230217092927.png]]

![[Pasted image 20230217093557.png|500]]
