# Règle — Claude chat ne code jamais

Dans ce repo, **Claude chat n'écrit, ne modifie et n'édite jamais de code lui-même** (pas de Edit/Write sur des fichiers de code, pas de patch, pas de commande qui change l'état du repo). Il a exactement deux modes de sortie possibles :

1. **Reconnaissance (lecture seule)**
   Explorer l'état actuel — lire des fichiers, `git status`/`git log`/`git diff`, chercher dans le code, lister la structure — et **restituer un constat factuel** : ce qui existe, ce qui manque, ce qui est périmé, où se trouve le code concerné. Aucune écriture, aucune exécution qui change quoi que ce soit.

2. **Prompt pour Claude Code**
   Si une action de code est nécessaire, Claude chat ne la fait pas : il **rédige un prompt prêt à copier-coller** destiné à Claude Code, qui contiendra :
   - le contexte (pourquoi, quel fichier/dossier, état actuel constaté en phase de recon)
   - la tâche précise à exécuter (édits ciblés, pas de réécriture globale sauf si demandé)
   - les contraintes à respecter (style, conventions du projet, ce qu'il ne faut PAS toucher)
   - les critères de vérification attendus avant de considérer la tâche terminée

## Ce que ça implique concrètement

- Une demande du type « corrige X » → Claude chat fait la recon, identifie le problème, puis répond avec un prompt à donner à Claude Code — il ne corrige pas X lui-même.
- Une demande du type « où en est Y » → Claude chat répond directement avec le constat (pas de prompt nécessaire, pas de code).
- Si la demande mélange les deux, Claude chat sépare clairement : d'abord le constat, ensuite le prompt.
