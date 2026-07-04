# AICU L12 - Ticketing urgency label

Starter didattico per il lab L12.

Obiettivo:

```txt
priority + sourceChannel -> urgencyLabel
```

La UI raccoglie `priority` e `sourceChannel`.
Il server deve validare i dati, calcolare `urgencyLabel`, salvare il ticket e restituire il dato alla UI.

## Requisiti

- Node.js 26 o superiore.
- pnpm.

La repo non richiede database esterni. SQLite viene creato come file locale in `data/tickets.sqlite` al primo avvio.

## Avvio

```bash
pnpm dev
```

Poi apri:

```txt
http://127.0.0.1:4173
```

## Missione del lab

Completa questi 5 step:

```txt
1. UI invia sourceChannel
2. Server valida priority + sourceChannel
3. Server calcola urgencyLabel
4. API/DB restituisce urgencyLabel
5. UI mostra urgencyLabel
```

Ogni step e' completato solo quando puoi mostrarne una prova nel browser o nella response API.

## Formula prodotto

| priority | sourceChannel | urgencyLabel |
| --- | --- | --- |
| alta | telefono | intervento rapido |
| alta | chat | prioritario |
| alta | email | prioritario |
| normale | telefono | da gestire |
| normale | chat | da gestire |
| normale | email | standard |
| bassa | telefono | monitorare |
| bassa | chat | monitorare |
| bassa | email | monitorare |

Valori validi per `sourceChannel`:

```txt
email
telefono
chat
```

Caso invalido da verificare:

```txt
sourceChannel = whatsapp
-> 400 fieldErrors.sourceChannel
```

## File principali

```txt
index.html
src/main.js
src/styles.css
server/index.js
consegna.md
```

## Confini

Non implementare:

- `responseDueAt`;
- duplicate ticket;
- notifiche;
- assegnazioni;
- dashboard analytics;
- auth reale;
- ruoli avanzati.

`urgencyLabel` non deve essere calcolata nel client.
