# JeromeSomnology — Plateforme Somnologie Médicale

Développeur de la plateforme digitale **Somnology** — solutions numériques pour la somnologie médicale (diagnostics, suivi patients, gestion de cabinet).

---

## Carte de navigation des projets

### Repositories

| Repo | Description | Stack | Statut |
|------|-------------|-------|--------|
| [somnology-digital](https://github.com/JeromeSomnology/somnology-digital) | App principale Patient + Médecin (B2C) | React / TypeScript / Supabase | Production |
| [somnology-direct](https://github.com/JeromeSomnology/somnology-direct) | Interface B2B médecins partenaires + OVH | React / TypeScript / Supabase / OVH API | Développement actif |

---

## somnology-digital — Application principale

Application PWA de somnologie médicale destinée aux patients et aux médecins.

**Fonctionnalités clés :**
- Pré-consultation en ligne et questionnaires de sommeil (Epworth, Berlin)
- Espace patient : hub central, suivi parcours soin
- Espace médecin : dashboard, gestion dossiers patients
- Génération de PDFs médicaux avec QR code
- Installable en PWA (iOS/Android/Desktop)
- Contenu médical : pathologies du sommeil, équipe, examens (polygraphie)
- Conformité RGPD : pages confidentialité + mentions légales

**Architecture :**
React 18 + TypeScript → Vite → Supabase (PostgreSQL + Auth + Edge Functions) → Lovable.dev

[Voir le README complet](https://github.com/JeromeSomnology/somnology-digital#readme) | [Dossier certification](https://github.com/JeromeSomnology/somnology-digital/tree/main/docs/certification)

---

## somnology-direct — Interface B2B

Plateforme B2B dédiée aux médecins partenaires avec intégration OVH pour la gestion des documents médicaux.

**Fonctionnalités clés :**
- Interface médecin partenaire direct
- Intégration API OVH pour documents médicaux (mapping des champs)
- Gestion des dossiers patients
- Suite de tests automatisés (Playwright E2E + Vitest unitaires)
- PWA installable

**Architecture :**
React 18 + TypeScript → Vite → Supabase + OVH API → Lovable.dev + Tests Playwright/Vitest

[Voir le README complet](https://github.com/JeromeSomnology/somnology-direct#readme) | [Dossier certification](https://github.com/JeromeSomnology/somnology-direct/tree/main/docs/certification)

---

## Stack technologique commune

| Couche | Technologie |
|--------|------------|
| Frontend | React 18 + TypeScript + Vite |
| Styling | TailwindCSS + shadcn/ui + Radix UI |
| Routing | React Router v7 |
| Data | TanStack Query v5 |
| Formulaires | React Hook Form + Zod |
| Backend | Supabase (PostgreSQL + Auth + Edge Functions) |
| Sécurité | Row Level Security (RLS) + JWT |
| CI/CD | Lovable.dev (auto-deploy depuis main) |
| Tests | Playwright (E2E) + Vitest (unitaires) — somnology-direct |
| Documents | jsPDF + QR Code |
| PWA | vite-plugin-pwa |

---

## Structure des dossiers (communs aux deux repos)

    src/
    ├── components/     # Composants React réutilisables (UI, doctor, patient)
    ├── contexts/       # Contextes React (Auth, Theme)
    ├── data/           # Données statiques (praticiens, pathologies)
    ├── hooks/          # Custom React Hooks
    ├── integrations/   # Client Supabase + types générés
    ├── lib/            # Utilitaires
    ├── pages/
    │   ├── doctor/     # Espace médecin
    │   └── patient/    # Espace patient
    └── test/           # Tests unitaires (somnology-direct uniquement)
    supabase/
    ├── functions/      # Edge Functions Deno
    └── migrations/     # Migrations SQL horodatées
    docs/
    └── certification/  # Dossiers ISO 27001 + Dispositif Médical

---

## Conformité & Certifications

Les deux repos sont structurés pour répondre aux exigences de :

**RGPD** — Pages Confidentialité + Mentions légales, consentement explicite, RLS Supabase, HTTPS

**ISO 27001** — Auth JWT, contrôle d'accès RLS, chiffrement TLS, audit trail Git, gestion secrets env

**Dispositif Médical Classe 1 (MDR UE 2017/745)** — Traçabilité Git, tests automatisés, versioning documenté

Les dossiers de certification sont dans :
- [somnology-digital/docs/certification/](https://github.com/JeromeSomnology/somnology-digital/tree/main/docs/certification)
- [somnology-direct/docs/certification/](https://github.com/JeromeSomnology/somnology-direct/tree/main/docs/certification)

---

## Contact

jerome.pinot@somnology.fr

*Mise à jour : Mars 2026*
