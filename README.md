# Production industrielle et masse monétaire au Royaume-Uni (1988-2023)

Deux théories économiques donnent des prédictions opposées sur le lien entre masse monétaire et production. Laquelle les données britanniques valident-elles ?

Trente-cinq ans de séries mensuelles, récupérées par API. Projet de Licence 3 en binôme, cours de macroéconomie dynamique.

## Un résultat négatif, documenté

C'est ce qui rend ce projet intéressant : **il ne conclut pas**.

La corrélation de Pearson entre les deux taux de croissance vaut −0,11. Les corrélations glissantes sur fenêtre de 24 mois sont centrées sur zéro. Et l'examen de quatre sous-périodes correspondant chacune à un choc économique ne fait pas mieux apparaître de relation.

Le rapport le dit explicitement : les données permettent d'étudier la corrélation, pas d'établir le sens de la causalité. Et il nomme sa propre limite — le décalage d'un mois retenu pour la masse monétaire est peut-être trop court.

Savoir écrire ça vaut mieux que de forcer une conclusion.

## Démarche

**Cadrage théorique posé avant les tests** : hypothèses keynésienne et néo-classique, chacune avec sa prédiction.

**Récupération des séries par API** sur le DataLab de TAC Economics — statistiques financières internationales du FMI pour la production industrielle, indicateurs de l'OCDE pour la masse monétaire.

**Corrélation globale**, puis **corrélation dynamique sur fenêtre glissante** pour mesurer la stabilité de la relation dans le temps plutôt que de se contenter d'un chiffre unique.

**Découpage en sous-périodes** correspondant aux épisodes de crise, pour voir si la relation apparaît là où la théorie l'attend le plus.

## Contenu

| | |
|---|---|
| `analyse.Rmd` | le code |
| `rapport/rapport.docx` | le rapport (20 pages) |

## Clé d'API

Le code lit sa clé dans l'environnement — aucune clé n'est versionnée :

```r
Sys.setenv(TACECONOMICS_API_KEY = "votre_cle")
```

## Reproduire

```r
install.packages(c("taceconomics", "ggplot2", "dplyr", "zoo", "runner", "stargazer"))
rmarkdown::render("analyse.Rmd")
```

---

Projet réalisé avec **Justine Barbot**.

**Léandre Gachet** — Master Science des données, statistique et économétrie, Université de Rennes
