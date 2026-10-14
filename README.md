# Rush 4 · User Segmentation

Projet Epitech (Bootcamp Data) : analyse du lien entre l'usage d'Instagram et le bien-être des utilisateurs, et segmentation des utilisateurs pour les équipes produit.

## Objectifs

1. Mesurer si et comment l'usage de l'app est lié au bien-être (stress, sommeil, bonheur).
2. Construire des segments d'utilisateurs **assignables à n'importe quel utilisateur** à partir des seules données d'usage et de profil.
3. Évaluer ce que la segmentation apporte par rapport à un simple classement par temps passé.

## Données

Réplique synthétique d'un panel de volontaires, fournie par l'équipe privacy :

- `instagram_usage_lifestyleSafe.csv`
- `instagram_users_lifestyleSafe.csv`

Les deux fichiers comptent 200 000 lignes et 57 colonnes. L'un d'eux a subi un nettoyage non documenté : le choix du fichier, colonne par colonne, est documenté dans le notebook.

> Les fichiers CSV ne sont pas versionnés (`.gitignore`) : la réplique synthétique peut avoir reproduit de vrais utilisateurs.

## Équipe et répartition des tâches

| Membre | Rôle | Branche |
|---|---|---|
| Maxime | Qualité des données : choix du fichier, incohérences, fonction de chargement et de nettoyage | `data-quality` |
| Abdelkarime | Exploration des données et variables construites | `features` |
| Elina | Critères d'évaluation, comparaison au classement par temps passé, limites | `evaluation` |
| Léonard | Segmentation ML, assignation d'un nouvel utilisateur, conformité (RGPD, AI Act, DSA) | `segmentation`, `compliance` |
| Lucas | Conformité (en binôme avec Léonard), coordination des slides et du README | `compliance` |

## Livrables

- **Notebook Python** : choix des données, exploration, variables construites, segmentation, évaluation, limites, protection des données.
- **Slides** : présentation de 15 min suivie de 10 min de questions.
- **Dépôt Git** : historique montrant le partage du travail.

## Principes de protection des données

- Les variables de santé et de bien-être ne servent **pas** à construire les segments. Elles servent uniquement à les décrire et à les évaluer.
- Aucune ligne individuelle n'est affichée dans le notebook. Aucun résultat ne porte sur un groupe de moins de 50 utilisateurs.
- Un segment ne doit pas révéler à lui seul une information de santé.

## Reproductibilité

- Graine aléatoire fixe : `random_state=42`.
- Versions des bibliothèques dans `requirements.txt`.
- Le notebook s'exécute de haut en bas et donne des résultats identiques à chaque exécution.

```bash
pip install -r requirements.txt
jupyter notebook
```

Placer les deux fichiers CSV dans le dossier `data/` avant l'exécution.

## Limites

- Aucune causalité : les liens observés sont des corrélations.
- Un panel de volontaires n'est pas représentatif de l'ensemble des utilisateurs.
- Une réplique synthétique n'est pas la réalité.
