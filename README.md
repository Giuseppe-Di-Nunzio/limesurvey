# limesurvey
## Appunti sparsi su tips & tricks su LimeSurvey

**Premessa**: L'amministrazione usa il tool [LimeSurvey CE](https://manual.limesurvey.org/Installation_-_LimeSurvey_CE) come strumento di rilevazione.

**Problema**: L'anteprima di stampa, generata dal browser con lo shortcut ctrl+p, non mostra i radio-button valorizzati come in video. Il problema si manifesta anche se si attiva la specifica opzione "Grafica in background".

![Anteprima di stampa](https://github.com/Giuseppe-Di-Nunzio/limesurvey/assets/98542217/c93594c9-1784-43b6-ab28-b2fa1692dc74)

**Soluzione proposta**: Un efficace work-around è quello di agire con i fogli di stile (CSS). 

1. Dal menu _Configuration_ -> _Template editor_, cercare il tema di riferimento e fare click su _Estendere_.
   In pratica si vuole estendere il template corrente per crearne uno con le modifiche personalizzate.

2. Sulla sezione a sinistra, cercare "File CSS". Fare click su custom.css per modificarlo. In questo file è possibile inserire tutte le modifiche personalizzare che saranno importate nel tema ed eseguite per ultime in ordine cronologico. Copiare e incollare nella box testuale posizionata al centro, lo snippet seguente:

```
@media print {
    .radio-item input[type="radio"] {
    opacity: 1;
    z-index: 1;
    top: 0;
}
}
```
Fare click sul pulsante _Copiare nel tema locale e salvare le modifiche_


3. A questo punto, nelle impostazioni dell'indagine, cambiare il tema selezionando quello appena creato.


**Risultato**: L'anteprima visualizzerà i radio-button così come sono valorizzati nel browser, a prescindere dalle impostazioni avanzate di stampa.
