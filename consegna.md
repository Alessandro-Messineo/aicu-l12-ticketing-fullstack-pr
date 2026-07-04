# Consegna - L12 Ticketing urgency label

## Obiettivo

Implementa una piccola verticale full-stack:

```txt
priority + sourceChannel -> urgencyLabel
```

La label deve nascere sul server, non nel client.

## Formula da implementare

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

Valori validi di `sourceChannel`:

```txt
email
telefono
chat
```

Valore non valido da provare:

```txt
whatsapp
```

## Mission board

Completa questi step nell'ordine:

1. La UI invia `sourceChannel` nella request.
2. Il server valida `priority` e `sourceChannel`.
3. Il server calcola `urgencyLabel`.
4. Il ticket salvato/restituito contiene `urgencyLabel`.
5. La lista mostra `urgencyLabel`.

## Prove da mostrare

Alla fine devi poter mostrare:

- payload con `sourceChannel`;
- caso valido, per esempio `alta + telefono -> intervento rapido`;
- caso invalido `whatsapp -> 400 fieldErrors.sourceChannel`;
- response API con `urgencyLabel`;
- UI con la label visibile nella lista ticket.

## Chiusura in 3 righe

Scrivi nel messaggio finale o nella PR:

```txt
Cosa ho cambiato:
Come l'ho verificato:
Cosa resta fuori scope:
```

## Fuori scope

Non implementare:

- `responseDueAt`;
- duplicate ticket;
- notifiche;
- assegnazioni;
- filtri avanzati;
- dashboard analytics;
- autenticazione reale;
- suite di test completa.
