# innlevering7

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

Et system har en båndbredde-effektivitet C/B = 3,75 bps/Hz. Finn den minste SNR som trengs, i dB. Finn også den tilsvarende verdien for Eb/N0 i dB.

	# Finne signal-støyforholdet
 	C/B = log2(1+SNR)
 	SNR = 2^(C/B) - 1
  	SNR = 12.45 
   	SNR_dB = 10 * log(SNR) = 10.95 dB

    # Finne "effekt-effektiviteten"
 	Eb/N0 = (2^(C/B) - 1) / (C/B)
 	Eb/N0 = (2^(3,75) - 1) / 3,75
  	Eb/N0 = 3.32 bit/s/Hz
   	Eb/N0_dB = 10 * log10(3.32) = 5.21 dB
    	

## Oppgave nr.6

En binær basisbånd-overføring har båndbredde lik 35 kHz og et RaisedCosinus filter med roll-offfaktor alfa = 0,65. Finn forventet kapasitet

	#RasiedCosinus filter kanalkapasitet
	B = 35000 Hz
 	alfa = 0,65
  
  	M = 2 #(binær basisbånd overføring)
  	C = (2 * B * log2(M)) / (1 + alfa)
   	C = 2 * 35000 * log2(2)) / (1 + 0,65)
    C = 42.4242 kbps

## Oppgave nr.7
En basisbånd binær datalink er i stand til å støtte en bitrate lik 6400 bps når det brukes et RaisedCosinus filter med  alfa = 0,55. Hvor mye raskere kunne informasjonen bli sendt hvis verdien på alfa ble redusert til  alfa = 0,15?

	C1 = 6400 bps # m/ alfa = 0,55
 	C2 = Bmin * (1 + alfa)
  	Bmin = C / 2 = 3200 Hz # begrunnelse basisbånd binær, M=2
   	C2 = 3200 * (1 + 0,15) = 3680 bps
    
    # Forhold mellom C1 og C2
    C1/C2 = 6400 / 3680 = 1.7391
    Sendes 1.7391 ganger raskere hvis alfa blir redusert
 	

## Oppgave nr. 8
a) Vi ønsker en binær basisbånd-overføring med bipolar NRZ signaleringog BER ≤ 10-6. Hva er den minste verdien Eb/N0kan ha (både lineær og i dB)?

b) Vi har Eb/N0= 11dB. Finn forventet BER.


	
 	





