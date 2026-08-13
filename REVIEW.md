# REVIEW.md

## Ce qui compte dans ce dépôt
- Préserver les règles métier et les invariants du dépôt.
- Traiter l’authentification, la facturation, la suppression de données et la gestion des secrets comme des modifications à haut risque.
- Préférer des correctifs ciblés et explicites aux refactorisations larges.

## Calibration de sévérité
- **Critique** : perte de données, élévation de privilèges, exposition de tokens/secrets, erreurs de facturation/données financières.
- **Avertissement** : validation manquante, valeurs par défaut non sécurisées, cas limites non testés.
- **Info / Ignorer** : ne pas signaler les différences de formatage si les outils de linting (`ruff`, `black`, `prettier`) s’en chargent déjà.

## Attentes de vérification
- Les nouvelles règles métier doivent comporter des tests vérifiant le résultat observable.
- Les modifications de base de données nécessitent des tests de migration et de rollback.
- Les évolutions d’interface doivent préserver la navigation au clavier et l’accessibilité.

## Sécurité et performances
- Aucun secret, token ou credential en clair dans le code ou les logs.
- Pas de requêtes réseau externes sans timeout explicite.
- Pas de `print()` en production — privilégier les logs structurés (`logging`).

## Style de revue
- Commentaires clairs et concis en français.
- Suggérer des correctifs concrets lorsque possible.
