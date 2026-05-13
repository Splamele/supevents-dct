# §10 — Matrice de traçabilité

Cette matrice assure la correspondance entre les exigences du CDC et les éléments produits dans la DCT.

## §10.1 — Matrice principale

| Réf    | Intitulé       | Modules            | Sections | ADR     |
| ------ | -------------- | ------------------ | -------- | ------- |
| EF-01  | Création event | EventModule        | §7       | —       |
| EF-02  | Catalogue      | EventModule        | §8       | —       |
| EF-03  | Inscription    | TicketModule       | §7       | ADR-001 |
| EF-04  | Paiement       | PaymentModule      | §7       | ADR-002 |
| EF-05  | Notification   | NotificationModule | §7       | ADR-003 |
| EF-06  | Auth           | ⚠️ Non couvert     | —        | —       |
| EF-07  | Profil         | ⚠️ Non couvert     | —        | —       |
| EF-08  | Admin          | ⚠️ Non couvert     | —        | —       |
| EF-09  | Historique     | TicketModule       | §6       | —       |
| EF-10  | Email          | NotificationModule | §7       | ADR-003 |
| EF-11  | Sécurité       | Tous               | §9       | —       |
| EF-12  | Logs           | Tous               | §9       | —       |
| EF-13  | Export         | ⚠️ Non couvert     | —        | —       |
| ENF-01 | Performance    | Tous               | §9.2     | —       |
| ENF-02 | Disponibilité  | Tous               | §9.2     | —       |
| ENF-03 | Sécurité       | Tous               | §9.1     | —       |
| ENF-04 | Scalabilité    | Tous               | §9.2     | —       |
| ENF-05 | RGPD           | Tous               | §9.3     | —       |
| ENF-06 | Maintenabilité | Tous               | §7       | —       |
| ENF-07 | Logs           | Tous               | §9       | —       |
| ENF-08 | Monitoring     | Tous               | §9       | —       |

## §10.2 — Synthèse

- Couverture EF : 9 / 13
- Couverture ENF : 8 / 8
- Exigences en attente :
  - EF-06 (Auth)
  - EF-07 (Profil)
  - EF-08 (Admin)
  - EF-13 (Export)
