# Innlevering8

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
Umod1 = Uam*U_bb = U0*(1+m*cos(wm*t))*sin(wc*t)*sin(wc*t)

// x=y=wc*t
sin(x)*sin(y) = 1/2[1-cos(2x)]
Umod1 = 0.5*U0*(1+m*cos(wm*t))*[1-cos(2x)]
Umod1 = 0.5*U0*(1+m*cos(wm*t))*(1-cos(2*wc*t))
Umod1 = 0.5*U0*(1-cos(2*wc*t)+m*cos(vm*t)-m*cos(vm*t)*cos(2*wc*t)

// x=vm*t, y=2*wc*t
cos(x)*cos(y) = 1/2[cos(x-y)+cos(x+y)]
Umod1 = 0.5*U0*(1-cos(2*wc*t)+m*cos(vm*t)-0.5(cos(vm*t-2*wc*t)+cos(vm*t+2*wc*t))

TILFELLE 2:
Umod2 = Uam * U_bb = U1*U0*(1+m*cos(wm*t))*sin(wc*t)*cos(wc*t)

// x=y=wc*t
sin(wc*t)*cos(wc*t) = 1/2[sin(x+y)+sin(x-y)]
Umod2 = 0.5*U1*U0*(1+m*cos(wm*t))*[sin(2*wc*t)+sin(0)]
Umod2 = 0.5*U1*U0*(sin(2*wc*t)+m*cos(wm*t)*sin(2*wc*t))

// x = wm*t, y = 2*wc*t
cos(x)*sin(y) = 1/2[sin(x+y)-sin(x-y)]
Umod2 = 0.5*U1*U0*(sin(2*wc*t)+ 0.5*m*(sin(2*wc*t+wm*t)-sin(wm*t-2*wc*t)))
Umod2 = 0

```
Min forståelse for at dette skjer:

Når vi bruker trigonometriske funksjoner er det veldig enkelt å se om vi får hentet in informasjonssignalet riktig eller ikke. Får vi et cos(x)*cos(x) vil vi få et ledd med -1 som vil representere at det modulerte signlet er i lik fase som det informasjonssignalet. Får vi cos(x)*sin(x) vil vi få et et led med 0 som vil representere at det modulerte signalet representerer informasjonssignalet, men i motsatt fase. Får vi sin(x)*cos(y) vil det bety at det modulerte signalet ikke representerer informasjonssignalet og dermed vil hele det modulerte signalet filtreres ut gjennom filteret. Dette fører til at vi kan sette det modulerte signalet til 0, fordi vi ikke får ut noe signal. 

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

```

Hvilken rolle spiller amplitudefaktoren i demodulasjonsprosessen?
