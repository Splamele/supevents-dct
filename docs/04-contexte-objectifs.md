# Contexte et objectifs

SupEvents est une plateforme de gestion d’événements destinée aux étudiants et aux organisateurs au sein d’un établissement. Elle permet de consulter, créer et gérer des événements, ainsi que de s’y inscrire en ligne.

Du point de vue technique, le système doit proposer une interface web simple et rapide permettant aux étudiants de s’inscrire en quelques étapes, tout en garantissant une authentification sécurisée via le SSO de l’établissement. La gestion des paiements en ligne impose l’intégration d’un prestataire externe (Stripe) afin d’assurer la conformité aux normes PCI-DSS.

La plateforme doit également être capable de supporter une charge importante d’utilisateurs simultanés, ce qui implique une architecture scalable et performante. L’accessibilité est un enjeu important, nécessitant le respect des standards WCAG. Enfin, le système doit être conçu de manière modulaire afin de faciliter son évolution et sa maintenance.

## Objectifs techniques

| Objectif technique                 | Origine dans le CDC                   | Niveau de priorité |
| ---------------------------------- | ------------------------------------- | ------------------ |
| Authentification sécurisée via SSO | Connexion via compte école            | Élevé              |
| Scalabilité horizontale            | 500 utilisateurs simultanés           | Élevé              |
| Paiement sécurisé                  | Paiement en ligne                     | Élevé              |
| Performance (P95 faible)           | Expérience utilisateur fluide         | Élevé              |
| Accessibilité (WCAG)               | Utilisateurs en situation de handicap | Moyen              |
| Modularité de l’architecture       | Évolution future du système           | Élevé              |
