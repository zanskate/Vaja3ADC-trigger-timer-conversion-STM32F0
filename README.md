# Vaja3ADC-trigger-timer-conversion-STM32F0
Z STM32F0 smo naredili ADC pretvorbo s časovnim proženjem.
------------------------------------------------------------------------------------------------------------------------------------------
ODGOVORI:

a) Glede na vašo razvojno ploščico in razširitveno vezje z tipkami ter potenciometri, izberite ustrezni
analogni vhod. Kateri pin je to?  PC0
b) Glede na potenciometer na vaši ploščici izberite-obkljukajte ustrezni
kanal/pin. Na zaslonu se vam mora usterzno pobarvati izbrani pin v
zeleno barvo. Kaj se izpiše poleg pina?  ADC_IN10
c) Aktiviramo samo zeleno LED diodo na ustreznem izhodu:  PC9
d) V Clock Configuration spremenimo APB1 Timerl clock (MHz) na 16 MHz. Kaj
opazite? Vse nastavitve časa gredo na 16MHz 
e) V configuration kliknemo gumb za TIM1, ki je v polju Control. Časovniku bi radi spremenili frekvenco na 1kHz, zato moramo frekvenco ABP1 Timer Clock preskalirati v polju Prescaler (PSC – 16 bit value). Koliko znaša ta vrednost?  16000
f) Branje vrednosti želimo prikazati z utripanjem zelene LED diode na STM32f0 ploščici. Uporabite metodo  TogglePin iz HAL knjižnice in zapišite ukaz:  HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_9);

------------------------------------------------------------------------------------------------------------------------------------------
KOMENTAR:

S pomočjo CUBE MX in μVision5 sprogramiramo STM32FO tako, da bo izvajal ADC pretvorbe sprožene s časovnimi prekinitvami(interrupt).
Označimo spremenljivko adcVal in izberemo Add adcVal to Watch 1. Zaženemo Debug Mode, kjer vidimo spreminjanje vrednosti na potenciometru(0-255).
Med delovanjem utripa tudi zelena LED dioda(pin9).

------------------------------------------------------------------------------------------------------------------------------------------
