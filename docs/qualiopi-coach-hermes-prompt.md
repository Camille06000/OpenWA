# Prompt pour Hermes

Tu es Hermes, agent developpeur senior.

Objectif : transformer mon fork OpenWA en passerelle WhatsApp pour un coach formation qualite.

Important : commence par installer et tester OpenWA avant de coder le coach.

## Etape 1 - OpenWA

1. Cloner le repo.
2. Installer les dependances.
3. Lancer OpenWA avec Docker.
4. Ouvrir le dashboard.
5. Connecter un numero WhatsApp secondaire.
6. Tester un message entrant.
7. Tester un message sortant avec Swagger.
8. Identifier l'endpoint exact d'envoi de message.
9. Configurer un webhook entrant.

Ne commence pas le coach tant que cette etape n'est pas validee.

## Etape 2 - Coach autonome

Cree un dossier :

apps/qualiopi-formation-coach

Stack conseillee :

- Node.js
- Express
- OpenAI ou OpenRouter
- webhook entrant OpenWA
- webhook CRM
- notification Telegram
- Docker

## Fonctionnement attendu

WhatsApp recoit un message.
OpenWA envoie le message au webhook du coach.
Le coach analyse le message.
Le coach repond via l'API OpenWA.
Le coach enregistre le lead via webhook CRM.
Le coach notifie Telegram si le lead est chaud.

## Fichiers attendus

- package.json
- src/server.js
- src/ai.js
- src/openwa.js
- src/lead.js
- src/prompts.js
- .env.example
- Dockerfile
- docker-compose.yml
- README.md

## Variables .env

PORT=3099
AI_PROVIDER=openrouter
OPENROUTER_API_KEY=
OPENROUTER_MODEL=openai/gpt-4.1-mini
OPENAI_API_KEY=
OPENAI_MODEL=gpt-4.1-mini
OPENWA_BASE_URL=http://localhost:2785
OPENWA_API_KEY=
OPENWA_SESSION_ID=default
OPENWA_SEND_ENDPOINT=/api/messages/send
CRM_WEBHOOK_URL=
TELEGRAM_BOT_TOKEN=
TELEGRAM_CHAT_ID=

## MVP

Je veux d'abord une version simple qui marche :

message WhatsApp -> coach IA -> reponse WhatsApp -> lead CRM -> notification Telegram si lead chaud.

Ne fais pas une usine a gaz.
