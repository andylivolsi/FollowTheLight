
# Inseguitore di Luce con Arduino

## 📖 Descrizione
Questo progetto consiste in un **inseguitore di luce** (light tracker) realizzato con una scheda **Arduino UNO**, due **fotoresistenze KLS6-3537** e un **motore passo-passo 28BYJ-48** controllato tramite il driver **ULN2003**.  
Il sistema è in grado di rilevare la direzione della luce predominante e ruotare il motore in modo da orientarsi verso di essa.  
È il mio primo progetto complesso con Arduino

## 🛠️ Componenti Utilizzati
- Arduino UNO (o compatibile)
- 2 × Fotoresistenze KLS6-3537
- Motore passo-passo 28BYJ-48
- Driver ULN2003
- Resistenze per il partitore di tensione (per le fotoresistenze)
- Cavi jumper
- Breadboard

## ⚙️ Descrizione del Funzionamento

Il principio di funzionamento si basa sull’impiego di due **fotoresistenze** montate su un **motore passo-passo**, utilizzando una **basetta multifori** e un **giunto stampato in 3D**.  

Le fotoresistenze sono state disposte a **V** e schermate mediante un **divisore stampato in 3D**, in modo da ricevere luce proveniente da direzioni differenti durante la rotazione del motore.

Le due fotoresistenze formano un **partitore di tensione** tra **+5V** e **GND**.  
Il punto di giunzione (**Vout**) viene letto da Arduino tramite l’ingresso analogico **A0**.
<p align="center">
<img width="255" height="191" alt="partitore" src="https://github.com/user-attachments/assets/7444ee65-0464-425b-ae45-3ac79e9d9251" />
</p>

- In condizioni di **luce bilanciata**, il partitore genera su `A0` un valore prossimo a `Vin/2`.
- In condizioni di **luce sbilanciata**, la tensione su `A0` sarà maggiore o minore di `Vin/2`.

Arduino utilizza questa informazione per determinare la **direzione di rotazione** del motore, orientandolo verso la fotoresistenza più illuminata **seguendo dinamicamente la sorgente luminosa**.

Questa logica viene eseguita in un **loop continuo**, realizzando un algoritmo semplice ma efficace per l'inseguimento della luce.

## ⚡ Verifica Assorbimento del Partitore
<p align="center">
<img width="455" height="155" alt="image" src="https://github.com/user-attachments/assets/14bdcc3f-c351-4b0f-a9b9-4ab09f966c50" /></p>
<p >
<img width="325" height="167" alt="image" src="https://github.com/user-attachments/assets/9ed357fd-2322-4e6c-ac75-1b7a3b5dc0b4" /></p>
<p >
<img width="385" height="195" alt="image" src="https://github.com/user-attachments/assets/af409b77-f818-4c3a-9a02-a9427507c3a7" /></p>

Il circuito non comporta forti assorbimenti, nemmeno nei casi estremi:
- 🌑 **In buio totale** il consumo è quasi nullo.  
- 💡 **In luce intensa** il consumo rimane ben sotto il milliampere.

## 📝 Conclusioni

Questo progetto mi ha permesso di:
- 🔧 Comprendere il funzionamento dei **partitori di tensione** e la **lettura analogica** con Arduino.  
- ⚙️ Controllare un **motore passo-passo** mediante sequenze di attivazione.  
- 🔦 Creare un semplice **algoritmo di inseguimento della luce** basato su confronto sensoriale.  
- 🖥️ Imparare a gestire **hardware e software** in modo integrato.  

È stata un'esperienza formativa che ha gettato le basi per **progetti futuri più complessi e interattivi**.
## 📷 Foto del Progetto

Ecco alcune immagini del prototipo realizzato:
<p align="center">
 <img width="543" height="457" alt="image" src="https://github.com/user-attachments/assets/a7d3a069-446a-4e7b-b8d0-d74ae533baeb" /><br/>
- 🔙 Vista posteriore della scheda (dettaglio giunto) 
</p>

<p align="center">
  <img width="550" height="456" alt="image" src="https://github.com/user-attachments/assets/568d19d8-e2c2-4633-a6ca-656f21a9614a" /><br/>
- 🔛 Vista frontale della scheda** (dettaglio schermo luce e fotoresistori)  
</p>

<p align="center">
- 🖨️ Oggetti stampati in 3D (giunto e divisore luce)  

<p align="center">
- 🌐 Vista d’insieme del progetto
