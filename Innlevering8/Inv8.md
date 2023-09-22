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
```

Hvilken rolle spiller amplitudefaktorene i demodulasjonsprosessen?

- Amplitudefaktoren til informasjonssignalet (U0) og gjenvunnet bærebølge (U1) bestemmer styrken til det demodulerte signalet. Endringer i amplitude til informasjonssignalet (m) kan påvirke modulasjonsgraden og dermed bredden av sidebåndene i  signalet. Endring i U1 kan påvirke styrken til demodulerte signalet.

### Oppgave1b
