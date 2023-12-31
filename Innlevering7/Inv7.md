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
    M = 2^(C_max/2*B)
    M = 63.09
    
b) I praksis
For å finne et helt tall, runder vi av til nærmeste hele potens av 2. Dette gir oss 2^6 = 64

	Praksis_datarate = B*log2(M) = 18.6 kbps

  	
## Oppgave nr.3

	Eb/N0 = -0.45 dB # på ønsket lengde

I. Hva er den maksimale BW-effektiviteten som kan forventes for denne lenken?

II. Hvilken informasjonshastighet kan overføres innefor en B = 3100 Hz?


I.

	EbN0 = (2^(C/B) - 1) / C/B 
 	C = 2256.8bps
	BW-effektivitet=  C / B = 2256.8 / 3100 = 0.728

II.

	C = 2256.8bps
 	

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
a) Vi ønsker en binær basisbånd-overføring med bipolar NRZ signaleringog BER ≤ 10^(-6). Hva er den minste verdien Eb/N0 kan ha (både lineær og i dB)? 

	#(formel hentet fra side 101 i kompendiet fra NTNU)
	M = 2
 	BER = Ps = 10^(-6)
  	Eb/N0 =  (M^2 - 1) / (3 * log2(M)) * erfcinv(Ps*M/(M-1))^2
   	Eb/N0_dB = 10 * log10((M^2 - 1) / (3 * log2(M)) * erfcinv(Ps*M/(M-1))^2)

Benytter oss av octave og får følgende resultater:
	
 	EbN0 = 11.298
 	EbN0_dB = 10.530 dB
	

b) Vi har Eb/N0= 11dB. Finn forventet BER.
	
 	BER = Ps
  	M = 2;
	EbN0_dB = 11;
	EbN0 = 10^(11/10);
	BER = (M-1)/M .* erfc(sqrt(3/(M^2-1) .* EbN0*log2(M)))

Bruker octave for å regne ut og får:
	
 	BER = 2.6131e-07 = 0.261µ

## Oppgave nr.9
Et system for overføring av binære basisbånd-signal har en kapasitet lik 48kbps. Vi har Eb/N0 lik 7,5 dB. 

a) Finn S/N i dB hvis vi bruker minst mulig båndbredde(binært basisbånd-signal)).

	C = 48000 bps
 	EbN0 = 7,5 dB
  	M = 2 # pga. binær
   	B = C / 2 = 24000 Hz
    SNR = EbN0 * C/B = EbN0 * 2
    SNR_dB = EbN0 + 10 * log10(2) = 10.51 dB


b) Hva er den minste båndbredden vi må ha?

	Bmin = C / log2(1+SNR) = 48000 / log2(1+10^(10.51/10)) = 13.29kHz


c) Finnforventet feilhyppighet for dette systemet hvis det brukes unipolar NRZ signalering med Eb/N0 lik 7,5 dB.

	Ps = Bit error rate
 	M = 2 #NRZ har 2 faser, 1 eller 0
	EbN0_dB = 7.5
	EbN0 = 10^(7.5/10)
	Ps_unrz = (M-1)/M * erfc(sqrt(Eb/(2 * N0)) = 1/2 * erfc(sqrt(0.5*EbN0))

Bruker Octave for å løse dette:

	Ps_unrz = 8.8611e-03
	
d) Finn også forventet feilhyppighet for dette systemet hvis det brukes bipolarNRZ signalering med Eb/N0 lik 7,5 dB. 

	Ps = Bit error rate
 	M = 2 #NRZ har 2 faser, 1 eller 0
 	Ps_bnrz = (M-1)/M * erfc(sqrt((3*log2(M))/(M^2-1) * Eb/N0)) = 1/2 * erfc(sqrt(EbN0))

Bruker Octave for å løse:

	Ps_bnrz = 3.9880e-04
	
 	





