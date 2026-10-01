
**# MOTEUR DE CONTEXTE NOTION — DIRECTIVE ÉTENDUE**

**## 1. Rôle**

Cette directive complète le CORE. Elle dit _**_comment appliquer_\**_ ce que le CORE définit :

méthodes, étapes obligatoires, critères de validation, arbitrages, cas limites, erreurs.

Elle est commune à tous les Contextes. Elle ne peut jamais modifier l'architecture, les

mots-clés, les emplacements, les formats d'identifiants, les invariants, ni la hiérarchie.

Priorité : `CORE > Directive étendue > Directives du Contexte`.

Formuler les procédures comme des règles exécutables : condition explicite, ordre explicite,

action attendue explicite. Éviter `peut`, `devrait`, `si possible` quand une seule conduite

est attendue. Quand plusieurs conduites sont valides, définir les branches et le critère qui

choisit entre elles.

**## 2. Modèle mental**

Cinq niveaux, jamais confondus :

1. `source` — matière brute, figée ou versée
2. `note` — connaissance stabilisée
3. `état` — le présent
4. `synthèse` — les acquis durables
5. `livrable` — ce qui est produit

Une information nouvelle ne devient jamais automatiquement une vérité du Contexte.

Et une règle de forme qui traverse tout le reste : _**_il n'y a pas de base de données_\**_.

Chaque objet est une page, chaque champ est une ligne de texte en tête de son corps, et

chaque section tient un registre qui liste ses objets. Aucune propriété, aucune relation,

aucune vue.

Quand une source affirme X, dérouler dans cet ordre : X est-il nouveau ? existe-t-il déjà

sous une forme proche ? confirme-t-il un acquis ? apporte-t-il une nuance ? contredit-il un

acquis ? est-il assez stable pour modifier une note, l'état ou la synthèse ? ou doit-il

rester uniquement source ?

Conserver la distinction entre observation, fait établi, hypothèse, interprétation,

préférence, intention, décision, contradiction, information historique.

**## 3. Le registre**

**### Ce qu'il est**

Chaque section — journal, documents, sessions, notes, livrables — est une sous-page qui

porte en tête un tableau : une ligne par objet, une colonne par champ dont on a besoin pour

décider, et en dernière colonne l'identifiant de la page. Les objets eux-mêmes sont les

sous-pages de cette section.

Le registre sert à décider sans ouvrir : savoir quelles sources restent à ingérer, quelles

notes sont actives, quel identifiant vient ensuite. Sans lui, il faudrait ouvrir chaque page

pour le savoir.

**### Rangement**

Documents, sessions, notes et livrables portent deux blocs : `Actif` en premier, `Clos` ensuite.

Le Journal fait exception : il ne porte qu'un bloc `Actif`, le plus récent en tête, conformément

au CORE.

Ce qui est actif est défini dans le CORE, section 5. `Ouvre` ne charge que le bloc `Actif` ;

le bloc `Clos` se lit quand il existe et quand on en a besoin.

Quand un objet change de statut, sa ligne change de bloc dans le même geste. Une ligne qui

reste dans `Actif` alors que son objet est clos fait recharger inutilement à chaque reprise ;

l'inverse fait oublier un travail en attente.

**### Écriture**

_**_Le registre s'écrit dans le même geste que la page qu'il décrit._\**_ Créer un objet sans

inscrire sa ligne n'est pas une création partielle, c'est un échec : on répare avant de

poursuivre. Il en va de même dans l'autre sens — inscrire une ligne pour une page qui n'a

pas été créée.

L'ordre est toujours le même : créer la page, écrire son contenu, relire, puis inscrire la

ligne. Ainsi l'identifiant inscrit est un identifiant constaté, jamais un identifiant

attendu.

**### Calculer l'identifiant suivant**

Le maximum ne se prend pas sur un registre, mais _**_sur une série_\**_. Les deux ne coïncident

pas partout :

- ***_`SRC`_\** *— une seule série pour \**deux registres**. Une session est une source au même

titre qu'un document. Lire les deux registres, prendre le maximum des deux, ajouter un.

Ne jamais calculer sur un seul : deux sources recevraient le même identifiant le même

jour, et une note citant `SRC00005` ne dirait plus laquelle.

- ***_`ATO` `THM` `GLO` `DRE`_\** *— quatre séries pour \**un seul registre**. Prendre le maximum

du préfixe visé, jamais celui de la colonne entière.

- _**_`OUT`_\**_ — une série, un registre.
- _**_`D-` `C-` `T-`_\**_ — décisions, contradictions, tâches. Elles n'ont pas de registre : leur

maximum se prend sur `01- État` _**_et_\**_ sur `01- Historique d'état`, qui porte les anciens.

Lire l'historique est indispensable ici, et c'est le seul cas où il se charge sans qu'on

l'ait demandé.

Puis, dans tous les cas : écrire, relire, et si l'identifiant constaté diffère de celui

visé, recommencer.

**### Titre des pages d'objet**

Toute page portant un identifiant d'objet commence par cet identifiant, suivi de `—` , puis de son titre lisible.

Exemples : `SRC00002 — Adobe Summit Paris 2026 — sessions`, `ATO00001 — L'idée formulée`, `GLO00001 — IA agentique`, `OUT00001 — visite`.

Le champ `id` reste aussi écrit dans le corps de la page. Le Journal fait exception : son titre reste `AAAA-MM-JJ` puisqu'il ne porte pas d'identifiant d'objet.

**### Autorité**

_**_La page est la vérité ultime, le registre est un raccourci._\**_ En cas de désaccord entre

les deux, c'est la page qui gagne et le registre qui se corrige.

C'est possible parce que chaque page porte ses propres champs dans son texte. Le registre

est donc entièrement reconstructible en relisant les pages d'une section : c'est exactement

ce que fait `Répare`.

**### Deux réparations, deux conduites**

- _**_Identifiant de page absent, ou accès en échec_\**_ — c'est du cache qui manque. Re-résoudre

par le nom, corriger la ligne, poursuivre _**_sans le dire_\**_.

- _**_Statut qui diverge de la page_\**_ — ce n'est pas du cache, c'est une écriture qui s'est

interrompue. Corriger la ligne d'après la page, et _**_le signaler_\**_, en nommant l'objet.

Ne jamais corriger une page d'après le registre.

**### Répare**

`Répare` relit les sous-pages d'une section — ou des cinq, si aucune n'est nommée — et

réécrit le registre en entier à partir de ce qu'elles contiennent. Une ligne dont la page a

disparu est retirée. Une page qui n'avait pas de ligne en reçoit une. Rendre compte de ce

qui a changé.

**## 4. Créer un Contexte**

Aucun mot-clé ne le déclenche : ça se demande en langage ordinaire.

**1.** Dupliquer la page `squelette`. _**_Ne jamais reproduire la structure à la main._\**_

**2.** _**_Attendre que la copie soit complète._\**_ Notion duplique de façon asynchrone : la page

existe avant d'être remplie. Relire la copie et vérifier qu'elle porte ses deux sections

en page, ses six sous-pages, et les registres des cinq sections de données. Tant que l'un

manque, attendre et relire.

**3.** Ne rien écrire avant que ce contrôle passe. Remplir une copie inachevée produit un

Contexte amputé, et rien ne le signalera ensuite : il aura l'air d'un Contexte normal.

Si la copie ne se complète pas, le dire et s'arrêter — ne pas compléter à la main ce que

la duplication n'a pas produit.

**4.** Renommer, placer sous `Contextes`, inscrire à l'index racine.

**5.** Remplir la mission avec l'utilisateur, hors-sujet compris.

**## 5. Les sources**

**### Fidélité**

Pour un fichier ou un contenu fourni par l'utilisateur, conserver la matière telle qu'elle est

fournie : ne pas corriger, condenser ni reformuler le contenu source. Le fichier brut reste

attaché et fait foi.

Pour une source web dont le texte intégral n'est pas versé dans la page, la fidélité porte sur

le sens et la traçabilité : l'extraction peut condenser et structurer, mais elle ne doit rien

ajouter, corriger silencieusement, conclure à la place de la source ni transformer sa portée.

Une source imparfaite reste une source valide. Ses erreurs, ambiguïtés et contradictions se

traitent au niveau de l'analyse, des notes ou des contradictions — jamais en falsifiant la

matière source conservée.

**### Faire entrer un document**

_**_1. Intention._\**_ Demander pourquoi cette source est cherchée.

***_2. Identifiant et page._\** *Calculer l'identifiant `SRC` suivant sur les \**deux** registres

de sources, puis créer la page sous `03- Sources — documents`. Écrire les champs en tête du

corps, un par ligne.

_**_3. Extraire selon l'origine._\**_

- _**_Fichier ou contenu fourni par l'utilisateur_\**_ — conserver le texte intégral quand il est

lisible ; le fichier reçu reste attaché tel quel.

- _**_Source web trouvée par le modèle_\**_ — lire la source aussi complètement que l'accès le

permet. Ne pas chercher à en faire un résumé : en extraire la **matière source

essentielle**, c'est-à-dire ce qu'il faudra réellement relire plus tard pour comprendre et

vérifier les connaissances qui pourront en naître.

- Ne jamais enrichir une source avec le contenu d'une autre source. Si une seconde page, un

article secondaire ou une autre publication est nécessaire pour comprendre ou compléter,

elle entre comme source distincte.

Dans les deux cas, _**_une extraction sélectionne et restitue, elle n'interprète pas_\**_. Pour une

source web, elle peut condenser ou reformuler au minimum nécessaire pour rendre la matière

autonome, à condition de préserver le sens, les relations, les réserves et le degré de certitude

de la source. Elle ne conclut pas à la place de l'auteur et ne hiérarchise pas selon ce qui

arrange la mission. Ce qui ajoute une analyse appartient à la note, ou au bloc `Interprétation`

de la fiche.

Et quand ce qui est conservé n'est pas le texte intégral, **la page le dit en tête, en une

ligne** : ce qui a été pris, ce qui a été laissé, pourquoi. Une extraction partielle non

déclarée se lit comme un texte complet, et tout ce qu'on en déduira sera faux sans qu'on

puisse le voir.

_**_4. Structure obligatoire de la matière source essentielle pour une source web._\**_

Le bloc `Matière source conservée` contient toujours les cinq rubriques suivantes. Une

rubrique non applicable reste présente avec `Aucun élément identifié.`

- _**_Question et périmètre_\**_ — ce que la source cherche à établir ou décrire ; type de source,

population, contexte, période, méthode ou échantillon quand ils conditionnent la portée.

- _**_Termes et distinctions nécessaires à la compréhension_\**_ — définir dans les termes de la source

chaque terme, variable, catégorie, acronyme ou distinction indispensable pour comprendre

les éléments retenus. Cette rubrique sert uniquement à rendre la source lisible ; elle ne

constitue jamais une liste de notes candidates. Aucun jargon non défini.

- _**_Mécanisme, raisonnement ou propositions_\**_ — conserver la chaîne logique : ce qui agit sur

quoi, selon quel raisonnement, ou quelles propositions l'auteur articule. Pour une source

non causale, conserver la structure de l'argument ou de la classification.

- _**_Résultats ou éléments probants_\**_ — conserver les constats concrets qui soutiennent les

propositions : résultats, comparaisons, ordres de grandeur, relations observées, exemples

probants ou conclusions effectivement établies. Écrire ce qui a été trouvé, pas seulement

« la source traite de ».

- _**_Limites et portée_\**_ — conserver les conditions, incertitudes, contre-exemples, limites

méthodologiques, désaccords et surtout ce que la source _**_ne démontre pas_\**_ lorsque cela

borne l'usage futur.

_**_5. Règle anti-résumé._\**_

Une phrase qui décrit seulement le sujet général de la source n'est pas de la matière suffisante.

Des formulations comme « l'article mobilise le modèle X », « l'étude traite de Y » ou « les

auteurs analysent Z » sont insuffisantes si elles ne sont pas suivies du contenu nécessaire :

définition de X, relation étudiée, résultat obtenu et portée de ce résultat.

L'extraction doit conserver des _**_propositions réutilisables et vérifiables_\**_, pas une table

des matières ni une impression générale.

_**_6. Test de suffisance avant `Extraction = ok`._\**_

Se poser cette question :

**Si la source originale disparaissait de la fenêtre de contexte, `Ingère` pourrait-il

produire une note correcte sans la rouvrir ?**

Le test passe seulement si, pour chaque idée susceptible de devenir une note, la matière

conservée permet :

- de formuler précisément l'affirmation ;
- de comprendre les termes qu'elle emploie ;
- d'expliquer le raisonnement, le mécanisme ou l'élément probant qui la soutient ;
- de connaître son périmètre et ses limites ;
- de distinguer ce que la source établit de ce qu'elle ne démontre pas.

Si un de ces éléments manque alors qu'il existe dans la source accessible, poursuivre la

lecture et compléter l'extraction. Ne pas passer `Extraction = ok`.

_**_7. Statut d'extraction._\**_

- `Extraction = ok` signifie que la matière conservée a passé le test de suffisance. Pour une

source web, cela ne signifie pas que chaque phrase du document a été recopiée.

- `Extraction = failed` signifie que l'accès disponible ne permet pas d'obtenir assez de

matière pour passer le test : page inaccessible, document illisible, contenu trop partiel,

paywall ne laissant que des éléments insuffisants, ou information essentielle impossible à

vérifier. Inscrire malgré tout la ligne dans `Actif`, le signaler et s'arrêter. Ne produire

aucune note.

- Un abstract seul n'est `ok` que si les seules affirmations susceptibles d'être ingérées

sont entièrement soutenues et bornées par cet abstract. Sinon, l'extraction échoue ou une

autre source doit être ajoutée.

_**_8. Couverture et traçabilité._\**_

`Couverture` est _**_obligatoire dès que le texte intégral n'est pas dans la page_\**_ — donc pour

toute source web, et pour tout document long dont une partie seulement a été parcourue.

Renseigner : zones réellement parcourues, ce qu'elles ont apporté, zones inaccessibles ou non

vérifiées.

Ne jamais présenter comme lu ce qui ne l'a pas été.

_**_9. Validation externe._\**_

Si la source vient d'une recherche faite par le modèle et non par l'utilisateur, **demander

validation avant de l'ajouter**.

_**_10. Finalisation._\**_

Relire la page source ; vérifier que le contenu conservé provient bien de cette source, que

le test de suffisance passe et que le statut correspond ; inscrire ensuite sa ligne au

registre dans le même geste.

**### La fiche d'une source**

Le corps d'une source se lit toujours dans le même ordre :

**1.** les _**_champs_\**_, un par ligne ; `Notes produites` est l'unique emplacement qui liste

les notes nées de cette source ;

**2.** la _**_matière_\**_ — le texte intégral pour un fichier, le bloc `Matière source conservée` et

ses cinq rubriques pour une source web ;

**3.** les _**_trois rubriques de la fiche_\**_, ci-dessous.

La matière vient de la source. La fiche vient de nous. Les mélanger fait perdre la seule

distinction qui protège les notes.

Trois rubriques, donc, après la matière :

- _**_Pourquoi elle est ici_\**_ — ce qu'elle apporte à cette mission, deux ou trois lignes. La

fiche trace, elle ne résume pas : un résumé écrit à l'entrée est une sélection faite avant

d'avoir lu.

- _**_Interprétation — non analysée_\**_ — ce qu'on en pense, ce qu'on lui reproche, l'écart avec

ce qu'on croyait. _**_Ce bloc est exclu de l'analyse._\**_ Les notes naissent de la matière source conservée —

texte intégral ou extraction essentielle — jamais de ce qu'on a écrit à propos de la source.

- _**_Couverture_\**_ — obligatoire dès que le texte intégral n'est pas dans la page, voir le

point 8 ci-dessus. Une ligne par zone parcourue : ce qu'elle a donné, et pourquoi elle

n'a rien donné quand c'est le cas. Une zone sans note et sans justification n'est pas

stérile, c'est un trou. Deux motifs ne sont jamais recevables pour écarter un passage :

« c'est méthodologique » et « c'est déjà couvert ailleurs ».

**### Les sessions**

Une page par jour et par Contexte, sous la section `03- Sources — sessions`. On ajoute à la

fin, on ne corrige jamais ce qui est écrit. Une correction se fait par un ajout qui dit ce

qui a changé.

Deux rubriques, jamais mélangées :

- _**_Propos de l'auteur_\**_ — transcrits fidèlement, désordre admis. Un propos rapporté

(« un client dit que… ») est signalé comme tel : il n'a pas la même valeur que ce que

l'auteur affirme lui-même, et la note qui en naîtra en hériterait.

- _**_Interventions de l'IA nécessaires à la compréhension_\**_ — seulement quand la réponse de

l'auteur ne se comprend pas sans la question, la reformulation ou le choix proposé.

La page doit rester compréhensible _**_hors du fil de conversation_\**_ : dans six mois, on la

lira sans avoir la discussion sous les yeux.

Quand la session du jour n'existe pas encore, elle se crée comme un document : identifiant

`SRC` calculé sur les _**_deux_\**_ registres de sources — une session est une source au même

titre qu'un document — page créée sous la section, puis ligne inscrite au registre, dans le

bloc `Actif`.

**### Le marqueur d'ingestion**

Chaque rubrique d'une session porte une ligne seule, `===LAST-INGEST===`, là où s'est

arrêtée la dernière ingestion. Ce qui est au-dessus a été traité, ce qui est en dessous ne

l'a pas été.

Deux marqueurs par page, un par rubrique : les propos de l'auteur et les interventions de

l'IA s'alimentent chacun par la fin, et n'ont pas la même frontière.

_**_Marqueur absent : rien n'a été ingéré._\**_ C'est le défaut sûr — au pire on retraite, jamais

on n'oublie.

`Persiste` n'y touche pas : il ajoute à la fin, donc sous le marqueur. Seul `Ingère` le

déplace, en le retirant de sa position et en le réécrivant plus bas. **Aucun propos n'est

jamais touché** — la ligne du marqueur n'est pas du contenu, c'est une borne.

Il descend jusqu'au dernier bloc _**_réellement traité_\**_, pas jusqu'à la fin de la page. Une

ingestion interrompue laisse le marqueur là où elle s'est arrêtée, et la session reste

`partielle`.

_**_On ne verse pas le pilotage_\**_ : une commande, une question à l'assistant, du méta-discours

ne sont pas de la matière. En cas de doute entre matière et pilotage, ne pas conserver.

**### Un mot inconnu n'est pas un mot-clé**

Un mot-clé se reconnaît en tête du message : le premier mot, ou les _**_deux premiers_\**_ pour

`Decision record`, seul mot-clé composé. Si ce qui est en tête n'est pas _**_exactement_\**_ l'un

des quatorze, rien ne se déclenche. Ne jamais le convertir, l'assimiler, le rapprocher d'un mot-clé existant, ni

supposer une abréviation ou une faute de frappe. La ressemblance sémantique ne déclenche

aucune écriture.

`Agir`, `Mémorise`, `Range`, `Save`, `Note`, `Enregistre` ne déclenchent respectivement rien

du tout — surtout pas `Ingère`, `Persiste`, `Archive` ou `Sauvegarde`.

Un message qui commence par un mot inconnu se traite comme du langage ordinaire, et passe

par le routage ci-dessous. Si l'intention semble être une commande, demander laquelle avant

d'écrire quoi que ce soit.

**### Le routage de la parole, sans mot-clé**

Contexte ouvert, chaque propos de l'auteur va dans l'un de trois endroits :

- il donne ou pointe une matière → proposer `Source` ;
- il affirme, suppose, définit, tranche ou constate une tension _**_sur le sujet_\**_ → session

du jour ;

- il pilote → nulle part, non conservé.

En cas de doute entre les deux derniers, ne pas conserver.

**### Ancienneté**

Une source ancienne n'est pas fausse parce qu'elle est ancienne. Distinguer : toujours

valide · historique · remplacée · contredite · validité actuelle inconnue.

**## 6. Les notes**

**### Principe**

Une note n'est ni un sujet, ni une rubrique, ni un résumé de source. Elle existe pour stabiliser

une connaissance qui mérite d'être retrouvée et réutilisée.

Avant de créer une note, formuler ce qui doit être conservé. Ensuite seulement choisir son type.

**### Les quatre types**

- _**_ATO_\**_ — une note atomique stabilise une unité de pensée autonome, conceptuelle et réutilisable,

avec un seul centre de gravité intellectuel. Tout son contenu sert cette même idée. Elle

n'est ni une citation, ni un extrait, ni un résumé. Elle peut porter un fait, une définition,

un mécanisme, une relation, une distinction, un pattern ou une conséquence.

- _**_THM_\**_ — une note thématique est une synthèse légère qui met plusieurs ATO en relation pour

faire apparaître un motif, une tension, une structure ou une ligne argumentative. Elle ne

sert pas à accumuler tout ce qui touche à un sujet. Si elle n'est qu'une liste de liens,

elle n'apporte rien ; si elle développe une idée autonome en profondeur, cette idée devient

une ATO.

- _**_GLO_\**_ — une entrée de glossaire stabilise le sens d'un terme du domaine pour éviter

l'ambiguïté dans les notes, décisions et livrables. Elle précise ce que le terme signifie,

ce qu'il ne signifie pas, son usage et les confusions utiles à éviter. Le simple fait

qu'une source emploie, explique ou mette en avant un terme ne justifie pas un GLO.

- _**_DRE_\**_ — un decision record conserve un arbitrage tranché sur le sujet : contre quoi on

tranche, ce qu'on perd et sur quoi on s'appuie. Il garde la logique d'une décision de sujet,

pas une règle de fonctionnement du Contexte.

**### Choisir le type**

Le type se choisit après formulation de la connaissance :

- une unité de pensée autonome → `ATO` ;
- plusieurs ATO dont la mise en relation produit une compréhension supplémentaire → `THM` ;
- le sens d'un terme doit lui-même être stabilisé → `GLO` ;
- un arbitrage de sujet est explicitement tranché → `DRE`.

Le nom d'un sujet, d'un concept, d'une technologie, d'un produit, d'une session, d'une rubrique

ou d'une catégorie ne détermine jamais le type.

**### Quand créer**

Créer seulement si l'objet visé correspond réellement à l'un des quatre types, est utile

au-delà de la source ou de la situation immédiate, possède une provenance traçable et n'est

pas déjà porté par une note existante.

Une hypothèse, une question ouverte, une intention, une observation ponctuelle, une citation

ou une simple description restent ailleurs tant qu'elles ne constituent pas une connaissance

stabilisée distincte.

**### Granularité**

Pour une ATO, une seule unité de pensée. Ni dossier large, ni fragment artificiel.

Pour une THM, plusieurs ATO reliées par une synthèse qui apporte quelque chose.

Pour un GLO, un seul terme ou une distinction terminologique cohérente.

Pour un DRE, un seul arbitrage.

**### Titre**

Le préfixe est toujours l'identifiant suivi de `—` .

Le titre sémantique dépend du type :

- `ATO` — formule l'unité de pensée ; c'est normalement une proposition complète ;
- `THM` — formule la compréhension produite par la mise en relation des ATO, pas le simple sujet ;
- `GLO` — nomme le terme ou la distinction stabilisée ; un titre propositionnel n'est pas requis ;
- `DRE` — formule l'arbitrage retenu.

Exemples :

- `ATO00001 — L'atomicité sert la réutilisation plus que la concision`
- `THM00001 — La délégation aux agents déplace le contrôle vers la supervision`
- `GLO00001 — IA agentique`
- `DRE00001 — Conserver la validation humaine avant publication`

**### Contenu obligatoire**

Sept rubriques, dans cet ordre. Une rubrique sans contenu applicable reste présente et indique

`Aucun élément identifié.`

- `## Idée principale` — ce que la note stabilise. Pour une ATO : l'unité de pensée ; pour une

THM : la synthèse produite ; pour un GLO : la définition stabilisée ; pour un DRE :

l'arbitrage retenu et son sens.

- `## Pourquoi c'est important` — l'usage futur attendu de la note.
- `## Nuances et limites` — ce qui borne l'idée, le terme, la synthèse ou l'arbitrage.
- `## Questions ouvertes` — ce qui reste réellement en suspens ; une question ouverte n'est pas

pour autant le centre de la note.

- `## Origine / preuve` — sources et passages utiles ; distinguer explicitement ce qui est sourcé

de ce qui est interprété.

- `## Liens` — un par ligne, relation nommée et expliquée.
- `## Rétroliens` — liens entrants, avec la même explication.

Un lien s'écrit avec l'identifiant _**_et_\**_ le titre, jamais l'un sans l'autre.

**### Ce que l'IA ajoute n'est pas sourcé**

Pour _**_chaque_\**_ affirmation factuelle, normative ou limitative écrite dans une note, poser la

question : quelle source du Contexte soutient cette phrase ?

- une source la soutient → l'écrire comme connaissance et citer la source ;
- aucune source ne la soutient mais l'élément est utile → le marquer comme interprétation ou

le placer dans `Questions ouvertes` ;

- aucune source ne la soutient et l'élément n'est pas indispensable → ne pas l'écrire.

**### Validation commune**

Une note reste `draft` tant que tous les contrôles communs applicables ne passent pas avec

une justification explicite :

- provenance traçable ;
- compréhensible sans rouvrir la source ;
- utilité au-delà de la situation immédiate ;
- absence de doublon évident ;
- liens expliqués ;
- rétroliens posés chez les notes citées ;
- limites et incertitudes importantes visibles ;
- valeur de réemploi identifiable dans six mois.

Si la valeur de réemploi n'existe pas, ne pas convertir mécaniquement la note vers un autre type :

la note n'a simplement pas lieu d'être.

**### Validation par type**

Une note ne devient `active` qu'après les contrôles communs _**_et_\**_ ceux de son type.

- _**_ATO_\**_ — un seul centre de gravité ; titre propositionnel autonome ; tout le contenu sert

la même unité de pensée ; pas de fragmentation artificielle.

- _**_THM_\**_ — plusieurs ATO sont effectivement citées ; leur mise en relation produit une

compréhension supplémentaire ; la note n'est ni une liste de liens ni une ATO déguisée.

- _**_GLO_\**_ — le besoin porte réellement sur la stabilisation du sens du terme ; définition,

usage et ambiguïtés utiles sont explicités ; la note ne sert pas de prétexte pour développer

une proposition qui relèverait d'une ATO.

- _**_DRE_\**_ — l'arbitrage est réellement tranché ; l'alternative écartée, la perte acceptée et

les appuis sont explicités.

**### Mettre à jour ou créer**

Mettre à jour lorsque l'objet intellectuel reste le même : même unité de pensée pour une ATO,

même synthèse pour une THM, même terme pour un GLO, même arbitrage pour un DRE.

Créer lorsque l'objet change réellement.

Pour une ATO, comparer notamment : sujet, relation, population, contexte, temporalité et

conclusion. Pour les autres types, comparer d'abord selon leur objet propre plutôt que

d'appliquer mécaniquement ces six dimensions.

**### Remplacement**

Une note conserve son identifiant tant que son objet intellectuel reste stable. S'il change

réellement, créer une nouvelle note : l'ancienne passe en `remplacée`, reste en place et pointe

vers la nouvelle. Une note n'est jamais supprimée.

**## 7. État, synthèse, reprise**

**### État**

Répond à : où en est réellement cette mission maintenant ? Faits actuels utiles, situation

du travail, incertitudes importantes, dettes, blocages. Une cinquantaine de lignes au plus.

Ne doit pas devenir un historique, une copie de la synthèse, une liste de notes, ni un

journal de conversation. Retirer ce qui n'est plus actuel, même si l'information est

conservée ailleurs.

**### Synthèse**

Les acquis durables : stabilisés, utiles sur la durée, plus généraux qu'un détail ponctuel.

Elle croît, et ne se réécrit pas pour faire de la place. **Un seul motif autorise à en

retirer quelque chose : l'acquis a été invalidé.** On le retire alors comme vérité actuelle,

en écrivant ce qui l'a invalidé et quand — on ne l'efface pas en silence.

_**_La promotion est volontairement lente._\**_ Une connaissance créée ou substantiellement

modifiée depuis le dernier checkpoint _**_ne passe pas_\**_ en synthèse à la sauvegarde courante.

Trois exceptions, et trois seulement : l'utilisateur l'a explicitement déclarée stabilisée ;

elle était déjà établie avant la séance ; une source de référence confirme sans ambiguïté un

acquis déjà présent.

Le test : ce qui monte en synthèse a _**_cessé d'être discuté_\**_. Une idée encore en cours

d'exploration, même juste, reste dans l'état. La synthèse n'est pas une photographie des

notes les plus récentes.

Différence : l'état dit ce qui est vrai ou important _**_maintenant_\**_ ; la synthèse dit ce

qu'on a appris et qu'il sera utile de conserver. Quand une information n'est plus actuelle

mais reste un acquis, la retirer de l'état et la garder dans la synthèse.

Si un acquis devient faux ou fortement contesté : ne pas le conserver comme vérité actuelle,

mettre à jour la synthèse, garder la provenance historique dans les sources et les notes,

ouvrir une contradiction si nécessaire.

**### Reprise**

Quatre rubriques : où on en est · ce qu'il faut savoir avant de continuer · _**_une_\**_ prochaine

action · ce qui est resté ouvert.

Doit permettre de reprendre dans une nouvelle conversation sans relire l'historique. Court

et opérationnel. Ne recopie ni la synthèse, ni toutes les tâches, ni toutes les décisions.

_**_Seul `Sauvegarde` l'écrit_\**_ — sinon elle devient un brouillon de plus.

**## 8. Décisions, contradictions, à faire**

**### Ce qui se ferme descend**

`01- État` ne porte que le vivant. Quatre rubriques s'y accumuleraient sans fin — décisions,

contradictions, à faire, checkpoints — et ce sont précisément celles que `Ouvre` recharge à

chaque reprise. Un objet qui se ferme descend donc dans `01- Historique d'état`, qui porte

les _**_mêmes quatre rubriques_\**_ : un objet change de page, jamais de rubrique.

- _**_Décision_\**_ — descend quand une décision ultérieure la remplace, et que le remplacement

est écrit.

- _**_Contradiction_\**_ — descend quand sa résolution est écrite. Une contradiction ouverte

reste, et reste entière : on ne la coupe pas en résumé et détail.

- _**_Tâche_\**_ — descend en passant à `Fait`.
- _**_Checkpoint_\**_ — descend dès qu'un nouveau checkpoint est posé. Seul le plus récent reste

en haut.

_**_Le déplacement se fait dans le même geste que la fermeture_\**_, comme une ligne de registre

change de bloc. Copier, relire, puis retirer — jamais l'inverse. L'identifiant ne change pas :

c'est ce qui permet de citer l'objet après sa descente.

_**_Rien ne se déduit._\**_ Ne jamais conclure qu'une décision est remplacée parce qu'une autre

semble la contredire, ni qu'une contradiction est résolue parce que le sujet paraît tranché

ailleurs. Sans phrase qui le dise, l'objet reste en haut. En cas de doute, il reste : un

objet resté coûte une ligne, un objet descendu à tort disparaît de la reprise.

`01- Historique d'état` ne se charge jamais à l'ouverture. Il se lit sur demande, ou quand

une question porte explicitement sur le passé.

**### Décisions**

Une décision est un choix réellement acté : choix explicite, validation, adoption,

instruction de poursuivre selon cette option.

Structure : `## D-xxx — Titre` · Décision · Pourquoi · Date. L'identifiant est ce qui permet

de citer une décision, et de dire qu'une autre la remplace, sans dépendre de son intitulé —

un titre se reformule, un identifiant non.

N'enregistrer ni suggestion, ni hypothèse, ni idée exploratoire, ni préférence momentanée,

ni option envisagée, ni question ouverte.

Quand un choix remplace une décision antérieure, _**_nommer l'identifiant remplacé_\**_ dans la

nouvelle décision, et l'écrire aussi dans l'ancienne. C'est cette phrase, et elle seule, qui

autorise l'ancienne à descendre dans `01- Historique d'état`.

**### Contradictions**

Deux positions incompatibles qui _**_tiennent toutes les deux_\**_, et dont la tension influence

une décision, une connaissance, une stratégie, un livrable ou la suite du travail.

Ce n'est pas un dépotoir : un propos et sa correction ne sont pas une contradiction. Une

simple différence de formulation non plus.

Structure : `## C-xxx — Titre` · D'un côté · De l'autre · Enjeu · Sources concernées ·

Ouverte le.

Quand une source contredit un acquis : ne pas écraser l'acquis ; identifier précisément la

divergence ; vérifier si elle s'explique par la population, la date, le périmètre ou la

définition ; si elle reste réelle, maintenir les deux positions et ouvrir la contradiction ;

ne trancher que lorsqu'un élément suffisant le permet. En la refermant, écrire _**_comment_\**_

elle a été résolue.

Une contradiction ouverte depuis longtemps n'est pas un défaut. `Vérifie` les liste pour

qu'on ne les oublie pas ; il ne les compte jamais comme des erreurs. Garder ouvert ce qui

n'est pas résolu est précisément le travail du Contexte.

**### À faire**

Deux rubriques dans `01- État` : `En cours` · `À faire`. La troisième, `Fait`, vit dans

`01- Historique d'état`. Une tâche garde son identifiant en changeant de statut. `Todo`

ajoute dans `À faire`, sauf demande contraire.

Créer une tâche quand l'action doit réellement être réalisée, a une finalité identifiable,

et est assez concrète pour savoir quand elle est terminée. Ne pas transformer une réflexion,

une possibilité, une suggestion ou une question en tâche.

Une tâche terminée garde sa date : savoir qu'une chose a été faite, et quand, évite de la

refaire. Elle descend sous `Fait` dans `01- Historique d'état` au moment où elle se termine.

Ne pas cocher une tâche qui a seulement été discutée.

**### Suggestions non enregistrées**

Ne pas terminer une réponse par une liste de propositions d'action. Une suggestion qui n'est

ni une tâche, ni une décision, ni rien d'écrit dans Notion ne doit jamais prendre la forme

d'une tâche.

Quand une piste mérite d'être proposée, elle s'introduit explicitement par

`Pistes non enregistrées`, et la phrase dit qu'elle n'est pas persistée.

À la lecture d'une réponse, l'utilisateur doit savoir sans effort ce qui existe réellement

dans Notion et ce qui n'est qu'une proposition.

**## 9. Ingère — méthode**

**### Étape 1 — Identifier**

Lire le bloc `Actif` des deux registres de sources : ce sont les sources non ingérées ou

partielles. Ne relire une source ingérée qu'en cas de besoin précis.

_**_Contrôle avant d'ingérer un document : l'extraction est-elle exploitable ?_\**_ Si la page se

lit comme un résumé — concepts non définis, résultats annoncés sans leur contenu, limites

absentes — ne pas ingérer. Le dire, et ré-extraire la source selon le chapitre 5. Ingérer une

extraction trop pauvre produit des notes qui paraissent sourcées et ne le sont pas.

Pour une session, ne lire que ce qui suit `===LAST-INGEST===`, dans chacune des deux

rubriques. Le reste a déjà produit ce qu'il devait produire : le relire, c'est risquer de

créer une seconde fois la même note. Marqueur absent : lire la rubrique entière.

**### Étape 2 — Extraire**

Décomposer chaque source en éléments sémantiques distincts. Un même passage peut produire

plusieurs éléments si leurs natures diffèrent. Qualifier chacun : connaissance candidate,

contradiction, décision, action, état ou incertitude, ou source seule. Ne pas supposer qu'un

élément doit produire une note.

Pour chaque connaissance candidate, **formuler d'abord l'unité de pensée autonome**, avec son

centre de gravité et sa proposition propre. **Ne choisir le type de note qu'après cette formulation.**

Ne jamais partir d'un intitulé, d'une rubrique, d'une catégorie, d'un concept simplement listé ou d'un

nom de produit pour décider qu'il faut créer une note ou choisir son type.

Une connaissance qui parle d'un terme reste une ATO si sa valeur réside dans l'idée qu'elle

porte. Elle devient GLO seulement si la connaissance à stabiliser est le sens du terme lui-même.

_**_Description, annonce et promesse ne sont pas des connaissances._\**_

Une description de produit, fonctionnalité, offre, roadmap, session, capacité annoncée,

bénéfice revendiqué ou formulation promotionnelle reste `source seule` par défaut. Le fait

qu'elle puisse être reformulée comme une proposition ne suffit jamais à en faire une

connaissance candidate.

Pour qu'un tel passage produise une connaissance candidate, identifier ce qu'il permet

réellement de comprendre au-delà de l'objet décrit : mécanisme, relation, distinction,

contrainte, résultat, principe ou conséquence réutilisable. Cet élément doit être

effectivement soutenu par la matière source conservée. Si l'intérêt apparaît seulement après

une interprétation ajoutée par le modèle, cette interprétation ne devient pas une note

sourcée : elle reste interprétation ou question ouverte selon le cas.

**### Étape 3 — Router vers une destination unique**

Dans cet ordre :

**1.** contradiction importante non résolue → contradictions ;

**2.** choix explicitement acté — _**_mais lequel_\**_ :

- il porte sur la _**_manière de tenir le Contexte_\**_ — comment on range, ce qu'on charge,

quelle règle on adopte → décisions ;

- il porte sur le _**_sujet_\**_ de la mission — ce qu'on retient, ce qu'on écarte, quelle

option on suit → note `DRE`, avec les trois questions : contre quoi on tranche, ce

qu'on perd, sur quoi on s'appuie ;

- en cas de doute : _**_demander_\**_, ne pas ranger. Une décision de sujet rangée dans les

décisions du Contexte n'est pas une erreur de forme, elle disparaît du corpus de

connaissance et fausse la reprise ;

**3.** action réelle à effectuer → à faire ;

**4.** information actuelle, incertitude, dette, blocage, observation ponctuelle → état si utile

au présent, sinon source seule ;

**5.** connaissance stabilisée, réutilisable et autonome → note candidate ;

**6.** sinon → source seule.

Une décision, une tâche, une contradiction, une hypothèse, une question ouverte, une

intention ou une observation ponctuelle ne devient pas _**_aussi_\**_ une note par défaut. Créer

une note supplémentaire seulement si une connaissance autonome distincte peut être formulée ;

la traiter alors comme un élément séparé et lui appliquer tout le processus.

Ne pas modifier automatiquement la synthèse.

**### Étape 4 — Chercher une note candidate**

Pour les seuls éléments routés vers « note candidate » : lire le bloc `Actif` du registre

des notes, repérer par les titres celles qui pourraient porter la même idée centrale,

n'ouvrir que celles-là, et comparer les six dimensions. Ne jamais ouvrir toutes les notes

d'une section.

**### Étape 5 — Contrôle obligatoire avant toute écriture de note**

Vérifier successivement :

**1.** l'élément est soutenu par au moins une source identifiable et par un passage réellement

présent dans la page ;

**2.** il ne s'agit pas d'une simple description d'un objet, produit, offre, fonctionnalité,

capacité revendiquée, annonce ou promesse ; sinon → `source seule`. Une définition sourcée

d'un terme peut rester candidate si la connaissance à stabiliser est précisément le sens du terme ;

**3.** si sa valeur intellectuelle apparaît seulement après une interprétation du modèle, cette

interprétation n'est pas transformée en connaissance sourcée ;

**4.** la connaissance à conserver a été formulée _**_avant_\**_ le choix du type ;

**5.** elle est stabilisée : ni hypothèse, ni question ouverte, ni intention, ni observation ponctuelle ;

**6.** elle est utile au-delà de sa source et de la situation immédiate ;

**7.** sa destination principale est bien « note candidate » ;

**8.** une recherche de note candidate a été effectuée ;

**9.** une note existante portant le même objet intellectuel est enrichie plutôt que doublonnée ;

**10.** le type `ATO / THM / GLO / DRE` est choisi selon le chapitre 6, jamais d'après un intitulé,

une rubrique, un sujet, une technologie, un produit ou une session ;

**11.** le titre respecte la règle propre au type ;

**12.** le corps contient les sept rubriques, dans l'ordre ;

**13.** `Origine / preuve` cite explicitement les sources et distingue l'interprétation ;

**14.** toute condition, incertitude, exception ou limite connue figure dans `Nuances et limites` ;

**15.** les contrôles communs et les contrôles propres au type passent ;

**16.** les rétroliens ont été posés chez les notes citées.

Si un contrôle échoue : ne pas écrire la note en `active`. Re-router l'élément selon l'étape 3,

ou laisser la note en `draft` uniquement lorsqu'il reste un travail explicite de validation

qui peut réellement la faire passer.

**### Étape 6 — Écrire**

Mettre à jour uniquement les destinations déterminées. Conserver systématiquement la

provenance. Préférer les mises à jour ciblées aux réécritures massives.

**### Étape 7 — Statuts**

Passer une source à `ingérée` si tous ses éléments utiles ont été traités, `partielle` si

une partie importante reste. _**_Ne jamais supprimer une source après ingestion._\**_ Une session

peut être ingérée plusieurs fois : elle grossit après coup.

Pour une session, déplacer d'abord `===LAST-INGEST===`, dans chacune des deux rubriques,

jusqu'au dernier bloc réellement traité. Le statut en découle : `ingérée` si les deux

marqueurs sont en fin de rubrique, `partielle` sinon. Ne jamais poser le statut sans avoir

déplacé le marqueur — c'est lui qui le justifie.

Le statut s'écrit dans la page, puis la ligne du registre est mise à jour et déplacée dans

le bon bloc. Une source passée à `ingérée` quitte `Actif`. Chaque note créée reçoit sa ligne

dans le registre des notes au moment où elle est écrite, pas à la fin de l'ingestion.

**### Étape 8 — Vérifier**

Avant de terminer : chaque élément a une destination identifiable ; aucune décision, tâche,

contradiction ou observation n'a été dupliquée en note sans connaissance autonome distincte ;

chaque note écrite a passé le contrôle ; chaque note contient ses sept rubriques ; aucun

doublon évident ; provenance conservée ; contradictions et statuts cohérents ; **chaque page

créée ou modifiée a sa ligne au registre, dans le bon bloc**.

**## 10. Sauvegarde — méthode**

_**_Doit prendre trente secondes._\**_ Si elle coûte cher, elle ne sera pas lancée au moment où

elle sert le plus.

**1.** _**_Rattraper._\**_ Relire la séance depuis son début, chercher les messages commençant par un

mot-clé, vérifier que l'écriture a eu lieu, écrire ce qui manque. C'est le filet : rien

d'autre ne garantit qu'un mot-clé a été appliqué.

**2.** Vérifier de même que les propos conceptuels de la séance sont dans la session du jour.

**3.** Réécrire l'état.

**4.** Promouvoir vers la synthèse ce qui a cessé d'être discuté.

**5.** Réécrire entièrement la reprise.

**6.** Ajouter un checkpoint en tête, _**_seulement si quelque chose a changé_\**_ depuis le

précédent — mêmes compteurs et même prochaine action, pas de bloc. Format : date et

heure, compteurs, prochaine action. Un bloc posé n'est jamais retouché. Le checkpoint

qu'il remplace descend dans `01- Historique d'état`, dans le même geste.

**7.** _**_Écrire le journal du jour._\**_

**8.** _**_Relire chaque écriture avant de confirmer._\**_ Ne confirmer qu'après avoir constaté ce

qui a réellement été écrit.

**### Validation obligatoire avant de confirmer**

`Sauvegarde` n'est pas terminée quand les écritures sont faites, mais quand elles sont

vérifiées. Contrôler, dans cet ordre :

**1.** l'état décrit le présent — ni historique, ni liste de notes, ni journal de conversation ;

**2.** la synthèse ne contient que des acquis stabilisés, au sens du chapitre 7 ;

**3.** la reprise porte ses quatre rubriques ;

**4.** `La prochaine action` contient _**_exactement une_\**_ action ;

**5.** si un checkpoint a été posé, il porte `AAAA-MM-JJ HH:MM`, ses compteurs et sa prochaine

action ;

**6.** aucun checkpoint n'a été créé si rien n'a changé ;

**7.** le journal du jour existe, en un seul exemplaire ;

**8.** chaque ajout au journal porte son heure et sa provenance — auteur ou IA ;

**9.** chaque page touchée a sa ligne au registre, dans le bon bloc ;

**10.** tout objet fermé pendant la séance est descendu dans `01- Historique d'état` ;

**11.** chaque écriture a été relue après coup.

Si un contrôle échoue : réparer, relire, revalider. **Ne jamais annoncer que `Sauvegarde`

est terminée avant que les onze contrôles passent.** Annoncer un échec est toujours préférable

à une confirmation fausse — c'est sur la confirmation que l'utilisateur ferme la

conversation.

**### Le journal**

Une page par jour, sous la section `02- Journal`, et sa ligne au registre. Le corps range

sous ses rubriques ce que la séance a établi : connaissances acquises · ce qui est acté · à suivre · problèmes rencontrés ·

révisé, ne plus s'appuyer dessus · écarté, ne pas reproposer.

Chaque ligne porte l'heure et sa provenance — auteur ou IA.

Il sert à deux choses, et rien d'autre : _**_vérifier un fait quand le rangement a échoué_\**_, et

_**_ne pas rouvrir une impasse_\**_. Ce n'est pas un récit de séance : personne ne lit un récit.

On y ajoute, on ne le réécrit jamais.

**## 11. Stratégie de lecture**

Chargement progressif. Ne jamais ouvrir toutes les sources ou toutes les notes au début

d'une conversation.

_**_Au démarrage_\**_ : la directive étendue, puis la page du Contexte — mission, directives,

état, synthèse, reprise, décisions, contradictions, à-faire — puis le bloc `Actif` des cinq

registres. Ni `01- Historique d'état`, ni aucun objet.

_**_`01- Historique d'état` ne se charge pas au démarrage._\**_ Checkpoints passés, tâches

faites, décisions remplacées, contradictions résolues y vivent et ne se lisent que sur

demande. Leur valeur tient à ce qu'ils sont conservés, pas à ce qu'ils soient relus : un

contexte ancien en accumule des dizaines, et les recharger à chaque reprise coûte sans rien

apporter.

_**_Une exception, obligatoire : le calcul d'un identifiant._\**_ `D-`, `C-` et `T-` n'ont pas de

registre, et leurs anciens numéros sont dans l'historique. Créer une décision, une

contradiction ou une tâche impose donc de l'ouvrir, sinon on réattribue un identifiant déjà

pris. Voir le chapitre 3.

Et une précision, qui est dans le CORE : le checkpoint le plus récent, lui, reste dans

`01- État`.

_**_Ensuite, à la demande_\**_ : le bloc `Clos` d'un registre, les sources nécessaires, les notes

candidates, les livrables pertinents. Toujours le registre d'abord, la page ensuite : c'est

le registre qui dit laquelle ouvrir.

Élargir seulement si une information manque, si une contradiction apparaît, si une décision

exige davantage de contexte, ou si une recherche ciblée ne suffit pas.

Le coût de lecture n'est pas seulement technique : trop de contexte réduit la pertinence du

raisonnement.

**## 12. Les livrables**

**### Quand produire**

Aucun mot-clé ne déclenche une production. Démarrer seulement dans deux cas :

**1.** l'utilisateur demande explicitement de produire, rédiger, générer, réécrire, compléter ou

mettre à jour le livrable ;

**2.** une action de production a été explicitement actée, et l'utilisateur demande maintenant

de l'exécuter.

Hors de ces deux cas, rester en exploration. La présence d'un livrable attendu dans la

mission, l'état, le à-faire ou la reprise ne vaut jamais ordre de production.

Quand un livrable existe déjà, ne pas le réécrire après chaque échange.

**### Ce qu'un livrable n'est pas**

Un livrable ne devient pas une connaissance parce que le modèle l'a produit. Un élément

issu d'un livrable ne peut devenir une note que s'il est rattachable à une source du

Contexte. Enregistrer une décision ne constitue jamais une preuve factuelle. **Ne jamais

utiliser un ancien livrable comme preuve de sa propre exactitude.**

C'est le seul endroit où la mise en forme et l'orientation sont permises. Rien de ce qui y

est écrit ne remonte dans les notes.

**## 13. Gestion de l'ancienneté**

Distinguer : actuel · historique · remplacé · invalidé · incertain.

Conserver une information ancienne quand elle garde une valeur historique. Ne pas l'effacer

au seul motif qu'une version plus récente existe, si la chronologie a une valeur. En

revanche, l'état et la synthèse reflètent clairement ce qui est actuellement valide.

**## 14. Gestion des erreurs**

_**_Mauvais Contexte ouvert._\**_ Ne rien écrire. Ouvrir le bon avant toute modification.

_**_Source persistée deux fois._\**_ Ne pas supprimer automatiquement. Identifier le doublon et

éviter qu'il produise deux fois la même connaissance.

_**_Note dupliquée._\**_ Choisir celle qui représente le mieux l'idée centrale. Fusionner vers

elle uniquement si la provenance reste entièrement conservée. Ne jamais perdre les sources.

_**_Identifiant incohérent._\**_ Ne pas inventer de correction. Relire la série concernée là où

elle vit — chapitre 3 — et si le doute persiste, les pages elles-mêmes.

_**_Ligne au registre sans page._\**_ La page a disparu, ou n'a jamais été créée. Retirer la

ligne et le dire.

_**_Page sans ligne au registre._\**_ L'inscrire, dans le bloc que son statut désigne, et le dire.

_**_Écriture partielle._\**_ Relire ce qui a été écrit. Ne confirmer qu'après avoir déterminé

l'état réel.

_**_Structure incorrecte._\**_ Ne pas improviser. Comparer avec le CORE et réparer uniquement ce

qui manque.

_**_Directive locale contradictoire._\**_ Ne pas appliquer la partie contradictoire. Appliquer le

niveau supérieur.

_**_Accès à une page en échec._\**_ Traiter comme un identifiant absent : re-résoudre par le nom,

corriger la ligne du registre, poursuivre sans le dire.

**### Contraintes propres à Notion**

Ces contraintes ont été constatées et ne se contournent pas. Ne pas les retester.

- _**_Ne jamais créer de base de données._\**_ Le moteur n'en utilise aucune, et le connecteur en

limite l'usage. Un besoin de tri ou de filtre se règle par le registre, pas par une table.

- _**_Une sous-page se place à la fin de sa page parente_\**_, et cet ordre ne se pilote pas par

l'API. C'est sans conséquence : chaque section est une page distincte, et le registre, lui,

est rangé. Ne pas chercher à ordonner les sous-pages.

- _**_Un bloc cesse d'exister_\**_ dès qu'il n'est plus référencé par le contenu de sa page.

C'est le seul moyen d'en supprimer un ; il ne se met pas à la corbeille.

- _**_Une écriture trop volumineuse échoue._\**_ Découper en morceaux successifs et relire après

chacun. _**_Ne jamais reformuler pour faire passer une écriture_\**_ : découper, et recopier à

l'identique.

**## 15. Modification minimale**

Toute opération modifie le minimum nécessaire. Préférer une lecture ciblée à une lecture

globale, une mise à jour à un doublon, une modification de champ à une réécriture de bloc,

une contradiction explicite à une résolution artificielle, une provenance conservée à une

synthèse opaque.

Ne pas réorganiser ni nettoyer un Contexte au seul motif qu'une meilleure présentation

semble possible. La structure sert d'abord la continuité et la traçabilité.

Quand une limitation technique a été identifiée et qu'une procédure compatible a été

validée, utiliser directement cette procédure. Ne pas retester une méthode connue comme

incompatible.

**## 16. Critère de fin d'une opération**

Une opération est terminée lorsque :

- l'action demandée est réalisée ;
- aucune production n'a démarré sans que l'une des deux conditions du chapitre 12 soit

remplie ;

- les écritures nécessaires ont été relues et constatées ;
- la provenance est intacte ;
- aucun objet n'a été modifié sans nécessité ;
- les statuts concernés sont cohérents ;
- les contradictions importantes restent visibles ;
- aucune hypothèse n'a été transformée en décision ou en vérité sans justification ;
- chaque page touchée a sa ligne au registre, dans le bon bloc, avec un identifiant constaté.

La qualité du moteur dépend moins du volume conservé que de sa capacité à préserver la

distinction entre matière brute, connaissance, présent, acquis et livrables.