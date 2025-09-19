
# Inseguitore di Luce con Arduino

## 📖 Descrizione
Questo progetto consiste in un **inseguitore di luce** (light tracker) realizzato con una scheda **Arduino UNO**, due **fotoresistenze KLS6-3537** e un **motore passo-passo 28BYJ-48** controllato tramite il driver **ULN2003**.  

Il sistema è in grado di rilevare la direzione della luce predominante e ruotare il motore in modo da orientarsi verso di essa.  
È il mio primo progetto complesso con Arduino, attraverso il quale ho potuto apprendere:
- l’interazione tra **sensori analogici** e **attuatori**,
- il controllo di un **motore passo-passo**,
- la **programmazione di sistemi embedded**.

---

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

