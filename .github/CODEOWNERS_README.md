<!-- GENEROVANO reconcile -- needitovat, prepise kazdy beh -->
# Automatické žádosti o review (CODEOWNERS)

Tento soubor i spravovanou sekci v `.github/CODEOWNERS` generuje denní
governance reconcile z konfigurace projektu `govtest1` v gov repu
(`conf.d/projects/govtest1.conf`, klíč `pr_reviewers_team`).

## Jak to funguje

- Při otevření PR požádá GitHub o review tým ze spravované sekce
  (`* @czmhorg/test-pr-reviewers`); konkrétní členy vybírá týmové round robin přiřazení
  (autor PR se vynechává).
- Další reviewery může autor PR kdykoli přidat ručně — eskalace zůstává
  na lidech, žádný automat ji nedělá.

## Vlastní pravidla

V CODEOWNERS vyhrává poslední odpovídající řádek. Vlastní řádky přidávejte
POD spravovanou sekci — pro konkrétní cesty tím výchozího vlastníka přebijete.
Reconcile vlastní jen sekci mezi svými značkami; zbytku souboru se nedotýká.
Zásah do obsahu sekce reconcile vrátí a ohlásí.

## Cesta ven z mechanismu

Odeberte klíč `pr_reviewers_team` z `conf.d/projects/govtest1.conf`
(změna konfigurace v gov repu). Příští reconcile spravovanou sekci i tento
soubor odstraní; vlastní řádky v CODEOWNERS zůstanou zachovány.
