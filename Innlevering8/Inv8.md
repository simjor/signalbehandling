# Innlevering 8
### Oppgave 1a

DSB FC:

```
Uam = U0*(1+m*cos(wm*t))*sin(wc*t)
```

Bruk trigonometriske formler og finn demodulerte informasjonssignalet for begge tilfellene:

```
1. U_bb = sin(wc*t)
2. U_bb = U1*cos(wc*t)
```

Finner demodulerte informasjonssignalet:

```
TILFELLE 1:
Motattsignal = Uam*U_bb = U0*(1+m*cos(wm*t))*sin(wc*t)*sin(wc*t)

// x=y=wc*t
sin(x)*sin(y) = 1/2[1-cos(2x)]
Motattsignal = 0.5*U0*(1+m*cos(wm*t))*[1-cos(2x)]
Motattsignal = 0.5*U0*(1+m*cos(wm*t))*(1-cos(2*wc*t))
Motattsignal = 0.5*U0*(1-cos(2*wc*t)+m*cos(vm*t)-m*cos(vm*t)*cos(2*wc*t)

// x=vm*t, y=2*wc*t
cos(x)*cos(y) = 1/2[cos(x-y)+cos(x+y)]
Motattsignal = 0.5*U0*(1-cos(2*wc*t)+m*cos(vm*t)-0.5(cos(vm*t-2*wc*t)+cos(vm*t+2*wc*t))

TILFELLE 2:
Motattsignal = Uam * U_bb = U1*U0*(1+m*cos(wm*t))*sin(wc*t)*cos(wc*t)

// x=y=wc*t
sin(wc*t)*cos(wc*t) = 1/2[sin(x+y)+sin(x-y)]
Motattsignal = 0.5*U1*U0*(1+m*cos(wm*t))*[sin(2*wc*t)+sin(0)]
Motattsignal = 0.5*U1*U0*(sin(2*wc*t)+m*cos(wm*t)*sin(2*wc*t))

// x = wm*t, y = 2*wc*t
cos(x)*sin(y) = 1/2[sin(x+y)-sin(x-y)]
Motattsignal = 0.5*U1*U0*(sin(2*wc*t)+ 0.5*m*(sin(2*wc*t+wm*t)-sin(wm*t-2*wc*t)))
Motattsignal = 0

Min forståelse for at dette skjer:
Når vi bruker trigonometriske funksjoner er det veldig enkelt å se om vi får 
hentet in informasjonssignalet riktig eller ikke.

Får vi et cos(x)*cos(x) vil vi få et ledd med 1 som vil representere at 
det modulerte signlet er i lik fase som det informasjonssignalet.

Får vi cos(x)*sin(x) vil vi få et et led med 0 som vil representere at det 
modulerte signalet representerer informasjonssignalet, men i motsatt fase.

Får vi sin(x)*cos(y) vil det bety at det modulerte signalet ikke representerer 
informasjonssignalet og dermed vil hele det modulerte signalet filtreres ut gjennom 
filteret. Dette fører til at vi kan sette det modulerte signalet til 0, fordi 
vi ikke får ut noe signal.
```

Hvilken rolle spiller amplitudefaktorene i demodulasjonsprosessen?

- Amplitudefaktoren til informasjonssignalet (U0) og gjenvunnet bærebølge (U1) bestemmer styrken til det demodulerte signalet. Endringer i amplitude til informasjonssignalet (m) kan påvirke modulasjonsgraden og dermed bredden av sidebåndene i  signalet. Endring i U1 kan påvirke styrken til demodulerte signalet.


### Oppgave1b

DSB-SC:

```
U_DSB-SC = Um*cos(wmt)*Uc*sin(wct)
```

Bruker en Kohernt detektor der gjenveunnet bb er gitt ved:

```
1. Ubb = sin(wct)
2. Ubb = U1*cos(wct) = U1sin(wct+pi/2)
```

Finner demodulerte informasjonssignalet for begge tilfellene:

```
TILFELLE 1:
motatt_sig = U_DSB-SC * Ubb = Um*cos(wmt)*Uc*sin(wct)*sin(wct)

// x=wct
sin(x)*sin(x) = 1/2[sin(2x)]
motatt_sig = Um*cos(vmt)*Uc*1/2(1 - sin(2*wct))
motatt_sig = Um*Uc*1/2(cos(vmt) - cos(vmt)*sin(2*wct))

//x = vmt, y = 2wct
cos(x)*sin(y)
motatt_sig = 1/2*Um*Uc*cos(vmt)-1/2(cos(x-y)+cos(x+y))
motatt_sig = 1/2*Um*Uc*cos(vmt)-1/2(cos(wmt-2wct)+cos(wmt+2wct))
motatt_sig = 1/2 Um*Uc*cos(vmt) - 1/4(cos(vmt-2wct)-cos(vmt+2wct))
//Det intressante
motatt_sig = cos(wmt)

TILFELLE 2:
Motatt_sig = Um*cos(wmt)*Uc*sin(wct)*U1cos(wct)

//x=wct
sin(x)*cos(x)
motatt_sig = Um*cos(wmt)*Uc*1/2(sin(2x)+sin(0))
motatt_sig = Um*cos(wmt)*Uc*1/2(sin(2x))

//x=wmt, y=2wct
cos(x)*sin(y)
motatt_sig = 1/4*Um*Uc*(sin(x+y)-sin(x-y))
motatt_sig = 1/4*Um*Uc*(sin(wmt+2wct)-sin(wmt-2wct))
motatt_sig = 0

```

Hvilken rolle spiller amplitudefaktoren i demodulasjonsprosessen? 

Vetke


# Oppgave2

a)

AM-DSB-FC

Midlere effekt: 5,6W over 50 ohm

m = 0,6

Finn AM til de forskjellige frekvenskomponentene i spekteret hvis LF er sinusformet. Skisser signalets tidsrespons hvis LF har f = 1kHz og BB = 10kHz.

```
amplitude:
P = P0*(1+m^2/2) = P0 * (1 + (0.6^2)/2) = 4,7W
P0 = 5.14W
U0 = sqrt(P0 * 2 * R) = sqrt(5.14 * 2 * 50) = 21.78V

sidefrekvensen: 
um = m*u0/2 = 6.54V
```

[![IMG_0729.jpeg](https://github.com/simjor/signalbehandling/blob/main/Innlevering8/IMG_0729.jpeg)

- Ikke kontrollert med matlab

b)

AM-DSB SC

Midlere effekt = 8,2W på 50 ohm

Finn A antar at LF er sinus

Skisser signalets tidsrespons for frekvenser fm = 1kHz og BB = 10kHz

```
P = U0^2/(2*R) * 2
8,2 = U0^2/50
U0 = 20,24V
```

![IMG_0730.jpeg](https://github.com/simjor/signalbehandling/blob/main/Innlevering8/IMG_0730.jpeg)

- Ikke testet i matlab

# Oppgave3
### 3a)

Et binært ASK modem bruker ikke-koherent deteksjon. Hvilken verdi må Eb/N0 ha for å oppnå en feilsannsynlighet mindre enn 8,5^10-5.

```
Pb = 1/2*e^(-Eb/2*N0) = 8,5^10-5
EbN0 = -2*ln(2*8,5^10-5)
EbN0 = 17,36
```

### 3b)

b)Hva er den tilsvarende feilsannsynlighetenfor et koherent ASK opplegg med samme verdien for Eb/N0?

```
For koherent ASK:
Pb = 1/2*erfc(sqrt(Eb/2N0) = 1.5463e-05
```

### 3c)

Et system bruker 8-ary ASK modulasjon og et ”root raised” cosinus-filter i både sender og mottaker, med en alfa = 0,45. Hva er den nødvendige båndbredden for å støtte en datarate lik 56 kbps?
```
Antakelse: Ideell brickwall filtrering
B = (1+alfa) * datarate / log2(M)
B = (1+0,45)*56kbps / log2(8) = 27,07kHz
```
