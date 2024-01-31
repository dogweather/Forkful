---
title:                "Gestione degli errori"
date:                  2024-01-26T00:54:58.086191-07:00
model:                 gpt-4-1106-preview
simple_title:         "Gestione degli errori"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/kotlin/handling-errors.md"
---

{{< edit_this_page >}}

## Cosa e Perché?
La gestione degli errori è il modo in cui il tuo codice si occupa dei problemi che emergono durante l'esecuzione, come se gestisse una palla curva senza farla cadere. I programmatori lo fanno per prevenire crash ed offrire agli utenti un'esperienza fluida.

## Come fare:
Kotlin fornisce `try`, `catch`, `finally` e `throw` per gestire gli errori. Ecco come si usano:

```Kotlin
fun main() {
    val numeratore = 10
    val denominatore = 0

    try {
        val risultato = numeratore / denominatore
        println("Risultato: $risultato")
    } catch (e: ArithmeticException) {
        println("Non si può dividere per zero, amico.")
    } finally {
        println("Questo accade a prescindere.")
    }
}
```

Output:
```
Non si può dividere per zero, amico.
Questo accade a prescindere.
```

Se qualcosa va storto nel blocco `try`, l'esecuzione salta al `catch`. Cattura l'errore specifico sollevato (in questo caso `ArithmeticException`). Il blocco `finally` viene eseguito dopo - indipendentemente dall'esito.

## Approfondimento
Il blocco `try-catch` esiste sin dai primi giorni di programmazione — è come una rete di sicurezza. Kotlin offre anche `throw` per lanciare manualmente un'eccezione nel ring e c'è `finally` per il codice che deve essere eseguito a tutti i costi — spesso si tratta di operazioni di pulizia.

Le alternative includono il tipo `Result` e `try` di Kotlin come espressione.

```Kotlin
val risultato: Result<Int> = try {
    Result.success(numeratore / denominatore)
} catch (e: ArithmeticException) {
    Result.failure(e)
}
```
Questo approccio restituisce un oggetto `Result` — ottieni un successo o un fallimento senza il dramma di un'eccezione non gestita.

L'implementazione in Kotlin è elegante perché puoi usare `try` come un'espressione, il che significa che restituisce un valore. Scelte come queste rendono la gestione degli errori in Kotlin piuttosto versatile. Si tratta di scegliere lo strumento giusto per il lavoro, proprio come si farebbe in un laboratorio.

## Vedi Anche
- Documentazione Kotlin sulle Eccezioni: [Gestione delle Eccezioni Kotlin](https://kotlinlang.org/docs/exception-handling.html)
- Documentazione sul tipo `Result` di Kotlin: [Result Kotlin](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-result/)
- Effective Java, 3° Edizione, di Joshua Bloch — ottime intuizioni sulle eccezioni, anche se specifico per Java.
