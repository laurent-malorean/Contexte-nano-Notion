**# PROMPT D'INITIALISATION — MOTEUR DE CONTEXTE NOTION**

À lancer une fois, dans une conversation neuve, avec le connecteur Notion actif.

Jetable ensuite — sauf pour rebâtir ailleurs, ou vérifier qu'un environnement est conforme.

- **--**

Tu vas construire l'environnement du moteur de Contexte dans Notion.

- *Règle qui prime sur tout le reste : les blocs de contenu fournis dans ce document se

recopient littéralement.** Tu ne les reformules pas, tu ne les réordonnes pas, tu n'en

corriges ni l'orthographe ni la ponctuation, tu n'ajoutes rien et tu n'enlèves rien. Ce qui

n'est pas fourni comme bloc littéral est une instruction, et seulement là tu as du travail

d'interprétation à faire.

- _**Deuxième règle : tu ne crées aucune base de données.**_* Ni table de base, ni vue, ni

propriété, ni relation. Tout est page et texte. Si tu penses qu'une base rendrait le résultat

meilleur, c'est un choix arrêté, pas un oubli.

Suis les étapes dans l'ordre. Après chaque étape, relis ce que tu viens d'écrire et ne passe

à la suivante qu'après avoir constaté le résultat. Si une étape échoue, arrête-toi et

dis-le : ne poursuis pas sur une structure incomplète.

Si une écriture échoue parce qu'elle est trop volumineuse, découpe-la en morceaux successifs

et relis après chacun. ****Ne reformule jamais pour faire passer une écriture**** : découpe, et

recopie à l'identique.

**## Étape 0 — Le point d'accroche**

Demande-moi sous quelle page Notion installer l'environnement. Attends ma réponse. N'invente

pas d'emplacement, ne crée pas de page à la racine de l'espace.

**## Étape 1 — La page racine**

Crée une page nommée `Contexte V2`, avec exactement ce contenu :

```

## Directives {color="blue_bg"}

## Contextes {color="green_bg"}

> Une page par contexte.

## Archives {color="brown_bg"}

> Une page par contexte archivé.

## Index racine {color="red_bg"}

> Nom → identifiant, pour ce qui s'adresse à ce niveau seulement : les trois directives, le squelette, chaque contexte actif, chaque contexte archivé. Jamais l'intérieur d'un contexte.

<table header-row="true">

<tr>

<td>Nom</td>

<td>Identifiant</td>

</tr>

<tr>

<td></td>

<td></td>

</tr>

</table>

```

Conserve l'identifiant de cette page. C'est la racine.

**## Étape 2 — Les quatre sous-pages**

Sous la page racine, crée quatre sous-pages vides, nommées exactement :

- `Directives`
- `Directives étendues`
- `Prompt d'initialisation`
- `squeleton`

Conserve leurs identifiants.

- _**Notion place les sous-pages à la fin de la page parente, pas sous le titre visé.**_* Reprends

donc le contenu de la page racine et réécris-le en plaçant les références de page aux bons

endroits : les trois premières sous le titre `Directives`, `squeleton` sous le titre

`Index racine`. Une référence de page placée dans le contenu déplace la page ; c'est le seul

moyen de les ranger.

**## Étape 3 — Le squelette**

Le squelette s'écrit ****en cinq morceaux successifs****, ajoutés l'un après l'autre à la fin de

la page `squeleton`. N'essaie pas de tout écrire en une fois. Relis après chaque morceau

avant de passer au suivant.

**### 3a — L'en-tête**

```

> Squelette d'un contexte. Cette page est dupliquée à chaque création. Créer un contexte se demande en langage ordinaire — aucun mot-clé ne le déclenche, comme pour produire un livrable.

> Les blocs en citation expliquent ce qu'on met où. Ils restent dans le squelette et disparaissent au remplissage.

```

**### 3b — Le cadre**

```

## 00- Cadre {toggle="true" color="green_bg"}

> Ce qui bouge peu. Écrit à la création, puis rarement.

### Mission

> Le but, la question centrale, ce qui est dans le sujet, ce qui est hors sujet, le livrable attendu.

#### Le but

#### La question centrale

#### Ce qui est dans le sujet

#### Ce qui est hors sujet

#### Le livrable attendu

### Directives

> Les règles propres à ce contexte : langue, anonymisation, niveau de preuve exigé. Chacune porte sa date. Écrit au vol par **Directive**.

### Chargement

> Ce qu'**Ouvre** charge, et rien d'autre. Par défaut : les sections 00 et 01, puis le bloc Actif des cinq registres. Ni 01- Historique d'état, ni aucun objet.

```

**### 3c — L'état**

```

## 01- État {toggle="true" color="yellow_bg"}

> Ce qui bouge à chaque séance.

### État

> Réécrit par **Sauvegarde**. Une cinquantaine de lignes au plus.

#### Ce qu'on sait

#### Ce qui reste incertain

#### Les dettes

### Synthèse

> Ce qui est devenu stable et ne bouge plus. Ne fait que croître, là où l'état se réécrit.

### Reprise

> Réécrit entièrement par **Sauvegarde**. Le premier bloc qu'on lit en reprenant.

#### Où on en est

#### Ce qu'il faut savoir avant de continuer

#### La prochaine action

#### Ce qui est resté ouvert

### Décisions

> Ce qu'on a tranché sur le contexte lui-même — comment on le range, ce qu'on charge, quelle règle on adopte. Une par bloc : D-xxx — Titre, puis Décision, Pourquoi, Date. Écrit au vol par **Décision**. Une décision explicitement remplacée descend dans 01- Historique d'état.

### Contradictions

> Ce qui s'oppose et qu'on n'a pas tranché. Un organe principal, pas une exception. Une contradiction ouverte depuis longtemps n'est pas un défaut ; elle reste ici, entière. Résolue par écrit, elle descend dans 01- Historique d'état. Écrit au vol par **Contradiction**.

### À faire

> En cours · À faire. Une tâche garde son identifiant quand elle change de statut ; passée à Fait, elle descend dans 01- Historique d'état. Écrit au vol par **Todo**.

### Checkpoints

> Le dernier checkpoint, et lui seul. Un bloc par **Sauvegarde**, et seulement si quelque chose a changé ; celui qu'il remplace descend dans 01- Historique d'état. Jamais retouché. Compteurs et prochaine action, rien d'autre.

```

**### 3d — Les sous-pages**

```

## Les sous-pages {color="gray_bg"}

> 01- Historique d'état — ce qui s'est fermé : décisions remplacées, contradictions résolues, tâches faites, checkpoints passés. Mêmes rubriques que 01- État. Jamais chargée à l'ouverture.

> Cinq sections de données — 02- Journal, 03- Sources — documents, 03- Sources — sessions, 04- Notes, 05- Livrables. Chacune porte son registre en tête, et ses objets en sous-pages.

> Il n'y a aucune base de données. Un objet est une page, ses champs sont des lignes de texte en tête de son corps, et le registre de sa section le liste. Le registre sert à décider sans ouvrir.

```

**### 3e — La doctrine du registre**

```

## Le registre {toggle="true" color="red_bg"}

> Un tableau par section. Une ligne par objet, la dernière colonne porte l'identifiant de la page.

> Deux blocs, **Actif** d'abord, **Clos** ensuite. **Ouvre** ne charge que le bloc Actif. Quand un objet change de statut, sa ligne change de bloc dans le même geste.

> Le registre s'écrit dans le même geste que la page qu'il décrit. Créer un objet sans inscrire sa ligne est un échec, réparé avant de poursuivre.

> La page est la vérité ultime, le registre est un raccourci. En cas de désaccord, la page gagne. **Répare** reconstruit un registre en relisant les pages de sa section.

> Un identifiant de page absent se re-résout en silence. Un statut qui diverge de sa page se signale : c'est une écriture interrompue.

```

**## Étape 4 — Les six sous-pages**

Sous `squeleton`, crée six sous-pages, nommées exactement :

- `01- Historique d'état`
- `02- Journal`
- `03- Sources — documents`
- `03- Sources — sessions`
- `04- Notes`
- `05- Livrables`

Dans `01- Historique d'état`, écris exactement ce contenu :

```

> Ce qui a cessé de servir au présent. Décisions remplacées, contradictions résolues, tâches faites, checkpoints passés.

> Rien n'est supprimé, seulement déplacé. Cette page n'est pas chargée à l'ouverture : elle se lit sur demande.

## Décisions

## Contradictions

## À faire

## Checkpoints

```

Les quatre rubriques portent les mêmes noms que dans `01- État` : un objet change de page,

jamais de rubrique.

Puis place les six références sous le titre `Les sous-pages`, comme à l'étape 2.

**## Étape 5 — Les registres**

`01- Historique d'état` n'a pas de registre : il ne contient pas d'objets, seulement des

blocs sous quatre rubriques.

Dans chacune des cinq sections de données, écris son registre : un titre `Actif` et un titre

`Clos`, chacun suivi

d'un tableau vide avec sa seule ligne d'en-têtes. Les colonnes, dans cet ordre, `Page`

toujours en dernier :

- `02- Journal` — `Jour` · `Page`. _**Un seul bloc**_*, pas de `Clos`. Le plus récent en tête.
- `03- Sources — documents` — `id` · `Titre` · `Intention` · `Fiabilité` · `Extraction` ·

`Ingestion` · `Page`.

- `03- Sources — sessions` — `id` · `Jour` · `Ingestion` · `Page`.
- `04- Notes` — `id` · `Titre` · `Type` · `Statut` · `Page`.
- `05- Livrables` — `id` · `Titre` · `Statut` · `Page`.

Sous chaque titre `Actif`, écris en citation le critère qui définit l'actif pour cette

section :

- documents — `Actif : extraction en échec, ou ingestion non faite ou partielle.`
- sessions — `Actif : ingestion non faite ou partielle.`
- notes — `Actif : statut draft ou active.`
- livrables — `Actif : statut brouillon ou en cours.`

Les tableaux restent vides : ils se remplissent à l'usage, pas à l'initialisation.

**## Étape 6 — L'index racine**

Remplis le tableau `Index racine` de la page racine avec, pour chaque objet créé à ce

niveau, son nom et son identifiant : les quatre sous-pages, et rien d'autre. **Les cinq

sections du squelette n'y figurent pas** : elles sont l'intérieur d'un contexte, et

appartiennent à son propre rangement.

**## Étape 7 — Les directives**

Demande-moi les trois documents — le CORE, la directive étendue, et ce prompt — et recopie

chacun dans sa page, littéralement. Dans le CORE, remplace les deux mentions

`<à renseigner>` par l'identifiant réel de la page racine et celui de la page des directives

étendues.

**## Étape 8 — Vérification**

Relis l'ensemble et rends-moi :

- l'identifiant de la page racine, des quatre sous-pages, et des six sous-pages du

squelette ;

- la liste des sections du squelette, dans l'ordre où elles apparaissent réellement ;
- pour chaque section, les colonnes de son registre et ses blocs ;
- la confirmation qu'aucune base de données n'a été créée ;
- tout écart entre ce qui était demandé et ce qui existe.

N'affirme rien que tu n'aies relu.

**## Ce que tu ne pourras pas faire**

Ces limites sont connues. Ne les teste pas, ne cherche pas à les contourner, signale-les

simplement si elles se présentent.

- _**Les sous-pages se placent à la fin de leur page parente**_*, et cet ordre ne se pilote pas

par l'API. Pour les ranger, il faut réécrire le contenu de la page en y plaçant leur

référence.

- _**Un bloc disparaît**_* quand il n'est plus référencé par le contenu de sa page. C'est le

seul moyen d'en retirer un ; il ne se met pas à la corbeille.

- _**Une écriture trop volumineuse échoue.**_* Découpe et recopie à l'identique.