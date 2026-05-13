## 🌐 §8 — Interfaces & contrats d’API

````markdown id="qk3p9a"
# §8 — Interfaces & contrats d’API

## Tableau des endpoints REST

| Méthode | Chemin                   | Description                | Auth             | Codes retour  | Dépendances                 |
| ------- | ------------------------ | -------------------------- | ---------------- | ------------- | --------------------------- |
| GET     | /api/v1/events           | Liste des événements       | Public           | 200, 500      | EventService                |
| GET     | /api/v1/events/{id}      | Détail événement           | Public           | 200, 404      | EventService                |
| POST    | /api/v1/tickets          | Inscription à un événement | JWT              | 201, 400, 409 | TicketService, EventService |
| DELETE  | /api/v1/tickets/{id}     | Annulation ticket          | JWT              | 200, 404      | TicketService               |
| POST    | /api/v1/payments/init    | Initier paiement           | JWT              | 200, 400      | PaymentService, Stripe      |
| POST    | /api/v1/payments/webhook | Webhook Stripe             | HMAC             | 200, 400      | Stripe                      |
| GET     | /api/v1/admin/users      | Liste utilisateurs         | JWT + role:admin | 200, 403      | UserService                 |
| POST    | /api/v1/auth/refresh     | Refresh token              | Public           | 200, 401      | AuthService                 |

---

## 🔧 Conventions transverses

- Toutes les routes commencent par `/api/v1/`
- Les erreurs suivent le format RFC 7807
- Authentification via JWT sauf webhook Stripe (HMAC)
- Rate limiting appliqué sur endpoints publics

---

## 📡 Événements asynchrones

---

### 🎫 ticket.confirmed

```markdown
| Champ         | Valeur                                |
| ------------- | ------------------------------------- |
| Nom           | ticket.confirmed                      |
| Producteur    | TicketService                         |
| Topic         | tickets.events.v1                     |
| Consommateurs | NotificationService, AnalyticsService |
| Garantie      | at-least-once                         |
| Retry         | exponentiel (5 tentatives + DLQ)      |
```
````

### Schéma JSON

````json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "TicketConfirmedEvent",
  "type": "object",
  "required": ["ticket_id", "user_id", "event_id", "confirmed_at"],
  "properties": {
    "ticket_id": { "type": "string", "format": "uuid" },
    "user_id": { "type": "string", "format": "uuid" },
    "event_id": { "type": "string", "format": "uuid" },
    "confirmed_at": { "type": "string", "format": "date-time" }
  }
}
```

```markdown
| Champ | Valeur |
|------|--------|
| Nom | payment.failed |
| Producteur | PaymentService |
| Topic | payments.events.v1 |
| Consommateurs | NotificationService |
| Garantie | at-least-once |
| Retry | exponentiel + DLQ |

````

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "PaymentFailedEvent",
  "type": "object",
  "required": ["ticket_id", "user_id", "reason", "failed_at"],
  "properties": {
    "ticket_id": { "type": "string", "format": "uuid" },
    "user_id": { "type": "string", "format": "uuid" },
    "reason": { "type": "string" },
    "failed_at": { "type": "string", "format": "date-time" }
  }
}
```
