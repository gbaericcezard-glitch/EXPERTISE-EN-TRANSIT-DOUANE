expertise-transit-douane/
├── .gitignore
├── README.md
├── package.json
├── docker-compose.yml
│
├── apps/api/                          ← Backend NestJS
│   ├── .env.example
│   ├── package.json
│   ├── nest-cli.json
│   ├── tsconfig.json
│   ├── prisma/
│   │   ├── schema.prisma              ← Modèle de données complet
│   │   └── seed.ts                    ← Données de démo
│   └── src/
│       ├── main.ts
│       ├── app.module.ts
│       ├── auth/                      ← JWT, guards, décorateurs, rôles
│       ├── users/                     ← Profils & gestion des comptes
│       ├── prisma/                    ← Service Prisma global
│       ├── referentiel/
│       │   ├── sh-codes/              ← Codes SH + import CSV
│       │   ├── taxes/                 ← Taxes spécifiques ivoiriennes
│       │   ├── regimes/               ← Régimes douaniers
│       │   └── taux-change/           ← Taux de change
│       ├── declarations/
│       │   ├── calculation/
│       │   │   ├── customs-calculator.ts       ← Moteur de calcul
│       │   │   └── customs-calculator.spec.ts  ← Tests unitaires
│       │   └── declarations.{controller,service,module}.ts
│       ├── cours/                     ← Bibliothèque pédagogique
│       └── exercices/                 ← Exercices + quiz QCM
│
└── apps/web/                          ← Frontend Next.js
    ├── .env.example
    ├── package.json
    ├── next.config.js / tailwind.config.js / postcss.config.js / tsconfig.json
    └── src/
        ├── app/
        │   ├── page.tsx               ← Landing page
        │   ├── login/, register/
        │   ├── dashboard/
        │   ├── declarations/ (liste, new, [id])
        │   ├── cours/, quiz/[id]/
        │   ├── exercices/
        │   └── admin/ (sh-codes, taux-change, utilisateurs)
        ├── components/                ← AppShell, RequireAuth, StatutBadge
        └── lib/                       ← api.ts, auth-context.tsx, types.ts