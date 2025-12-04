# MVP OmniSoin

**MVP OmniSoin : Bot vocal et chat IA pour patients et médecins (MSP Faidherbe)**

## Fonctionnalités principales

- Chat textuel et vocal pour patients (triage, orientation, prise RDV, info avec IA)
- Chat assistant médical pour professionnels (diagnostic, protocoles, rédaction automatique)
- Stockage structuré dans Airtable (patients, conversations, intentions, logs, médecins)
- Orchestration IA via n8n (OpenAI GPT-4 + Whisper / TTS)
- Frontend React simple déployable sur Vercel

## Architecture technique

- Frontend : React - chat et bouton micro (Web Speech API)
- Backend orchestration : n8n Cloud ou Node.js (API HTTP Exchange)
- IA : OpenAI GPT-4 (LLM), Whisper (Speech-to-text), ElevenLabs ou Google TTS (Text-to-speech)
- BDD : Airtable/Supabase - tables Patients, Conversations, Intents, Médecins, Logs_IA
- Auth : Supabase Auth ou authentification Airtable

## API Contracts principaux (JSON extrait)

- Frontend → Backend :
```json
{
  "type": "patient" | "medecin",
  "conversation_id": "uuid-v4",
  "user_input": {
    "mode": "text" | "audio",
    "content": "string"
  }
}
```

- Backend → Frontend :
```json
{
  "conversation_id": "uuid-v4",
  "response": {
    "text": "string",
    "audio_url": "string",
    "intent_detected": "urgence_vitale | rdv_standard | info",
    "confidence": 0.95
  }
}
```

## Prompts système (résumé)

- BOT PATIENT : triage, orientation, collecte données, empathie, stricte non-diagnostic
- BOT MEDECIN : aide décisionnelle, protocoles, rédaction, rappel limitations IA

## Roadmap MVP 3 jours

**Jour 1 :**
- Setup GitHub, Airtable, n8n, architecture
- Documentation API + prompts

**Jour 2 :**
- Dev frontend (chat+vocal), backend AI workflow, mapping intents

**Jour 3 :**
- Tests bout-en-bout, optimisation, démo live

---
