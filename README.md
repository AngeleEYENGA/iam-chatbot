# IAM Security Advisor 
Chatbot IA expert cybersécurité — gouvernance IAM & conformité ISO 27001  
Alimenté par **Llama 3.3 70B** via **Groq API** (gratuit) · Déployé sur **Vercel** (gratuit)

---

## Structure du projet

```
iam-chatbot/
├── public/
│   └── index.html      ← Interface du chatbot
├── api/
│   └── chat.js         ← Route serverless (appel Groq)
├── vercel.json         ← Configuration Vercel
└── package.json
```

---

## Étape 1 — Créer un compte Groq (clé API gratuite)

1. Aller sur https://console.groq.com
2. Créer un compte (Google ou email)
3. Menu **API Keys** → **Create API Key**
4. Copier la clé (commence par `gsk_...`)

> Quota gratuit : ~500 000 tokens/jour, largement suffisant pour un POC.

---

## Étape 2 — Préparer le projet sur GitHub

1. Créer un compte sur https://github.com si pas encore fait
2. Créer un **nouveau repository** (ex: `iam-chatbot`) — mettre en **Private**
3. Uploader les fichiers (glisser-déposer dans l'interface GitHub) :
   - `public/index.html`
   - `api/chat.js`
   - `vercel.json`
   - `package.json`

---

## Étape 3 — Déployer sur Vercel

1. Aller sur https://vercel.com → **Sign up with GitHub**
2. Cliquer **Add New Project** → sélectionner votre repo `iam-chatbot`
3. Vercel détecte automatiquement la configuration
4. Avant de déployer, ajouter la variable d'environnement :
   - **Name** : `GROQ_API_KEY`
   - **Value** : votre clé `gsk_...`
5. Cliquer **Deploy**

En ~1 minute, votre app est en ligne sur une URL du type :
`https://iam-chatbot-XXXX.vercel.app`

---

## Étape 4 — Tester

Ouvrez l'URL Vercel dans votre navigateur.  
Le chatbot doit répondre en utilisant Llama 3.3 via Groq.

---

## Modifier le prompt système

Pour adapter la personnalité ou le domaine de l'assistant, modifiez la constante `SYSTEM_PROMPT` dans `public/index.html` (ligne ~120).

---

## Coût total : 0 €

| Service | Plan | Coût |
|---------|------|------|
| Groq API (Llama 3.3 70B) | Free tier | 0 € |
| Vercel hosting | Hobby (gratuit) | 0 € |
| GitHub | Free | 0 € |

---

## Support

Pour toute question sur le déploiement, consultez :
- https://vercel.com/docs
- https://console.groq.com/docs
