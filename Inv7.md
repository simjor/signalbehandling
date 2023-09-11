# Dette er innlevering7

## Oppgave nr.1

	dataskevens = [0,1,0,1,1,0,1,0,1,0];
	bittid = 62e-6;

Finn den minste verdien for kanalens båndbredde som trengs for å overføre dette signalet når det brukes NRZ (non return to zero)?

	symbolrate = 1 / bittid = 16129.03
 	symbolrate [symboler per sekund]

Nyquist-teoremet

	BW = symbolrate / 2
 	BW = 8064.52
  	BW [Hz]


## Oppgave nr.2
Det skal konstrueres et modem som skal benytte en analog telefonkanal med båndbredde lik 3,1 kHz, og midlere signalstøy forhold lik 36 dB.

a) Teoretisk største feilfrie dataraten (R):
	
Shannon hartely lov:

	C_max = B * log2(1 + S/N)
 	SNR = 10^(36/10)
   	B = 3.1e3
    C_max = 37.07e3 = 37073.8
    C_max [bps]

Symboltilstander:

    C_max = B * log2(M)
    M = 2^(C_max/B)
    M = 3981
    
b) I praksis
For å finne et helt tall, runder vi av til nærmeste hele potens av 2. Dette gir oss 2^12 = 4096

	Praksis_datarate = B*log2(M) = 37200 bps

  	
## Oppgave nr.3

	Eb/N0 = -0.45 dB på ønsket lengde

I. Hva er den maksimale BW-effektiviteten som kan forventes for denne lenken?
II. Hvilken informasjonshastighet kan overføres innefor en BW = 3100 Hz?
	
II.
	C = B * log2(1+Eb/N0)
 	Eb/N0 = 10^(-0.45/10)
 	C = 2874.3 bps

I.

	BW-effektivitet=  C / B = 0.927 bps/Hz
 	

## Oppgave nr.4

Vi ønsker å overføre en datastrøm på 56 kbps med bruk av spredt spektrum. Finn nødvendig båndbredde i kanalen hvis kanalen har et termisk signal-støyforhold (SNR) lik: -7 dB

	B = C / log2(1+SNR)
 	B = 213kHz

## Oppgave nr.5
 	





